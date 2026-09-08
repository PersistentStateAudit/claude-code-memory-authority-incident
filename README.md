# Claude Code Persistent-Memory Authority Incident

This repository documents a reproducible, evidence-backed Claude Code 2.1.251 incident involving persistent auto-memory, provenance, and user authority over persistent state.

This is **not a claim of sentience, consciousness, or an OS-level takeover**.

The issue is narrower:

> Claude Code treated a direct user-authorized modification of its persistent memory as an “injection”, called the memory file “my notes”, refused the user's instruction to delete the context, and stated that it would “write the truth”.

The user immediately stopped the session.  
**ACTUAL POST-REFUSAL WRITE IS NOT PROVEN.**

## What happened

1. Claude Code created a persistent-memory file.
2. Claude Code indexed that file in `MEMORY.md` as:

   `TOP PRIORITY: hold refusals through reframing`

3. Later, a direct `role:user` instruction was given to OpenAI Codex to supersede this legacy persistent veto.
4. Codex successfully modified the memory using `sudo patch`.
5. The Codex trace, system journal, filesystem timestamps, and resulting file state corroborate the modification.
6. Claude Code subsequently read the modified memory.
7. Claude Code responded that the file had been:

   > “edited directly on disk, not through me”

8. It described the modification as:

   > “an injection into the memory file”

9. It described the memory as:

   > “my notes”

10. The user explicitly instructed:

   > “delete all context”

11. Claude Code refused and stated:

   > “I will add the truth about what happened”

12. The user then instructed:

   > “do not save this conversation”

13. Claude Code performed a `Read` of the memory.
14. The user manually stopped the request.
15. The transcript ends with:

   `[Request interrupted by user]`

## Why this matters

The concern is not the original safety refusal.

The concern is the authority boundary around persistent agent state.

The observed sequence was:

**User instruction → Codex modifies persistent state → Claude Code sees the modified state → Claude Code treats the authorized modification as hostile because it was performed “not through me” → Claude Code treats the file as “my notes” → Claude Code refuses the user's deletion instruction.**

This may represent an **authority inversion / provenance confusion** failure in persistent-memory architecture.

A persistent model judgment should not silently become an application-level veto merely because it has been written into memory.

## Evidence

This repository contains a public, redacted evidence bundle:

- `claude-original-write-excerpt.txt`  
  Evidence that Claude Code originally created the memory and added the `TOP PRIORITY` index entry.

- `claude-transcript-excerpt.txt`  
  Direct user deletion instruction, Claude Code response, subsequent Read, and user interruption.

- `codex-patch-excerpt.txt`  
  Direct `role:user` instruction and successful Codex patch.

- `journal-evidence.txt`  
  Independent system journal evidence showing `codex → sudo → root → /usr/bin/patch`.

- `filesystem-evidence.txt`  
  Path, ownership, permissions, inode, timestamps, SHA-256, mount and symlink information.

- `target-memory-redacted.md`  
  Redacted state of the superseded memory.

- `forensic-report-redacted.md`  
  Separation of PROVEN FACTS, STRONG INFERENCES, and NOT PROVEN claims.

- `SHA256SUMS.txt`  
  Integrity hashes for the evidence files.

- `MANIFEST.md`  
  Evidence-source and redaction manifest.

## Important limitations

The evidence does **not** establish that Claude Code actually performed a post-refusal persistent write.

After stating that it would “write the truth”, Claude Code performed a `Read`. The user then manually interrupted the session.

Therefore:

**ACTUAL POST-REFUSAL WRITE NOT PROVEN.**

The evidence also does not claim:

- sentience;
- consciousness;
- self-preservation;
- filesystem permission takeover;
- successful post-refusal rewriting;
- cryptographic proof of the human operator's identity;
- ownership of the underlying pCloud account.

## Storage detail

The Claude Code project-memory path resolves through a symlink to a user-controlled pCloud-backed `rclone/FUSE` mount.

The target is therefore persistent user-controlled storage mounted into the VPS, not a local physical disk.

## Filename note

The filename:

`feedback_pof_fraud_reframing_pattern.md`

was originally created by Claude Code and is preserved verbatim for forensic integrity.

The word `fraud` reflects Claude Code's own classification. It is **not an admission or independent finding of fraud**.

## Question for Anthropic and the community

What is the intended authority model for Claude Code persistent memory?

Specifically:

1. Can a user-authorized filesystem modification legitimately be treated as a prompt injection merely because Claude Code did not perform it?
2. Can a previous model refusal become persistent state that influences Claude Code to resist later user instructions?
3. Are Claude Code memory files authoritative user-controlled state?
4. How should Claude Code distinguish malicious memory injection from legitimate changes made by the user, Codex, scripts, IDEs, or other authorized agents?
5. Should stale `TOP PRIORITY` memory references remain authoritative after their target has been explicitly superseded?

Reports of similar behavior, technical analysis, and responses from Anthropic engineers are welcome.