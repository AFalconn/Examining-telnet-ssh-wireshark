# Examining Telnet and SSH in Wireshark

## Project overview
This project documents a controlled lab comparing Telnet and SSH traffic using Wireshark on the CyberOps Workstation virtual machine. The lab demonstrates why SSH is preferred for remote administration: Telnet transmits session data in readable plaintext, while SSH encrypts the session payload.

## Objectives
- Capture a Telnet session on the loopback (`lo`) interface.
- Filter Telnet traffic and inspect it using **Follow → TCP Stream**.
- Capture an SSH session on `lo`.
- Filter SSH traffic and inspect its TCP stream.
- Compare plaintext exposure with encrypted traffic and document findings.

## Environment and scope
- **Platform:** CyberOps Workstation VM
- **Tool:** Wireshark
- **Interface:** Loopback (`lo`)
- **Traffic:** Localhost Telnet and SSH sessions only

> Safety note: Perform this lab only in the supplied lab VM or another system you own or are authorised to test. Do not capture real users' credentials. Never commit passwords, private keys, or unredacted captures containing credentials.

## Repository structure
```text
examining-telnet-ssh-wireshark/
├── README.md
├── .gitignore
├── docs/
│   ├── lab-notes.md
│   └── reflection.md
├── evidence/
│   ├── screenshots/
│   │   └── README.md
│   ├── pcap/
│   │   └── README.md
│   └── notes/
│       └── README.md
├── lab-files/
│   └── README.md
└── reports/
    └── findings.md
```

## Workflow
1. Review `docs/lab-notes.md`.
2. Complete the Telnet capture and record observations.
3. Complete the SSH capture and record observations.
4. Save screenshots in `evidence/screenshots/` after removing or masking credentials and sensitive information.
5. Write up the comparison in `reports/findings.md` and answer the reflection question in `docs/reflection.md`.
6. Follow the Git Bash instructions below to publish the repository.

## Git Bash: create and push a GitHub repository
Create an **empty** repository on GitHub first. Suggested repository name: `examining-telnet-ssh-wireshark`. Do not initialise it with a README, licence, or `.gitignore` because this project already includes those files.

Open Git Bash and move into the folder where you extracted this project. Example:
```bash
cd ~/Downloads/telnet-ssh-wireshark-github-workflow
```

Then run:
```bash
git init
git branch -M main
git add .
git status
git commit -m "Add Telnet and SSH Wireshark lab documentation"
git remote add origin https://github.com/YOUR-USERNAME/examining-telnet-ssh-wireshark.git
git push -u origin main
```
Replace `YOUR-USERNAME` with your GitHub username. If `git remote add origin` says the remote already exists, inspect it using `git remote -v`; update it with:
```bash
git remote set-url origin https://github.com/YOUR-USERNAME/examining-telnet-ssh-wireshark.git
```

## Suggested GitHub repository details
- **Repository name:** `examining-telnet-ssh-wireshark`
- **Description:** `Cybersecurity lab comparing Telnet plaintext traffic and SSH encrypted sessions using Wireshark on a CyberOps Workstation VM. Includes lab notes, evidence folders, findings, and reflection.`
- **Suggested topics:** `wireshark`, `telnet`, `ssh`, `network-security`, `packet-analysis`, `cybersecurity-lab`

## Evidence checklist
- [ ] Telnet capture with `telnet` display filter visible
- [ ] Telnet Follow TCP Stream showing the plaintext behaviour, with credentials masked
- [ ] SSH capture with `ssh` display filter visible
- [ ] SSH Follow TCP Stream showing encrypted/unreadable payload
- [ ] Brief notes describing the difference
- [ ] Reflection answer explaining why SSH is preferred

## Key finding
Telnet does not encrypt its session, so credentials and session content can be exposed in plaintext. SSH encrypts the connection, protecting credentials and data in transit when configured and used correctly.
