<div align="center">

  <img src="assets/banner.svg" alt="Subham Chauhan — Systems, Networking & AI" width="100%" />

  <br /><br />

  <p align="center">
    <em>Building high-throughput systems, low-level networking engines, and intelligent applications.</em>
  </p>

  <p align="center">
    <a href="https://github.com/subhamchauhan0">
      <img src="https://img.shields.io/badge/GitHub-subhamchauhan0-0B0B0B?style=flat-square&logo=github&logoColor=D6C6A5" alt="GitHub" />
    </a>
    &nbsp;&nbsp;
    <a href="https://leetcode.com/u/Subham_chauhan/" target="_blank" rel="noopener noreferrer">
      <img src="https://img.shields.io/badge/LeetCode-Subham__chauhan-0B0B0B?style=flat-square&logo=leetcode&logoColor=D6C6A5" alt="LeetCode" />
    </a>
  </p>

  <img src="assets/berserk-divider.png" alt="Divider" width="80%" />

</div>

<br />

## ⚔️ About Me

```
[SYSTEM INITIALIZED]
Target: subhamchauhan0
Discipline: Systems Programming • Network Protocols • Distributed Backends • Applied AI
Philosophy: "In this world, is the destiny of mankind controlled by some transcendental entity or law? 
             At least it is true that man has no control, even over his own will." — Endure & Overcome.
```

- ⚙️ **Low-Latency & Systems:** Focused on cache-aligned memory layout, lock-free concurrency, zero-allocation logging, and hardware core pinning in **C++17**.
- 🌐 **Networking & Kernel Bypass:** Exploring Layer 4 packet interception (`gopacket`/`libpcap`), raw socket transmission (`SOCK_RAW`), and Layer 7 reverse proxies in **Go**.
- 🛡️ **Cybersecurity & Protocols:** Researching network attack surfaces, packet craft/inspection, authentication primitives (JWT/OAuth), and vulnerability patterns.
- 🧠 **Applied AI & LLMs:** Engineering Retrieval-Augmented Generation (RAG) pipelines, Model Context Protocol (MCP) integrations, and async agent workflows.
- 🔨 **Methodology:** Practical systems engineering driven by performance profiling, RFC standards, and clean modular codebases.

<br />

<div align="center">
  <img src="assets/berserk-divider.png" alt="Divider" width="80%" />
</div>

<br />

## 🗡️ Featured Engineering Projects

### 01. [Trade_Engine](https://github.com/subhamchauhan0/Trade_Engine) — Ultra-Low Latency C++ Trading Engine
> **Core Stack:** `C++17` `CMake` `POSIX Threads` `Lock-Free SPSC` `CPU Pinning` `Memory Pools`

An ultra-low latency, deterministic order matching engine designed for sub-microsecond transaction execution and high-frequency market mechanics.

```
+--------------------------------------------------------------------------------+
|                           TRADE ENGINE ARCHITECTURE                            |
+--------------------------------------------------------------------------------+
|  [Core 3: AlphaServer]   <== SPSC Ring Buffer ==>   [Core 2: OrderGateway]     |
|   (Client Orders / Acks)                             (Validation & Sequencing) |
|            ^                                                   |               |
|            | Market Data Broadcast                             | Inbound Order |
|            v                                                   v               |
|  [Core 4: AsyncLogger]   <== Lock-Free Queue <====  [Core 1: MatchingEngine]   |
|   (Zero-Allocation Log)                              (Limit Order Book / LOB)  |
+--------------------------------------------------------------------------------+
```

- **Deterministic Execution:** Uses dedicated thread-to-core CPU affinity (`pthread_setaffinity_np`) to eliminate context-switch jitter and cache thrashing.
- **Lock-Free Pipeline:** Thread boundaries communicate asynchronously over single-producer single-consumer (SPSC) bounded circular queues without mutex locking.
- **Hardware Alignment:** Core data structures aligned to 64-byte L1 CPU cache lines (`alignas(64)`) to prevent false sharing.
- **Custom Memory Management:** Fixed-size object memory pools for order allocations, avoiding runtime `malloc` overhead on critical paths.
- **Limit Order Book (LOB):** Price-Time Priority order matching logic supporting limit orders, cancellations, and market fills.

