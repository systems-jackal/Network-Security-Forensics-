# Linux Administration Roadmap

Scope: Linux fundamentals through to basic hardening, built for a backend dev with zero prior sysadmin experience. Server/CLI-focused throughout — no desktop-Linux distractions.

Structure: complete the **Linux Upskill Challenge** end to end first as your foundation, then go back through and deep-dive each major area beyond what the 20-day course covers.

---

## Stage 1 — Complete the Linux Upskill Challenge (Weeks 1–3)

[linuxupskillchallenge.org](https://linuxupskillchallenge.org/) — free, 20-day, hands-on course. You spin up and administer your own real Linux server from Day 0 and work through it day by day. Restarts on the first Monday of every month if you want a cohort, but it's fully self-paced.

**Do the whole thing straight through before branching into the deep-dive stages below.** It covers, in order:
- Server setup, SSH, shell navigation, package management (Days 0–5)
- Filesystem, permissions, users/groups, processes (Days 6–13)
- Networking basics, firewalls, systemd/services (Days 9, 14–17)
- Logs, log rotation, shell scripting fundamentals (Days 18–20)

Log each day's work in `notes/stage1-upskill-challenge.md` as you go — one entry per day is enough. Treat this stage as your baseline: everything in Stages 2–5 assumes you've finished it.

➡️ **Chains into Stages 2–5**: the course gives you working competence in each area; the deep-dive stages below take each one further than a 20-day course has room for.

---

## Stage 2 — Deep Dive: Filesystem, Permissions, Users & Access Control (2–3 weeks)
Go beyond what the course covers on Linux's access model:
- Full permission model: `rwx`, special bits (SUID, SGID, sticky bit), `umask`.
- Access Control Lists (`setfacl`/`getfacl`) for permissions beyond the basic owner/group/other model.
- `sudo` configuration in depth — `/etc/sudoers`, `visudo`, least-privilege sudo rules.
- User/group management at scale: bulk user creation, password policies, account expiry.
- Filesystem internals: inodes, hard vs symbolic links, disk usage tools (`du`, `df`, `ncdu`).

➡️ Supplement with: **OverTheWire: Bandit** (overthewire.org/wargames/bandit) for puzzle-based reinforcement of permissions/filesystem concepts.

Mini-project: **`user-audit-tool`** — script that reports users with sudo access, weak/no password expiry, unused or stale accounts.

---

## Stage 3 — Deep Dive: Networking, Services & Firewalls (2–3 weeks)
This is where the Linux track overlaps your networking-security track — worth running in parallel with that track's Stage 2 if timing allows.
- CLI networking tools in depth: `ss`, `ip`, `nmap`, `netstat`/`ss` comparisons.
- Firewall configuration beyond `ufw` basics: `iptables`/`nftables` rule writing, stateful vs stateless rules.
- systemd in depth: writing your own unit files, timers (cron replacement), dependency ordering, `journalctl` filtering.
- Installing, configuring, and securing a real service end to end (web server, database, etc.) — includes binding to specific interfaces, running as a non-root user, basic service hardening.

➡️ Supplement with: **DigitalOcean Community Tutorials** — strongest free source specifically for systemd/services/process management depth.

Mini-project: **`systemd-service-monitor`** — script that checks a list of services and alerts if any are down or misconfigured.

---

## Stage 4 — Deep Dive: Logs, Scripting & Automation (2–3 weeks)
- Log architecture: `rsyslog`/`journald`, centralizing logs, structured vs unstructured logs.
- `logrotate` configuration in depth — custom rotation policies, compression, post-rotation hooks.
- Shell scripting beyond fundamentals: functions, arrays, trap/error handling, argument parsing (`getopts`), writing scripts meant to run unattended (cron-safe scripting).
- Text processing at depth: `awk`, `sed`, `grep` with regex, chaining pipelines for real log analysis.

➡️ Supplement with: **ShellCheck** (shellcheck.net) — run every script through it, non-negotiable habit from here on. Also: bash chapters of **The Linux Command Line** by William Shotts (free PDF, linuxcommand.org/tlcl.php).

Mini-project: **`log-rotation-script`** — grows directly out of the course's Day 18 exercise; extend it into something genuinely reusable with configurable rules.

---

## Stage 5 — Deep Dive: Hardening & Auditing (3–4 weeks)
The most security-relevant stage — this is where "Linux admin" becomes "Linux security."
- **CIS Benchmarks for Linux** (cisecurity.org) — the industry standard for hardened Linux. Work through benchmark items one at a time, applying and verifying each on your lab server.
- SSH hardening: key-only auth, disabling root login, changing default ports, `fail2ban`.
- Audit tooling: `auditd` rules, reviewing SUID/SGID binaries, checking cron jobs and startup services for anything unexpected.
- Kernel/network hardening basics: `sysctl` parameters relevant to security (IP forwarding, SYN cookies, etc.) — ties back to networking-security Stage 2.
- Minimal attack surface principles: removing unused packages/services, closing unused ports.

➡️ Optional formal course: **Linux Foundation's "Introduction to Linux" (LFS101)** on edX, free, if you want a more structured/certificate-adjacent supplement.

Mini-project: **`hardening-checklist-scanner`** — script that checks a server against a set of CIS Benchmark items and reports pass/fail, with remediation suggestions.

---

## Lab environment
Reuse the VM lab already built for the networking-security track — don't stand up a separate Linux environment. Run your Upskill Challenge server as one of your existing VMs so notes and mini-projects tie back into the same lab throughout all five stages.

## Notes & commit habit
One notes file per stage (`stage1-upskill-challenge.md`, `stage2-permissions.md`, `stage3-networking-services.md`, `stage4-logs-scripting.md`, `stage5-hardening.md`). Keep them messy — this is a study log, not a polished document. Commit as you go, not in one batch at the end.

## Rough timeline
Stage 1: 2–3 weeks (course pace, ~1–2 hrs/day). Stages 2–5: 2–4 weeks each depending on depth pursued. Total: roughly 12–16 weeks part-time for the full track.
