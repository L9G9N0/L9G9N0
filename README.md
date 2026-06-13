<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:000000,100:202020&height=180&section=header&text=Hariom%20Kumar%20Bharti&fontSize=40&fontColor=ffffff&animation=fadeIn&fontAlignY=35" alt="Hariom Header" />
  
  <a href="https://git.io/typing-svg">
    <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=600&size=22&pause=1000&color=ffffff&center=true&vCenter=true&width=600&lines=Agentic+AI+%26+MLOps+Engineer;Low-Level+Systems+%26+macOS+Native+Dev;Competitive+Programmer+(Graph+%26+DP);CSE+Sophomore+%40+IIIT-Delhi;Execution-First+Mindset" alt="Typing SVG" />
  </a>
</div>

---

### 👨‍💻 Executive Summary
I am a **Computer Science Sophomore at Indraprastha Institute of Information Technology, Delhi (IIIT-D)** with a strong academic standing. My engineering spectrum spans across low-level systems programming, native macOS development, and agentic AI pipelines. I don't just write code; I architect solutions that demand rigorous memory management, high concurrency, and production-grade scalability. 

Whether it's building offline biometric daemons in C++ or orchestrating LLMs for MLOps pipelines, my approach is rooted in first principles and mathematical logic.

- 🔭 **Currently Building:** High-performance macOS utilities and scalable AI microservices.
- 🧠 **Problem Solving:** Solved **300+ algorithmic problems** across Codeforces and LeetCode, specializing in Graph Theory and Dynamic Programming paradigms.
- ⚡ **Engineering Philosophy:** *Analyze the constraints. Build the architecture. Write zero-fluff code.*

---

### 🛠️ Technical Ecosystem

