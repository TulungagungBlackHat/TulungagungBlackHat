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

> **Authorization policy:** these tools are for education and for testing systems you own or are explicitly authorized to test. Unauthorized access is abuse, not hacking. See [SECURITY.md](https://github.com/TulungagungBlackHat/TBH-Recon/blob/main/SECURITY.md).

---

## Quick Start

Install the full toolset in one line (Termux / Kali / Linux):

```bash
curl -sSL https://raw.githubusercontent.com/TulungagungBlackHat/TBH-Toolkit/main/install.sh | bash
```

Or grab a single tool:

```bash
git clone https://github.com/TulungagungBlackHat/TBH-Recon
cd TBH-Recon
pip install -r requirements.txt
python3 main.py --help
```

Prefer a plain CLI with no JSON output? Use [`TBH-CLI`](https://github.com/TulungagungBlackHat/TBH-CLI). Want everything in one scanner? Use [`TBH-AllScan`](https://github.com/TulungagungBlackHat/TBH-AllScan) (`python3 allscan.py --help`).

---

## Toolset

### Recon & Discovery
| Tool | What it does |
|------|--------------|
| [**TBH-Recon**](https://github.com/TulungagungBlackHat/TBH-Recon) | Web recon: headers, ports, subdomains in one pass |
| [**TBH-SubFinder**](https://github.com/TulungagungBlackHat/TBH-SubFinder) | Subdomain enumeration (25+ wordlist entries, JSON output) |
| [**TBH-DirFinder**](https://github.com/TulungagungBlackHat/TBH-DirFinder) | Directory discovery, flags leaked `.git` / `.env` files |
| [**TBH-ParamFinder**](https://github.com/TulungagungBlackHat/TBH-ParamFinder) | Hidden parameter discovery (IDOR / XSS hunting) |
| [**TBH-JSLeak**](https://github.com/TulungagungBlackHat/TBH-JSLeak) | Secrets hunting in JavaScript: API keys, tokens |

### Web Vulnerability Detectors (safe probes)
| Tool | What it does |
|------|--------------|
| [**TBH-XSS**](https://github.com/TulungagungBlackHat/TBH-XSS) | Reflected XSS detector |
| [**TBH-SQLi**](https://github.com/TulungagungBlackHat/TBH-SQLi) | SQL injection detector (safe payloads) |
| [**TBH-LFI**](https://github.com/TulungagungBlackHat/TBH-LFI) | Local file inclusion detector |
| [**TBH-SSRF**](https://github.com/TulungagungBlackHat/TBH-SSRF) | SSRF misconfiguration detector |
| [**TBH-SSTI**](https://github.com/TulungagungBlackHat/TBH-SSTI) | Server-side template injection detector |
| [**TBH-OpenRedirect**](https://github.com/TulungagungBlackHat/TBH-OpenRedirect) | Open redirect detector |
| [**TBH-IDOR**](https://github.com/TulungagungBlackHat/TBH-IDOR) | IDOR detector |
| [**TBH-CORS**](https://github.com/TulungagungBlackHat/TBH-CORS) | CORS misconfiguration detector |

### Bug Bounty Workflow
| Tool | What it does |
|------|--------------|
| [**TBH-AllScan**](https://github.com/TulungagungBlackHat/TBH-AllScan) | All-in-one scanner (10 modules, JSON + HTML reports) |
| [**TBH-BugBounty**](https://github.com/TulungagungBlackHat/TBH-BugBounty) | Hunter toolkit: headers, SSL, ports, subdomains — JSON for HackerOne |
| [**TBH-CLI**](https://github.com/TulungagungBlackHat/TBH-CLI) | Lightweight pure-CLI edition for Termux |
| [**TBH-Toolkit**](https://github.com/TulungagungBlackHat/TBH-Toolkit) | One-click installer for the whole toolset (Bash) |

### Network & Defensive
| Tool | What it does |
|------|--------------|
| [**TBH-PortScanner**](https://github.com/TulungagungBlackHat/TBH-PortScanner) | 100-thread port scanner with banner grabbing + CVE hints |
| [**TBH-PhishDetector**](https://github.com/TulungagungBlackHat/TBH-PhishDetector) | Phishing URL detector (9 heuristics) |
| [**TBH-PassStrength**](https://github.com/TulungagungBlackHat/TBH-PassStrength) | Password strength checker (defensive) |
| [**TBH-Utils**](https://github.com/TulungagungBlackHat/TBH-Utils) | Everyday utilities: QR, Base64, hashes, URLs |

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
- **CI:** smoke tests (`py_compile` + `--help`) on every ACTIVE repo
- **Docs:** `SECURITY.md` + `CONTRIBUTING.md` + `CHANGELOG.md` in every ACTIVE repo
- **Dependencies:** `requests` + standard library only — runs on a stock Termux install
- **Targets:** `127.0.0.1`, RFC1918 lab networks, `example.*` domains, or hosts with explicit written permission

Found a bug in one of our tools? Open a [security advisory](https://github.com/TulungagungBlackHat/TBH-Recon/security/advisories/new) — not a public issue.

Contributions welcome: fork, branch, test, PR. See [CONTRIBUTING.md](https://github.com/TulungagungBlackHat/TBH-Recon/blob/main/CONTRIBUTING.md).

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
