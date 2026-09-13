# FUNTOKEN — Deployment and Delegated Account Architecture

**BlackVault Public Network · Prepared 13 September 2026 · Records through 12 September**

FUNTOKEN is documented on Sepolia through three successful deployments of **FunToken (FUN)**. Each contract began with 20 FUN, uses 18 decimal places, and contains the same deployed runtime code. Each address represents a separate token contract.

The deploying wallet had already enabled MetaMask’s EIP-7702 account implementation. The distinctive part of this history is the relationship between that smart-account capability and the wallet’s later, direct token deployments.

## Token identity

| Field | Recorded value |
| --- | --- |
| Public project name | FUNTOKEN |
| Onchain token name | FunToken |
| Symbol | FUN |
| Network | Sepolia |
| Chain ID | 11155111 |
| Decimals | 18 |
| Initial supply | 20 FUN per contract |
| Initial recipient and deployment sender | `0x9D00701A151A60cEC42Dd75be82c5DDE71f58DE5` |
| Number of recorded token deployments | Three |
| Canonical deployment designation | To be selected |
| Token source verification | Original source and compiler settings remain to be matched and published |

The address and chain ID identify a token independently of its name or symbol. The three balances are tracked independently; they do not form a single 60-FUN contract.

## Deployment register

### Deployment 1

| Field | Value |
| --- | --- |
| Contract | `0x4fe664a5941f1b8317b5e1a5a2e4aab5032d870a` |
| Transaction | `0xfaa114d14e4553adfd500caae0cc29abf18b6ff2990f57fc524bc3a679e3b144` |
| Timestamp | 9 September 2026, 11:41:48 UTC |
| Block | 11,667,722 |
| Sender nonce | 10 |
| Initial mint | 20 FUN |
| Deployment fee | 0.002392135663481388 Sepolia ETH |

