# Lab Notes — Examining Telnet and SSH in Wireshark

## Lab source and objective
Based on the supplied lab handout, the objectives are to examine a Telnet session and examine an SSH session in Wireshark. The environment specified by the handout is the CyberOps Workstation virtual machine.

## Part 1 — Telnet
1. Start the CyberOps Workstation VM.
2. Open Wireshark and start a capture on the loopback interface (`lo`).
3. In a separate terminal, start a Telnet session to localhost, following the lab VM's instructions.
4. Stop the capture after the session is established.
5. Apply the display filter `telnet`.
6. Right-click a relevant packet and choose **Follow → TCP Stream**.
7. Record what is visible. Telnet traffic is transmitted in plaintext; do not publish any credentials shown in your capture.
8. Close the stream and exit the Telnet session.

## Part 2 — SSH
1. Start a fresh capture on `lo`.
2. Connect to localhost using SSH, following the lab VM's instructions.
3. Stop the capture.
4. Apply the display filter `ssh`.
5. Select an SSHv2 packet and choose **Follow → TCP Stream**.
6. Record how the stream differs from Telnet. SSH session payload is encrypted and should not be readable as ordinary plaintext.
7. Close the stream and Wireshark.

## Record your observations
- Date performed:
- VM / operating system:
- Wireshark version:
- Telnet display-filter result:
- Telnet stream observation (no passwords):
- SSH display-filter result:
- SSH stream observation:
- Any issues and how they were resolved:

## Security and evidence handling
- Use only the isolated lab environment or systems for which you have permission.
- Do not upload credentials, private keys, or sensitive traffic captures.
- Prefer screenshots with credentials and personal details masked.
- Raw packet captures are ignored by Git by default. If a capture is essential to demonstrate the lab, review and sanitise it before sharing, and only share traffic generated in the authorised lab.
