FUNTOKEN

FUN · BlackVault Public Network · Sepolia

FUNTOKEN is BlackVault Public Network’s Sepolia token project. This README introduces the deployed FunToken (FUN) contracts, their token functions, and the earlier account delegation recorded for the deploying wallet.

The project’s deployment history connects a standard token interface with an EIP-7702-enabled wallet. The contract addresses and transaction receipts below make that history publicly traceable.

Token details · Deployments · Account delegation · Milestones

Token details

Field

Value

Project

FUNTOKEN

Onchain name

FunToken

Symbol

FUN

Network

Sepolia testnet

Chain ID

11155111

Interface

ERC-20 transfer and allowance functions

Decimals

18

Initial supply

20 FUN per deployment

Recorded deployments

Three separate token contracts

Canonical Sepolia address

Pending selection

All deployments listed here are on Sepolia. Each contract maintains its own supply, balances, and spending allowances. A token’s network and full contract address identify which deployment a wallet or application is using.

Deployment register

All three creation transactions succeeded. The deployed runtime bytecode is identical across the three contracts, and each creation recorded an initial mint of 20 FUN to the deploying wallet.

Deployment

Created, UTC

Contract on Sepolia Etherscan

Creation receipt

1

9 September 2026, 11:41:48

0x4fe664a5941f1b8317b5e1a5a2e4aab5032d870a

View transaction

2

9 September 2026, 11:50:48

0xfb6b14ab39dbc1ce5b58f7bbd0442fa1838ccc30

View transaction

3

10 September 2026, 00:44:00

0xc5009a5b1e91bee6ce941552e8b9e9e9f9db6c47

View transaction

Deploying wallet and initial recipient:

0x9D00701A151A60cEC42Dd75be82c5DDE71f58DE5

Zero native ETH sent as contract-creation value is compatible with the initial FUN mint. FUN balances are recorded in each token contract’s ledger independently of the contract’s native ETH balance.

What FUN supports

The deployed interface exposes nine functions following the ERC-20 transfer and allowance model.

Capability

Functions

Read token identity and precision

name(), symbol(), decimals()

Read supply and holder balances

totalSupply(), balanceOf(address)

Transfer a holder’s FUN

transfer(address,uint256)

Set or read a spending allowance

approve(address,uint256), allowance(address,address)

Transfer using an allowance

transferFrom(address,address,uint256)

The reviewed runtime exposes no public mint, burn, pause, ownership-transfer, or upgrade function. Holding the initial supply provides the holder’s transfer and allowance permissions; it does not establish a separate token administrator role.

Publishing the matching Solidity source, ABI, and build settings is an outstanding documentation milestone.

Account delegation

On 30 August 2026, the deploying wallet authorized the following shared implementation through an EIP-7702 transaction:

MetaMask EIP7702StatelessDeleGator · version 1.3.0
0x63c0c19a282a1b52b07dd5a65b58948a07dae32b

View the earlier authorization transaction.

EIP-7702 allows an account to use code from another address while retaining its account identity and execution context. MetaMask’s implementation provides authorized execution, batching, signature validation, and permission-based wallet operations. Implementation source.

FUNTOKEN was deployed from an EIP-7702-enabled wallet. Its three creation receipts record direct, type-2 contract-creation transactions. The earlier delegation belongs to the wallet; the FUN contracts maintain their own token state and fixed deployed functions. Wallet delegation does not add minting or upgrade functions to FUN.

Recorded activity

On 12 September 2026 at 10:56:12 UTC, deployment 1 processed a successful 1 FUN self-transfer by the deploying wallet. The transaction emitted a transfer event, with no net change to that wallet’s FUN balance. View the transfer receipt and event.

Transfers between different holders and the approval-based spending workflow remain separate demonstrations to document.

Explore FUNTOKEN

Select a contract from the deployment register and open its Sepolia Etherscan page.

Review the creation receipt, token activity, and deploying wallet history.

To display a deployment in a compatible wallet, select Sepolia and import that deployment’s full contract address. The token symbol is FUN, with 18 decimals.

Use the same network and contract address consistently when comparing balances or integrating a deployment into an application.

Milestones

Record three successful Sepolia deployments and their creation receipts.

Compare deployed runtime bytecode and document the token interface.

Trace the wallet’s EIP-7702 authorization to its earlier transaction.

Document the successful self-transfer on deployment 1.

Select the canonical Sepolia FUN contract for shared project references.

Recover and publish the original source, ABI, dependencies, and compiler settings.

Complete matching source verification on Sepolia Etherscan.

Document wallet display, a transfer between holders, and allowance-based spending.

Expand the project wiki with the deployment chronology and integration examples.

Documentation snapshot: 13 September 2026, covering reviewed transaction records through 12 September 2026. Completed items describe the recorded deployment and documentation work; unchecked items identify work still to finish.

Krista Dawn
Software Engineer & Product Architect
Blackvault Public Network
