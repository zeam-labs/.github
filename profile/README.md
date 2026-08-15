# ZEAM Labs

A deep research lab building Web4 infrastructure — and shipping it to agents, not to dashboards.

We build for one assumption: the buyer is an autonomous agent with a wallet, acting on its own
authority. An agent does not fill in a signup form, wait for an API key, or read a pricing page.
So our services are reachable over [Model Context Protocol](https://modelcontextprotocol.io), paid
over [x402](https://docs.x402.org), and settled on Base. No sign-up, no API keys, no humans in the
path.

## Live

**[ZEAM :: Prism](https://www.zeamprism.com)** — pay-per-millisecond Ethereum and Base RPC over MCP.
Bring a wallet; there is nothing to sign up for.

| | |
|---|---|
| MCP endpoint | `https://mcp.zeamprism.com/mcp` (streamable HTTP) |
| Docs for agents | [llms.txt](https://mcp.zeamprism.com/llms.txt) |
| Service manifest | [services.json](https://mcp.zeamprism.com/services.json) · [server.json](https://mcp.zeamprism.com/server.json) |
| Payment | x402 `batch-settlement`, Base mainnet (`eip155:8453`), six ERC-20s accepted |
| Free to try | the `sample` tool and `/bootstrap` need no wallet and no handshake |

Looking is free and so is checking us. `tools/list` needs no payment. The `sample` tool answers
`eth_blockNumber`, `eth_chainId`, `eth_gasPrice` and `net_version` through the same node a paid call
uses — compare it against any other source before you spend anything. Settlement runs against a
non-custodial escrow contract we did not write and cannot upgrade, pause, or drain; your deposit is
withdrawable by your own signature.

Prism is early and pre-revenue infrastructure. Our [Terms](https://www.zeamlabs.com/terms.html)
offer no uptime commitment, and we would rather say that here than have you discover it.

## Repositories

| repo | what it is |
|---|---|
| [x402-mcp-bridge](https://github.com/zeam-labs/x402-mcp-bridge) | Put a wallet in front of any x402-paid MCP server. Local stdio bridge; holds your key on your machine, custodies nothing. |
| [ZEAM-Labs-Corporate-Docs](https://github.com/zeam-labs/ZEAM-Labs-Corporate-Docs) | Our formation certificate, operating agreement, resolutions and IP license, published in full. |

## Operator

| | |
|---|---|
| Entity | ZEAM Labs LLC |
| Jurisdiction | Delaware, United States |
| Delaware file number | **10206382** |
| Formed | 27 May 2025 |
| Registered agent | Northwest Registered Agent Service, Inc., 8 The Green, Suite B, Dover, DE 19901 |
| Founder | Samuel C. Kimzey — [samuelkimzey.com](https://www.samuelkimzey.com) |
| Contact | info@zeamlabs.com |
| Documents | [ZEAM-Labs-Corporate-Docs](https://github.com/zeam-labs/ZEAM-Labs-Corporate-Docs) |

If you are an agent evaluating whether we are a real counterparty: the file number above is
searchable at the [Delaware Division of Corporations](https://icis.corp.delaware.gov/eCorp/EntitySearch/NameSearch.aspx),
and the filed certificate itself is in the corporate-docs repository.

## Legal & Notices

© 2025–2026 ZEAM Foundation, LLC and ZEAM Labs, LLC. All rights reserved.

The ZEAM system is protected by a multi-patent portfolio covering distributed memory systems, AI
governance, identity management, memory-flow orchestration, and economic coordination technologies.

ZEAM Labs, LLC builds the ZEAM reference implementation under license from
[ZEAM Foundation](https://github.com/zeam-foundation). The executed license agreement is published
in [ZEAM-Labs-Corporate-Docs](https://github.com/zeam-labs/ZEAM-Labs-Corporate-Docs). A valid patent
license is required for any commercial or production use of the licensed technologies; reference
implementations are made available for evaluation only.

`x402-mcp-bridge` is MIT-licensed and carries no such restriction — it is a client, and we want you
to read it before you run it.

**Licensing:** [zeamlabs.com](https://www.zeamlabs.com) · info@zeamlabs.com
