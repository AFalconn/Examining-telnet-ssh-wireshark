# Findings — Telnet vs SSH

## Summary
The lab compares local Telnet and SSH sessions using Wireshark on the loopback interface.

| Check | Telnet | SSH |
|---|---|---|
| Display filter used | `telnet` | `ssh` |
| Follow TCP Stream | Session content appears as readable plaintext | Session payload is encrypted and not readable as ordinary session text |
| Credential confidentiality | Credentials can be exposed in plaintext | Credentials are protected in transit by the encrypted connection |
| Recommendation | Avoid for remote administration | Prefer SSH when securely configured |

## Evidence references
Replace the placeholders after completing the lab:
- Telnet filter screenshot: `evidence/screenshots/01-wireshark-telnet-filter.png`
- Redacted Telnet stream screenshot: `evidence/screenshots/02-telnet-follow-tcp-stream-redacted.png`
- SSH filter screenshot: `evidence/screenshots/03-wireshark-ssh-filter.png`
- SSH stream screenshot: `evidence/screenshots/04-ssh-follow-tcp-stream.png`

## Observations
Add your own observations here after performing the lab. Do not claim that a step was completed until you have performed it and collected your own evidence.

## Conclusion
Telnet sends session data without encryption, making captured traffic readable. SSH encrypts the session and is the safer choice for remote administration when properly configured.
