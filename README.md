<img src="https://capsule-render.vercel.app/api?type=waving&color=0:000000,100:FF0000&height=200&section=header&text=TULUNGAGUNG%20BLACK%20HAT&fontSize=45&fontColor=ffffff&animation=fadeIn&fontAlignY=35&desc=Ethical%20Hacking%20%26%20Bug%20Bounty%20Tooling&descAlignY=55&descAlign=50" />

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=22&pause=1000&color=FF0000&center=true&vCenter=true&width=600&lines=Open-source+security+tools+from+Indonesia;Termux-friendly+%C2%B7+MIT+licensed+%C2%B7+tests+you+can+read;Always+Smile+%3A%29" alt="Typing SVG" />
</p>

<p align="center">
  <a href="https://tulungagungblackhat.github.io"><img src="https://img.shields.io/badge/Website-tulungagungblackhat.github.io-FF0000?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Website"></a>
  <a href="https://github.com/TulungagungBlackHat/TBH-Toolkit"><img src="https://img.shields.io/badge/Install-1--liner-2ea44f?style=for-the-badge&logo=github&logoColor=white" alt="Install"></a>
  <img src="https://img.shields.io/badge/License-MIT-red?style=for-the-badge" alt="License">
  <img src="https://img.shields.io/badge/Platform-Termux%20%7C%20Linux%20%7C%20Kali-000000?style=for-the-badge" alt="Platform">
  <a href="https://github.com/TulungagungBlackHat?tab=followers"><img src="https://img.shields.io/github/followers/TulungagungBlackHat?label=Followers&style=for-the-badge&color=black" alt="Followers"></a>
</p>

---

## About

**Tulungagung Black Hat (TBH)** is an open-source security tooling project from Tulungagung, East Java, Indonesia. We build small, auditable Python tools for **bug bounty reconnaissance, web vulnerability detection, and defensive checks** — designed to run on Termux, Kali, or any Linux box with nothing more than `requests` and the standard library.

Every ACTIVE repository ships with `SECURITY.md`, `CONTRIBUTING.md`, `CHANGELOG.md`, `requirements.txt`, and a CI smoke test. No black boxes, no "trust me bro" scripts.

