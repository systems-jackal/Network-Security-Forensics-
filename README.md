# Security Portfolio

A hands-on learning log and project portfolio covering **network security & forensics** and **Linux**, built from scratch and documented as I go. Each track has its own notes, mini-projects, and tools — everything here is actually run in a lab, not just read about.

## Why this repo exists

I'm learning these skills in public: every lab, script, and write-up here reflects what I actually did, what broke, and what I learned from it. The goal is to end up with working tools and real incident reconstructions, not just tutorial completions.

## Tracks

### 🌐 [`networking-security/`](./networking-security)
Networking fundamentals → network security → traffic analysis → flow monitoring → network forensics capstone.

| Stage | Focus | Status |
|---|---|---|
| [Stage 1](./networking-security/stage1-networking) | OSI/TCP-IP fundamentals, subnetting, lab setup | 🔄 In progress |
| [Stage 2](./networking-security/stage2-network-security) | Firewalls, VPNs, common attacks (ARP/DNS spoofing, scanning) | ⬜ Not started |
| [Stage 3](./networking-security/stage3-traffic-analysis) | Wireshark/tcpdump, pcap analysis | ⬜ Not started |
| [Stage 4](./networking-security/stage4-flow-monitoring) | Zeek, Suricata, flow-based detection | ⬜ Not started |
| [Stage 5](./networking-security/stage5-forensics-capstone) | Full incident reconstruction (capstone) | ⬜ Not started |

### 🐧 [`linux/`](./linux)
Filesystem & permissions, processes & services, shell scripting, users & groups — building toward general Linux administration and hardening skills.

| Area | Status |
|---|---|
| Filesystem & permissions | ⬜ Not started |
| Processes & services | ⬜ Not started |
| Shell scripting | ⬜ Not started |
| Users & groups | ⬜ Not started |

*(Update the tables above as you move through each stage — swap ⬜ for 🔄 then ✅.)*

## Structure

Each track follows the same internal pattern:

```
<track>/
├── README.md          <- what this track covers, its own mini-roadmap
├── notes/              <- raw learning notes, messy is fine, organized by topic
├── mini-projects/       <- small, complete, standalone tools — one folder each
└── tools/               <- scripts reused across the track's stages
```

- **`notes/`** — my study log. Concepts, commands, diagrams, mistakes. Not polished, but consistent.
- **`mini-projects/`** — small finished builds that demonstrate a specific skill end to end. Each has its own README: problem → approach → how to run it → limitations.
- **`tools/`** — scripts that get reused and improved across a track's stages, versioned like real code rather than one-off throwaway files.

## Highlighted work

*(Fill this in as mini-projects and the capstone land — link your best 2-3 pieces here so they're not buried.)*

- Coming soon: Stage 5 incident report (network forensics capstone)
- Coming soon: ARP spoof detector (mini-project)

## Lab environment

Networking/security labs are built in VirtualBox/GNS3 with a Kali attacker VM, plain Linux/Windows victim VMs, and a monitoring VM running Zeek + Suricata. Full setup details are in [`networking-security/stage1-networking/README.md`](./networking-security/stage1-networking).

## Setup notes

- No real/sensitive network captures are ever committed — only lab-generated traffic.
- See `.gitignore` for excluded file types (credentials, real pcaps, etc).

---

*This repo is a work in progress and updated regularly as I move through each stage.*
