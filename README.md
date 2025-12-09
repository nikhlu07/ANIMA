# 🛡️ A.E.G.I.S.
### (Autonomous Ethereum Guardian & Intelligence System)

> **The AI Agent that doesn't just chat—it protects.** > *Built for the Agent Arena Hackathon 2025*

![License](https://img.shields.io/badge/license-MIT-blue) ![Stack](https://img.shields.io/badge/Built%20With-ADK--TS-purple) ![Status](https://img.shields.io/badge/Status-Hackathon%20Submission-orange)

## 📖 Overview
**A.E.G.I.S.** is an autonomous DeFi agent designed to solve the "Dark Forest" problem of Web3. While most AI agents focus on executing trades, A.E.G.I.S. focuses on **risk management and user safety**.

Built using **IQAI's ADK-TS (Agent Development Kit)**, this agent acts as a sentinel for your wallet. It autonomously queries on-chain state, analyzes token approvals, and assesses gas levels to prevent failed transactions and security risks before they happen.

## 🚀 Key Features

* **⚡ Gas Sentinel:** Proactively monitors ETH balances and calculates if the user has enough gas for intended operations, preventing failed transaction fees.
* **🔓 Approval Watchdog:** Scans the wallet for "Unlimited Allowance" approvals to risky contracts and flags them using AI reasoning.
* **🧠 Intelligent Risk Scoring:** Uses an LLM to interpret raw blockchain data into a natural language "Risk Report" for the user.
* **🔗 On-Chain Integration:** Direct interaction with Ethereum Mainnet via Ethers.js wrapped in ADK Tools.

## 🛠️ Tech Stack

* **Agent Framework:** [ADK-TS (IQAI)](https://github.com/IQAIcom/adk-ts)
* **Blockchain Interaction:** Ethers.js (v6)
* **LLM Engine:** Gemini 1.5 Flash (via ADK Model Provider)
* **Environment:** Node.js / TypeScript

## ⚙️ How it Works

A.E.G.I.S. utilizes the **ADK-TS** architecture to bridge the gap between Natural Language and EVM State:

1.  **User Intent:** User asks: *"Is my wallet safe to interact with this protocol?"*
2.  **Tool Execution:** The Agent calls custom ADK Tools (`get_balance`, `check_allowance`).
3.  **Data Fetch:** Tools query the RPC Provider (Ethereum).
4.  **AI Synthesis:** The LLM receives the raw data (e.g., "Balance: 0.002 ETH") and contextualizes it (e.g., *"Critical Warning: Insufficient funds for gas"*).

## 📦 Installation & Usage

### Prerequisites
* Node.js (v18+)
* An Ethereum RPC URL (Infura/Alchemy/LlamaNodes)
* Google Gemini API Key (or OpenAI Key)

### Steps

1.  **Clone the Repository**
    ```bash
    git clone [https://github.com/yourusername/AEGIS.git](https://github.com/yourusername/AEGIS.git)
    cd AEGIS
    ```

2.  **Install Dependencies**
    ```bash
    npm install
    ```

3.  **Configure Environment**
    Create a `.env` file in the root directory:
    ```env
    GOOGLE_API_KEY=your_gemini_key_here
    RPC_URL=[https://eth.llamarpc.com](https://eth.llamarpc.com)
    ```

4.  **Run the Sentinel**
    ```bash
    npx tsx src/agents/aegis.ts
    ```

## 🎥 Demo
*[Link to your YouTube/Loom video here]*

## 🏆 Hackathon Tracks
This project is submitted for the **Agent Arena** hackathon under the following categories:
* **DeFi / Web3 Agent:** Pure software agent for blockchain management.
* **ADK-TS Implementation:** Built 100% using the Agent Development Kit.

## 🗺️ Roadmap
* **Phase 1 (Current):** Read-only analysis of balances and approvals.
* **Phase 2:** "Kill Switch" capabilities (Agent autonomously revokes permissions if a hack is detected).
* **Phase 3:** Launch on **IQAI Agent Tokenization Platform (ATP)** for decentralized access.

---
*Built with ❤️ by [Your Name/Team Name]*
