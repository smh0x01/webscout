<!-- Cyberpunk glow effect – GitHub may strip some CSS, but it adds flair locally -->
<div align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=28&duration=2000&pause=500&color=0FF&center=true&vCenter=true&width=600&lines=%F0%9F%94%A5+WEBSCOUT+%F0%9F%94%A5;Discover.+Select.+Download.;Cyber+File+Hunter" alt="WebScout" />
</div>


```markdown
┬ ┬┌─┐┌┐ ┌─┐┌─┐┌─┐┬ ┬┌┬┐
│││├┤ ├┴┐└─┐│ │ ││ │ │
└┴┘└─┘└─┘└─┘└─┘└─┘└─┘ ┴

Discover. Select. Download.
```

[![Python](https://img.shields.io/badge/Python-3.7%2B-00ffff?style=for-the-badge&logo=python&logoColor=ff00ff)](https://python.org)
[![Status](https://img.shields.io/badge/Status-Active-00ffff?style=for-the-badge)]()

**WebScout** is a powerful Python tool that helps you **discover**, **select**, and **download** files from any website. It combines fast fuzzing (path brute-forcing) with traditional crawling, then offers an interactive menu to cherry-pick what you want to download – all with multithreading and resume support.

---

## ✨ Features

-  **Smart Discovery** – Combine fuzzing with a built‑in wordlist and recursive crawling to find hidden files and directories.
-  **Interactive Selection** – Hand‑pick files by type, regex, directory, or manual numbering. Preview your selection before downloading.
-  **Multithreaded** – Scan and download with configurable thread count for maximum speed.
-  **Resume Support** – Downloads can be paused and resumed. Already downloaded files are skipped.
-  **Extension Filtering** – Only look for (or download) files with specific extensions (e.g. `.pdf`, `.jpg`, `.zip`).
-  **Custom Wordlists** – Use your own wordlist for fuzzing in addition to the default 100+ common paths.
-  **Metadata Saving** – Discoveries are saved as JSON, so you can re‑use results without rescanning.
-  **Colorful Output** – Console output with colored status icons and progress bars.

---

## 📦 Installation

### Requirements

- Python 3.7 or higher
- pip

### Install Dependencies

```bash
pip install requests beautifulsoup4 colorama
```

*Alternatively, install from `requirements.txt`:*

```bash
pip install -r requirements.txt
```

### Clone the Repository

```bash
git clone https://github.com/smh0x01/webscout.git
cd webscout
```

---

## 🚀 Usage

```bash
python webscout.py <URL> [options]
```

### Options

| Flag / Argument        | Description                                                                 |
|------------------------|-----------------------------------------------------------------------------|
| `url`                  | Target URL to scan and download from (required)                             |
| `-w`, `--wordlist`     | Custom wordlist file for fuzzing                                            |
| `-e`, `--extensions`   | File extensions to focus on (comma-separated, e.g. `.pdf,.jpg`)             |
| `-l`, `--depth`        | Maximum crawl depth (default: 5)                                            |
| `-t`, `--threads`      | Number of threads for checking/downloading (default: 10)                    |
| `-d`, `--delay`        | Delay between requests in seconds (default: 0.3)                            |
| `-o`, `--output`       | Output directory (default: `downloads`)                                     |
| `--crawl-only`         | Skip fuzzing, only crawl links                                              |
| `--fuzz-only`          | Skip crawling, only fuzz paths                                              |
| `--load-discovery`     | Load a previous discovery file instead of scanning again                    |
| `--no-interactive`     | Download all discovered files automatically (skip the selection menu)       |

---

## 💡 Examples

```bash
# Basic scan with interactive selection
python webscout.py https://example.com

# Use a custom wordlist and only look for PDF/JPEG files
python webscout.py https://example.com -w my_words.txt -e .pdf,.jpg

# Crawl only (no fuzzing), then download everything automatically
python webscout.py https://example.com --crawl-only --no-interactive

# Load a previous discovery and enter interactive selection
python webscout.py https://example.com --load-discovery

# Aggressive scanning with 20 threads and minimal delay
python webscout.py https://example.com -t 20 -d 0.1
```

---

## ⚙️ How It Works

WebScout operates in **three phases**:

### Phase 1 – Discovery (Fuzzing + Crawling)
- **Fuzzing**: Sends HEAD/GET requests to a list of common paths (e.g. `admin/`, `robots.txt`, `backup.zip`).  
- **Crawling**: Parses HTML pages within the same domain to extract links to other resources (images, scripts, documents, etc.).  
- All discovered files and directories are stored in memory and saved to `downloads/.metadata/discovery.json`.

### Phase 2 – Interactive Selection
- A menu lets you **precisely choose** what to download.  
- Select by file extension, regex pattern, specific index numbers, or entire directories.  
- You can review your selection, clear it, and re‑select as many times as you like.

### Phase 3 – Download
- Selected files are downloaded in parallel using multiple threads.  
- The tool checks for previously downloaded files and resumes partial downloads if possible.  
- A final summary shows time, success/failure counts, and the output location.

---

## 📁 Output

All downloaded files are placed in the directory specified with `-o` (default: `downloads/`).  
Metadata (discovery and download history) is stored in `downloads/.metadata/`.

After a successful scan you can:
- Re‑run with `--load-discovery` to skip scanning and go straight to selection/download.
- Inspect `discovery.json` to see all found paths and their sizes.

---

## ⚠️ Disclaimer

This tool is intended for **authorized security testing** and **educational purposes only**.  
Always obtain permission before scanning any network or website.  
**You are responsible for your own actions.**

---

## 👤 Author

**smh0x01**  
[GitHub](https://github.com/smh0x01) · [Repository](https://github.com/smh0x01/webscout)

---

<div align="center">

> *"Discover. Select. Download."*

</div>
```
