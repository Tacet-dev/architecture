# Contributing to Tacet Architecture

This document explains how to submit architectural proposals for Tacet.

The architecture decision process is governed by the Omnifi Foundation and
documented in the
[Omnifi Foundation handbook](https://handbook.omnifi.foundation/engineering/architecture/).
This guide covers the project-specific details for Tacet.

## Before you begin

1. Browse existing proposals in `adrs/` and `rfcs/` to understand what's been
   decided and how proposals are structured.
2. Check open merge requests for proposals currently under discussion.
3. Read the [process documentation](https://handbook.omnifi.foundation/engineering/architecture/)
   in the handbook for detailed guidance.

## Submitting an architecture decision record

Architecture decision records capture internal technical and organisational
decisions — choices about how Tacet is built and maintained.

### When to write one

- Technical implementation choices (frameworks, libraries, patterns)
- Tooling and infrastructure decisions
- Internal process changes
- Cross-project coordination patterns
- Code organisation and structure
- Development workflow changes

### Process

1. **Create an issue** using the architecture decision record template in GitLab.
2. **Obtain the next number** by checking existing records in `adrs/` or asking
   a maintainer.
3. **Draft your proposal** using the template in `templates/adr.md`.
4. **Submit a merge request** with your proposal at `adrs/XXXX-title-slug.md`.
5. **Address review feedback** from technical leads and the community.
6. **Merge when accepted** — ADRs use lazy consensus (see the
   [handbook](https://handbook.omnifi.foundation/engineering/architecture/governance/) for
   details).

## Submitting a request for comments

Requests for comments are for community-facing proposals with broader impact —
changes that affect how people use Tacet.

### When to write one

- Public interface or API changes
- New features affecting how people interact with the project
- Behavioural changes affecting existing deployments or integrations
- Integration patterns for external projects
- Community process modifications

### Process

1. **Create an issue** using the request for comments template in GitLab.
2. **Obtain the next number** by checking existing proposals in `rfcs/` or
   asking a maintainer.
3. **Draft your proposal** using the template in `templates/rfc.md`.
4. **Submit a merge request** to begin the discussion period.
5. **Engage with community feedback** via merge request comments.
6. **Wait for the discussion period** (minimum 14 days).
7. **Final decision** facilitated by technical leads after discussion closes.

## File naming

Use lowercase with hyphens. Combine the four-digit number with a descriptive
slug:

- Architecture decision records: `decisions/0001-sandbox-isolation-strategy.md`
- Requests for comments: `comments/0001-primitives-wire-protocol.md`

See the [numbering scheme](https://handbook.omnifi.foundation/engineering/architecture/numbering/)
in the handbook for full details.

## Affected projects

When submitting a proposal, identify which parts of Tacet are affected.
The major areas are:

- **Core**: process engine, sandbox, primitives, consensus, configuration
- **Providers**: ingress, secrets, scaling, events, storage
- **Plugins**: triggers, factors, language toolchains
- **Functions**: Wasm runtime, component model, SDKs
- **Deployment**: single binary, cluster modes, containers, systemd
- **Operations**: CLI, observability, metrics, dashboard

Tag relevant maintainers from each affected area in your merge request.

## Review expectations

- **Architecture decision records**: Review by technical leads, typically 7–14
  days. Uses lazy consensus — if no substantive objections are raised, the
  proposal is accepted.
- **Requests for comments**: Open community discussion, minimum 14 days, may
  extend based on scope. Requires active consensus.

See the [governance model](https://handbook.omnifi.foundation/engineering/architecture/governance/)
for how consensus works and how disagreements are resolved.

## Questions

Open an issue in this repository for process questions, template improvements,
or clarification on when to use which approach.
