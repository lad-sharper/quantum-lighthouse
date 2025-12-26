# Quantum Lighthouse — Architecture Breakdown

## Overview

Quantum Lighthouse is designed to work seamlessly with **Base's ecosystem**, primarily focusing on **Base Mainnet** and **Base Sepolia** for deployment and testing. This document provides a detailed breakdown of how the tool operates, the key design decisions, and how it integrates with **Base's read-only model**.

---

## Key Design Decisions

### 1. **Base Network Integration**

Quantum Lighthouse is integrated with **Base networks** to leverage their secure, scalable, and decentralized infrastructure. The tool interacts with **Base Mainnet** for production purposes and **Base Sepolia** for testing. 

- **Base Mainnet** (Chain ID: `8453`) is used for real transactions and data queries.
- **Base Sepolia** (Chain ID: `84532`) is used for testing, contract verification, and experimentation.

Network configuration details, including RPC URLs and explorer links, are managed in the `config/base.networks.json` file. This file allows easy updates, additions, or removals of network configurations.

---

### 2. **Read-only Model**

A core principle of Quantum Lighthouse is its **read-only design**, which limits the operations to queries and inspections without making any modifications to the blockchain state. This approach aligns with Base's commitment to **safe, secure, and efficient** network interactions.

Allowed operations include:
- **Balance checks**: Verifying the balance of native tokens and tokens on Base.
- **Contract code inspection**: Ensuring that the contract exists and is deployed on the correct network.
- **Metadata queries**: Retrieving token metadata like symbols and decimals.

By restricting write operations, Quantum Lighthouse minimizes the risk of unintended consequences and simplifies validation processes.

---

## How It Works

Quantum Lighthouse uses a combination of standard web3 tools and Base-specific configurations to interact with the network:
1. **RPC Integration**: The tool queries the blockchain using the RPC endpoints configured in `config/base.networks.json`.
2. **Explorer Integration**: For visual verification, it links out to **BaseScan** (for both Base Mainnet and Sepolia), providing transparent access to on-chain data.
3. **Contract Interaction**: The tool interacts with deployed smart contracts using standard ABI calls to ensure the contract is deployed correctly and can return expected results (such as balance, contract code, etc.).

---

## Security Considerations

- **No transaction execution**: Quantum Lighthouse does not perform any transactions or state-changing operations, which reduces the risk of exploiting the tool.
- **Public RPC URLs**: All interactions occur via public RPC endpoints, ensuring no direct reliance on proprietary or private nodes.
- **Minimal exposure to external risks**: By focusing on read-only interactions, Quantum Lighthouse reduces the exposure to malicious attacks or errors resulting from unintended transactions.

---

## Future Considerations

1. **Transaction Simulation**:  
   While the tool currently focuses on read-only operations, future iterations might include transaction simulation to verify how transactions would behave on Base networks without actually executing them.

2. **Support for additional networks**:  
   If Base launches new testnets or mainnets, Quantum Lighthouse can be easily updated to support those by simply adding new network configurations to the `config/base.networks.json` file.

_Last updated: initial scaffold_
