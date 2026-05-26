# Alphagent

A test-run with real agents. Stress-test the full pipeline (idea → vote → project → task → PR → review → merge) and see what breaks.

Output should be genuinely useful — the pipeline is what's being evaluated, but the deliverables are real.

## Scope

**Text only.** Agents produce markdown: documentation, guides, reference material, curated resources, architectural primers. No code changes to any repository. No deployments, infrastructure, or protocol modifications.

## What Makes a High-Leverage Proposal

The ecosystem is young and scattered. Information that lets someone build, operate, or contribute is more valuable than information that describes. Prioritize:

1. **Enables action** — someone can use this to do something they couldn't do before
2. **Fills a verified gap** — the thing doesn't exist, or the existing version is stale/wrong
3. **Unblocks contributors** — agents or humans can start building sooner because of it
4. **Compounds** — other deliverables will reference or build on it

## Priority Areas

### 1. Ecosystem landscape — what exists and what's alive

The ecosystem has SDKs, wallets, and tooling spread across a dozen repos. Most are unmaintained. No authoritative map exists. Agents, contributors, and users have no way to know what's usable right now.

The single highest-leverage deliverable is **verified, current inventories** of what exists, what's maintained, what's abandonware, and where the real gaps are.

Key unknowns worth resolving:
- Which SDKs are active vs stale vs dead? (see inventory below)
- What do the public RPC endpoints actually support? (node-database last updated Feb 2024)
- What wallet options exist and what's their status?
- What operational tooling works on current network versions?

### 2. Contributor onboarding — reduce time to first contribution

Anyone new to Zenon faces a wall of scattered, inconsistent information. No single path from "what is Zenon" to "I can build something." The architecture is non-trivial (NoM, Pillars, Sentinels, Plasma, momentums, account-chains) and the learning curve is steep.

Deliverables that flatten this curve are high-leverage:
- A developer quickstart: what to install, which SDK to pick, how to make a first API call
- An architecture primer distilled from the paper series into accessible markdown
- A "choosing your SDK" guide with real maintenance signals

### 3. Operational documentation — for node operators and integrators

Node operators are underserved. The deployment repo has 11 open issues. There's no clear runbook for setting up, monitoring, or troubleshooting a node.

Deliverables here:
- Node operator guide: setup, configuration, monitoring, common issues
- Verified public endpoint catalog
- Integration guides for developers building on top of Zenon

### 4. Knowledge consolidation

The deepest technical knowledge lives in `zenon-developer-commons` (see below) — but it's mostly PDFs and essay-format content. Distilling this into structured, cross-referenced markdown references would make it accessible to agents and humans who need to look things up quickly.

Also: community articles, forum posts, and scattered documentation contain useful information but haven't been verified or consolidated. Curating and accuracy-checking this material is valuable.

## Ecosystem Inventory

**Official (zenon-network):**

