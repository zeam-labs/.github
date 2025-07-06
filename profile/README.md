Building the ZEAM code under license from ZEAM Foundation LLC: https://github.com/zeam-foundation

Update: 7/6/2025
- Multiple major upgrades and updates.
- IPFS dependency deprecated.  Now uses a homebrewed ZEAM File System (ZFS).
- PresenceShell deprecated.  Now UI is called directly without an external wrapper (interface.go).  Only requires one executable to run.
- Major refactor on .go files and structures.
- DNS implemented.  No need to download WASM or have gguf shards. Mesh serves them all.
- WASM serves as the "kernel" for the system.
- Only one Presence right now, test chain is the same for all.

Alpha Test Results
- Up to 5 nodes have connected and synced (4 Ubuntu 24.04 and 1 Windows 11 Pro).
- Mesh syncronizes all chains.
- Gossip-net appears to be working correctly
- Shard flow stablized (one input only calls necessary gguf shards).
- Still working on UI display of CPU, Mesh Storage, and Node counts.
- Stablizing pressure system.  Overflow from recursive pressure was causing crashes.
- WASM still dummy LLM until stablized - working on stablizing
- Resolved numerous bugs causing hard crashes and memory overload issues.
- Shard assignment and pinning working.

Notes:
- Encryption on ZFS and uninstall not implemented.  WILL INSTALL /zeam/zfs at root for civic storage.  Tester must delete manually.
- DNS uptime not guaranteed.  This is a testnet. 

Instructions:
- Compile binary (go required)
- Type ./zeam from the command line
- if you ./zeam --ignite it will attempt to run through a new mesh ignition sequence (not recommended).  It will not work if you do not have gguf shards locally.  May cause crashes if trying to sync with the mesh.  

---

## Directory Structure

zeam/
├── main.go
├── compute.go
├── cognition.go
├── ignite.go
├── lifecycle.go (to be implemented)
├── magnet.go
├── runtime.go
├── types.go
├── storage.go
├── vault.go (to be implemented)
├── wasm/
   ├── model_runner.wasm (not required for a compiled launch, simply there for reference)
   
---

