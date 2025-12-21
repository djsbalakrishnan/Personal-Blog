---
title: "Building a private data center for 10k: Why I Ditched the Raspberry Pi"
date: 2025-12-21T18:39:10+05:30
draft: false
---

In my previous posts, I’ve talked about how perfection is overrated and the importance of just getting things done. Recently, that philosophy was put to the test when I decided it was time to take control of my data and build a dedicated "Digital Headquarters."

I needed a playground. A place to experiment with automation, host my own tools, and learn Data Engineering concepts **without the "meter running" anxiety of AWS billing.**

Here is the story of how I built my homelab, the architectural decisions behind the hardware, and the exact terminal commands I used to build the platform.

![The Lenovo M700 Tiny sitting in its actual spot in your home, with cables plugged in. Caption: The Digital HQ, running silently in the corner](/images/HeroShot.jpg)

## The Architecture Decision: Why x86 Beats ARM for Data Engineering

When you decide to host your own services, the first question is always: *Where does it live?*

My initial instinct was the **Raspberry Pi 5**, the darling of the homelab community. But as a Data Engineer, I had to look beyond the hype and look at the architecture.

1.  **The Compatibility Bottleneck:** The Pi runs on ARM architecture. While ARM support is improving, many "Big Data" legacy stacks (older Hadoop clusters, Oracle DBs, specific Spark builds) are still optimized for **amd64 (x86)**. I didn't want to waste weekends debugging multi-arch build failures or dealing with slow emulation layers just to run a standard Docker container.
2.  **The Cost-Per-Core:** By the time you buy a Pi 5 (8GB), active cooler, power supply, NVMe HAT, and SSD, you are looking at **₹14,000+**.

### The Winner: Lenovo ThinkCentre M700 Tiny

I settled on a refurbished Lenovo M700 Tiny. It offers a true [Intel Core i5 (SkyLake)](https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i5-6500+%40+3.20GHz&id=2599) processor. This ensures I can pull any standard Docker image from the hub and it just works; no "ARM tax" on performance or compatibility.

![The M700 Tiny next to my phone to show scale](/images/ScaleComparisonShot.jpg)

#### The Negotiation Strategy

I didn't just buy it online. I visited a local vendor, **Recyclekart**, in Delhi. They listed it for **₹13,500**. I walked in and asked for "Grade B" hardware explicitly stating I didn't care about cosmetic scratches as long as the silicon was intact. That conversation dropped the price to **₹10,000**.

Now, many might still consider ₹10k steep for 6th Gen hardware. But we have to be realistic, hardware prices have skyrocketed globally, partly thanks to the AI data center boom sucking up inventory.

