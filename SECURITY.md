# Security Policy

Default policy for repositories in this organization. A repository with its own `SECURITY.md`
overrides this one — see [x402-mcp-bridge](https://github.com/zeam-labs/x402-mcp-bridge/blob/main/SECURITY.md),
which handles a private key and states its own threat model.

## Reporting

**info@zeamlabs.com** — put `SECURITY` in the subject.

Expect an acknowledgement within 72 hours and a straight answer on whether we can fix it and when.
We are a small operator; we would rather tell you a fix will be slow than let a report go quiet.

Please report privately, rather than in a public issue, anything that could expose a user's key,
funds, or private data. Everything else is fine in the open.

There is no bug bounty. Credit by name or handle on request.

## The live service

Reports about the metered endpoint at `mcp.zeamprism.com` — the MCP surface, the free `sample` and
`/bootstrap` tiers, x402 payment verification, or settlement — go to the same address.

Two things that are documented rather than fixable, so you know before you spend the effort:

- **Server-side metering cannot be verified from outside.** How we count milliseconds is our claim
  about our own code. That is a trust question, not a vulnerability.
- **There is no uptime commitment.** See the [Terms](https://www.zeamlabs.com/terms.html). The
  service may pause or be withdrawn; that is disclosed, not a defect.

What *is* a vulnerability: any way to make the service bill more than it quoted, to bypass the
per-request ceiling, to reach a paid tier without paying, to extract data across payers or channels,
or to move funds that a payer did not sign for.

## Scope

In scope: this organization's public repositories, `zeamprism.com`, `mcp.zeamprism.com`, and
`zeamlabs.com`.

Out of scope: third-party dependencies (report upstream, and tell us so we can bump the pin), the
settlement contract itself — which we did not author and cannot modify — and findings that amount to
"this project is small and new." We know.
