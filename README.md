# Quantum Lighthouse (Built for Base)

Quantum Lighthouse is a super handy, read-only tool built for Base Mainnet and Base Sepolia. It helps you validate network connections, explore blockchain data, and check out deployed contracts using Coinbase Wallet SDK, all while making sure everything checks out with Basescan.

---

## What It Can Do

- **Easy Wallet Connection** using **Coinbase Wallet SDK** (EIP-1193)  
- **ChainId Validation** for both Base Mainnet (8453) and Sepolia (84532)  
- **Block Snapshot** to pull in details like block height, gas price, and usage  
- **Address Check** to see balances, transaction history, and bytecode presence  
- **ERC-20 Token Inspection** to view token details like total supply, balance, and metadata  
- **Basescan Verification** to independently confirm contract and address info  

---

## How Everything's Organized

- **app/quantum-lighthouse.ts**  
  The main script that connects to Coinbase Wallet and queries Base RPC for data.
  
- **docs/architecture.md**  
  A breakdown of how the tool works and how it connects to Base, focusing on the read-only design.

- **docs/testnet-validation.md**  
  A record of how everything was tested on Base Sepolia.

- **contracts/**  
  Solidity contracts deployed on Base Sepolia to test everything out:
  - `Minimaltoken.sol` — implements the basic features of a token: tracking balances, allowing transfers, and managing total supply
  - `imports.sol` — uses the import keyword to bring in external Solidity files (contracts, libraries, or interfaces)

- **package.json**  
  All the dependencies for the project, including references to Coinbase and Base libraries.

- **README.md**  
  This document that explains everything you need to know.

---

## Supported Networks

- **Base Sepolia**  
  ChainId (decimal): 84532  
  Explorer: [sepolia.basescan.org](https://sepolia.basescan.org)

- **Base Mainnet**  
  ChainId (decimal): 8453  
  Explorer: [basescan.org](https://basescan.org)

---

## What It Does

Quantum Lighthouse is here to help you validate and inspect everything in the Base ecosystem. Here's what it can do:
- Connect to Coinbase Wallet through **Coinbase Wallet SDK**  
- Query **Base RPC** for data like block info, gas prices, and balances  
- Check addresses and contracts with **Basescan** verification  
- All actions are completely read-only, so no data gets written to the blockchain!

---

## Tools and Dependencies

Here are the main tools we’re using:
- **Coinbase Wallet SDK** for easy wallet access  
- **OnchainKit** for interacting with Base’s native features  
- **Viem** for fast and type-safe RPC communication with Base  
- Additional references from **Base** and **Coinbase GitHub repositories**

---

## License

MIT License

Copyright (c) 2025 YOUR_NAME

---

## Author Info

GitHub: [https://github.com/lad-sharper](https://github.com/lad-sharper)  

Email: lad.sharper.0j@icloud.com

My twitter: [https://x.com/daniell93273247](https://x.com/daniell93273247)  

---

## Testnet Deployment on Base Sepolia

To make sure everything works as expected, the following contracts have been deployed to Base Sepolia for testing:

**Network**: Base Sepolia  
**ChainId (decimal)**: 84532  
**Explorer**: [sepolia.basescan.org](https://sepolia.basescan.org)

**Contract Minimaltoken.sol address**:  
0xc0196c3781b3440C6b1095eA354FC8523E22b4E8

Deployment and verification:
- [Deployment link](https://sepolia.basescan.org/address/0xc0196c3781b3440C6b1095eA354FC8523E22b4E8)
- [Code verification](https://sepolia.basescan.org/0xc0196c3781b3440C6b1095eA354FC8523E22b4E8/0#code)

**Contract imports.sol address**:  
0x27816460F6377C218141d40b4270EF96b8F79A2D 

Deployment and verification:
- [Deployment link](https://sepolia.basescan.org/address/0x27816460F6377C218141d40b4270EF96b8F79A2D)
- [Code verification](https://sepolia.basescan.org/0x27816460F6377C218141d40b4270EF96b8F79A2D/0#code)

These deployments are used to confirm that the Base tools and network work as expected before moving to Mainnet.
