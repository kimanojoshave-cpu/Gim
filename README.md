<div align="center">

# 💠 YT-DLP PRO TERMUX

### ⚡ Professional Media Downloader for Android / Termux

**Fast • Modular • Powerful • Easy to Use**

[![Version](https://img.shields.io/badge/version-V2.1-2196F3?style=for-the-badge)](https://github.com/kimanojoshave-cpu/Gim)
[![Platform](https://img.shields.io/badge/platform-Android%20%7C%20Termux-42A5F5?style=for-the-badge)](https://termux.dev/)
[![Python](https://img.shields.io/badge/Python-3.x-1976D2?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![yt--dlp](https://img.shields.io/badge/Engine-yt--dlp-0D47A1?style=for-the-badge)](https://github.com/yt-dlp/yt-dlp)

</div>

---

## 🔷 Overview

**YT-DLP PRO TERMUX** is a modular terminal media downloader built around **yt-dlp**, designed especially for **Android + Termux**.

The project separates the user interface, download engine, queue system, storage, diagnostics, localization, security and tests into dedicated modules so the codebase is easier to maintain and extend.

> 🚀 **Current source:** V2.1 Crash Hotfix

---

# ✨ FEATURES

| Feature | Details |
|---|---|
| 🎬 **Video Download** | Download videos with quality and format selection |
| 🎵 **Music Download** | Audio-only downloads with metadata and artwork support |
| 📋 **Playlist Mode** | Download complete playlists or selected entries |
| 🔢 **Range Selection** | Examples: `1,3,5-8` |
| 📦 **Batch URLs** | Process multiple URLs with duplicate suppression |
| ⚙️ **Advanced Mode** | Manual download configuration |
| 🚀 **Quick Presets** | Best Quality, Balanced, Efficient, Compatible, Audio Best, Music Library |
| 🔍 **Format Analyzer** | Analyze and score available audio/video formats |
| 🖼️ **Metadata & Thumbnail** | Embed metadata and artwork when supported |
| 🛡️ **SponsorBlock** | Post-process supported SponsorBlock segments |
| 📥 **Download Queue** | Queue, retry, pause, resume, cancel and remove jobs |
| 🗂️ **History** | Persistent download history |
| 🕘 **Recent URLs** | Quickly reuse previously downloaded URLs |
| 🔄 **Redownload** | Redownload items from history |
| 📋 **Clipboard** | Termux clipboard integration |
| 🌐 **Thai / English** | Built-in localization system |
| 🩺 **Diagnostics** | Check Python, yt-dlp, FFmpeg, storage, network and environment |
| 🧪 **Automated Tests** | Regression and unit tests for core behavior |

---

# 🎨 TERMINAL UI

The application uses a structured **Textual TUI** rather than putting everything into one giant script.

### Main sections

- 🏠 **Download** — primary download workflow
- 📋 **Queue** — manage active and waiting downloads
- 🕘 **History** — browse previous downloads
- 🔗 **Recent URLs** — reuse recent links
- ⚙️ **Settings** — configure application defaults
- 🩺 **Diagnostics** — inspect the Termux environment

The interface is designed to keep actions organized and make the application comfortable to use from a phone terminal.

---

# 🧩 PROJECT ARCHITECTURE

```text
ytdlp-pro-termux/
│
├── main.py                       # Application entry point
├── requirements.txt              # Python dependencies
│
├── app/
│   ├── core/                     # Download/business logic
│   │   ├── engine.py             # yt-dlp engine and download flow
│   │   ├── models.py             # Media, stream, quality and container models
│   │   ├── format_analyzer.py    # Format parsing and scoring
│   │   ├── media_processor.py    # Container/output processing
│   │   ├── metadata_mapper.py    # Metadata and post-processing options
│   │   ├── playlist_selection.py # Playlist/range selection
│   │   └── presets.py             # Quick download presets
│   │
│   ├── ui/                       # Textual terminal interface
│   │   └── tui.py                # Main UI and application panes
│   │
│   ├── queue/                    # Download queue management
│   │   └── manager.py
│   │
│   ├── storage/                  # Persistent application data
│   │   ├── history.py
│   │   └── recent_urls.py
│   │
│   ├── diagnostics/              # Environment checks
│   │   └── doctor.py
│   │
│   ├── locales/                  # Translations
│   │   ├── en.json
│   │   └── th.json
│   │
│   ├── config.py                 # Application configuration
│   ├── security.py               # Safe subprocess/path handling
│   ├── clipboard.py              # Termux clipboard integration
│   ├── i18n.py                   # Localization engine
│   └── logging_setup.py           # Logging and secret redaction
│
├── tests/                        # Unit/regression tests
│
└── docs/
    └── PROJECT_FILE_MAP.md       # Detailed file-by-file documentation
```

---

# 🛠️ V2.1 HOTFIX

### Fixed

- 🔵 **Textual `DuplicateIds` crash** in Recent URLs by pre-allocating UI slots.
- 🔵 **Audio-only metadata/artwork issue** where postprocessors were not being applied correctly.
- 🔵 Preserved the modular separation between UI, engine, storage and tests.

---

# 📱 REQUIREMENTS

- Android device
- Termux
- Python 3
- yt-dlp
- FFmpeg / ffprobe
- Network connection

The included diagnostics module can help identify missing or incorrectly configured dependencies.

---

# 🚀 QUICK START

```bash
# Install the required packages in Termux
pkg update
pkg install python ffmpeg

# Install Python dependencies
pip install -r requirements.txt

# Start the application
python main.py
```

> 💡 The exact installation requirements can change with the project version. Check `requirements.txt` before installation.

---

# 📚 DOCUMENTATION

For a detailed explanation of **what every file does, which feature belongs to which module, and how the architecture is separated**, see:

👉 [`docs/PROJECT_FILE_MAP.md`](docs/PROJECT_FILE_MAP.md)

---

# 🧪 TESTING

Run the automated test suite with:

```bash
python -m unittest discover -s tests -v
```

The V2.1 reference source includes regression/unit coverage for configuration, security, clipboard, media processing, format analysis, playlist selection, history, recent URLs, presets, i18n, engine helpers and the TUI static audit.

---

# 🧱 DESIGN PRINCIPLES

```text
UI                 → app/ui/
Download Logic     → app/core/
Queue              → app/queue/
Persistence        → app/storage/
Diagnostics        → app/diagnostics/
Localization       → app/locales/
Configuration      → app/config.py
Security           → app/security.py
Tests              → tests/
Documentation      → docs/
```

The goal is simple: **one responsibility per module**. This makes the project easier to debug, test, improve and expand without turning `main.py` into an unmaintainable monolith.

---

# 📦 DOWNLOAD

Once this repository is made public, GitHub's **Code → Download ZIP** can be used to download the source directly.

---

# 📌 PROJECT STATUS

**V2.1 — Crash Hotfix / Modular Architecture**

The repository is being organized as the clean development home for YT-DLP PRO TERMUX. The source architecture is designed to keep individual features separated so future versions can be developed without rebuilding the entire application.

---

<div align="center">

## 💙 YT-DLP PRO TERMUX

**Built for Android • Powered by yt-dlp • Designed for Termux**

</div>