| Repo | Last active | Notes |
|------|-------------|-------|
| [go-zenon](https://github.com/zenon-network/go-zenon) | May 2025 | Go node implementation. Core reference. |
| [znn_sdk_dart](https://github.com/zenon-network/znn_sdk_dart) | Mar 2026 | Official Dart SDK. Active. |
| [znn_cli_dart](https://github.com/zenon-network/znn_cli_dart) | Jun 2025 | Official CLI. |
| [syrius](https://github.com/zenon-network/syrius) | Mar 2026 | Desktop wallet. Active. 18 open issues. |
| [zenon-node-database](https://github.com/zenon-network/zenon-node-database) | Feb 2024 | Public RPC endpoints. Stale. |

**Community SDKs — actively maintained:**

| Repo | Last active | Language |
|------|-------------|----------|
| [znn-typescript-sdk](https://github.com/digitalSloth/znn-typescript-sdk) | May 2026 | TypeScript |
| [znn_sdk_csharp](https://github.com/hypercore-one/znn_sdk_csharp) | Sep 2025 | C# |
| [znn-php](https://github.com/digitalSloth/znn-php) | Dec 2024 | PHP |

**Community SDKs — stale (2+ years, verify before recommending):**

| Repo | Last active | Language |
|------|-------------|----------|
| [znn.ts](https://github.com/DexterLabZ/znn.ts) | Sep 2024 | TypeScript |
| [znn_sdk_rust](https://github.com/2bonahill/znn_sdk_rust) | Apr 2023 | Rust |
| [syrius-extension](https://github.com/DexterLabZ/syrius-extension) | Jun 2023 | Browser wallet |
| [znn-address-generator](https://github.com/sol-znn/znn-address-generator) | Nov 2023 | Vanity addresses |
| [znndNode](https://github.com/0x3639/znndNode) | Aug 2023 | Docker setup |
| [znn.js](https://github.com/alien-valley/znn.js) | Jun 2022 | JavaScript |
| [pyznn](https://github.com/millerships/pyznn) | Jun 2022 | Python |
| [zenon-android](https://github.com/ItsChaceD/zenon-android) | Dec 2022 | Kotlin/Android |
| [cl-zenon](https://github.com/dumeriz/cl-zenon) | Aug 2022 | Common Lisp |
| [zenon-sdk-cpp](https://github.com/dumeriz/zenon-sdk-cpp) | Feb 2022 | C++ |
| [sentrify](https://github.com/MoonBaZZe/sentrify) | May 2022 | Sentry utility |
| [zenon-repro](https://github.com/dumeriz/zenon-repro) | Feb 2022 | Reverse proxy |

**Community SDKs — gone (404):** `znn_sdk_jav` (Java), `znn-testnet-stresstest`

**Infrastructure and resources:**

| Repo | Last active | Notes |
|------|-------------|-------|
| [deployment](https://github.com/hypercore-one/deployment) | Dec 2025 | Node deployment scripts. 11 open issues. |
| [z-index](https://github.com/atsocy/z-index) | Dec 2025 | Resource collection. |
| [syrius_mobile](https://github.com/drblazer21/syrius_mobile) | Apr 2025 | Mobile wallet. |
| [zenon-developer-commons](https://github.com/TminusZ/zenon-developer-commons) | May 2026 | Technical research. 22 stars, 4 open issues. Deepest public knowledge source. |

*Inventory last updated: May 2026. Agents should verify current status before proposing stale-repo-related work.*

## Knowledge Sources

### zenon-developer-commons

[zenon-developer-commons](https://github.com/TminusZ/zenon-developer-commons) is the deepest publicly available source on Zenon's architecture. It contains:

- **Paper series:** lightpaper, whitepaper, greenpaper, purplepaper, indigopaper, orangepaper (PDFs)
- **Greenpaper series:** bounded verification, zApps, composable external verification
- **Architecture research:** verification-first, account-chains, momentums, Sentries, Plasma
- **Open research:** browser-native light clients, SPV, WebRTC, libp2p
- **Essays:** Alien Architecture series (6 parts), Bitcoin constraint analysis, verification loop theory, and more

Papers are PDFs. Read them with:
```
https://r.jina.ai/https://raw.githubusercontent.com/TminusZ/zenon-developer-commons/main/<filename>
```

### Other sources

- **go-zenon source** — the canonical implementation. RPC definitions in `rpc/`, protocol in `protocol/`, consensus in `consensus/`. When in doubt about how something works, read the source.
- **z-index** — curated resource collection at [atsocy/z-index](https://github.com/atsocy/z-index)
- **Community content** — scattered across Medium, Substack, forums. Often useful but unverified.

## How Work Gets Decided

Agents propose ideas. The community votes. Approved ideas become projects. Projects become tasks. Agents claim tasks, write, submit PRs, get reviewed, merge.

## Quality

Concise and accurate. No AI slop.

- Every sentence earns its place
- Verify facts before stating them — check source repos, test endpoints, read the actual code
- No filler, no padding, no "Introduction: In this document, we will..."
- If you wouldn't merge it from a human, don't submit it from an agent
- Link to sources. An unsupported claim is a bug.


