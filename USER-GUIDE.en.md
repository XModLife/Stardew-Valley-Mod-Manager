[简体中文](USER-GUIDE.md) | [**English**](USER-GUIDE.en.md)

# Stardew Valley Mod Manager User Manual

Applies to Stardew Valley Mod Manager 1.0.0 and later versions until this manual is updated.

Stardew Valley Mod Manager ("SVMM") is a local Mod-management application for macOS. It reads and manages your existing Stardew Valley Mods rather than creating a separate parallel Mod environment. Most management data remains on your Mac.

## Contents

- [Stardew Valley Mod Manager User Manual](#quick)
- [Folders & Scanning](#setup)
- [Interface Language](#language)
- [Overview](#overview)
- [Mod Library](#library)
- [Categories & Profiles](#organization)
- [Updates & Nexus Mods](#updates)
- [Dependencies & Acquisition](#dependencies)
- [Diagnostics & Storage](#diagnostics)
- [Save Overview](#save)
- [Troubleshooting & Feedback](#troubleshooting)

---

<a id="quick"></a>
## Stardew Valley Mod Manager User Manual

The basic workflow from initial setup to everyday Mod management.

> **What SVMM does**  
> SVMM organizes, checks, and performs Mod-management operations requested by the user. It does not replace Stardew Valley, SMAPI, or third-party Mods, and it cannot guarantee third-party Mod compatibility.

### Recommended daily workflow

1. Open SVMM and review the Mod status shown on Overview.
2. If you changed the Mods folder in Finder or another tool, rescan Mods first.
3. Adjust categories, profiles, or Mod enabled state when needed.
4. When an update, missing dependency, or dependency-version issue appears, open Mod details and verify the source, version, and dependency status before updating, acquiring the dependency, or handling it manually.

<a id="setup"></a>
## Folders & Scanning

Point SVMM to the correct Stardew Valley Mods and keep the library consistent with disk.

### Set the Mods folder

On first use, select the Stardew Valley Mods folder in Settings. SVMM needs the corresponding file access in order to read Mod information and perform actions such as enabling, disabling, updating, or deleting Mods.

1. Open Settings and locate the game / Mods folder setting.
2. Use the macOS file picker to choose the Mods folder you actually use.
3. Return to the main interface and confirm that Mods are scanned and displayed normally.

> **About macOS file permissions**  
> Choosing a folder through the system file picker is part of granting the app local file access. If the folder is moved, permission is revoked, or storage changes, you may need to select it again.

### Rescan Mods

Use Tools > Rescan Mods to read the current Mods folder again. Rescanning synchronizes SVMM’s current view with the actual files on disk; the scan itself does not automatically delete normal Mods merely because an issue is detected.

- You manually added, removed, or moved Mods in Finder.
- Another tool modified the Mods folder.
- SVMM’s current list is clearly inconsistent with the folder on disk.


<a id="language"></a>
## Interface Language

SVMM supports **English**, **Simplified Chinese**, and **System Default**.

Language selection is treated as an application launch setting. When you select a different language, SVMM saves the requested language and asks whether you want to restart.

- **Restart** — reopen SVMM immediately and apply the new language to both app content and native macOS menus.
- **Later** — continue using the current launch language; the selected language is applied the next time SVMM is fully quit and reopened.
- Selecting the current launch language again cancels a pending language change.
- **System Default** removes SVMM's own language override so macOS chooses the app language on the next launch.

This avoids a partially mixed-language interface.

<p align="center">
  <img src="docs/images/en/settings.png" alt="Language and Settings" width="94%">
</p>

<a id="overview"></a>
## Overview

<p align="center"><img src="docs/images/en/overview.png" alt="Overview" width="96%"></p>


Quickly determine whether the current Mod environment needs attention.

Overview summarizes Mod counts and major states and provides a farm save summary. Status cards are navigation and triage aids; they are not absolute judgments about third-party Mod safety or compatibility.

### Enabled

Indicates that the Mod is in the enabled state recognized by SVMM.

### Update Available

Indicates that a newer version was found using currently available update information. Whether to install it should still be judged against author notes, game version, SMAPI, and dependencies.

### Needs Attention

Indicates a scan, dependency, structure, or other management issue that needs review. A missing dependency does not always mean you must install something immediately; open the relevant Mod details first to see whether the dependency is required, optional, disabled, too old, or ambiguous before deciding what to do.

### Error

Indicates an error during scanning, parsing, file operations, or a related process. Treat the message as diagnostic evidence rather than deleting the Mod solely because an error is shown.

> **Statuses are decision aids**  
> SVMM can narrow down problems, but whether a Mod is suitable for a save or conflicts with another Mod still depends on the third-party Mod and your actual environment.

<a id="library"></a>
## Mod Library

| Card View | List View |
| --- | --- |
| ![Card View](docs/images/en/mod-library-card.png) | ![List View](docs/images/en/mod-library-list.png) |


View, filter, select, and manage Mods that have been scanned.

The Mod Library is SVMM’s main working area. Card and list views change presentation only; they do not create separate sets of Mod data.

### Two ways to view Mods

- **Card View**: Designed for quick browsing. Nexus thumbnails are shown when available; a safe fallback is used when no image is available or while offline.
- **List View**: Designed for comparing structured information such as name, version, type, dependencies, status, and installation time, with sorting support.

### Common actions

- Use Mod Status to filter the Mods you need to inspect.
- Select a Mod to inspect details, version, Unique ID, dependencies, and update source. The dependency area shows current status and, when a reliable source can be resolved, offers actions such as Get Dependency, Get New Version, or View Page.
- Use a display-name note to record a more understandable personal name.
- Use the context menu to classify, add to a profile, open details, delete, and perform related actions.
- Before high-impact actions such as deletion or batch updating, confirm the selected Mods and scope.

### Display-name notes do not modify the Mod

Display-name notes are local SVMM management data. For example, “Elle's Seasonal Buildings” can be noted as “Seasonal building visuals.” This does not rewrite the Mod’s original name or manifest.json.

> **Disabled is not deleted**  
> Disabling temporarily prevents a Mod from participating in normal loading; deleting removes its files. Prefer disabling when testing conflicts or temporarily changing a setup, and delete only after you are sure the Mod is no longer needed.

### macOS selection controls

- **Click**: Select one Mod.
- **⌘ + Click**: Select or deselect individual non-contiguous Mods.
- **⇧ + Click**: Select a contiguous range.
- **⌘A**: Select all Mods in the current list.

<a id="organization"></a>
## Categories & Profiles

| Categories | Profiles |
| --- | --- |
| ![Categories](docs/images/en/categories.png) | ![Profiles](docs/images/en/profiles.png) |


One organizes Mods; the other defines which Mods are used together.

### Categories

Categories are for organizing and finding Mods. They are SVMM management data; they do not change a type defined by the Mod author or automatically change whether the Mod is enabled.

- The system default classification scheme can be used as a read-only reference.
- Users can create and maintain their own editable classification schemes.
- The Mod Library and Categories page use the same category assignments.

### Profiles

Profiles store a set of actual enabled/disabled states so you can switch between play styles or test environments. The main interface shows the current applied result rather than a historical database-record count. If a saved profile member has been removed from the Mods folder, SVMM reports it as an unmatched historical record; if that Mod was permanently deleted, use Settings → Clean residual management records for uninstalled Mods to remove the corresponding profile-membership record.

> **The simplest distinction**  
> Categories = “how to organize”; profiles = “what to actually use this time.” Do not treat categories as enablement rules or profiles as a tagging system.

<a id="updates"></a>
## Updates & Nexus Mods

### Nexus update workflows

| Free account workflow | Premium batch update |
| --- | --- |
| ![Free update workflow](docs/images/en/update-free.png) | ![Premium batch update](docs/images/en/update-premium-batch.png) |


Check update sources and, where supported, complete download and installation.

SVMM uses Mod metadata and information from third-party services such as SMAPI and Nexus Mods to check update status for supported Mods. Updates and dependency acquisition share some Nexus Mods download capabilities, but they are different tasks: updates act on an already installed Mod, while dependency acquisition addresses a missing or version-problem dependency declared by another Mod. Results depend on Mod metadata, third-party services, and available files.

> **“Unavailable” does not mean the Mod is broken**  
> The Mod may simply lack a valid Update Key, have an obsolete source, be affected by a temporary third-party outage, or use a source that cannot currently be identified automatically. A Mod may still work normally in the game.

### Connect Nexus Mods (optional)

Connecting Nexus Mods is not required for SVMM’s local management features. Once connected, SVMM can obtain supported Nexus metadata, file information, thumbnails, and download information.

- **Free accounts**: When an update or dependency must be downloaded from Nexus Mods, Free accounts normally complete NXM authorization in the browser, after which SVMM continues the authorized download, validation, and supported installation flow.
- **Premium accounts**: For eligible updates or dependencies, Premium accounts allow SVMM to obtain direct download links. Premium also supports batch updates and eligible batch dependency acquisition; writes into the Mods folder still go through local validation and are committed in a controlled transaction sequence.

> **Nexus API credentials**  
> SVMM stores Nexus API credentials in the macOS Keychain. Do not place an API Key in public issues, screenshots, logs, or messages to other users.

### Before updating

1. Confirm the Mod to be updated and the target version.
2. Verify the update source, especially for Mods whose source was manually corrected.
3. Read the author’s notes before updating large content Mods or important save environments.
4. Keep an independent backup for important setups; do not treat temporary update backups as a long-term backup strategy.

<a id="dependencies"></a>
## Dependencies & Acquisition

### Dependency acquisition workflows

| Free account | Premium batch acquisition |
| --- | --- |
| ![Free dependency acquisition](docs/images/en/dependencies-free.png) | ![Premium dependency acquisition](docs/images/en/dependencies-premium-batch.png) |


Understand dependency status and, where supported, resolve sources, download, validate, and install dependencies.

SVMM reads dependency declarations from Mod manifests and compares them with the actual Mods currently present in the Mods folder. It can help determine whether a dependency exists, is disabled, or is too old, and in some cases can resolve a reliable source and assist with acquisition. Dependency status is a management aid and does not replace the Mod author’s installation instructions.

### Understand dependency declarations first

- **Required dependency**: The parent Mod explicitly declares it as required. If it is missing, disabled, or does not meet the required version, the parent Mod may fail to load or may be incomplete; review the author’s instructions first.
- **Optional dependency**: The parent Mod declares it as optional. A missing optional dependency does not normally mean the parent Mod is necessarily broken; it may affect only specific integration features.

### Common dependency states

- Missing: no installed Mod currently matches the declared Unique ID.
- Installed but disabled: the dependency exists on disk but is not currently enabled. Normally enable the existing dependency instead of downloading another copy.
- Version too low: an installed dependency was found, but its version is below the minimum declared by the parent Mod.
- Version unknown: the dependency exists, but available metadata is insufficient for a reliable version comparison; do not treat this automatically as “must update.”
- Duplicate Unique ID: multiple possible Mods currently match the identity, so SVMM cannot reliably determine which instance should satisfy the dependency.

### Dependency-source resolution

For missing, version-too-low, or version-unknown dependencies, SVMM can query SMAPI for public metadata associated with the Unique ID and prefers explicit project pages returned by the service. Sources may include Nexus Mods, GitHub, CurseForge, ModDrop, or others. If a reliable source cannot be resolved, SVMM does not invent a download URL and instead lets you copy the Unique ID for manual searching.

> **A resolved source does not guarantee that every file is appropriate**  
> Source resolution answers only “where this dependency is normally published.” Which file to install, whether an older version is required, and whether additional prerequisites or special installation steps apply must still be determined from the Mod author’s documentation.

### Acquire a single dependency

1. In the dependency area of Mod details, locate the missing or version-problem dependency and first confirm whether it is required and whether a minimum version is declared.
2. Wait for SVMM to resolve a source. An explicit Nexus Mods Mod page can enter the in-app dependency acquisition flow; other sources normally open the corresponding project page.
3. For a missing Nexus dependency, use Get Dependency. For an installed Nexus dependency whose version is too old, SVMM reuses the Mod update flow.
4. Choose a supported Nexus file. If multiple possible MAIN ZIP files are available, the single-dependency flow asks you to choose explicitly rather than guessing.
5. Free accounts complete NXM authorization through the browser; eligible Premium accounts can obtain the download link directly in SVMM.
6. After download, SVMM extracts the package in a temporary location and validates manifests, Unique IDs, target folders, and conflicts with installed Mod identities. If validation fails, the package is not written into the Mods folder.
7. After you confirm installation, SVMM performs the local installation transaction and rescans Mods. Review the parent Mod’s dependency area again to confirm that the issue is actually resolved.

### Nexus Mods account differences

- **Free**: Dependency acquisition requires browser participation for NXM authorization. After authorization, SVMM continues the temporary download, validation, and installation flow.
- **Premium**: When eligible, SVMM can obtain direct download links and supports batch dependency acquisition. The account remains subject to Nexus Mods API rate limits, file availability, and platform rules.

> **Local safety checks before installation**  
> Automatic dependency installation handles supported ZIP packages only. SVMM does not overwrite an installed Mod with the same Unique ID. For ZIP files containing multiple Mods, SVMM installs them as one transaction only when it can validate that they belong to the same bundled package. Dependency installation is not committed while the game is running. RAR and 7z are not part of the current automatic-install flow.

### Premium batch dependency acquisition

When multiple Mods have actionable Nexus dependency issues, Premium accounts can process eligible items in a batch. The batch feature uses conservative rules and does not guess files merely to maximize automation.

- Items are deduplicated by Unique ID, with required dependencies prioritized.
- Only dependencies with a clear Nexus Mods source and a uniquely determinable supported MAIN ZIP are processed automatically; items that do not meet the rules are skipped with an explanation.
- Missing dependencies use the dependency-install transaction, while version-too-low dependencies use the existing update transaction.
- Writes to the Mods folder are committed serially rather than through concurrent file transactions; after the queue finishes, SVMM rescans at most once.
- When stopping a batch, network requests and active downloads can be cancelled. An item that is already committing its final file-system write is not force-cancelled, to avoid leaving an unclear installation state.

> **Current boundary: dependency trees are not installed recursively**  
> SVMM processes only the dependencies explicitly shown for the Mod being reviewed or included in the current batch queue. If a newly installed dependency has further dependencies of its own, SVMM does not recursively download them in the same operation. After installation and rescanning, review dependency status again. This boundary reduces the risk of incorrect source resolution and uncontrolled chained installations.

<a id="diagnostics"></a>
## Diagnostics & Storage

Understand the problem before deciding whether files need to be changed or removed.

### Scan Diagnostics

Tools > Scan Diagnostics shows structure, manifest, and parsing problems found while scanning Mods and helps explain why a Mod was not identified normally or why its state could not be determined.

- Read the exact issue and affected Mod first.
- Inspect the corresponding folder and manifest.json in Finder when necessary.
- After correcting external files, rescan to confirm whether the issue is resolved.

> **A diagnostic issue is not an automatic “broken Mod” verdict**  
> Some older Mods, unusual folder layouts, or non-standard manifests may trigger scan diagnostics. Dependency issues come from a Mod’s declared relationships and the current installed state and should not be treated as the same thing as scan errors. Consider SMAPI, actual game behavior, dependency details, and the Mod author’s documentation before drawing conclusions.

### Storage & Cache

Settings > Storage & Cache lets you inspect caches and update-transaction data managed by SVMM and perform targeted cleanup.

- Clearing the Nexus thumbnail cache does not uninstall Mods.
- Removing completed or abandoned update-transaction data frees temporary space managed by SVMM.
- “Clean residual management records for uninstalled Mods” targets SVMM’s own remaining notes, categories, and similar records; it does not clean Stardew Valley game files.

<a id="save"></a>
## Save Overview

View a read-only summary of local Stardew Valley saves on Overview.

SVMM can read selected information from local Stardew Valley saves to display farm status. This is a quick overview feature and does not participate in Mod enablement, updates, or profile logic.

- Player and farm names.
- Summary information such as in-game date, play time, and money.
- Game state such as spouse, children, and farmhouse upgrades.
- Game version and readable progress information.

> **Read-only access**  
> SVMM parses saves in read-only mode for this overview and does not modify save contents merely by displaying farm status.

<a id="troubleshooting"></a>
## Troubleshooting & Feedback

Preserve useful evidence and narrow the problem down in a controlled order.

### Recommended troubleshooting order

1. Confirm that the selected Stardew Valley / Mods folder is correct and accessible.
2. Run Tools > Rescan Mods.
3. Open Scan Diagnostics and review specific folder-structure or manifest issues.
4. If the issue involves dependencies, open Mod details and verify the dependency Unique ID, whether it is required, minimum version, current status, and resolved source; do not install files blindly based only on a “missing dependency” label.
5. If the cause is still unclear, report an SVMM issue with reproducible steps.

> **Do not start by reinstalling everything**  
> Do not clear all Mods, delete all management data, or reinstall the game before the cause is understood. Preserve necessary backups and error information before high-impact actions.

### Include this information when reporting an issue

A useful report should provide enough context to reproduce the operation rather than only saying “it does not work” or providing an unexplained screenshot.

- SVMM version and macOS version.
- Stardew Valley and SMAPI versions.
- Relevant Mod names, versions, and Unique IDs when needed.
- Exact steps from a known state, the actual result, and the expected result.
- Relevant error text or reviewed diagnostic information.

> **Do not disclose authentication secrets**  
> Do not include Nexus API Keys, tokens, payment passwords, account passwords, or other authentication credentials in public issues, screenshots, or ordinary email. Security, privacy, or non-public matters may be sent to SVMM@npccare.cn.

SVMM@npccare.cn
