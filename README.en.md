<p align="center">
  <img src="docs/images/SVMM.png" width="150" alt="Stardew Valley Mod Manager">
</p>

<h1 align="center">Stardew Valley Mod Manager</h1>

<p align="center">
  <strong>专用于 macOS 的中文友好型《星露谷物语》Mod 管理器。</strong><br>
  A Chinese-friendly native Stardew Valley Mod manager for macOS.
</p>

<p align="center">
  <img alt="Minimum macOS" src="https://img.shields.io/badge/Minimum%20macOS-27.0%2B-111111?logo=apple&logoColor=white">
  <img alt="Version" src="https://img.shields.io/badge/Version-1.0.0-0969da">
  <img alt="Languages" src="https://img.shields.io/badge/Languages-Simplified%20Chinese%20%7C%20English-8250df">
  <img alt="Data" src="https://img.shields.io/badge/Data-Local--first-1a7f37">
  <img alt="License" src="https://img.shields.io/badge/License-Proprietary-d97706">
</p>

<p align="center">
  开发者：<strong>李薇（Li Wei）</strong><br>
  Developer: Li Wei
</p>

<p align="center">
  <a href="README.md">简体中文</a>
  ·
  <strong>English</strong>
  ·
  <a href="https://github.com/XModLife/Stardew-Valley-Mod-Manager/releases">Releases</a>
  ·
  <a href="USER-GUIDE.en.md">User Manual</a>
  ·
  <a href="https://github.com/XModLife/Stardew-Valley-Mod-Manager/issues">Issues</a>
</p>

---

## Positioning

**Chinese-friendly support is one of SVMM's core product goals and part of the reason the project exists.** Simplified Chinese UI, documentation, and the practical needs of Chinese-speaking Stardew Valley players are treated as first-class requirements rather than an afterthought.

SVMM is a native macOS application for organizing and managing an existing **Stardew Valley + SMAPI** Mod environment.

Its basic principle is simple:

> **Manage the Mods you already use instead of creating a second parallel Mod library.**

<p align="center">
  <img src="docs/images/en/overview.png" alt="SVMM Overview" width="100%">
</p>

## Current Release Notes & Known Issues

SVMM is approaching its first public release. Core workflows are usable, but edge cases may still exist across unusual Mod structures, third-party services, and macOS behavior.

Known items include:

- **The Help menu may briefly change on macOS beta / seed systems.** macOS can dynamically inject a Feedback Assistant item such as “Send Stardew Valley Mod Manager Feedback to Apple” the first time the Help menu is opened. This system-provided item may briefly appear, disappear, or reposition while the menu initializes. It is separate from SVMM's User Manual and does not affect Mod data, categories, profiles, or other core functions.
- Non-standard third-party Mod directory structures can still expose compatibility edge cases.
- Changes to Nexus Mods, SMAPI, GitHub, or related download infrastructure can affect optional online workflows.

See [KNOWN-ISSUES.md](KNOWN-ISSUES.md) for the maintained list.

Please report reproducible issues through [GitHub Issues](https://github.com/XModLife/Stardew-Valley-Mod-Manager/issues).

## Core Features

### Mod Library

| Card View | List View |
| --- | --- |
| ![Mod Library Card View](docs/images/en/mod-library-card.png) | ![Mod Library List View](docs/images/en/mod-library-list.png) |

### Categories & Profiles

| Categories | Profiles |
| --- | --- |
| ![Categories](docs/images/en/categories.png) | ![Profiles](docs/images/en/profiles.png) |

### Settings

<p align="center">
  <img src="docs/images/en/settings.png" alt="SVMM Settings" width="92%">
</p>

## Interface Language

SVMM currently supports, in product priority order:

1. **Simplified Chinese**
2. **English**
3. **System Default**

A restart is required to fully apply a language change so app content and native macOS menus switch together.

## System Requirements

The current 1.0.0 build has a **minimum deployment target of macOS 27.0**.

- **Supported:** macOS 27.0 and later.
- **Not supported by the current build:** macOS 26 and earlier; the application cannot launch there.
- Future macOS versions are intended compatibility targets, but releases that do not yet exist or have not been tested cannot be guaranteed in advance.
- Stardew Valley for macOS.
- SMAPI for a normal modded Stardew Valley setup.
- User-granted access to the Stardew Valley game / `Mods` location.

`macOS 27.0+` means **macOS 27.0 is the minimum**, not that the app is limited to macOS 27 only.

## Download

### [Download the latest official release →](https://github.com/XModLife/Stardew-Valley-Mod-Manager/releases/latest)

## Documentation

- [使用手册](USER-GUIDE.zh-CN.md) · [User Manual](USER-GUIDE.en.md)
- [隐私政策](PRIVACY.md) · [Privacy Policy](PRIVACY.en.md)
- [软件许可协议](SOFTWARE-LICENSE.md) · [Software License Agreement](SOFTWARE-LICENSE.en.md)
- [Known Issues](KNOWN-ISSUES.md)
- [FAQ](FAQ.md)
- [Support](SUPPORT.md)
- [Security](SECURITY.md)
- [Changelog](CHANGELOG.md)

## Contact

**开发者 / Developer:** 李薇（Li Wei）  
**Email:** SVMM@npccare.cn
