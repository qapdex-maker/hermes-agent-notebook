# ⚕  Kaggle-Hermes-Agent-Notebook

[![Version](https://img.shields.io/badge/Version-v0.15.1-orange.svg)](https://github.com/kun1gund3/Kaggle-Hermes-Agent-Notebook)
[![Model](https://img.shields.io/badge/Model-Hermes_3_8B-blueviolet.svg)](https://nousresearch.com/)
[![Platforms](https://img.shields.io/badge/Platforms-Termux%20|%20Windows%20|%20Ubuntu-green.svg)]()

Run the **Hermes Agent** locally on your device (Termux, Windows, or Ubuntu) while utilizing a **Kaggle Notebook** as a high-performance **Custom API Endpoint** for remote LLM inference.

---

### 🏗️ Hybrid Architecture

This project splits the workload to combine local control with cloud-based GPU power:

*   **Local Client (Termux/Win/Linux):** Handles the agentic loop, logic, file operations, and tool execution.
*   **Remote Backend (Kaggle):** Serves as the inference engine (API Point), running heavy models like Hermes 3 8B on Kaggle's free T4/P100 GPUs.

| Component | Specification |
| :--- | :--- |
| **Framework** | Nous Hermes AI Agent Framework |
| **Local OS** | Termux (Android), Windows (WSL/CMD), Ubuntu |
| **Remote GPU** | Kaggle Notebook (Acting as API Server) |
| **Agentic Loop** | Thought ➔ Action ➔ Observation ➔ Reflection |
| **TTS Support** | Piper local TTS (44 languages) |

---

### 🛠️ Tools & Capabilities
The agent operates locally on your machine, giving it direct access to your local environment:

*   **💻 Terminal:** Execute local shell commands and scripts.
*   **📂 Filesystem:**
    *   `read_file` / `write_file`: Manage local workspace files.
    *   `patch`: Smart "Find-and-Replace" for code editing.
    *   `search_files`: Recursive local directory search.
*   **🌐 Web Intelligence:** 
    *   `web_search` & `web_extract`: Browse the live web for data.
*   **🧠 Python Integration:** Full `hermes_tools` support for local Python execution.

---

### ⚠️ Note on Model Agentics
**Nous Research Hermes 3 & 4 models are NOT natively agentic.** They lack built-in tool-calling protocols found in proprietary models. 
**This framework provides the bridge:** It uses sophisticated prompt engineering and a recursive feedback loop to enable these models to work autonomously via the Kaggle API.

---

### ⏯️ Setup & Usage

#### 1. The Backend (Kaggle)
1.  Open the provided notebook in [Kaggle](https://www.kaggle.com/).
2.  Enable **GPU Acceleration** and **Internet**.
3.  Run the notebook to start the **Custom API Server** (typically using an Ngrok or Localtunnel bridge).
4.  Copy the generated API URL.

#### 2. The Client (Local)
1.  Clone Hermes Agent Repository to your local machine (Termux/Windows/Ubuntu).
2.  Configure the agent to point to your **Kaggle API URL**.
3.  Run the agent.

---

### 🎙️ Local Voice (TTS)
The agent features integrated **Piper TTS**, running entirely on your local CPU for instant voice feedback without cloud latency.
*   **Storage:** Voices are cached in `~/.hermes/cache/piper-voices/`.
*   **Privacy:** No voice data ever leaves your local device.

---

### 🔗 Links & Resources
*   **GitHub Repository:** [Hermes Agent](https://github.com/nousresearch/hermes-agent)
*   **Technical Documentation:** [Documentation](https://docs.google.com/document/d/13qf3zHT7KEKHb-p_-HSPJJUXqfx-f3eQ5t2CHjHLaAc/edit?usp=drivesdk)

---
*Developed with ❤️*
