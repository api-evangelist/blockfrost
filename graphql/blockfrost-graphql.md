# Blockfrost GraphQL Schema

## Overview

This is a conceptual GraphQL schema for the [Blockfrost API](https://docs.blockfrost.io/), a RESTful infrastructure service that provides access to the Cardano blockchain and its ecosystem. Blockfrost exposes endpoints for querying blocks, transactions, epochs, accounts, addresses, native assets, governance data, scripts, and IPFS storage across Cardano mainnet, preview testnet, preprod testnet, and Midnight mainnet.

The schema in `blockfrost-schema.graphql` is a design artifact — it maps the REST surface of the Blockfrost API onto a typed GraphQL vocabulary. It is intended for tooling, documentation, and discovery purposes rather than as a live endpoint.

## Source API

- **Provider:** Blockfrost
- **Base documentation:** https://docs.blockfrost.io/
- **Authentication:** `project_id` header (API key obtained from https://blockfrost.io)
- **Networks supported:** Cardano mainnet, preprod testnet, preview testnet, Midnight mainnet

## Schema Coverage

The schema is organised into the following domain areas:

### Network

Types `Network`, `NetworkDetails`, `NetworkSummary`, `NetworkStakeSummary`, `NetworkSupplySummary` cover the `/api/v0/network` endpoints, giving callers access to genesis hash, network magic, supply figures, and live/active stake totals.

### Blocks

Types `Block`, `BlockDetails` and scalars `BlockHash`, `SlotNumber`, `SlotInEpoch` map to the `/api/v0/blocks` family of endpoints. `BlockDetails` includes previous/next block references, VRF keys, and the block's transaction list.

### Epochs

Types `Epoch`, `EpochDetails`, `EpochParameter` cover `/api/v0/epochs` and `/api/v0/epochs/latest/parameters`. `EpochParameter` encodes the full set of protocol parameters in force during an epoch, including Plutus execution prices and collateral settings introduced in the Alonzo era.

### Transactions

Types `Transaction`, `TransactionDetails`, `TransactionType`, `TransactionInput`, `TransactionOutput`, `TransactionMetadata`, `TransactionMIR`, `TransactionPoolCert`, `TransactionDelegation` map to the `/api/v0/txs` endpoint family, covering inputs, outputs, metadata labels, MIR certificates, pool certificates, and delegation certificates.

### UTxOs

Types `UTxO`, `UTxODetails`, `UTxOAmount` represent the unspent transaction output model that underpins the Cardano ledger. These underpin address and transaction queries.

### Addresses

Types `Address`, `AddressDetails`, `AddressAmount`, `AddressUTxO`, `AddressTransaction` map to the `/api/v0/addresses` endpoints, including UTxO listings, total balances, and full transaction history per address.

### Assets

Types `Asset`, `AssetDetails`, `AssetPolicy`, `AssetOnchainMetadata`, `AssetHistory` and scalars `PolicyId`, `AssetFingerprint` cover the `/api/v0/assets` endpoints. `AssetOnchainMetadata` reflects CIP-25 and CIP-68 on-chain NFT metadata.

### Staking

Types `StakeAddress`, `StakeDetails`, `Stake`, `StakeDistribution`, `Delegation`, `Rewards` map to the `/api/v0/accounts` endpoints, covering stake address balances, delegation history, reward history, and controlled addresses.

### Stake Pools

Types `StakePool`, `PoolDetails`, `PoolMetadata`, `PoolStatus`, `PoolBlock` cover the `/api/v0/pools` endpoints, including live and active stake, saturation, fixed and margin costs, and per-pool block history.

### Governance

Types `Governance`, `DRep`, `DRepDetails`, `DRepStatus`, `Proposal` map to the Conway-era governance endpoints under `/api/v0/governance`, including DRep registrations, vote tallies, and governance action proposals.

### Scripts

Types `Script`, `ScriptDetails`, `ScriptType`, `ScriptHash`, `DatumDetails` cover the `/api/v0/scripts` endpoints for native scripts and Plutus (v1/v2/v3) scripts, including serialised CBOR and JSON representations.

### Protocol

Type `Protocol` wraps `EpochParameter` for the current epoch, reflecting the current `/api/v0/epochs/latest/parameters` response.

### IPFS

Types `IPFSPin`, `IPFSObject`, `IPFSPinState` cover the Blockfrost IPFS API under `/api/v0/ipfs`, supporting pin management and object retrieval via the Blockfrost IPFS gateway.

### Auth / API Keys

Types `APIKey` and `Token` represent Blockfrost project credentials and their associated network scope.

## Type Summary

| Domain | Types |
|---|---|
| Network | Network, NetworkDetails, NetworkSummary, NetworkStakeSummary, NetworkSupplySummary |
| Blocks | Block, BlockDetails, BlockHash, SlotNumber, SlotInEpoch |
| Epochs | Epoch, EpochDetails, EpochParameter |
| Transactions | Transaction, TransactionDetails, TransactionType, TransactionInput, TransactionOutput, TransactionMetadata, TransactionMIR, TransactionPoolCert, TransactionDelegation |
| UTxOs | UTxO, UTxODetails, UTxOAmount |
| Addresses | Address, AddressDetails, AddressAmount, AddressUTxO, AddressTransaction |
| Assets | Asset, AssetDetails, AssetPolicy, PolicyId, AssetFingerprint, AssetOnchainMetadata, AssetHistory |
| Staking | Stake, StakeAddress, StakeDetails, StakeDistribution, Delegation, Rewards |
| Stake Pools | StakePool, PoolDetails, PoolMetadata, PoolStatus, PoolBlock |
| Governance | Governance, DRep, DRepDetails, DRepStatus, Proposal |
| Scripts | Script, ScriptDetails, ScriptType, ScriptHash, DatumDetails |
| Protocol | Protocol, EpochParameter (shared) |
| IPFS | IPFSPin, IPFSObject, IPFSPinState |
| Auth | APIKey, Token |

## Example Queries

### Fetch the latest block

```graphql
query {
  latestBlock {
    hash
    height
    slot
    epoch
    txCount
    time
    fees
    output
  }
}
```

### Fetch an address with UTxOs

```graphql
query {
  address(address: "addr1qx...") {
    address
    stakeAddress
    amount {
      unit
      quantity
    }
    utxos {
      txHash
      outputIndex
      amount {
        unit
        quantity
      }
    }
  }
}
```

### Fetch an NFT asset

```graphql
query {
  asset(asset: "d5e6bf0500378d4f0da4e8dde6becec7621cd8cbf5cbb9b87013d4cc537061636542756473") {
    policyId
    assetName
    fingerprint
    quantity
    onchainMetadata {
      name
      image
      description
    }
  }
}
```

### Fetch a stake account

```graphql
query {
  stakeAddress(stakeAddress: "stake1u9ylzsgxaa6xctf4juup682ar3juj85n8tx3hthnljg47zctvm3rc") {
    active
    controlledAmount
    rewardsSum
    withdrawableAmount
    poolId
    delegations {
      activeEpoch
      poolId
      amount
    }
    rewards {
      epoch
      amount
      type
    }
  }
}
```

### Submit a transaction

```graphql
mutation {
  submitTransaction(cbor: "84a500...") 
}
```

## Files

- `blockfrost-schema.graphql` — Full GraphQL schema definition (SDL)
- `blockfrost-graphql.md` — This documentation file