**Languages:**
![C++](https://img.shields.io/badge/c++-%2300599C.svg?style=for-the-badge&logo=c%2B%2B&logoColor=white) ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Swift](https://img.shields.io/badge/Swift-FA7343?style=for-the-badge&logo=swift&logoColor=white) ![Java](https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white) ![TypeScript](https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white) ![C](https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white)

**AI, ML & Data Pipelines:**
![Scikit-Learn](https://img.shields.io/badge/scikit_learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white) ![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white) ![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white) ![Groq](https://img.shields.io/badge/Groq_API-000000?style=for-the-badge&logo=ai&logoColor=white) ![Llama-3](https://img.shields.io/badge/Llama_3.1-0466C8?style=for-the-badge&logo=meta&logoColor=white)

**Frameworks & Back-End:**
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white) ![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white) ![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB) ![SwiftUI](https://img.shields.io/badge/SwiftUI-007AFF?style=for-the-badge&logo=swift&logoColor=white)

**Infrastructure & Databases:**
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white) ![AWS S3](https://img.shields.io/badge/AWS_S3-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white) ![Linux Internals](https://img.shields.io/badge/UNIX_Sockets-FCC624?style=for-the-badge&logo=linux&logoColor=black)

---

### 🚀 Deep Dive: Featured Architectures

#### 🧠 [Q-Commerce Logistics Intelligence Engine](https://github.com/L9G9N0/q-commerce-sla-predictor)
*An end-to-end MLOps pipeline built to benchmark predictive delivery delays and automate root-cause analysis.*
- **The Core Engine:** Benchmarked XGBoost against baseline Logistic Regression, ultimately identifying the algorithmic data ceiling to pivot the strategy toward a GenAI-based Root Cause Analysis.
- **Architecture:** Engineered a highly modular MLOps system that strictly decouples data processing, modeling, and inference logic, guaranteeing production-grade maintainability.
- **Tech Stack:** `Python`, `XGBoost`, `Scikit-Learn`, `Groq API (Llama-3.1-8b)`, `Pandas`.

#### 🍏 [macOS FaceUnlock (Apple Silicon Native)](https://github.com/L9G9N0/MACOS-FACEUNLOCK)
*An offline, secure macOS authentication daemon utilizing 3D Liveness state machines.*
- **Performance:** Achieved microsecond IPC latency by meticulously routing secure data streams to the kernel via UNIX sockets and a custom C++ PAM module.
- **Optimization:** Accelerated verification to $O(1)$ time complexity by caching 128-D facial vectors directly in RAM for instant distance matching.
- **Security:** Engineered to operate with a 0% false-positive spoofing rate.
- **Tech Stack:** `Python`, `C++`, `MediaPipe`, `dlib`, `UNIX Sockets`, `PAM`.

#### ☁️ [OrbitSync Vault: Agentic Cloud Storage](https://github.com/L9G9N0/OrbitSync-Backend)
*A cloud-native local synchronization daemon powered by automated semantic AI tagging.*
- **AI Integration:** Engineered an Agentic AI pipeline (Llama-3.1-8b) capable of automated semantic tagging, heavily optimizing file discoverability through PostgreSQL ILIKE vector-searches.
- **System Internals:** Developed a daemon utilizing `Watchdog` and `FSEvents` to achieve real-time data replication with absolutely zero manual delays.
- **Tech Stack:** `FastAPI`, `PostgreSQL`, `Llama-3.1-8b`, `Watchdog`, `React`.

#### ⏳ [Devotee Mode: macOS Distraction Blocker](https://github.com/L9G9N0/Devotee-Mode-macOS)
*A hardcore native macOS menu-bar utility enforcing deep work via process termination.*
- **System Automation:** Engineered a "Sweep & Kill" engine leveraging `NSWorkspace` to continuously monitor and force-terminate blocked applications in real-time.
- **State Management:** Overhauled state management using a Dictionary-based structure (`[String: BlockInfo]`) to guarantee $O(1)$ lookup times for background process validation.
- **Tech Stack:** `Swift`, `SwiftUI`, `AppKit`, `Combine Framework`.

#### 📘 [TypeLearn AI: Intelligent Learning Mentor](https://github.com/L9G9N0/typelearn-ai)
*An educational platform integrating real-time AI feedback loops and data visualization.*
- **AI Engine:** Leveraged the Groq API and Llama-3.1-8b for sub-second AI analysis to generate highly contextual, real-time feedback.
- **Full-Stack Implementation:** Secured backend routes via custom Next.js Middleware and architected data-driven dashboards featuring asynchronous activity heatmaps.
- **Tech Stack:** `Next.js`, `Groq API`, `TypeScript`, `Llama-3.1-8b`.

---

### 🏆 Industry Certifications & Training
- **Cybersecurity Virtual Internship:** Verified simulation by **Deloitte Australia** focusing on high-stakes log analysis and incident response.
- **Ethical Hacking & Penetration Testing:** Completed a rigorous 45-day intensive training program conducted by **C-DAC Noida** (Cyber Gyan).

---

### 🤝 Leadership & Community Operations
<details>
<summary>Click to view campus impact</summary>
<br>

* **Operations Lead @ Esya 2025:** Orchestrated massive-scale logistics for 40+ technical events, successfully managing a footfall of over 2,000+ participants.
* **Volunteer Lead @ Summer Camp 2025:** Directed an inclusive STEM curriculum, leading a team of 10+ volunteers to teach tech fundamentals to 125+ high school students.
* **Organizing Team @ Induction 2025:** Executed onboarding and infrastructural guidance for over 650+ incoming university freshers.
</details>

---

### 📊 Analytics & Activity
<div align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=L9G9N0&bg_color=000000&color=ffffff&line=ffffff&point=ffffff&hide_border=true" width="100%" alt="Activity Graph" />
</div>
<br>
<div align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com?user=L9G9N0&theme=tokyonight&hide_border=true&date_format=M%20j%5B%2C%20Y%5D&background=000000" alt="streak graph" />
</div>

---

<div align="center">
  <h3>Initiate a Connection</h3>
  <a href="https://www.linkedin.com/in/hariomkumarbharti">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>
  <a href="mailto:hariom24229@iiitd.ac.in">
    <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" />
  </a>
  <a href="https://hariomkumarbharti.netlify.app">
    <img src="https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=vercel&logoColor=white" />
  </a>
</div>
