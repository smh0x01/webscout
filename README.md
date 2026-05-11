# 
┬ ┬┌─┐┌┐ ┌─┐┌─┐┌─┐┬ ┬┌┬┐
│││├┤ ├┴┐└─┐│  │ ││ │ │ 
└┴┘└─┘└─┘└─┘└─┘└─┘└─┘ ┴ 

<div align="center">
┬ ┬┌─┐┌┐ ┌─┐┌─┐┌─┐┬ ┬┌┬┐
│││├┤ ├┴┐└─┐│ │ ││ │ │
└┴┘└─┘└─┘└─┘└─┘└─┘└─┘ ┴

Discover. Select. Download.
# 🔍 WebScout

**Intelligent Web File Discovery & Download Tool**

[![Python](https://img.shields.io/badge/Python-3.7%2B-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![OSINT](https://img.shields.io/badge/OSINT-Ready-red.svg)](#)

*Scout the web. Select your target. Snag the files.*

</div>

---

## 📖 Table of Contents
- [What is WebScout?](#-what-is-webscout)
- [Features](#-features)
- [Installation](#-installation)
- [Quick Start](#-quick-start)
- [Usage](#-usage)
- [Command-Line Options](#-command-line-options)
- [Interactive Menu](#-interactive-menu)
- [How It Works](#-how-it-works)
- [Use Cases](#-use-cases)
- [Output Structure](#-output-structure)
- [Screenshots](#-screenshots)
- [Requirements](#-requirements)
- [Contributing](#-contributing)
- [Author](#-author)
- [License](#-license)

---

## 🎯 What is WebScout?

WebScout is a powerful command-line OSINT tool that discovers hidden files and directories on any website, then lets you **interactively select** and download exactly what you need.

Think of it as **wget on steroids** — it doesn't just download blindly. It first **scouts** the entire website to find hidden content, then gives you a smart menu to filter and pick files before downloading.

### The Three-Phase Approach:

| Phase | Name | What Happens |
|:-----:|------|-------------|
| **1** | 🔍 **Discovery** | Fuzzes 100+ common paths + crawls links to find all available files & directories |
| **2** | 🎯 **Selection** | Interactive menu to filter by extension, regex pattern, directory, or hand-pick files |
| **3** | 💾 **Download** | Multi-threaded downloads with progress bars, resume support, and retry logic |

---

## ✨ Features

### 🔍 Smart Discovery
- **Path Fuzzing**: Checks 100+ common paths (admin panels, backups, configs, uploads, etc.)
- **Link Crawling**: Follows links on pages to find additional content
- **Custom Wordlists**: Bring your own wordlist for targeted fuzzing
- **Extension Filtering**: Only discover files of specific types (`.pdf`, `.zip`, `.jpg`, etc.)

### 🎯 Interactive Selection
- **Filter by Extension**: Grab all PDFs, ZIPs, or images with one command
- **Regex Pattern Search**: Find files matching complex patterns
- **Directory Selection**: Download everything from a specific folder
- **Hand-Pick Files**: Choose individual files by number
- **Selection Preview**: See what you've selected before downloading

### 💾 Powerful Downloads
- **Multi-threaded**: Download multiple files simultaneously
- **Progress Bars**: Real-time download progress with file sizes
- **Resume Support**: Interrupted downloads continue from where they stopped
- **Auto-Retry**: Failed downloads retry up to 3 times
- **Compression**: Requests gzip/deflate for faster transfers

### 💡 Quality of Life
- **Session Saving**: Save discoveries to JSON and reload later
- **Colored Output**: Beautiful terminal UI with emojis and colors
- **Thread-Safe**: Concurrent operations with proper locking
- **Metadata Storage**: All file info saved for later reference

---

## 📦 Installation

### Prerequisites
- Python 3.7 or higher
- pip (Python package manager)

### Step 1: Clone the Repository
```bash
git clone https://github.com/smh0x01/webscout.git
cd webscout
