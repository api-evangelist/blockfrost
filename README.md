# Blockfrost (blockfrost)
Blockfrost is a RESTful API service providing access to the Cardano blockchain and its ecosystem. It serves as an infrastructure layer for developers building dApps, wallets, NFT platforms, DeFi protocols, and analytics tools on Cardano. Blockfrost provides endpoints for querying blocks, transactions, accounts, addresses, native assets, epochs, governance data, and IPFS storage, supporting both mainnet and testnet networks.

**URL:** [https://blockfrost.io](https://blockfrost.io)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags:

 - Blockchain, Cardano, Cryptocurrency, DApps, NFT, Web3

## Timestamps

- **Created:** 2024-09-27
- **Modified:** 2026-04-19

## APIs

### Blockfrost API
RESTful API for interacting with the Cardano blockchain and parts of its ecosystem. Provides access to blocks, transactions, accounts, addresses, native assets, epochs, governance data, and IPFS. Requires a project_id obtained from blockfrost.io for authentication. Supports Cardano mainnet, preview testnet, preprod testnet, and Midnight mainnet networks.

**Human URL:** [https://blockfrost.io/](https://blockfrost.io/)

#### Tags:

 - Blockchain, Cardano, Cryptocurrency, Web3

#### Properties

- [Documentation](https://docs.blockfrost.io/)
- [OpenAPI](openapi/blockfrost-openapi.yaml)
- [NaftikoCapability](capabilities/blockfrost-cardano-explorer.yaml)
- [SpectralRules](rules/blockfrost-spectral-rules.yml)
- [Vocabulary](vocabulary/blockfrost-vocabulary.yaml)

## Common Properties

- [Website](https://blockfrost.io/)
- [Documentation](https://blockfrost.dev/)
- [Getting Started](https://blockfrost.dev/overview/getting-started)
- [Pricing](https://blockfrost.io/#pricing)
- [Status Page](https://status.blockfrost.io/)
- [Support](https://blockfrost.dev/support)
- [GitHub Organization](https://github.com/blockfrost)
- [Discord](https://discord.gg/inputoutput)
- [Terms of Service](https://blockfrost.io/terms)
- [Privacy Policy](https://blockfrost.io/privacy)
- [Login](https://blockfrost.io/auth/signin)
- [Official SDKs](https://blockfrost.dev/sdks)

## Features

| Name | Description |
|------|-------------|
| Cardano Blockchain Access | Query blocks, transactions, slots, epochs, accounts, and addresses on the Cardano mainnet and testnet networks. |
| Native Asset Support | Full support for Cardano native assets including fungible tokens, NFTs, and multi-asset UTXOs with on-chain metadata (CIP-25, CIP-68). |
| Stake Pool and Delegation Data | Query stake pool information, delegation history, rewards, and account activity for Cardano staking workflows. |
| Governance Data | Access Cardano governance data including proposals, DRep registrations, and voting activity introduced in the Conway era. |
| IPFS Integration | Built-in IPFS API for storing and retrieving off-chain NFT metadata and other content via Blockfrost's IPFS gateway. |
| Multi-Network Support | Single API surface covering Cardano mainnet, preview testnet, preprod testnet, and the Midnight blockchain. |
| Transaction Submission | Submit signed transactions directly to the Cardano network via the Blockfrost API without running a local node. |

## Use Cases

| Name | Description |
|------|-------------|
| dApp Development | Developers build Cardano dApps using Blockfrost to query blockchain state, submit transactions, and interact with smart contracts. |
| NFT Platform Integration | NFT marketplaces and minting platforms use Blockfrost to track asset minting, transfers, and metadata across the Cardano network. |
| DeFi Protocol Building | DeFi protocols integrate Blockfrost to monitor liquidity pool states, track DEX transactions, and manage smart contract interactions. |
| Wallet Development | Cardano wallet applications use Blockfrost to fetch UTXOs, balances, transaction history, and submit transactions. |
| Blockchain Analytics | Analytics platforms query Blockfrost for on-chain data including block history, epoch statistics, and network activity metrics. |

## Integrations

| Name | Description |
|------|-------------|
| Mesh SDK | The Mesh JavaScript/TypeScript SDK integrates with Blockfrost as a provider for Cardano dApp development. |
| Lucid Evolution | Lucid Evolution (TypeScript library) supports Blockfrost as a blockchain provider for transaction building and submission. |
| PyCardano | PyCardano Python library uses Blockfrost as a chain context provider for Cardano smart contract development. |
| Cardano Serialization Library | The Cardano Serialization Library (CSL) pairs with Blockfrost for transaction construction and UTXO management. |

## Artifacts

Machine-readable API specifications organized by format.

### OpenAPI

- [Blockfrost API](openapi/blockfrost-openapi.yaml)

### JSON Schema

- [block_content](json-schema/blockfrost--block-content-schema.json)
- [transaction_content](json-schema/blockfrost--transaction-content-schema.json)
- See json-schema/ for all 20 schema files

### JSON Structure

- See json-structure/ for all 20 JSON Structure files

### JSON-LD

- [Blockfrost Context](json-ld/blockfrost-context.jsonld)

### Examples

- See examples/ for all 20 example files

## Capabilities

Naftiko capabilities organized as shared per-API definitions composed into customer-facing workflows.

### Shared Per-API Definitions

- [Blockfrost API](capabilities/shared/blockfrost-api.yaml) — 8 operations for blocks, transactions, accounts, addresses, assets, epochs, and transaction submission

### Workflow Capabilities

| Workflow | APIs Combined | Tools | Persona |
|----------|--------------|-------|---------|
| [Blockfrost Cardano Explorer](capabilities/blockfrost-cardano-explorer.yaml) | Blockfrost API | 8 | dApp Developers, Blockchain Analysts, NFT Creators, DeFi Users |

## Vocabulary

- [Blockfrost Vocabulary](vocabulary/blockfrost-vocabulary.yaml) — Unified taxonomy mapping 7 resources, 3 actions, 1 workflow, and 4 personas across operational (OpenAPI) and capability (Naftiko) dimensions

## Rules

- [Blockfrost Spectral Rules](rules/blockfrost-spectral-rules.yml) — 29 rules across 12 categories enforcing Blockfrost API conventions

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
