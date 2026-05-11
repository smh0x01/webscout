
<!-- Cyberpunk glow effect – GitHub may strip some CSS, but it adds flair locally -->
<div align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=28&duration=2000&pause=500&color=0FF&center=true&vCenter=true&width=600&lines=%F0%9F%94%A5+WEBSCOUT+%F0%9F%94%A5;Cyberdeck+for+the+Digital+Frontier;Discover.+Select.+Download." alt="WebScout" />
</div>

```
┬ ┬┌─┐┌┐ ┌─┐┌─┐┌─┐┬ ┬┌┬┐
│││├┤ ├┴┐└─┐│ │ ││ │ │
└┴┘└─┘└─┘└─┘└─┘└─┘└─┘ ┴
```
<p align="center">
  <code>Discover. Select. Download.</code>
</p>

---

# 🔍 **WEBSCOUT v2.0**  
### *Neon-Enhanced Web File Hunter*

[![Python](https://img.shields.io/badge/Python-3.7%2B-cyan?style=flat-square&logo=python)](https://python.org)
[![License](https://img.shields.io/badge/License-MIT-neon?style=flat-square)](LICENSE)
[![Status](https://img.shields.io/badge/Build-Cyberpunk%20Ready-ff00ff?style=flat-square)]()

**WebScout** is your all-in-one **cyber-deck tool** for sniffing out files on any website.  
It fuzzes paths like a brute-force daemon, crawls pages like a spider‑bot, and gives you a **neural interface** to pick exactly what you want – all at the speed of light over multithreaded connections.

---

## ⚡ **Cyber Modules**

- 🕵️ **Stealth Fuzzing** – Inject a custom wordlist into the target’s hidden corners.  
- 🧬 **Deep Crawling** – Recursively map the domain for linked resources.  
- 💻 **Interactive Terminal UI** – Hand‑pick files by type, pattern, directory or manual range.  
- ⛓️ **Resume & Skip** – Already grabbed files? We skip ’em. Interrupted? Resume right where you left off.  
- 🧪 **Extension Filters** – Hunt only `.pdf`, `.zip`, `.env`, `.sql` or whatever payload you need.  
- 🧠 **Memory Bank** – Discoveries are saved as JSON; reload them anytime to skip rescanning.  
- 🎨 **Hacker Aesthetic** – Colored output, progress bars, and cyberpunk vibes.

---

## 📡 **Installation – Jack In**

```bash
# Clone the repository
git clone https://github.com/smh0x01/webscout.git
cd webscout

# Install dependencies
pip install requests beautifulsoup4 colorama
```

*Or use the `requirements.txt` (create one with those three packages).*

---

## ⌨️ **Usage – Execute**

```bash
python webscout.py <TARGET_URL> [OPTIONS]
```

### Command‑Line Augments

| Flag | Description |
|------|-------------|
| `-w`, `--wordlist` | Custom wordlist file for fuzzing |
| `-e`, `--extensions` | Comma‑separated extensions (e.g. `.env,.sql,.zip`) |
| `-l`, `--depth` | Maximum crawl depth (default: 5) |
| `-t`, `--threads` | Number of parallel threads (default: 10) |
| `-d`, `--delay` | Delay between requests (default: 0.3s) |
| `-o`, `--output` | Where to drop downloaded files (default: `downloads`) |
| `--crawl-only` | Skip fuzzing – only follow links |
| `--fuzz-only` | Skip crawling – only blast paths |
| `--load-discovery` | Load previous scan from cache |
| `--no-interactive` | Download everything discovered (skip selection menu) |

---

## 🚀 **Quick Runs**

```bash
# Basic cyber‑scan with interactive selection
python webscout.py https://target.io

# Fuzz with a custom wordlist, grab only sensitive configs & backups
python webscout.py https://target.io -w ./wordlists/deep.txt -e .env,.conf,.bak,.sql

# Crawl only, download all found automatically
python webscout.py https://target.io --crawl-only --no-interactive

# Resume a previous session directly to selection
python webscout.py https://target.io --load-discovery

# Maximum speed – 20 threads, 0.1s delay
python webscout.py https://target.io -t 20 -d 0.1
```

---

## 🧠 **How the Neural Engine Works**

### **Phase 1 – Signal Scanning (Discovery)**
- **Fuzz Burst**: A swarm of HEAD/GET probes on common paths, admin panels, backup files, and more.  
- **Web Crawler**: Recursively parses HTML to extract every hidden asset (images, scripts, docs).  
- Results are stored in the `downloads/.metadata/discovery.json` “databank”.

### **Phase 2 – Neural Selection (Interactive Menu)**
- Hand‑pick your loot using an intuitive menu:  
  - By file extension (e.g., `.pdf`, `.zip`)  
  - By regex pattern (e.g., `backup.*`, `config`)  
  - By directory (`/uploads/`, `/admin/`)  
  - By individual index numbers  
- Preview your haul, clear, and reselect until it’s perfect.

### **Phase 3 – Extraction (Download)**
- Parallel download threads with resume support.  
- Already acquired files are skipped.  
- Final summary with execution time, success/failure counts.

---

## 💾 **Output**

All downloaded files land in your specified output directory (default: `downloads/`).  
The `.metadata` subfolder holds:

- `discovery.json` – full scan results  
- `download_history.json` – after‑action report

Use `--load-discovery` next time to skip right to the selection phase.

---

## 🤝 **Contribute to the Grid**

Pull requests, issue reports, and new wordlists are all welcome.  
Let’s make the digital frontier a little more transparent.

---

## ⚠️ **Disclaimer**

This tool is intended for **authorized security testing** and **educational purposes only**.  
Always obtain permission before scanning any network or website.  
**You are responsible for your own actions.**

---

<div align="center">

`Ｃｙｂｅｒ★ｐｕｎｋ ２.０`

</div>

---

## 👤 **Operator**

**smh0x01**  
[GitHub](https://github.com/smh0x01) · [Repository](https://github.com/smh0x01/webscout)
