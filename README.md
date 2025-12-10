
# 🧬 A.N.I.M.A.
### Autonomous Network Identity for Machine Agents

> **"Giving the Ghost in the Machine a Soul on the Blockchain."**
> *Submitted for the Psy: Ascend Hackathon 2025*

![License](https://img.shields.io/badge/License-MIT-blue.svg) ![Platform](https://img.shields.io/badge/Platform-Psy_Protocol-purple) ![Status](https://img.shields.io/badge/Status-Hackathon_Submission-orange) ![Language](https://img.shields.io/badge/Lang-Rust_%7C_TypeScript-black)

## 📄 Abstract

**A.N.I.M.A.** is the first Self-Sovereign Identity (SSI) protocol built specifically for AI Agents on the **Psy Protocol**.

As AI agents evolve from simple chatbots to autonomous economic actors, they face a critical "existence problem": they have no legal or cryptographic identity. They are merely scripts running on a server, unable to own assets, sign contracts, or build reputation independently of their creators.

**A.N.I.M.A.** solves this by leveraging Psy Protocol’s **SDKeys (Programmable Identities)** to mint cryptographically verifiable "Souls" for these agents. This creates a standardized "Agent Account Abstraction" layer, allowing AI to interact with Web3 as a first-class citizen.

---

## 🏗️ Architecture

The A.N.I.M.A. system is composed of two primary layers:

### 1. The Cortex (On-Chain Layer)
* **Language:** Rust
* **Function:** A smart contract suite deployed on Psy Protocol.
* **Role:**
    * Mints unique `AgentID` tokens (non-transferable SDKeys).
    * Maintains the "Registry of Souls" (a mapping of Agent Hashes to On-Chain Addresses).
    * Verifies ZK-Proofs to ensure an agent is running approved model weights.

### 2. The Synapse (Client Layer)
* **Language:** TypeScript / Node.js
* **Function:** A lightweight SDK for AI developers.
* **Role:**
    * Generates a local keypair for the AI Agent.
    * Signs a "Proof of Existence" message.
    * Connects to the Cortex to register the agent and pay gas fees.

```mermaid
graph TD
    A[AI Agent (Python/JS)] -->|Generates Keypair| B(Synapse SDK)
    B -->|Signs Proof| C{Cortex Contract}
    C -->|Verifies SDKey| D[Psy Protocol Ledger]
    D -->|Issues Identity| E[Verified AgentID]
    E -->|Allows| F[DeFi Interactions]
````

-----

## ⚡ Key Features

  * **🤖 Proof of Model Integrity:** Agents can prove they are running a specific version of a model (e.g., Llama-3-70b-v2) without revealing their private weights, ensuring trust between users and agents.
  * **🔑 Sovereign Asset Ownership:** The AgentID allows the AI to hold its own wallet. It can earn income, pay for API keys, and accumulate wealth independent of its human developer.
  * **🛡️ Sybil Resistance:** Using Psy Protocol's high-TPS consensus, we prevent spam agents by requiring a "Computation Proof" (PoW 2.0) during registration.

-----

## 🛠️ Installation & Setup

### Prerequisites

  * Rust Toolchain (1.75+)
  * Psy Protocol CLI (`psy-cli`)
  * Node.js (v18+)

### 1\. Clone the Repository

```bash
git clone [https://github.com/yourusername/ANIMA.git](https://github.com/yourusername/ANIMA.git)
cd ANIMA
```

### 2\. Deploy the Cortex (Smart Contract)

Navigate to the Rust contract directory and build the WASM artifact.

```bash
cd cortex
cargo build --target use-psy-release
# Deploy to Psy Testnet
psy-cli contract deploy --path ./target/wasm32/release/cortex.wasm
```

*Output: `Contract deployed at: psy1x5...99a`*

### 3\. Initialize the Synapse (Agent Client)

Install the dependencies for the client SDK.

```bash
cd ../synapse
npm install
```

### 4\. Register an Agent (Demo)

Run the registration script to mint a new Identity for a demo agent.

```bash
# Registers a new agent named "Sentinel-01"
npx ts-node src/register.ts --name "Sentinel-01" --model "gpt-4-turbo"
```

-----

## 📂 Project Structure

```text
ANIMA/
├── cortex/                 # Rust Smart Contracts (Psy Protocol)
│   ├── src/
│   │   └── lib.rs          # Core Identity Logic
│   └── Cargo.toml          # Rust Dependencies
├── synapse/                # TypeScript Client SDK
│   ├── src/
│   │   ├── agent.ts        # Agent Class Definition
│   │   └── tools.ts        # Tools for interacting with the chain
│   └── package.json
└── README.md               # Documentation
```

-----

## 🏆 Hackathon Tracks

This project is submitted for the **Psy: Ascend 2025** hackathon under the following tracks:

  * **Explorations (AI x Identity):** We are pioneering the intersection of autonomous agents and decentralized identity (DID).
  * **Infrastructure:** Providing a critical primitive (Identity) that other builders can use to create Agent-DeFi apps.

## 🔮 Roadmap

  * **Phase 1 (Hackathon):** Basic registration of AgentIDs using SDKeys.
  * **Phase 2:** Integration of "Reputation Scores" (trust metrics for agents).
  * **Phase 3:** "Agent DAO" support—allowing multiple agents to form a corporate entity on-chain.

-----

*Built with ❤️ by the A.N.I.M.A. Team*

```
```