Could I have saved another ₹1,500 by trekking all the way to Nehru Place? Maybe. But it is December in Delhi. To quote [Zakir Khan](https://www.youtube.com/watch?v=jU83SwFeXCQ&t=79s):

> *"Mard ko dard nahi hota hoga manliya, par thand lagti hai."*

> *(Men might not feel pain, but they definitely feel cold.)*

Saving ₹1,500 wasn't worth freezing on a bike ride across the city. I walked away with an enterprise-grade x86 server for the price of a toy, without the frostbite.

## The Network Pattern: Bypassing CGNAT with Zero Trust

Connecting a home server to the internet is usually a nightmare because most ISPs put residential connections behind a **CGNAT (Carrier-Grade NAT)**. This makes traditional port forwarding impossible because you don't have a real public IP.

Instead of fighting the ISP, I bypassed them completely using a **Zero Trust** architecture.

![Laptop (Tailscale) -> Internet -> [Bypassing ISP Router] -> Lenovo M700 (Tailscale) -> Docker Containers.](/images/FlowDiagram.jpg)

**1. The Magic Tunnel (Tailscale)**
I used Tailscale to create a private, encrypted mesh network. This allows me to SSH into the server from a hotel in Thailand or my parents' home in Chennai without exposing port 22 to the public internet.

 ``` bash
# Installing Tailscale
curl -fsSL https://tailscale.com/install.sh | sh
sudo tailscale up
 ```

**2. The Firewall (UFW)**
We configured `ufw` to drop all traffic by default, only allowing the encrypted Tailscale interface.

 ``` bash
# Deny everything incoming, allow only SSH and Tailscale interface
sudo ufw default deny incoming
sudo ufw allow in on tailscale0
sudo ufw enable
 ```

### The Reliability Protocol (Travel-Proofing)

Since I travel often, I can't physically reboot the server if there's a power outage in Delhi. I configured the BIOS **"Restore on AC Power Loss"** setting to "Power On."

This turns a fragile desktop into a self-healing node that comes back online automatically after a blackout.

## The Software Stack: Containerizing the Platform

I avoided installing tools directly on the OS to keep the system clean. **Docker** was non-negotiable for this platform.

 ``` bash
# Installing Docker
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
 ```

To manage the cluster visually, I deployed **Portainer**.

 ``` bash
docker run -d -p 9000:9000 --name portainer \
    --restart=always \
    -v /var/run/docker.sock:/var/run/docker.sock \
    portainer/portainer-ce:latest
 ```

![Portainer Dashboard - Screenshot showing active containers (n8n, nginx, memos) with green "Healthy" status.](/images/PortainerStacks.png)

### Core Workloads

Currently, the Digital HQ runs three mission-critical apps:

**1. Nginx Proxy Manager (The Ingress Controller)**
To handle SSL termination without a static IP, I used a **DNS Challenge** via Cloudflare. By generating API tokens and feeding them into Nginx, I can auto-renew SSL certificates even behind the CGNAT.

 ``` bash
    version: '3'
    services:
    app:
        image: 'jc21/nginx-proxy-manager:latest'
        container_name: proxy_manager
        restart: unless-stopped
        ports:
        - '80:80'      # Public Web Port (HTTP)
        - '81:81'      # Admin Interface Port
        - '443:443'    # HTTPS Port
        volumes:
        - ./data:/data
        - ./letsencrypt:/etc/letsencrypt
        networks:
        - proxy_net

    networks:
    proxy_net:
        external: true

 ```

![The Victory - Screenshot of browser address bar showing the green SSL Padlock next to your domain.](/images/SecureConnection.png)

**2. n8n (The Orchestrator)**
This is my self-hosted automation bus, connecting APIs and routing alerts.

 ``` bash
    version: '3'
    services:
    n8n:
        image: n8nio/n8n:latest
        container_name: n8n
        restart: always
        environment:
        - N8N_HOST=n8n.dhirajbalakrishnan.dev
        - N8N_PORT=5678
        - N8N_PROTOCOL=https
        - WEBHOOK_URL=https://n8n.dhirajbalakrishnan.dev/
        - GENERIC_TIMEZONE=Asia/Kolkata
        - N8N_SECURE_COOKIE=true
        ports:
        - "5678:5678"
        volumes:
        - n8n_data:/home/node/.n8n
        networks:
        - proxy_net

    volumes:
    n8n_data:

    networks:
    proxy_net:
        external: true
 ```

**3. Memos (The Knowledge Graph)**
A lightweight, privacy-focused tool for capturing code snippets and engineering notes.

 ``` bash
    version: "3"
    services:
    memos:
        image: neosmemo/memos:latest
        container_name: memos
        restart: unless-stopped
        ports:
        - "5230:5230"
        volumes:
        - memos_data:/var/opt/memos
        networks:
        - proxy_net

    volumes:
    memos_data:

    networks:
    proxy_net:
        external: true
 ```

## What's Next?

Right now, the platform is stable. The immediate goal isn't to add more "toys" but to use this infrastructure to simulate real-world **Data Engineering scenarios**.

I plan to use this refurbished beast to deploy heavy JVM workloads, perhaps an Airflow scheduler or a Spark job that would have choked a Raspberry Pi.

The best part? It’s *mine*. No subscription fees, no data harvesting, just pure silicon and code.

I’ll keep you posted on the data engineering experiments as they happen. Until then, keep building.