<div align="center">

<h1>FUNTOKEN</h1>

<p><strong>FUN · BlackVault Public Network</strong></p>

<p>Sepolia token deployments · ERC-20 functionality · EIP-7702 account history</p>

</div>

---

## Welcome to FUNTOKEN

**FUNTOKEN** is BlackVault Public Network’s Sepolia token project.

Its public documentation brings together the deployed **FunToken (FUN)** contracts, their token functions, and the earlier account delegation recorded for the deploying wallet.

The deployment history connects a standard token interface with an **EIP-7702-enabled wallet**. Every deployment listed below includes its contract address and transaction receipt so readers can explore the onchain record directly.

**Explore:** [Token details](#token-details) · [Deployments](#deployment-register) · [Token functions](#what-fun-supports) · [Account delegation](#account-delegation) · [Milestones](#project-milestones)

---

## Token details

| Property | Recorded value |
| :--- | :--- |
| **Project** | FUNTOKEN |
| **Onchain name** | FunToken |
| **Symbol** | FUN |
| **Network** | Sepolia testnet |
| **Chain ID** | `11155111` |
| **Interface** | ERC-20 transfer and allowance functions |
| **Decimals** | 18 |
| **Initial supply** | 20 FUN per deployment |
| **Recorded deployments** | Three separate token contracts |
| **Canonical Sepolia address** | Pending selection |

Each contract maintains its own supply, balances, and spending allowances. The network and full contract address identify which deployment a wallet or application is using.

---

## Deployment register

Three successful contract deployments were recorded on **Sepolia**.

All three contain identical deployed runtime bytecode. Each creation recorded an initial mint of **20 FUN** to the deploying wallet.

### Deployment 1

| Detail | Record |
| :--- | :--- |
| **Contract address** | `0x4fe664a5941f1b8317b5e1a5a2e4aab5032d870a` |
| **Deployment date** | 9 September 2026 |
| **Time** | 11:41:48 UTC |
| **Initial supply** | 20 FUN |

[View contract](https://sepolia.etherscan.io/address/0x4fe664a5941f1b8317b5e1a5a2e4aab5032d870a#code) · [View deployment transaction](https://sepolia.etherscan.io/tx/0xfaa114d14e4553adfd500caae0cc29abf18b6ff2990f57fc524bc3a679e3b144)

### Deployment 2

| Detail | Record |
| :--- | :--- |
| **Contract address** | `0xfb6b14ab39dbc1ce5b58f7bbd0442fa1838ccc30` |
| **Deployment date** | 9 September 2026 |
| **Time** | 11:50:48 UTC |
| **Initial supply** | 20 FUN |

[View contract](https://sepolia.etherscan.io/address/0xfb6b14ab39dbc1ce5b58f7bbd0442fa1838ccc30#code) · [View deployment transaction](https://sepolia.etherscan.io/tx/0xe2cf645347a126b412e09cb7fa9e1f9f99dfe27db09c10fc09477c78c2bbf395)

### Deployment 3

| Detail | Record |
| :--- | :--- |
| **Contract address** | `0xc5009a5b1e91bee6ce941552e8b9e9e9f9db6c47` |
| **Deployment date** | 10 September 2026 |
| **Time** | 00:44:00 UTC |
| **Initial supply** | 20 FUN |

[View contract](https://sepolia.etherscan.io/address/0xc5009a5b1e91bee6ce941552e8b9e9e9f9db6c47#code) · [View deployment transaction](https://sepolia.etherscan.io/tx/0x65d6686b522105232602fe7b3d242522bb47a0ed991938220dfa1842225e56db)

### Deploying wallet

The same wallet originated all three deployments and received each initial supply:

**`0x9D00701A151A60cEC42Dd75be82c5DDE71f58DE5`**

[Explore the deploying wallet](https://sepolia.etherscan.io/address/0x9d00701a151a60cec42dd75be82c5dde71f58de5)

FUN balances are recorded in each token contract’s ledger independently of the contract’s native ETH balance. A creation transaction showing **0 ETH transferred** can still create the contract and mint its initial FUN supply.

---

## What FUN supports

The reviewed deployed interface exposes nine functions following the [ERC-20 transfer and allowance model](https://eips.ethereum.org/EIPS/eip-20).

| Capability | Available functions |
| :--- | :--- |
| **Read token identity** | `name()`, `symbol()` |
| **Read display precision** | `decimals()` |
| **Read token supply** | `totalSupply()` |
| **Check a holder’s balance** | `balanceOf(address)` |
| **Transfer FUN** | `transfer(address,uint256)` |
| **Set a spending allowance** | `approve(address,uint256)` |
| **Check an allowance** | `allowance(address,address)` |
| **Transfer using an allowance** | `transferFrom(address,address,uint256)` |

The deployed feature set is fixed. The reviewed runtime exposes no public mint, burn, pause, ownership-transfer, or upgrade function.

Holding the initial supply provides the holder’s transfer and allowance permissions. It does not establish a separate token administrator role.

Publishing the matching Solidity source, ABI, and build settings remains a documentation milestone.

---

## Account delegation

### An earlier step in the deployment history

On **30 August 2026**, the deploying wallet authorized a shared MetaMask implementation through an EIP-7702 transaction.

| Component | Identification |
| :--- | :--- |
| **Implementation** | MetaMask `EIP7702StatelessDeleGator` |
| **Version** | 1.3.0 |
| **Implementation address** | `0x63c0c19a282a1b52b07dd5a65b58948a07dae32b` |

[View verified implementation](https://sepolia.etherscan.io/address/0x63c0c19a282a1b52b07dd5a65b58948a07dae32b#code) · [View authorization transaction](https://sepolia.etherscan.io/tx/0x5791ec8e43180b66d70ae3c9e05ac60355f2de9afff00a4675aa7f8ad8a5c9ed)

### How the relationship works

[EIP-7702](https://eips.ethereum.org/EIPS/eip-7702) allows an account to use code from another address while retaining its account identity and execution context.

MetaMask’s implementation supports authorized execution, batching, signature validation, and permission-based wallet operations. These capabilities belong to the wallet’s account architecture. [Read the implementation source](https://github.com/MetaMask/delegation-framework/blob/v1.3.0/src/EIP7702/EIP7702DeleGatorCore.sol).

**FUNTOKEN was deployed from an EIP-7702-enabled wallet.**

The three token creation receipts record direct, type-2 contract-creation transactions. The wallet’s earlier delegation and its later token deployments are distinct records.

The FUN contracts maintain their own token state and deployed functions. Wallet delegation does not add minting or upgrade functions to FUN.

---

## Recorded activity

### Successful transfer call

On **12 September 2026 at 10:56:12 UTC**, deployment 1 processed a successful **1 FUN self-transfer** by the deploying wallet.

| Detail | Result |
| :--- | :--- |
| **Deployment** | Deployment 1 |
| **Amount** | 1 FUN |
| **Sender and recipient** | Deploying wallet |
| **Transaction result** | Successful |
| **Transfer event** | Recorded |
| **Net wallet FUN balance change** | Zero |

[View the transfer receipt and event](https://sepolia.etherscan.io/tx/0x2ccc2ea1f70a3e4b267a9da6b572c9233b724beea334acaa8c8fcd9daa6312d4#eventlog)

Transfers between different holders and the approval-based spending workflow remain separate demonstrations to document.

---

## Explore FUNTOKEN

1. **Choose a deployment.** Open a contract from the deployment register.
2. **Explore its history.** Review the creation receipt, token activity, and deploying wallet.
3. **Display FUN in a compatible wallet.** Select Sepolia and import the chosen contract address. The symbol is **FUN**, with **18 decimals**.
4. **Keep the deployment consistent.** Use the same network and contract address when comparing balances or connecting an application.

---

## Project milestones

### Recorded and documented

- [x] Three successful Sepolia deployments.
- [x] Creation receipts and initial mint records.
- [x] Matching deployed runtime bytecode.
- [x] Token transfer and allowance interface.
- [x] Earlier EIP-7702 wallet authorization.
- [x] Successful self-transfer on deployment 1.

### Next steps

- [ ] Select the canonical Sepolia FUN contract for shared project references.
- [ ] Recover and publish the original source, ABI, dependencies, and compiler settings.
- [ ] Complete matching source verification on Sepolia Etherscan.
- [ ] Document wallet display and a transfer between holders.
- [ ] Document approval-based spending.
- [ ] Expand the project wiki with the deployment chronology and integration examples.

---

**Documentation snapshot:** 13 September 2026  
**Transaction records covered:** Through 12 September 2026

**Krista Dawn**  
Software Engineer & Product Architect  
Blackvault Public Network
