---

#### Blockitecture Project Overview - QBBC (Quantum Blockchain Bitchat)

The Blockitecture project is designed to enhance QBBC's modular architecture with advanced encryption and decentralized messaging capabilities.

#### Key Features

* **Encryption**: Integration of Kyber's key encapsulation mechanism (KEM) and hybrid encryption layer (Kyber + AES-GCM).
* **Blockchain**: Implementation of Hyperledger Fabric for tamper-proof key management.
* **Decentralized Transport**: Exploration of options inspired by BlackBerry Messenger's NOC.

#### Roadmap

1. **Discovery & Foundation**:
   * Break down bitchat codebase
   * Map data flow and message lifecycle

2. **Encryption Overhaul**:
   * Integrate Kyber key exchange
   * Build hybrid encryption layer (Kyber + AES-GCM)
   * Validate performance under load

3. **Blockchain Infrastructure**:
   * Set up Hyperledger Fabric
   * Create smart contracts for key management
   * Test key submission and retrieval

4. **Integration**:
   * Connect app modules with Fabric
   * Add UI toggles for enterprise features
   * Test edge cases

#### Updated Layered Architecture Diagram

```mermaid
graph TB
    subgraph "Application Layer"
        UI["Chat UI"]
        CMD["Commands"]
        ROOM["Channel Management"]
        KYC["Know Your Chatter Settings"]
    end

    subgraph "Service Layer"
        KYBER["Kyber Key Exchange"]
        ENC["Hybrid Encryption - Kyber + AES-GCM"]
        RETRY["Message Retry Service"]
        RETAIN["Message Retention Service"]
        FOIA["FOIA Logging Engine"]
        COMP["Compression Service"]
        BATT["Battery Optimizer"]
    end

    subgraph "Smart Contract Layer"
        FABRIC["Hyperledger Chaincode"]
        CONTRACTS["User Verification & Key Storage"]
    end

    subgraph "Transport Layer"
        PROTO["Binary Protocol"]
        FRAG["Fragment Handler"]
        BLE["BLE Central / Peripheral"]
        NOC["Hybrid NOC Transport - Relay / Federated"]
    end

    subgraph "Mesh Network Layer"
        ROUTE["Message Router"]
        RELAY["Relay Engine"]
        STORE["Store and Forward Cache"]
    end

    %% Flows
    UI & CMD & ROOM --> KYC --> KYBER & ENC & RETRY & RETAIN & FOIA & COMP & BATT
    KYBER & ENC --> CONTRACTS
    CONTRACTS --> FABRIC
    RETRY & RETAIN & FOIA & COMP & BATT --> ROUTE & RELAY & STORE
    ROUTE & RELAY & STORE --> PROTO & FRAG & BLE & NOC

    %% Styling
    style KYC fill:#e1f5fe
    style KYBER fill:#f3e5f5
    style ENC fill:#f3e5f5
    style CONTRACTS fill:#ede7f6
    style FABRIC fill:#ede7f6
    style FOIA fill:#f3e5f5
    style NOC fill:#fff3e0
```
