# FUNTOKEN Integration Status

**Updated:** 2026-09-18

The existing [deployment register](../README.md#deployment-register) records three separate FUN contracts on Sepolia (`11155111`). This update preserves their historical receipt references; it does not assert a new live-chain verification.

## Application identity

The shared canonical FUN contract remains pending owner selection. Keep all three historical deployment records, but activate only explicitly configured contracts in a wallet or agent. Resolve identity by chain ID plus contract address, with token decimals and metadata checked against that contract.

## SafeVault

FUN is the testnet token experience within SafeVault's primary Homebase smart-account model and optional external-wallet views. Adding FUN to an interface does not migrate an external wallet balance into Homebase. A transfer between those accounts is a separately authorized transaction.

## Vault AI

The Botpress workspace agent may use enabled Sepolia discovery tools to explain FUN balances, transfers, and deployment history. Its initial mainnet recovery workflow is a separate context. The documented FUN interface contains ERC-20 transfer/allowance methods; the history does not establish a dedicated claim or asset-rescue function.

The deploying wallet's earlier EIP-7702 delegation belongs to the wallet account. It neither turns the three FUN token contracts into three wallets nor adds new token-admin functions.

## Remaining milestones

| Item | Required completion evidence |
| --- | --- |
| Canonical FUN deployment | Owner-selected full address on Sepolia |
| Matching source | Original source/compiler input and verified matching build |
| Wallet display | Recorded wallet/version, network, and selected token |
| Between-holder transfer | Receipt and matching sender/recipient balance or event outcome |
| Allowance interaction | Confirmed approval/spend behavior for the selected token |
| External registry listing | Actual accepted registry entry and supported network |
| SafeVault integration | Implemented asset registry, interface, and successful configured reads |

[Public ecosystem](https://github.com/blackvault-opps/Blackvault-Public-Network-repo) · [SafeVault](https://github.com/blackvault-opps/SafeVault_deploy-repo) · [Vault AI](https://github.com/blackvault-opps/Vault-AI-Extension-Public-Deployment-Repo)
