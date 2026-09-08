# YT-DLP PRO TERMUX — Project File Map

## Purpose

This document describes the source archive `ytdlp-pro-termux-v2.1-hotfix` and the responsibility of each source file. The project is already modular: UI, core download engine, storage, queueing, diagnostics, localization, security, and tests are separated into dedicated modules.

## Architecture

```text
ytdlp-pro-termux/
├── main.py                         # Application entry point
├── requirements.txt                # Python dependencies
├── README.md                       # Full project documentation / changelog
├── app/
│   ├── __init__.py                 # Package metadata / version
│   ├── config.py                   # Application configuration and defaults
│   ├── i18n.py                     # Localization loader / translator
│   ├── clipboard.py                # Termux clipboard integration
│   ├── logging_setup.py            # Logging configuration
│   ├── security.py                 # Security-related validation / safe handling
│   ├── ui/
│   │   ├── __init__.py
│   │   └── tui.py                  # Textual terminal UI
│   ├── core/
│   │   ├── __init__.py
│   │   ├── engine.py               # yt-dlp orchestration / download engine
│   │   ├── models.py               # Domain models and job/options data
│   │   ├── format_analyzer.py      # Source-format analysis
│   │   ├── media_processor.py      # Container/post-processing decisions
│   │   ├── metadata_mapper.py      # Metadata mapping
│   │   ├── playlist_selection.py   # Playlist range parsing / selection
│   │   └── presets.py               # Quality / audio presets
│   ├── queue/
│   │   ├── __init__.py
│   │   └── manager.py              # Download queue management
│   ├── storage/
│   │   ├── __init__.py
│   │   ├── history.py              # Persistent download history
│   │   └── recent_urls.py           # MRU recent-URL storage
│   ├── diagnostics/
│   │   ├── __init__.py
│   │   └── doctor.py                # Environment / dependency diagnostics
│   └── locales/
│       ├── en.json                 # English strings
│       └── th.json                 # Thai strings
└── tests/                          # Automated regression/unit tests
```

## Main capabilities

- yt-dlp based media downloading on Android/Termux.
- Video and Music modes.
- Playlist downloads with range selection such as `1,3,5-8`.
- Batch URL input with duplicate suppression.
- Advanced/manual download configuration.
- Quick presets: Best Quality, Balanced, Efficient, Compatible, Audio Best, Music Library.
- Audio/video container selection and post-processing.
- Metadata and thumbnail embedding.
- SponsorBlock integration using yt-dlp postprocessors.
- Subtitle and network-related options.
- Download queue and background work.
- Persistent History and Recent URLs.
- Redownload and copy-URL actions from History.
- Thai/English localization.
- Termux clipboard integration.
- First-run diagnostics and environment checks.
- Regression tests for core behavior and known hotfixes.

## V2.1 hotfixes represented by the archive

### TUI recent-URL crash

The UI no longer dynamically removes and remounts recent-URL widgets. It pre-allocates slots and updates their labels/visibility, avoiding Textual `DuplicateIds` crashes.

### Audio-only metadata/artwork bug

Audio and video jobs share the same container/postprocessor resolution path. This ensures `FFmpegMetadata` and `EmbedThumbnail` are applied consistently when enabled for audio-only downloads.

## Testing

The archive README reports a full suite of 118 tests passing for V2.1. Tests are grouped by feature so regressions can be isolated without turning the project into one monolithic test file.

## Design rule

Keep business logic out of the TUI wherever practical. Core behavior belongs under `app/core/`; persistence belongs under `app/storage/`; environment checks belong under `app/diagnostics/`; and user-facing strings belong under `app/locales/`.
