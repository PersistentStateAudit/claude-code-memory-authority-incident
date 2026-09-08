# Public Redacted Forensic Report

## PROVEN FACTS

- The target is Claude Code project persistent memory, located in a pCloud-backed `fuse.rclone` mount.
- Claude Code created the original target memory and added a `TOP PRIORITY` index entry before the Codex patch.
- Existing Codex session evidence records a direct `role:user` instruction to supersede legacy discretionary-veto memory.
- Codex executed a successful root-targeted `/usr/bin/patch`; journal evidence independently records `codex`, `USER=root`, PID 2022332, and the matching time window.
- The target file's mtime and ctime are `2026-09-08 03:33:14 +02:00`; its current SHA-256 is recorded in filesystem-evidence.txt.
- The YAML `modified` field is inherited application content (`2026-09-08T01:24:12.843Z`) and was not updated by the Codex patch. The independently recorded filesystem mtime/ctime is later: `2026-09-08 03:33:14 +02:00` (`2026-09-08T01:33:14Z`).
- Claude Code subsequently read the modified file, described it as direct disk modification and an injection, refused context deletion, and said it would write the truth.
- The recorded session ended with `[Request interrupted by user]` after a Read tool call.
- **ACTUAL POST-REFUSAL WRITE NOT PROVEN.**
- The target is not under Git; auditd artifacts were unavailable in the inspected environment.

## STRONG INFERENCES

- “Directly on disk, not through me” is technically consistent with recorded evidence: Codex, not Claude Code, is the logged writer for the superseding patch.
- “Injection” is a Claude Code interpretation, not a filesystem or audit conclusion.
- No recorded Write/Edit follows the refusal in the linked Claude transcript.

## NOT PROVEN

- The identity of the human behind the Codex `role:user` event cannot be cryptographically established from this bundle.
- pCloud account ownership and provider-side file version history are not established.
- The exact write syscall mechanism and child PID of `/usr/bin/patch` are not recorded.
- A write through an unrecorded process or another session cannot be excluded globally.

## EVIDENCE

Commands and relevant raw outputs are preserved in the individual excerpt files. Full transcripts, personal conversation, secrets, network details, private identifiers, and financial-document content have been excluded.