[Contract and deployed code](https://sepolia.etherscan.io/address/0x4fe664a5941f1b8317b5e1a5a2e4aab5032d870a#code) · [Deployment receipt](https://sepolia.etherscan.io/tx/0xfaa114d14e4553adfd500caae0cc29abf18b6ff2990f57fc524bc3a679e3b144)

### Deployment 2

| Field | Value |
| --- | --- |
| Contract | `0xfb6b14ab39dbc1ce5b58f7bbd0442fa1838ccc30` |
| Transaction | `0xe2cf645347a126b412e09cb7fa9e1f9f99dfe27db09c10fc09477c78c2bbf395` |
| Timestamp | 9 September 2026, 11:50:48 UTC |
| Block | 11,667,766 |
| Sender nonce | 11 |
| Initial mint | 20 FUN |
| Deployment fee | 0.002367373267965222 Sepolia ETH |

[Contract and deployed code](https://sepolia.etherscan.io/address/0xfb6b14ab39dbc1ce5b58f7bbd0442fa1838ccc30#code) · [Deployment receipt](https://sepolia.etherscan.io/tx/0xe2cf645347a126b412e09cb7fa9e1f9f99dfe27db09c10fc09477c78c2bbf395)

### Deployment 3

| Field | Value |
| --- | --- |
| Contract | `0xc5009a5b1e91bee6ce941552e8b9e9e9f9db6c47` |
| Transaction | `0x65d6686b522105232602fe7b3d242522bb47a0ed991938220dfa1842225e56db` |
| Timestamp | 10 September 2026, 00:44:00 UTC |
| Block | 11,671,519 |
| Sender nonce | 12 |
| Initial mint | 20 FUN |
| Deployment fee | 0.002515923210697314 Sepolia ETH |

[Contract and deployed code](https://sepolia.etherscan.io/address/0xc5009a5b1e91bee6ce941552e8b9e9e9f9db6c47#code) · [Deployment receipt](https://sepolia.etherscan.io/tx/0x65d6686b522105232602fe7b3d242522bb47a0ed991938220dfa1842225e56db)

All three receipts record successful **type-2, EIP-1559** transactions. Each used **939,774 gas**, from a limit of 948,400, and sent zero native ETH as contract-creation value. The combined deployment fees were **0.007275432142143924 Sepolia ETH**.

## Code comparison

The runtime bytecode retrieved from the three contract pages is identical, including its metadata. Each runtime is **3,554 bytes** long. Its SHA-256 digest, calculated over the decoded bytecode bytes, is:

`4f263d8e18d84b27961a38f64f506809909118222a953786a5851b499e0cf8fa`

The metadata indicates Solidity **0.8.34**. This identifies a compiler version to reconcile with the original build files; it does not supply all compilation settings.

The code comparison establishes three matching token implementations. Their separate contract storage preserves separate balances and allowances. All three creation receipts record a mint, and the wallet’s explorer holdings list includes 20 FUN for each address. [Deploying wallet](https://sepolia.etherscan.io/address/0x9d00701a151a60cec42dd75be82c5dde71f58de5).

## Token functions

The dispatch table in each deployed runtime exposes these nine functions:

| Function | Selector | Purpose |
| --- | --- | --- |
| `name()` | `0x06fdde03` | Read the token name. |
| `symbol()` | `0x95d89b41` | Read the token symbol. |
| `decimals()` | `0x313ce567` | Read the display precision, 18. |
| `totalSupply()` | `0x18160ddd` | Read the token supply. |
| `balanceOf(address)` | `0x70a08231` | Read a holder’s balance. |
| `allowance(address,address)` | `0xdd62ed3e` | Read an approved spending allowance. |
| `transfer(address,uint256)` | `0xa9059cbb` | Transfer the caller’s tokens. |
| `approve(address,uint256)` | `0x095ea7b3` | Set a spender’s allowance. |
| `transferFrom(address,address,uint256)` | `0x23b872dd` | Transfer tokens using the applicable allowance. |

The interface follows the familiar ERC-20 transfer and allowance model. [ERC-20 specification](https://eips.ethereum.org/EIPS/eip-20).

The deployed interface provides **no public mint, burn, pause, blacklist, confiscation, ownership-transfer, permit, or upgrade function**. Inspection of the runtime also found no external-call or delegatecall opcode path. Creating these contracts and receiving their initial supply does not provide a separate token administrator role.

The holder can transfer FUN and manage its spending allowances. Token metadata and the deployed feature set are fixed in these deployments. Wallet interface labels can be changed independently of the onchain token name.

## The earlier EIP-7702 authorization

On **30 August 2026 at 14:31:36 UTC**, transaction

`0x5791ec8e43180b66d70ae3c9e05ac60355f2de9afff00a4675aa7f8ad8a5c9ed`

recorded a **type-4 EIP-7702 transaction** authorizing the deploying wallet to use this implementation:

`0x63c0c19a282a1b52b07dd5a65b58948a07dae32b`

The same transaction also created a Safe wallet through the delegation execution flow. This establishes that the delegation relationship existed before all three FUN deployments. [Authorization and execution receipt](https://sepolia.etherscan.io/tx/0x5791ec8e43180b66d70ae3c9e05ac60355f2de9afff00a4675aa7f8ad8a5c9ed).

| Component | Address | Role |
| --- | --- | --- |
| Deploying wallet / authority | `0x9d00701a151a60cec42dd75be82c5dde71f58de5` | Holds the initial FUN balances and originates the token deployments. |
| EIP-7702 implementation | `0x63c0c19a282a1b52b07dd5a65b58948a07dae32b` | Supplies the wallet’s smart-account execution code. |
| DelegationManager | `0xdb9b1e94b5b69df7e401ddbede43491141047db3` | Processes permissions and authorized execution through the framework. |
| FUN contracts | The three addresses in the deployment register | Maintain token supply, balances, and allowances. |

Etherscan identifies the shared implementation as **EIP7702StatelessDeleGator**, version **1.3.0**, with verified source. Its two principal source files match MetaMask’s published v1.3.0 files. [Implementation source](https://sepolia.etherscan.io/address/0x63c0c19a282a1b52b07dd5a65b58948a07dae32b#code), [MetaMask v1.3.0 account core](https://github.com/MetaMask/delegation-framework/blob/v1.3.0/src/EIP7702/EIP7702DeleGatorCore.sol).

## What the wallet architecture enables

EIP-7702 lets an existing account use code from another address while retaining its own account identity and execution context. MetaMask’s implementation supports authorized single and batched calls, contract signature validation, ERC-4337 operations, and permission-based execution. Sponsorship can be supported by suitable accompanying infrastructure; the token deployment receipts in this record show native gas fees paid by the sender. [EIP-7702](https://eips.ethereum.org/EIPS/eip-7702), [MetaMask account architecture](https://github.com/MetaMask/delegation-framework/blob/main/documents/EIP7702DeleGator.md).

| Capability | How it applies |
| --- | --- |
| Execute wallet operations | Supported through the implementation’s authorized execution paths. |
| Combine calls into a batch | Supported for compatible execution modes. |
| Validate account signatures | The stateless implementation checks the signer against the account executing its code. |
| Manage a permission delegation | The account can enable or disable a particular delegation through the authorized framework path. |
| Use an EntryPoint deposit | Deposit and withdrawal functions concern the executing account’s own EntryPoint balance. |
| Change the wallet’s code delegation | A separate valid EIP-7702 authorization can replace or clear the account’s delegation. |

These are **wallet capabilities**. They do not add functions to the existing FUN contracts or convey control over the shared implementation’s assets. The shared contract address and the wallet address have separate balances and state. Reads that depend on the account’s context should be directed to the delegated wallet with the appropriate interface. [Verified implementation](https://sepolia.etherscan.io/address/0x63c0c19a282a1b52b07dd5a65b58948a07dae32b#code).

## Recorded transfer after deployment

On **12 September 2026 at 10:56:12 UTC**, the first deployment processed a successful transfer of **1 FUN from the deployment wallet back to itself**.

| Field | Value |
| --- | --- |
| Transaction | `0x2ccc2ea1f70a3e4b267a9da6b572c9233b724beea334acaa8c8fcd9daa6312d4` |
| Block | 11,688,467 |
| Contract | First deployment, `0x4fe6…d870a` |
| Amount | 1 FUN |
| Net token balance change | Zero |
| Transaction fee | 0.00006900989995116 Sepolia ETH |

This is evidence of a successful transfer call and emitted transfer event. A transfer to another holder and the allowance workflow remain separate integration demonstrations. [Transfer receipt and log](https://sepolia.etherscan.io/tx/0x2ccc2ea1f70a3e4b267a9da6b572c9233b724beea334acaa8c8fcd9daa6312d4#eventlog).

## Reading the explorer record

- **A mint from the zero address** records token creation. The initial FUN was credited to the deployment wallet.
- **Zero ETH creation value** means the transaction did not endow the new contract with native ETH. It does not indicate zero token supply.
- **A zero native balance at the token address** is compatible with a working ERC-20 ledger.
- **Burnt fees** describe the transaction’s native base fee. They do not represent a FUN token burn.
- **Storage slots** are locations inside contract state, rather than receiving wallets. The raw amount `20000000000000000000`, with 18 decimals, represents 20 FUN.
- **Nonce and block position** describe transaction ordering, rather than token quantity or special contract status.
- **Matching bytecode** establishes matching deployed code; publishing matching source is a separate documentation step.

## Documentation objectives

1. Select the canonical Sepolia FUN address for website, wallet, and wiki references.
2. Recover the original FunToken source, compiler input, dependency versions, and compilation settings.
3. Complete exact source verification for the selected contract and correlate the other matching deployments.
4. Document wallet display, an ordinary transfer between holders, and allowance-based interaction when those demonstrations are completed.
5. Maintain the distinction between FUNTOKEN’s Sepolia record and Vault Coin’s Ethereum mainnet production objective.

**Krista Dawn**  
Software Engineer & Product Architect  
Blackvault Public Network
