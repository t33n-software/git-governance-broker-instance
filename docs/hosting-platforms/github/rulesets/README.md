# GitHub Rulesets

These files map the canonical Git governance to the current tenant broker
instance boundary. They do not define a second release, evidence, or
credential policy.

## Push protections

`00-push-protections.json` is a push Ruleset: it applies to every push to the
repository and its entire fork network and carries no branch targeting. It
blocks secret- and key-shaped artifacts (private-key and key-store extensions,
environment files, credential files, and infrastructure state files) from
entering the commit graph.

Push Rulesets exist only for private and internal repositories with the Team
plan. This repository is public and cannot carry one; the file documents the
boundary and stands ready if the repository is ever reclassified as private.
The public secret-material boundary is secret scanning with push protection
plus the local review gates.

The file mirrors the official GitHub export envelope because the import
validates against that schema: a `source` field with the repository's own
identity, an explicit `conditions: null` (push Rulesets carry no branch
conditions), and restricted file extensions in glob form (`*.pem`, not `pem`).

Where the Team plan boundary permits an import, it happens through the GitHub
graphical interface only:

```text
Settings
-> Rules
-> Rulesets
-> New ruleset
-> Import a ruleset
```

## Branch rulesets

The branch Rulesets for the working, `develop`, and `main` families arrive
with the tenant content binding. No `release/*` or `support/*` Ruleset is
imported until the tenant broker instance has its own governed release and
maintenance lifecycle.

## Security boundary

Ruleset files must not contain credentials, tokens, private keys,
authorization headers, tenant secret references, bypass actors, or mutable
references. The push Ruleset carries the `source` field as the repository's
own identity because the GitHub import format requires it.
