<div align="center">
  <img src="assets/banner.svg" alt="Subham Chauhan — Systems, Networking and AI" width="100%" />
  <p>
    <em>Building systems, exploring networking protocols, and engineering intelligent applications.</em>
  </p>
  <p>
    <a href="https://codolio.com/profile/shubbu" target="_blank" rel="noopener noreferrer">
      <img src="https://img.shields.io/badge/Codolio-shubbu-0B0B0B?style=flat-square&logo=codeforces&logoColor=D6C6A5" alt="Codolio Profile — shubbu" />
    </a>
    &nbsp;&nbsp;
    <a href="https://www.linkedin.com/in/subham-chauhan-6abb39282" target="_blank" rel="noopener noreferrer">
      <img src="https://img.shields.io/badge/LinkedIn-Subham_Chauhan-0B0B0B?style=flat-square&logo=linkedin&logoColor=D6C6A5" alt="LinkedIn Profile" />
    </a>
  </p>
</div>

---

## About

I am a software developer interested in systems programming, backend engineering, computer networking, and applied AI. I enjoy understanding software at a low level and building practical projects around concurrency, network protocols, and LLM tooling.

## Engineering Focus

- **Systems & Performance:** C++17, multithreading, lock-free SPSC queues, cache-aligned memory layout, and custom memory pools.
- **Networking & Backend:** Go, TCP/IP packet handling, raw sockets, HTTP reverse proxies, WebSockets, and REST APIs.
- **Applied AI:** Python, Retrieval-Augmented Generation (RAG), tool-calling workflows, and Model Context Protocol (MCP) exploration.

---

## Featured Projects

### [Trade_Engine](https://github.com/subhamchauhan0/Trade_Engine) — Multithreaded C++ Limit-Order Matching Engine
A C++17 order-matching engine exploring deterministic execution pipelines, concurrency, and memory management.

- Dedicated thread-to-core CPU affinity (`pthread_setaffinity_np`) separating matching, gateway, client, and logging threads.
- Lock-free single-producer single-consumer (SPSC) ring buffers and 64-byte cache-aligned structures (`alignas(64)`).
- Price-time priority limit order book backed by fixed-size object memory pools and an asynchronous logger.

**Stack:** `C++17` · `CMake` · `POSIX Threads` · [View source →](https://github.com/subhamchauhan0/Trade_Engine)

### [LoadBalancer](https://github.com/subhamchauhan0/LoadBalancer) — Layer 4 NAT & Layer 7 HTTP Load Balancer
A modular Go networking project implementing Layer 4 packet manipulation and Layer 7 HTTP reverse proxying.

- **Layer 4 NAT Mode:** Captures incoming TCP packets via `gopacket` and `libpcap`, rewrites IP/TCP headers and checksums in user space, and injects packets through raw sockets (`AF_INET`/`SOCK_RAW`).
- **Layer 7 Proxy Mode:** Routes HTTP traffic via `net/http` with `X-Forwarded-*` header injection.
- **Routing & Health Checks:** Round Robin and min-heap Least Connections scheduling (`container/heap`), periodic 20-second TCP health checks, and a Cobra CLI.

**Stack:** `Go` · `gopacket` · `libpcap` · `Cobra CLI` · [View source →](https://github.com/subhamchauhan0/LoadBalancer)

### [MatchMaker](https://github.com/subhamchauhan0/MatchMaker) — Real-Time Multiplayer Matchmaking Service
A full-stack matchmaking and lobby service orchestrating player queues and live game sessions.

- Concurrent WebSocket broker (`client.go`, `websockets.go`) for bidirectional player communication and room state updates.
- JWT-based authentication with token refresh controllers and route-level middleware.
- SQL schema migrations for game catalogs and matchmaking persistence, paired with a React frontend.

**Stack:** `Go` · `WebSockets` · `JWT` · `SQL` · `React` · [View source →](https://github.com/subhamchauhan0/MatchMaker)

### [chatbot](https://github.com/subhamchauhan0/chatbot) — RAG & Tool-Calling AI Application
An applied AI application exploring Retrieval-Augmented Generation (RAG), model/tool integration, and conversational state.

- Document ingestion and vector retrieval pipeline (`rag.py`) to ground model responses in source context.
- Modular tool routing (`tools.py`) and middleware for structured model workflows.
- SQLite conversation persistence paired with a React/Vite frontend.

**Stack:** `Python` · `RAG` · `SQLite` · `React` · `Vite` · [View source →](https://github.com/subhamchauhan0/chatbot)

---

## Other Projects & Experiments

- **[url_shortener](https://github.com/subhamchauhan0/url_shortener):** URL shortening service in Go with database persistence and Docker Compose setup.
- **[CLI_TODO_LIST](https://github.com/subhamchauhan0/CLI_TODO_LIST):** Command-line task manager implemented in Go.
- **[lang_chain](https://github.com/subhamchauhan0/lang_chain) & [learn-langGraph](https://github.com/subhamchauhan0/learn-langGraph):** Learning experiments with LangChain pipelines and asynchronous LangGraph workflows.

---

## Tech & Links

<div align="center">
  <img src="https://skillicons.dev/icons?i=cpp,go,py,js,ts,react,nodejs,postgres,mongodb,sqlite,linux,git,cmake,docker&theme=dark" alt="Technologies: C++, Go, Python, JavaScript, TypeScript, React, Node.js, PostgreSQL, MongoDB, SQLite, Linux, Git, CMake, Docker" />
  <br /><br />
  <a href="https://github.com/subhamchauhan0" target="_blank" rel="noopener noreferrer"><img src="./assets/icons/github.svg" width="36" height="36" alt="GitHub" /></a>&nbsp;&nbsp;<a href="https://www.linkedin.com/in/subham-chauhan-6abb39282" target="_blank" rel="noopener noreferrer"><img src="./assets/icons/linkedin.svg" width="36" height="36" alt="LinkedIn" /></a>&nbsp;&nbsp;<a href="https://codolio.com/profile/shubbu" target="_blank" rel="noopener noreferrer"><img src="./assets/icons/codolio.svg" width="36" height="36" alt="Codolio" /></a>&nbsp;&nbsp;<a href="mailto:subham15062005@gmail.com"><img src="./assets/icons/gmail.svg" width="36" height="36" alt="Gmail" /></a>
</div>

---

## Activity

<div align="center">
  <img src="https://raw.githubusercontent.com/subhamchauhan0/subhamchauhan0/output/github-snake-crimson.svg" alt="GitHub Contribution Snake Animation" width="100%" />
</div>

---

## Contact

- **GitHub:** [github.com/subhamchauhan0](https://github.com/subhamchauhan0)
- **LinkedIn:** [linkedin.com/in/subham-chauhan-6abb39282](https://www.linkedin.com/in/subham-chauhan-6abb39282)
- **Codolio:** [codolio.com/profile/shubbu](https://codolio.com/profile/shubbu)
- **Email:** [subham15062005@gmail.com](mailto:subham15062005@gmail.com)

<div align="center">
  <strong>STRUGGLE. ENDURE. OVERCOME.</strong>
</div>
