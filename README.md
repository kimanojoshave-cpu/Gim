# YT-DLP PRO TERMUX

Modular yt-dlp-powered media downloader for Android/Termux.

> **Current source:** V2.1 crash hotfix

## What it does

- Video and Music download modes
- Playlist downloads with range selection (`1,3,5-8`)
- Batch URL downloads with duplicate suppression
- Advanced/manual download configuration
- Quick presets: Best Quality, Balanced, Efficient, Compatible, Audio Best, Music Library
- Audio/video format analysis and container decisions
- Metadata and thumbnail embedding
- SponsorBlock post-processing
- Queue, retry, pause/resume and cancellation support
- Persistent download History and Recent URLs
- Redownload and clipboard actions
- Thai/English localization
- Termux clipboard integration
- Environment diagnostics for Python, yt-dlp, FFmpeg, storage and network
- Automated regression/unit tests

## V2.1 hotfix highlights

- Fixed Textual `DuplicateIds` crash in Recent URLs by pre-allocating UI slots.
- Fixed audio-only downloads not receiving metadata/thumbnail postprocessors.
- Keeps the download engine, UI, storage and tests modular instead of putting everything in one file.

## Project layout

```text
ytdlp-pro-termux/
├── main.py
├── requirements.txt
├── app/
│   ├── core/          # download engine, formats, models, presets, media processing
│   ├── ui/            # Textual terminal UI
│   ├── queue/         # queue management
│   ├── storage/       # history and recent URLs
│   ├── diagnostics/   # environment checks
│   ├── locales/       # English / Thai translations
│   ├── config.py
│   ├── security.py
│   ├── clipboard.py
│   ├── i18n.py
│   └── logging_setup.py
└── tests/             # regression and unit tests
```

## Documentation

See [`docs/PROJECT_FILE_MAP.md`](docs/PROJECT_FILE_MAP.md) for a file-by-file explanation of responsibilities and features.

## Source organization rule

UI code stays in `app/ui/`; download/business logic stays in `app/core/`; persistence stays in `app/storage/`; environment checks stay in `app/diagnostics/`; translations stay in `app/locales/`; tests mirror the behavior they verify.

## Status

This repository is being prepared as the clean development home for the project. The uploaded V2.1 source archive is the reference implementation to be imported into the repository while preserving the modular structure above.
