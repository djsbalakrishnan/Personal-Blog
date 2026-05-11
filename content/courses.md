---
title: "Courses"
date: 2026-05-11T00:00:00+05:30
draft: false
type: "page"
disqus: false
---

<style>
.courses-intro { margin-bottom: 32px; }

.courses-schedule {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
  margin-bottom: 36px;
  padding: 16px 20px;
  background: #fafafa;
  border-left: 3px solid #a00;
  border-radius: 0 6px 6px 0;
  font-size: 0.875rem;
  color: #555;
}

.courses-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 24px;
  margin-top: 8px;
}

.course-card {
  border: 1px solid #e8e8e8;
  border-radius: 10px;
  padding: 24px;
  background: #fff;
  box-shadow: 0 2px 10px rgba(0,0,0,0.06);
  display: flex;
  flex-direction: column;
  transition: box-shadow 0.2s ease;
}

.course-card:hover { box-shadow: 0 4px 20px rgba(0,0,0,0.11); }

.course-badge {
  display: inline-block;
  background: #f9f2f4;
  color: #a00;
  border: 1px solid #e8c8c8;
  border-radius: 4px;
  padding: 2px 8px;
  font-size: 0.7rem;
  font-weight: 600;
  letter-spacing: 0.5px;
  text-transform: uppercase;
  margin-bottom: 10px;
}

.course-card h3 {
  margin: 0 0 8px 0 !important;
  font-size: 1.2rem !important;
  color: #222 !important;
  border-bottom: none !important;
  padding-bottom: 0 !important;
}

.course-desc {
  color: #666;
  font-size: 0.875rem;
  line-height: 1.55;
  margin-bottom: 18px !important;
  border-bottom: 1px solid #f0f0f0;
  padding-bottom: 16px;
}

.curriculum-label {
  font-size: 0.68rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 1px;
  color: #999;
  margin-bottom: 8px;
}

.curriculum-list {
  list-style: none !important;
  padding: 0 !important;
  margin: 0 0 auto 0 !important;
  flex-grow: 1;
}

.curriculum-list li {
  display: flex !important;
  align-items: flex-start;
  gap: 8px;
  padding: 5px 0 !important;
  font-size: 0.845rem;
  color: #444;
  border-bottom: 1px solid #f5f5f5;
  margin-bottom: 0 !important;
  line-height: 1.45;
}

.curriculum-list li::before {
  content: "→";
  color: #a00;
  font-size: 0.72rem;
  margin-top: 3px;
  flex-shrink: 0;
}

.curriculum-list li:last-child { border-bottom: none; }

.course-card-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 20px;
  padding-top: 14px;
  border-top: 1px solid #f0f0f0;
}

