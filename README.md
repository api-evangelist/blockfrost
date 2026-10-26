# Blockfrost (blockfrost)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
