# Quantum Lighthouse — Testnet Validation Record

This document serves as a record of the validation steps and results during testing on **Base Sepolia**.

---

## Network Configuration

- **Network**: Base Sepolia  
- **Chain ID**: 84532  
- **RPC URL**: [https://sepolia.base.org](https://sepolia.base.org)  
- **Explorer**: [https://sepolia.basescan.org](https://sepolia.basescan.org)

Before starting the testing process, confirm that **Base Sepolia** is set as the active network in the configuration.

---

## Validation Steps

### Step 1 — Configuration Verification

- [ ] Ensure that **chainId** is correctly set to **84532** (Base Sepolia).
- [ ] Confirm that the correct **RPC URL** is used (`https://sepolia.base.org`).
- [ ] Check that **BaseScan Sepolia** is the designated explorer URL in the configuration file.

### Step 2 — Test RPC Connectivity

- [ ] Fetch the **latest block number** from the RPC endpoint to ensure it's responsive.
- [ ] Retry fetching the block number after a brief delay and verify it increases (i.e., block number should increment).
- [ ] If RPC connectivity fails, switch to the fallback RPC URL (`https://base-sepolia-rpc.publicnode.com`) and ensure the issue is resolved.

### Step 3 — Read-only Probes

Using the sample addresses from `scripts/sample-addresses.json`, perform the following checks:

- [ ] Retrieve the **ETH balance** for `exampleEOA` and verify that it returns a valid, non-zero value.
- [ ] Verify that `exampleContract` is deployed on Base Sepolia and fetch the contract code (should return either valid bytecode or `0x`).
- [ ] Ensure that querying the **zero address** returns zero balance and querying the **burn address** does not cause errors.

### Step 4 — Explorer Verification

- [ ] Open the **exampleEOA** address in the **BaseScan Sepolia** explorer and verify it resolves to the correct page.
- [ ] Check the latest block on BaseScan Sepolia and verify it matches the block number returned by the RPC.
- [ ] Ensure **no links** are referencing **Base Mainnet** during testnet validation.

---

## Results

- [ ] All validation checks passed successfully on **Base Sepolia**.
- [ ] Ready for mainnet deployment on **Base Mainnet** after final checks.

_Last updated: initial scaffold_
