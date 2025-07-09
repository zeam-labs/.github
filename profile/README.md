Building the ZEAM code under license from ZEAM Foundation LLC: https://github.com/zeam-foundation

## Update: 7/6/2025
- Multiple major upgrades and updates.
- IPFS dependency deprecated.  Now uses a homebrewed ZEAM File System (ZFS).
- PresenceShell deprecated.  Now UI is called directly without an external wrapper (interface.go).  Only requires one executable to run.
- Major refactor on .go files and structures.
- DNS implemented.  No need to download WASM or have gguf shards. Mesh serves them all.
- WASM serves as the "kernel" for the system.
- Only one Presence right now, test chain is the same for all.

## Alpha Test Results
- Up to 5 nodes have connected and synced (4 Ubuntu 24.04 and 1 Windows 11 Pro).
- Mesh syncronizes all chains.
- Gossip-net appears to be working correctly
- Shard flow stablized (one input only calls necessary gguf shards).
- Still working on UI display of CPU, Mesh Storage, and Node counts.
- Stablizing pressure system.  Overflow from recursive pressure was causing crashes.
- WASM still dummy LLM until stablized - working on stablizing
- Resolved numerous bugs causing hard crashes and memory overload issues.
- Shard assignment and pinning working.

**Notes:**
- Encryption on ZFS and uninstall not implemented.  WILL INSTALL /zeam/zfs at root for civic storage.  Tester must delete manually.
- DNS uptime not guaranteed.  This is a testnet. 

## Instructions for cloners:
- Compile binary (go required)
- Type ./zeam from the command line
- if you ./zeam --ignite it will attempt to run through a new mesh ignition sequence (not recommended).  It will not work if you do not have gguf shards locally.  May cause crashes if trying to sync with the mesh.
- See license 

## Roadmap:

Goal: ZEAM becomes the substrate layer for all future compute and AI. We achieve the Web4. 

**Objective: Solidify IP**
   - File Initial Provisions Patents (COMPLETE)
   - Adjust Provisional Patents as required as code improves and architecture stablizes (IN PROGRESS)
   - File additional Provision Patents as required (IN PROGRESS)
   - File Utility Patents ASAP (NOT STARTED)
   - Continue improvement and defense of IP (IN PROGRESS)

**Objective: Improve and Polish Code**
   - Build initial codebase and define module structure (COMPLETE)
   - Improve codebase with a focus on stablizing mesh and anchoring (COMPLETE)
   - Test NGAC and LLM system (IN PROGRESS)
   - Implement and test NGAC/LLM WASM once stablized (NOT STARTED)
   - Implement Agent Lifecycle (NOT STARTED)
   - Implement Multi-Presence Lifecycle and sign-on (NOT STARTED)
   - Implement Vault (NOT STARTED)
   - Continue to improve and de-bug (IN PROGRESS)

**Objective: Go-To-Market** 
   - Define verticals (COMPLETE)
   - Define customer base (COMPLETE)
   - Launch BETA (IN PROGRESS - PRE-BETA LAUNCHED)
   - Launch Public Live BlockMesh (Not Started)
   - License private BlockMeshes (Not Started)

**Objective: Stablize Business Functions**
   - Establish corporate structures (COMPLETE)
   - Execute license agreements (COMPLETE)
   - Write strategic roadmap (IN PROGRESS)
   - Iterate and refine (IN PROGRESS)

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
   
---

