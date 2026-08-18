# git-governance-broker-instance

`git-governance-broker-instance` is the versioned tenant instance for the
`git-governance` tenant: the decision plane for the tenant credential policy,
repository allowlist, app and installation references, secret references,
workload identity, runtime, registry, and evidence references of the tenant
broker instance.

This repository contains only non-sensitive references. It never contains
secrets, tokens, private keys, authorization headers, or credential material.
The tenant broker runtime stays private and authenticated regardless of this
repository's visibility.

The platform digest pin stays unbound until a verified credential broker
platform artifact exists.

Governed changes land through ticket branches and pull requests into
`develop`. `main` is the production and control-plane truth.

Branch governance is bound through the organization-level rule-sets; the
canonical source and the rule-set family of this repository are documented in
[`docs/conventions/hosting-plattform/github/rule-sets`](docs/conventions/hosting-plattform/github/rule-sets/README.md).
