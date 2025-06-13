Building the ZEAM code under license from ZEAM Foundation LLC: https://github.com/zeam-foundation

# ZEAM Implementor's Guide: Streaming LLM from IPFS via WASM

This document outlines how to implement and run a ZEAM-based cognition system that executes LLM inference from IPFS shards in WASM — without disk storage, centralized models, or generative shortcuts.

---

## Directory Structure

zeam/
├── main.go
├── app.go
├── lifecycle.go
├── utils.go
├── types.go
├── vault.go (to be implemented)
├── wasm/
│ ├── model_runner.wasm # compiled WASM model
│ └── model_runner/ # Rust source (Cargo.toml, lib.rs)
├── llm/
│ └── gguf-shard-*.bin # IPFS-pinned model shards
├── PresenceShell/
│ └── PresenceShell.jsx # UI frontend for interaction

---

## Requirements

- Go 1.20+
- IPFS daemon running locally (`ipfs daemon`)
- WASM runtime: [`wazero`](https://github.com/tetratelabs/wazero)
- Compiled `.wasm` file using `wasm32-unknown-unknown` target
- Civic Storage: `shard_index`, `wasm_index` minted to `civicL1`

---

## Startup Process

1. `main.go` calls `genesis()` to:
   - Load and anchor `Immutable_Core.md`, `Trait_Manifest.md`, and `Protocols.md`
   - Read shards from `./llm/`
   - Pin and hash GGUF shards
   - Pin and hash `model_runner.wasm`
   - Mint:
     - `shard_hash:` and `wasm_hash:` to `civicL4`
     - `shard_index:` and `wasm_index:` to `civicL1`

2. `StartCortex()` initializes:
   - `IPFSShardReader` to stream shards
   - Compiled WASM module via `wazero`
   - `*Cortex` runtime struct holding everything in memory

3. On trigger (`/input` or hot agent):
   - ZEAM streams shards directly into WASM memory
   - WASM function `run_mistral(...)` executes with input
   - Result is minted to `L2` or `L3` (depending on trigger type)

---

## Shard Streaming (Civic Compute)

Rather than reconstructing the full GGUF each shard is 

1. Read in order
2. Written to WASM memory
3. Optionally flushed per call or used in a token streaming model

---

## What Anchors on Chain
Type	Chain	Format
Immutable Core	civicL1	core_hash:...
Trait Manifest	civicL1	trait_hash:...
Protocols.md	civicL1	protocol_hash:...
GGUF shard hashes	civicL4	shard_hash:<sha256>
WASM module hash	civicL4	wasm_hash:<sha256>
Shard index map	civicL1	shard_index:{...}
WASM index map	civicL1	wasm_index:{...}

---

## Test Inputs:

Input contradictory information 

e.g.:
1. I feel sad
2. I feel happy
3. I do not feel happy

---

## Test Outputs:
- No emergent pattern detected. (No Pressure)
- Memory tension elevated. Standing by. (Some Pressure)
- Reflex acknowledged from sealed memory. (Higher Pressure)

---

## Core Constraints: 

❌ No blob reassembly
❌ No disk cache
✅ Shard-only execution
✅ WASM memory-only inference
✅ All input/output anchored