> **Authorization policy:** these tools are for education and for testing systems you own or are explicitly authorized to test. Unauthorized access is abuse, not hacking. See [SECURITY.md](https://github.com/TulungagungBlackHat/TBH-Toolkit/blob/main/SECURITY.md).

---

## Quick Start

Install the full toolset in one line (Termux / Kali / Linux):

```bash
curl -sSL https://raw.githubusercontent.com/TulungagungBlackHat/TBH-Toolkit/main/install.sh | bash
```

Or grab the one repo directly:

```bash
git clone --depth 1 https://github.com/TulungagungBlackHat/TBH-Toolkit
python3 TBH-Toolkit/tbh        # numbered menu
python3 TBH-Toolkit/tbh ui     # curses UI
```

Every subcommand also works headless (`python3 tbh recon -u https://example.com --ssl`),
and `python3 tbh config set proxy http://127.0.0.1:8080` makes all of them share your proxy.

---

## Toolset

Everything lives in **[TBH-Toolkit](https://github.com/TulungagungBlackHat/TBH-Toolkit)**
now — one clone, one `tbh` command, numbered menu + curses UI.

| Subcommand | What it does |
|------------|--------------|
| `tbh scan` | Many tools at once against one target, combined JSON/HTML report |
| `tbh recon` | Web recon: headers, SSL, ports, subdomains in one pass |
| `tbh subfinder` | Subdomain enumeration + CNAME takeover check |
| `tbh dirfinder` | Directory discovery with `--depth` recursion, `.git`/`.env` leaks |
| `tbh paramfinder` | Hidden parameter discovery (active + passive) |
| `tbh jsleak` | Secrets hunting in JavaScript |
| `tbh xss` | Reflected XSS (multi-payload, blind callback) |
| `tbh sqli` | Error-based SQL injection |
| `tbh lfi` | Path traversal / LFI |
| `tbh ssrf` | SSRF (URL params, OOB collab) |
| `tbh ssti` | Template injection (dual-math) |
| `tbh redirect` | Open redirect |
| `tbh idor` | IDOR probe |
| `tbh cors` | CORS misconfiguration |
| `tbh portscan` | Port scan: top-100, banners, CVE hints |
| `tbh phish` | Phishing URL heuristics |
| `tbh passstrength` | Password strength + generator |
| `tbh utils` | base64 / url / hash / jwt / qr utilities |
| `tbh web` | 34-module web check suite + HTML report (old TBH-CLI) |
| `tbh ui` · `config` · `findings` | curses UI, shared proxy/cookie store, saved findings |

The old per-tool repositories (TBH-Recon, TBH-XSS, ...) are archived —
each has a banner pointing to the monorepo.

### Learning & Community
| Project | What it is |
|---------|------------|
| [**TBH-CTF**](https://github.com/TulungagungBlackHat/TBH-CTF) | Mini CTF for beginners: crypto, web, forensics |
| [**awesome-tulungagung**](https://github.com/TulungagungBlackHat/awesome-tulungagung) | Curated Indonesian cyber security resources |
| [**Portfolio**](https://tulungagungblackhat.github.io) | Project website and write-ups |

<details>
<summary><b>Legacy projects (kept for history)</b></summary>

- [`darkfb`](https://github.com/TulungagungBlackHat/darkfb) — educational Facebook security testing simulator (Python 2.7, EOL)
- [`uchil404-ddos`](https://github.com/TulungagungBlackHat/uchil404-ddos) — stress-testing lab tool; unsafe capabilities intentionally not preserved
- [`DEFACE`](https://github.com/TulungagungBlackHat/DEFACE) — archived fork

Safe replacements for anything above live in [TBH-Toolkit](https://github.com/TulungagungBlackHat/TBH-Toolkit).

</details>

---

## Standards

- **License:** MIT across the toolset
- **CI:** smoke tests on [TBH-Toolkit](https://github.com/TulungagungBlackHat/TBH-Toolkit) (compile + every subcommand `--help`)
- **Docs:** `SECURITY.md` + `CONTRIBUTING.md` + `CHANGELOG.md` in the toolkit
- **Dependencies:** `requests` + standard library only — runs on a stock Termux install
- **TBH v3 CLI:** shared flags (`--proxy`, `--cookie`, `-H`, `--timeout`, `--json`, `--version`, `--no-color`) and pipeline exit codes (`0` clean / `1` finding / `2` error) across tools; detectors baseline the request first to cut false positives
- **Targets:** `127.0.0.1`, RFC1918 lab networks, `example.*` domains, or hosts with explicit written permission

Found a bug in one of our tools? Open a [security advisory](https://github.com/TulungagungBlackHat/TBH-Toolkit/security/advisories/new) — not a public issue.

Contributions welcome: fork, branch, test, PR. See [CONTRIBUTING.md](https://github.com/TulungagungBlackHat/TBH-Toolkit/blob/main/CONTRIBUTING.md).

---

## GitHub Stats

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=TulungagungBlackHat&show_icons=true&theme=dark&hide_border=true&bg_color=0D1117&title_color=FF0000&icon_color=FF0000" width="48%" alt="GitHub stats">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=TulungagungBlackHat&theme=dark&hide_border=true&background=0D1117&ring=FF0000&fire=FF0000" width="48%" alt="Streak stats">
</p>

---

<p align="center">
  <a href="https://www.youtube.com/channel/UCZafyhwr-38rDM5rBlgl4Og"><img src="https://img.shields.io/badge/YouTube-Tulungagung_Black_Hat-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="YouTube"></a>
  <br><br>
  <img src="https://komarev.com/ghpvc/?username=TulungagungBlackHat&label=Profile+Views&color=FF0000&style=flat" alt="Profile views">
  <br><br>
  <b>Always Smile :)</b> — Tulungagung, East Java, Indonesia
</p>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:FF0000,100:000000&height=120&section=footer" />