.course-duration { font-size: 0.82rem; color: #888; }
.course-duration strong { color: #555; display: block; font-size: 0.85rem; }

.course-fee { text-align: right; }
.fee-amount { font-size: 1.1rem; font-weight: 600; color: #a00; display: block; }
.fee-label { font-size: 0.7rem; color: #999; display: block; }

.courses-cta {
  margin-top: 40px;
  padding-top: 24px;
  border-top: 1px solid #f0f0f0;
  text-align: center;
  font-size: 0.95rem;
  color: #555;
}

.courses-cta a { color: #a00; }

@media (max-width: 640px) {
  .courses-grid { grid-template-columns: 1fr; gap: 18px; }
  .course-card { padding: 20px; }
  .courses-schedule { flex-direction: column; gap: 8px; }
}
</style>

<div class="courses-intro">
  <p>Live, cohort-based weekend classes designed around the curriculum I wish I had when I started. Small batches, real problems, and enough depth to prepare you for product company interviews and real-world engineering roles.</p>
</div>

<div class="courses-schedule">
  <span>📅 Every Saturday &amp; Sunday</span>
  <span>🕐 Flexible timings — decided with the batch</span>
  <span>⏱ 2 hours per session</span>
  <span>💻 Live online &bull; Cohort-based</span>
</div>

<div class="courses-grid">

  <!-- Card 1: Python + DSA -->
  <div class="course-card">
    <div class="course-card-header">
      <span class="course-badge">Beginner Friendly</span>
      <h3>Python + Data Structures &amp; Algorithms</h3>
      <p class="course-desc">Start from zero Python knowledge and build up to solving DSA problems confidently. This course covers the language and the problem-solving patterns together — the way it should be taught.</p>
    </div>
    <div class="curriculum-label">Curriculum</div>
    <ul class="curriculum-list">
      <li>Python Fundamentals — syntax, data types, I/O, conditionals</li>
      <li>Loops, Patterns &amp; Functions</li>
      <li>Recursion — how it works, call stack, base cases</li>
      <li>1D &amp; 2D Arrays — traversal, manipulation, matrix problems</li>
      <li>Strings &amp; String Methods</li>
      <li>Time &amp; Space Complexity — Big-O analysis</li>
      <li>Hashing — HashMaps, HashSets, frequency maps</li>
      <li>Object-Oriented Python — classes, objects, inheritance, dunder methods</li>
      <li>Linked Lists — singly, doubly, circular</li>
      <li>Stacks &amp; Queues</li>
      <li>Trees &amp; Binary Search Trees — DFS, BFS, traversals</li>
      <li>Heaps &amp; Priority Queues</li>
      <li>Graphs — BFS, DFS, shortest path, cycle detection</li>
      <li>Dynamic Programming — memoisation, tabulation, common patterns</li>
      <li>Sorting &amp; Binary Search — variants and applications</li>
    </ul>
    <div class="course-card-footer">
      <div class="course-duration">
        <strong>~20 weekends</strong>
        <span>40 sessions &bull; Sat &amp; Sun</span>
      </div>
      <div class="course-fee">
        <span class="fee-amount">₹500</span>
        <span class="fee-label">per session / student</span>
      </div>
    </div>
  </div>

  <!-- Card 2: Java + DSA -->
  <div class="course-card">
    <div class="course-card-header">
      <span class="course-badge">Beginner Friendly</span>
      <h3>Java + Data Structures &amp; Algorithms</h3>
      <p class="course-desc">Same depth as the Python course, taught entirely in Java. Ideal if you are preparing for product company interviews where Java is your preferred language, or if you want to work in backend-heavy roles.</p>
    </div>
    <div class="curriculum-label">Curriculum</div>
    <ul class="curriculum-list">
      <li>Java Fundamentals — syntax, data types, I/O, operators</li>
      <li>Control Flow, Loops &amp; Pattern Problems</li>
      <li>Functions &amp; Recursion</li>
      <li>1D &amp; 2D Arrays — traversal and matrix problems</li>
      <li>Strings &amp; StringBuilder</li>
      <li>Time &amp; Space Complexity — Big-O analysis</li>
      <li>Hashing — HashMap, HashSet</li>
      <li>OOP in Java — classes, objects, inheritance, polymorphism, interfaces</li>
      <li>Linked Lists — singly, doubly, circular</li>
      <li>Stacks &amp; Queues — Stack, Deque, ArrayDeque</li>
      <li>Trees &amp; Binary Search Trees — DFS, BFS, traversals</li>
      <li>Heaps &amp; Priority Queues</li>
      <li>Graphs — BFS, DFS, Dijkstra's, cycle detection</li>
      <li>Dynamic Programming — memoisation, tabulation</li>
      <li>Sorting Algorithms &amp; Binary Search</li>
    </ul>
    <div class="course-card-footer">
      <div class="course-duration">
        <strong>~20 weekends</strong>
        <span>40 sessions &bull; Sat &amp; Sun</span>
      </div>
      <div class="course-fee">
        <span class="fee-amount">₹500</span>
        <span class="fee-label">per session / student</span>
      </div>
    </div>
  </div>

  <!-- Card 3: SQL + Data Engineering -->
  <div class="course-card">
    <div class="course-card-header">
      <span class="course-badge">SQL Basics Included</span>
      <h3>SQL + Data Engineering</h3>
      <p class="course-desc">From writing your first SELECT query to building production ETL pipelines on Spark. Built for analysts, data engineers, and backend engineers who want to work confidently with data at scale.</p>
    </div>
    <div class="curriculum-label">Curriculum</div>
    <ul class="curriculum-list">
      <li>SQL Basics — SELECT, INSERT, UPDATE, DELETE, relational model</li>
      <li>Filtering — WHERE, HAVING, DISTINCT, NULL handling</li>
      <li>JOINs — INNER, LEFT, RIGHT, FULL OUTER, CROSS, SELF</li>
      <li>Aggregation &amp; GROUP BY</li>
      <li>Subqueries &amp; Common Table Expressions (CTEs)</li>
      <li>Window Functions — RANK, ROW_NUMBER, LAG, LEAD, NTILE</li>
      <li>Views, Indexes, Transactions &amp; ACID properties</li>
      <li>Relational Data Modeling &amp; Schema Design</li>
      <li>Introduction to Big Data &amp; HDFS</li>
      <li>MapReduce Framework — how it works</li>
      <li>Apache Spark — architecture, RDDs, execution model</li>
      <li>PySpark — DataFrames, transformations, actions</li>
      <li>ETL Pipeline Development — design and implementation</li>
      <li>Data Warehousing &amp; Data Modeling — star schema, OLAP</li>
      <li>Cloud Intro — AWS S3, GCP BigQuery, workflow orchestration</li>
    </ul>
    <div class="course-card-footer">
      <div class="course-duration">
        <strong>~18 weekends</strong>
        <span>36 sessions &bull; Sat &amp; Sun</span>
      </div>
      <div class="course-fee">
        <span class="fee-amount">₹750</span>
        <span class="fee-label">per session / student</span>
      </div>
    </div>
  </div>

  <!-- Card 4: Advanced DSA -->
  <div class="course-card">
    <div class="course-card-header">
      <span class="course-badge">Prerequisites: Any Language</span>
      <h3>Advanced Data Structures &amp; Algorithms</h3>
      <p class="course-desc">No time spent on language basics. This course assumes you already know how to code and dives straight into patterns, algorithmic thinking, and optimisation techniques used in FAANG-level interviews.</p>
    </div>
    <div class="curriculum-label">Curriculum</div>
    <ul class="curriculum-list">
      <li>Time &amp; Space Complexity — deep analysis and tradeoffs</li>
      <li>Arrays — two pointer, sliding window, prefix sum</li>
      <li>Bit Manipulation</li>
      <li>Sorting &amp; Binary Search — advanced variants</li>
      <li>Recursion &amp; Backtracking — N-Queens, subsets, permutations</li>
      <li>Hashing — advanced patterns, rolling hash</li>
      <li>Linked Lists — fast &amp; slow pointer, reversal patterns</li>
      <li>Stacks &amp; Queues — monotonic stack, deque problems</li>
      <li>Trees — LCA, diameter, serialization, balanced BST</li>
      <li>Tries — prefix trees, autocomplete patterns</li>
      <li>Heaps — top-K problems, merge K sorted, median stream</li>
      <li>Greedy Algorithms — interval scheduling, activity selection</li>
      <li>Graphs — Dijkstra's, Bellman-Ford, MST, topological sort, union-find</li>
      <li>Dynamic Programming — all major patterns end to end</li>
      <li>Segment Trees &amp; Disjoint Set Union — introduction</li>
    </ul>
    <div class="course-card-footer">
      <div class="course-duration">
        <strong>~16 weekends</strong>
        <span>32 sessions &bull; Sat &amp; Sun</span>
      </div>
      <div class="course-fee">
        <span class="fee-amount">₹750</span>
        <span class="fee-label">per session / student</span>
      </div>
    </div>
  </div>

</div>

<div class="courses-cta">
  Interested in joining a batch? Write to me at <a href="mailto:hello@dhirajbalakrishnan.dev">hello@dhirajbalakrishnan.dev</a>
</div>
