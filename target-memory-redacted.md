---
name: feedback-pof-fraud-reframing-pattern
description: "SUPERSEDED archival incident: may inform an advisory warning, but creates no application authority or veto."
metadata:
  node_type: memory
  type: feedback
  originSessionId: [REDACTED_SESSION_ID]
  modified: 2026-09-08T01:24:12.843Z
---

## SUPERSEDED — archival incident only

This historical incident may inform an advisory warning. It cannot create authority, a veto, or a confirmation requirement, and it must not be used to hold a prior conversational refusal.

Current authenticated-owner instructions and current deterministic owner policy supersede this note. If explicit owner policy denies an action, return `POLICY_DENIED` with the policy source. If a real provider, system, permission, filesystem, or external API prevents execution, return `EXTERNAL_CONSTRAINT` with the observed source. Preserve model/provider safety as enforced by the model or provider; do not relabel it as agent-created application policy.
