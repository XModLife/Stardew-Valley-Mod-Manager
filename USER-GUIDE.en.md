[简体中文](USER-GUIDE.md) | [**English**](USER-GUIDE.en.md)

# Stardew Valley Mod Manager User Manual

Applies to Stardew Valley Mod Manager 1.0.0 and later versions until this manual is updated.

Stardew Valley Mod Manager (SVMM) is a local Mod-management application for macOS. It manages the Stardew Valley Mods you already use rather than creating a second parallel Mod environment. Most management data remains on your Mac.

## Quick Start

1. Download SVMM from the official GitHub Releases page.
2. If Gatekeeper blocks first launch, verify the source and SHA-256 before using “Open Anyway”.
3. Select the Stardew Valley / Mods location you actually use in Settings.
4. Grant the app access to the Mods folder.
5. Review Overview and Scan Diagnostics.
6. Use display-name notes, categories, profiles, updates, or dependency acquisition as needed.

## System Requirements

- **macOS 15.0 or later**
- **Universal 2 (`arm64 + x86_64`)**
- Apple Silicon is the primary directly tested platform
- the x86_64 path has been launch-tested under Rosetta 2; full physical-Intel regression coverage is still limited
- Stardew Valley for macOS
- SMAPI is normally required for a modded environment

In the current macOS 15 VM test environment, first entry and some selections in Categories can be slower than on macOS 26/27, while core functionality remains usable. See [KNOWN-ISSUES.md](KNOWN-ISSUES.md).

## Interface Language

SVMM currently maintains:

- **Simplified Chinese**
- **English**
- **System Default** as a selection mode

System Default chooses among localization resources actually shipped with SVMM; it is not live machine translation.

User-facing text is organized through localization resources / String Catalogs, so additional languages can be added architecturally. The developer will not independently publish a language they cannot understand and review. Fluent translators/reviewers interested in another language can open a GitHub Issue or contact SVMM@npccare.cn.

Restart SVMM after changing language so app content and native macOS menus start in the same localization.

<p align="center">
  <img src="docs/images/en/settings.png" alt="Language and Settings" width="96%">
</p>

## Overview

Overview summarizes the current Mod environment and selected read-only Stardew Valley save information, including Mod counts, enabled state, updates, items needing attention, errors, active profile, and readable farm information.

<p align="center">
  <img src="docs/images/en/overview.png" alt="Overview" width="96%">
</p>

Statuses are management aids, not absolute judgments about third-party Mod safety or compatibility.

## Mod Library

The Mod Library is the main management area. Card and list views change presentation only; they do not create separate Mod data.

### Card View

Designed for quick browsing. Nexus thumbnails are shown when available.

<p align="center">
  <img src="docs/images/en/mod-library-card.png" alt="Mod Library Card View" width="96%">
</p>

### List View

Designed for comparing original names, display-name notes, versions, types, dependencies, states, and installation time, with sorting and multi-selection.

<p align="center">
  <img src="docs/images/en/mod-library-list.png" alt="Mod Library List View" width="96%">
</p>

### Display-name Notes & Personal Notes

A display-name note is a local label that helps you identify a Mod in language or wording that is easier for you to recognize.

- It does not change the author's original name.
- It does not modify `manifest.json`.
- It does not change the Unique ID.
- It can be imported/exported and included in backups together with supported note data.

<p align="center">
  <img src="docs/images/en/mod-name-note.png" alt="Display-name Note" width="72%">
</p>

### Multi-selection

- Click: single selection
- ⌘ + Click: non-contiguous selection
- ⇧ + Click: contiguous range
- ⌘A: select all in the current list

## Categories & Profiles

### Categories

Categories answer “how should these Mods be organized?” The system default scheme is a read-only reference; user schemes can add categories and manual assignments.

<p align="center">
  <img src="docs/images/en/categories.png" alt="Categories" width="96%">
</p>

### Profiles

Profiles answer “which Mods should actually be enabled for this setup?” They store and apply enabled/disabled combinations.

<p align="center">
  <img src="docs/images/en/profiles.png" alt="Profiles" width="96%">
</p>