👉 **[Inspect Repository →](https://github.com/subhamchauhan0/Trade_Engine)**

---

### 02. [LoadBalancer](https://github.com/subhamchauhan0/LoadBalancer) — Layer 4 NAT & Layer 7 HTTP Reverse Proxy
> **Core Stack:** `Go` `Raw Sockets (AF_INET)` `gopacket / libpcap` `net/http` `Min-Heap` `Cobra CLI`

A high-performance dual-mode networking load balancer handling packet interception, address translation, and dynamic application traffic routing.

```
                              +---------------------------+
                              |   Incoming TCP Traffic    |
                              +-------------+-------------+
                                            |
                    +-----------------------+-----------------------+
                    |                                               |
             [ Layer 4 Mode ]                                [ Layer 7 Mode ]
         Link-Layer Packet Capture                       HTTP Reverse Proxying
       (gopacket & libpcap intercept)                        (net/http Engine)
                    |                                               |
         User-Space NAT Rewrite                          Dynamic Header Injection
      (IP/TCP Checksum Recalculation)                  (X-Forwarded-*, Host Rewrite)
                    |                                               |
      Layer 3 Raw Socket Bypass                       Routing: Round Robin &
       (AF_INET / SOCK_RAW Send)                       Least-Conn (Min-Heap)
                    |                                               |
                    +-----------------------+-----------------------+
                                            |
                              +-------------v-------------+
                              | Backend Pool with Active  |
                              | TCP Health Checks (20s)   |
                              +---------------------------+
```

- **Layer 4 NAT Manipulation:** Intercepts raw TCP packets at the device driver layer using `libpcap`, rewrites IP/TCP headers in user-space, recalculates checksums, and transmits via raw sockets (`SOCK_RAW`), bypassing the host kernel TCP stack.
- **Layer 7 HTTP Reverse Proxy:** Routes HTTP traffic with automated header manipulation (`X-Forwarded-For`, `X-Forwarded-Host`, `X-Forwarded-Proto`).
- **Dynamic Scheduling:** Implements Round Robin and an optimized Least Connections algorithm using an in-memory binary min-heap (`container/heap`).
- **Active Health Checks:** Automated background supervisor verifying TCP socket availability every 20 seconds, dynamically modifying healthy upstream pools.
- **Interactive Control:** Cobra-powered CLI interface for configuring listeners, algorithm parameters, and backend clusters.

👉 **[Inspect Repository →](https://github.com/subhamchauhan0/LoadBalancer)**

---

### 03. [MatchMaker](https://github.com/subhamchauhan0/MatchMaker) — Real-Time Multiplayer Matchmaking Service
> **Core Stack:** `Go` `WebSockets` `JWT Auth` `SQL / Migrations` `React` `RESTful API`

A low-latency backend service orchestrating real-time player matchmaking pools, room assignments, and live WebSocket sessions.

- **Real-Time WebSocket Core:** Concurrent connection broker managing bidirectional player heartbeats, state broadcasts, and room matchmaking queues.
- **Session & Identity Security:** Stateless JWT authentication with secure token renewal controllers and route-level protection middleware.
- **Relational Persistence:** Structured SQL migrations for game cataloging, match histories, and player matchmaking profiles.
- **Full-Stack Integration:** Modular Go backend paired with a responsive client frontend for live match queuing.

👉 **[Inspect Repository →](https://github.com/subhamchauhan0/MatchMaker)**

---

### 04. [chatbot](https://github.com/subhamchauhan0/chatbot) — Retrieval-Augmented Generation (RAG) & Tool Engine
> **Core Stack:** `Python` `LangChain / LLM APIs` `RAG Vector Search` `SQLite` `React / Vite`

An applied AI system exploring vector context retrieval, tool invocation workflows, and conversational knowledge grounding.

- **Context Grounding (RAG):** Document parsing, chunking, and semantic vector retrieval pipelines to prevent LLM hallucinations.
- **Tool & Agent Extensibility:** Modular tool interfaces enabling autonomous model-driven query routing and computation.
- **Persistent State:** SQLite database recording session histories and conversational metadata.
- **Client Interface:** Vite-powered interactive frontend communicating with the Python backend server.

👉 **[Inspect Repository →](https://github.com/subhamchauhan0/chatbot)**

<br />

<div align="center">
  <img src="assets/berserk-divider.png" alt="Divider" width="80%" />
</div>

<br />

## 🛠️ Technical Arsenal

| Domain | Technologies & Tooling |
| :--- | :--- |
| **Languages** | `C++17` &nbsp;•&nbsp; `Go` &nbsp;•&nbsp; `Python` &nbsp;•&nbsp; `JavaScript` &nbsp;•&nbsp; `TypeScript` &nbsp;•&nbsp; `SQL` |
| **Systems & Architecture** | Multi-threading &nbsp;•&nbsp; Cache Alignment (`alignas(64)`) &nbsp;•&nbsp; CPU Affinity &nbsp;•&nbsp; Lock-Free Ring Buffers &nbsp;•&nbsp; Memory Pools |
| **Networking & Protocols** | Raw Sockets (`SOCK_RAW`) &nbsp;•&nbsp; `gopacket` / `libpcap` &nbsp;•&nbsp; TCP/IP Stack &nbsp;•&nbsp; HTTP Reverse Proxy &nbsp;•&nbsp; WebSockets |
| **Backend & Databases** | REST APIs &nbsp;•&nbsp; JWT / Session Auth &nbsp;•&nbsp; SQLite &nbsp;•&nbsp; Database Migrations &nbsp;•&nbsp; Docker Compose |
| **AI & Intelligent Systems** | Retrieval-Augmented Generation (RAG) &nbsp;•&nbsp; LangChain &nbsp;•&nbsp; LangGraph Workflows &nbsp;•&nbsp; Model Context Protocol (MCP) |
| **Environment & Tooling** | Linux / POSIX &nbsp;•&nbsp; Git &nbsp;•&nbsp; CMake &nbsp;•&nbsp; Make &nbsp;•&nbsp; GDB &nbsp;•&nbsp; Vim |

<br />

<div align="center">
  <img src="assets/berserk-divider.png" alt="Divider" width="80%" />
</div>

<br />

## 🌑 Additional & Collaborative Work

- **[url_shortener](https://github.com/subhamchauhan0/url_shortener):** High-throughput URL redirection service built in Go with containerized Docker Compose architecture.
- **[CLI_TODO_LIST](https://github.com/subhamchauhan0/CLI_TODO_LIST):** Terminal-first productivity CLI application implemented in Go.
- **[lang_chain](https://github.com/subhamchauhan0/lang_chain) & [learn-langGraph](https://github.com/subhamchauhan0/learn-langGraph):** Hands-on exploration of asynchronous multi-agent coordination and LLM prompt pipelines.
- **[TAI](https://github.com/subhamchauhan0/TAI):** Autonomous agent evaluation, testing frameworks, and brute-force detection agent modules.

<br />

<div align="center">
  <img src="assets/berserk-divider.png" alt="Divider" width="80%" />
</div>

<br />

## 📊 Activity & Telemetry

<div align="center">

  <!-- GitHub Stats & Top Languages -->
  <a href="https://github.com/subhamchauhan0">
    <img src="https://github-readme-stats.vercel.app/api?username=subhamchauhan0&show_icons=true&bg_color=0B0B0B&title_color=D6C6A5&text_color=A0A0A0&icon_color=8B0000&border_color=444444" alt="Subham's GitHub Stats" width="49%" />
  </a>
  <a href="https://github.com/subhamchauhan0">
    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=subhamchauhan0&layout=compact&bg_color=0B0B0B&title_color=D6C6A5&text_color=A0A0A0&border_color=444444" alt="Top Languages" width="49%" />
  </a>

  <br /><br />

  <!-- GitHub Streak & LeetCode Stats (Side-by-Side) -->
  <a href="https://github.com/subhamchauhan0">
    <img src="https://streak-stats.demolab.com/?user=subhamchauhan0&theme=dark&background=0B0B0B&border=444444&stroke=444444&ring=8B0000&fire=8B0000&currStreakLabel=D6C6A5&sideLabels=A0A0A0&dates=A0A0A0" alt="GitHub Streak Stats" width="49%" />
  </a>
  <a href="https://leetcode.com/u/Subham_chauhan/" target="_blank" rel="noopener noreferrer">
    <img src="https://leetcard.jacoblin.cool/Subham_chauhan?theme=dark&font=JetBrains%20Mono&ext=heatmap" alt="LeetCode Stats" width="49%" />
  </a>

  <br /><br />

  <!-- Animated Contribution Snake (Generated via .github/workflows/snake.yml) -->
  <img src="https://raw.githubusercontent.com/subhamchauhan0/subhamchauhan0/output/github-snake-crimson.svg" alt="Contribution Snake Animation" width="100%" />

</div>

<br />

<div align="center">
  <img src="assets/berserk-divider.png" alt="Divider" width="80%" />
</div>

<br />

## ⚔️ The Brand of Struggle

<div align="center">

  > *"Even if force of destiny is immutable, even if all actions are predetermined... a man must still brandish his sword and fight through the dark."*

  <br />

  # STRUGGLE. ENDURE. OVERCOME.

  <br />

  [![GitHub](https://img.shields.io/badge/GitHub-subhamchauhan0-0B0B0B?style=for-the-badge&logo=github&logoColor=D6C6A5&borderColor=444444)](https://github.com/subhamchauhan0)
  &nbsp;&nbsp;
  [![LeetCode](https://img.shields.io/badge/LeetCode-Subham__chauhan-0B0B0B?style=for-the-badge&logo=leetcode&logoColor=D6C6A5&borderColor=444444)](https://leetcode.com/u/Subham_chauhan/)

</div>

