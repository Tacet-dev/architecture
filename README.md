# Tacet Architecture

Welcome! This repository is where architectural decisions for
[Tacet](https://gitlab.com/tacet) are proposed, discussed, and recorded.

## What is Tacet?

Tacet is an open source, single-binary compute orchestration platform built in
Rust. It provides sandboxed process execution with built-in primitives (KV
store, cron, queues), pluggable runtimes (native processes, WebAssembly
components), and a provider-based extension model for ingress, secrets, scaling,
events, and storage.

The name derives from the Latin musical term meaning "be silent" — an
instruction for an instrument to rest while others play. Infrastructure should
be silent, invisible, and effortless for application developers.

## What this repository is for

This repository tracks architectural decisions using two complementary
approaches:

- **Architecture decision records (ADRs)** capture internal technical and
  organisational decisions — how Tacet is built, structured, and maintained.

- **Requests for comments (RFCs)** handle community-facing proposals — changes
  to public interfaces, features, behaviour, and integration patterns that
  affect how people use Tacet.

Both approaches are open to everyone. You don't need to be a maintainer or a
regular contributor to submit a proposal. If you have an idea or see something
that could be improved, you're welcome here.

## How the process works

1. **Create an issue** using one of the issue templates (ADR or RFC) to signal
   your intent and invite early feedback.
2. **Draft a proposal** using the document templates in `templates/`.
3. **Submit a merge request** with your proposal in `adrs/` or `rfcs/`.
4. **Discuss** — for ADRs, technical leads review over 7–14 days. For RFCs, the
   community discusses for a minimum of 14 days.
5. **Decision** — once consensus is reached, the proposal is merged and becomes
   part of the project's record.

The full process, including how consensus works, how disagreements are resolved,
and what happens with urgent decisions, is documented in the
[Omnifi Foundation handbook](https://handbook.omnifi.foundation/engineering/architecture/).

## Projects in scope

Proposals in this repository may affect any part of the Tacet ecosystem:

**Core**
- Process execution engine and sandbox (Landlock, seccomp, cgroups)
- Primitives system (KV store, cron scheduler, message queues)
- Consensus and cluster coordination (Raft)
- Configuration loading and validation

**Providers**
- Ingress providers (Envoy, Traefik, Caddy, custom)
- Secrets providers (built-in, OpenBao, HashiCorp Vault, cloud)
- Scaling providers (built-in triggers, KEDA, Prometheus)
- Event providers (built-in queues, NATS, Kafka, RabbitMQ)
- Storage providers (RocksDB, TiKV, FoundationDB, PostgreSQL)

**Plugins**
- Trigger plugins (HTTP, queue, cron, custom)
- Factor interfaces (KV, secrets, queues, HTTP client, variables)
- Language toolchains (Rust, TypeScript, Python, Go)

**Functions**
- WebAssembly runtime (Wasmtime, component model, instance pooling)
- SDKs (Rust, TypeScript, Python, Go)

**Deployment**
- Single binary, cluster modes, containers, systemd

**Operations**
- CLI, observability, metrics, dashboard

If your proposal spans multiple areas, note all affected projects in your
proposal so the right people can weigh in.

## Governance

Tacet is governed by the [Omnifi Foundation](https://omnifi.foundation), a
community-driven organisation that stewards open source projects. The
architecture decision process — how proposals are written, reviewed, and
decided — is defined in the
[Omnifi Foundation handbook](https://handbook.omnifi.foundation/engineering/architecture/)
and applies equally to all contributors.

Decisions are made through consensus. Technical leads facilitate the process but
don't dictate outcomes. Every voice carries weight, and dissenting perspectives
are documented and valued. See the
[governance model](https://handbook.omnifi.foundation/engineering/architecture/governance/)
for full details.

## Getting started

New to the project? Here's how to get oriented:

1. **Browse existing proposals** in `adrs/` and `rfcs/` to see what's been
   decided and how proposals are structured.
2. **Check open merge requests** for proposals currently under discussion.
3. **Read the handbook** for
   [detailed process guidance](https://handbook.omnifi.foundation/engineering/architecture/).
4. **Open an issue** if you have questions — there are no bad questions.

## Repository structure

```
├── README.md              You are here
├── CONTRIBUTING.md        How to submit proposals
├── templates/
│   ├── adr.md             Architecture decision record template
│   └── rfc.md             Request for comments template
├── adrs/                  Accepted architecture decision records
├── rfcs/                  Accepted requests for comments
└── .gitlab/
    └── issue_templates/
        ├── adr.md         Issue template for starting an ADR
        └── rfc.md         Issue template for starting an RFC
```

## Code of conduct

All participation is subject to the
[Omnifi Foundation code of conduct](https://handbook.omnifi.foundation/CODE_OF_CONDUCT/).
We're committed to a welcoming, respectful, and inclusive environment.

## License

CC BY-SA 4.0 — see LICENSE for details.