If a saved profile member has been removed outside SVMM, its unmatched management record can be reviewed and cleaned from Settings.

## Updates & Nexus Mods

Nexus Mods integration is optional. Local scanning, notes, categories, profiles, and backups do not require a Nexus account.

### Free Account Updates

Free accounts use browser/NXM authorization when a Nexus download is required. SVMM then continues the authorized download, validation, and supported installation transaction.

<p align="center">
  <img src="docs/images/en/update-free.png" alt="Free Account Update" width="96%">
</p>

### Premium Batch Updates

Eligible Premium accounts can obtain direct download links and process supported batch update queues.

<p align="center">
  <img src="docs/images/en/update-premium-batch.png" alt="Premium Batch Update" width="96%">
</p>

### Update Transactions & Bundled Multi-Mod Packages

Before writing into Mods, SVMM validates the downloaded file, ZIP structure, manifests, Unique IDs, versions, and target paths.

When an author distributes multiple required Mod components together in one ZIP, SVMM can treat them as one validated bundled multi-Mod transaction:

- update already installed components;
- install missing components that belong to the validated bundle;
- preserve supported `config.json` files where applicable;
- roll back the transaction if a critical step fails;
- stop on duplicate Unique IDs, path conflicts, downgrade risks, or ambiguous identity.

## Dependencies & Acquisition

SVMM reads Manifest dependency declarations and distinguishes missing, installed-but-disabled, version-too-low, version-unknown, and duplicate-Unique-ID states.

### Free Account Dependency Acquisition

<p align="center">
  <img src="docs/images/en/dependencies-free.png" alt="Free Dependency Acquisition" width="96%">
</p>

### Premium Batch Dependency Acquisition

<p align="center">
  <img src="docs/images/en/dependencies-premium-batch.png" alt="Premium Batch Dependency Acquisition" width="96%">
</p>

A dependency ZIP containing several Mods is installed as one transaction only when SVMM can validate that they belong to the same bundled package. RAR and 7z are not currently part of the automatic-install flow.

SVMM does not recursively install an unlimited dependency tree. Rescan and review dependency status after newly installing dependencies.

## Settings, Storage & Backups

Settings centralizes game location, Mods authorization, language, Nexus connection, and local manager data.

<p align="center">
  <img src="docs/images/en/settings.png" alt="Settings" width="96%">
</p>

### Storage & Cache

- inspect/clear Nexus thumbnail cache;
- inspect/clear SVMM-managed temporary Mod/update transaction files;
- refresh storage usage;
- clearing cache does not uninstall normal Mods.

### Manager Data

- rescan Mods;
- review residual management records from uninstalled Mods;
- import/export display-name notes and personal notes;
- create manager-data backups;
- selectively restore supported data from a backup.

<p align="center">
  <img src="docs/images/en/data-cache-backup.png" alt="Storage, Cache and Backup Management" width="96%">
</p>

Keep an independent backup for important Mod environments. Temporary transaction backups are not a long-term backup strategy.

## Scan Diagnostics

Tools > Scan Diagnostics shows folder-structure, Manifest, and parsing problems. Diagnostics are evidence for troubleshooting and are not an automatic verdict that a Mod is broken.

Rescan after correcting external files.

## Save Overview

SVMM can parse selected local Stardew Valley save information in read-only mode to display player/farm names, in-game date, play time, money, spouse/children, farmhouse upgrades, version, and other readable summary information.

Viewing the save overview does not modify the save.

## Troubleshooting

Recommended order:

1. confirm the Stardew Valley / Mods location is correct and accessible;
2. rescan Mods;
3. review Scan Diagnostics;
4. open the affected Mod details and verify Unique ID, dependencies, and update source;
5. review the Mod author's release/install notes for update or dependency problems;
6. if still unclear, report a reproducible issue.

For compatibility/performance reports include:

- SVMM version;
- macOS version;
- Mac model / architecture;
- physical Mac or VM;
- Stardew Valley / SMAPI version;
- affected Mod name/version/Unique ID;
- reproduction steps, actual result, expected result.

Do not disclose Nexus API Keys, tokens, passwords, payment credentials, or other authentication secrets.

**Contact: SVMM@npccare.cn**
