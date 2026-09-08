# Manifest

| filename | purpose | source | redactions applied |
| --- | --- | --- | --- |
| README.md | Neutral incident timeline and scope | Existing forensic findings | Private context omitted |
| target-memory-redacted.md | Current target memory text | Current target file | originSessionId replaced |
| claude-transcript-excerpt.txt | Refusal, Read, interruption sequence | Claude transcript | Session ID, full conversation, reasoning omitted |
| codex-patch-excerpt.txt | Direct role:user instruction and successful patch | Codex session trace | Full session and unrelated paths omitted |
| journal-evidence.txt | Root patch journal records | Existing system journal | Working directory redacted |
| filesystem-evidence.txt | Metadata, checksum, mount and symlink evidence | Existing filesystem state | No private identifiers included |
| claude-original-write-excerpt.txt | Initial Write and MEMORY.md Edit evidence | Claude transcript | Private body omitted |
| claude-version.txt | Claude Code version | Existing binary version output | None |
| forensic-report-redacted.md | Public four-section forensic report | Existing forensic findings | Session IDs and private context omitted |
| SHA256SUMS.txt | Integrity checksums for all payload files | Generated after privacy scan | Self-checksum excluded by necessity |
