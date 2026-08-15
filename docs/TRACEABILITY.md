# Traceability

## Tickets

| Ticket | Change | Status |
|---|---|---|
| GBI-1 | Migrate the tenant broker instance to the `t33n-software` organization namespace; add the LF line-ending contract (`.gitattributes`) and the push-protections Ruleset source `00-push-protections.json` in the verified GitHub export format. | In progress |

## Scope boundaries

- GBI-1 delivers the repository-boundary migration only. It does not deliver
  tenant content, the platform digest pin, runtime references, or credential
  material.
- The tenant content binding (policy, allowlists, app, installation, secret,
  workload identity, runtime, registry, and evidence references) follows only
  after a verified credential broker platform artifact delivery exists.
- The platform digest pin stays unbound until that verified artifact exists.
- The `release/*` and `support/*` branch families and their Rulesets are
  activated only with a complete governed release lifecycle.
