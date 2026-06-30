# Infrix — governed, verifiable execution on Accumulate

> Built by **OpenDLT**. The public devnet runs on the Accumulate **Kermit testnet**.

Most chains answer *"is this valid?"* with **"because our node says so."**
Infrix hands you a **portable proof you re-verify yourself** — against a server
you don't have to trust. Every state change is a *governed intent*
(intent → policy → approval → outcome → evidence → anchor), and the result is
cryptographic, not a promise.

## ▶ Try it now — no install, no wallet, no funds

**[Run a real governed flow and verify its proof in your browser → play.infrix.opendlt.org](https://play.infrix.opendlt.org)**

## Prove it to yourself in 30 seconds

```sh
mkdir infrix-taste && cd infrix-taste && npm init -y && npm i @infrix/verify
```
```js
// verify.mjs — check a real Infrix proof offline, against nobody's word
import { verifyPortablePackage } from '@infrix/verify';
import { createRequire } from 'node:module';
const proof = createRequire(import.meta.url)('@infrix/verify/portable-fixture.valid.json');
const r = await verifyPortablePackage(proof);
console.log(r.passed ? '✅ proof verified offline' : '❌ failed');
```
```sh
node verify.mjs   # ✅ proof verified offline
```

## Start here

| Step | Do this |
|---|---|
| **See it** | [Live playground](https://play.infrix.opendlt.org) — run the golden escrow flow, watch the spine |
| **Trust it** | `npm i @infrix/verify` — re-verify the proof yourself (the snippet above) |
| **Install the CLI** | `npx @infrix/cli version` &nbsp;·&nbsp; or `curl -fsSL https://raw.githubusercontent.com/opendlt/infrix-cli/main/install.sh \| sh` |
| **Build** | `npm i @infrix/client`, point it at the public devnet API `https://devnet.infrix.opendlt.org`, submit your first intent |

## Repositories

| Repo | What it is |
|---|---|
| [infrix-cli](https://github.com/opendlt/infrix-cli) | Prebuilt `infrix` CLI binaries + installers (`curl\|sh`, `npx @infrix/cli`) |
| [infrix-sdk-js](https://github.com/opendlt/infrix-sdk-js) | TypeScript / AssemblyScript SDKs (`@infrix/client`, `@infrix/verify`, …) |
| [infrix-crates](https://github.com/opendlt/infrix-crates) | Rust SDK for authoring WASM contracts |
| [infrix-verify](https://github.com/opendlt/infrix-verify) | Node-free, offline proof verifier |
| [infrix-playground](https://github.com/opendlt/infrix-playground) | The hosted playground |
| [infrix-schema](https://github.com/opendlt/infrix-schema) | Stdlib-only contract / verification kernel |
| [infrix-nexus-web](https://github.com/opendlt/infrix-nexus-web) | The Nexus governance SPA |
| [infrix-website](https://github.com/opendlt/infrix-website) | Docs & funnel site (infrix.opendlt.org) |

## How the pieces fit

**Infrix** is the governed-execution fabric. It runs on **Accumulate** (the L0
ledger — identity, key books, anchoring) and anchors its proofs to **Kermit**
(Accumulate's testnet). **OpenDLT** is the organization that builds Infrix.

MIT licensed.
