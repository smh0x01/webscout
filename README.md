```markdown
# WebScout – Intelligent Web File Discovery & Download Engine

WebScout is a powerful Python tool that helps you **discover**, **select**, and **download** files from any website. It combines fast fuzzing (path brute-forcing) with traditional crawling, then offers an interactive menu to cherry-pick what you want to download – all with multithreading and resume support.

![Python](https://img.shields.io/badge/Python-3.7%2B-blue)
![License](https://img.shields.io/badge/license-MIT-green)

---

## Features

- 🔍 **Smart Discovery** – Combine fuzzing with a built‑in wordlist and recursive crawling to find hidden files and directories.
- 📋 **Interactive Selection** – Hand‑pick files by type, regex, directory, or manual numbering. Preview your selection before downloading.
- ⚡ **Multithreaded** – Scan and download with configurable thread count for maximum speed.
- ⏸️ **Resume Support** – Downloads can be paused and resumed. Already downloaded files are skipped.
- 🎯 **Extension Filtering** – Only look for (or download) files with specific extensions (e.g. `.pdf`, `.jpg`, `.zip`).
- 🧠 **Custom Wordlists** – Use your own wordlist for fuzzing in addition to the default 100+ common paths.
- 💾 **Metadata Saving** – Discoveries are saved as JSON, so you can re‑use results without rescanning.
- 🌈 **Colorful Output** – Console output with colored status icons and progress bars.

---

## Installation

### Requirements

- Python 3.7 or higher
- pip

### Install dependencies

```bash
pip install requests beautifulsoup4 colorama
```

*Alternatively, install from `requirements.txt`:*

```bash
pip install -r requirements.txt
```

*(Create a `requirements.txt` with the three packages above.)*

### Clone the repository

```bash
git clone https://github.com/smh0x01/webscout.git
cd webscout
```

---

## Usage

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

## Examples

1. **Basic scan and interactive download**  
   ```bash
   python webscout.py https://example.com
   ```

2. **Use a custom wordlist and only look for PDF/JPEG files**  
   ```bash
   python webscout.py https://example.com -w my_words.txt -e .pdf,.jpg
   ```

3. **Crawl only (no fuzzing), then download everything automatically**  
   ```bash
   python webscout.py https://example.com --crawl-only --no-interactive
   ```

4. **Load a previous discovery and enter interactive selection**  
   ```bash
   python webscout.py https://example.com --load-discovery
   ```

5. **Aggressive scanning with 20 threads and minimal delay**  
   ```bash
   python webscout.py https://example.com -t 20 -d 0.1
   ```

---

## How It Works

WebScout operates in **three phases**:

### 1. Discovery (Fuzzing + Crawling)
- **Fuzzing**: Sends HEAD/GET requests to a list of common paths (e.g. `admin/`, `robots.txt`, `backup.zip`).  
- **Crawling**: Parses HTML pages within the same domain to extract links to other resources (images, scripts, documents, etc.).  
- All discovered files and directories are stored in memory and saved to `downloads/.metadata/discovery.json`.

### 2. Interactive Selection
- A menu lets you **precisely choose** what to download.  
- Select by file extension, regex pattern, specific index numbers, or entire directories.  
- You can review your selection, clear it, and re‑select as many times as you like.

### 3. Download
- Selected files are downloaded in parallel using multiple threads.  
- The tool checks for previously downloaded files and resumes partial downloads if possible.  
- A final summary shows time, success/failure counts, and the output location.

---

## Output

All downloaded files are placed in the directory specified with `-o` (default: `downloads/`).  
Metadata (discovery and download history) is stored in `downloads/.metadata/`.

After a successful scan you can:
- Re‑run with `--load-discovery` to skip scanning and go straight to selection/download.
- Inspect `discovery.json` to see all found paths and their sizes.

---

## Contributing

Pull requests and issues are welcome!  
Feel free to suggest new features, improve wordlists, or fix bugs.

---

## License

This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.

---

## Author

**smh0x01**  
GitHub: [https://github.com/smh0x01](https://github.com/smh0x01)  
Tool repo: [https://github.com/smh0x01/webscout](https://github.com/smh0x01/webscout)

---

> *“Discover. Select. Download.”* 🚀
```
