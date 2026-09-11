[简体中文](PRIVACY.md) | [**English**](PRIVACY.en.md)

# Stardew Valley Mod Manager Privacy Policy

Document Version: 1.1
Applicable Software Versions: Stardew Valley Mod Manager 1.1.0 and later versions, until this Privacy Policy is updated or replaced.
Effective Date: September 11, 2026
Developer: Li Wei (李薇)
Contact: SVMM@npccare.cn

## 1. Introduction

Stardew Valley Mod Manager (hereinafter referred to as “SVMM”) is an independent macOS Stardew Valley Mod-management application developed and published by Li Wei (李薇).

This Privacy Policy explains how SVMM accesses, processes, stores, and uses information while providing Mod scanning and management, categories and profiles, save overview, update checking, dependency-source resolution, dependency acquisition and installation, Nexus Mods connectivity, software updates, voluntary support, and related diagnostic features, and how those features may interact with third-party services when necessary.

SVMM follows a local-first data-processing principle. Except for the third-party network communications expressly described in this Policy, core Mod-management data is primarily processed and stored on the user’s own Mac. The current version does not operate developer-controlled backend servers for receiving users’ Mods, save files, or SVMM management databases.

## 2. Data Collection Practices SVMM Does Not Perform

As of the software version covered by this Policy, SVMM itself:

- does not operate a developer-controlled user account system;
- does not require users to register an SVMM account;
- does not display advertising;
- does not integrate advertising SDKs;
- does not integrate user-behavior analytics SDKs;
- does not include a telemetry system;
- does not perform cross-app tracking;
- does not perform cross-site tracking;
- does not create advertising or behavioral profiles of users;
- does not sell user data;
- does not rent user data;
- does not use user data for targeted advertising;
- does not upload Stardew Valley save files, Mod files, or SVMM management data to developer-controlled servers.

As of the current version, the developer does not operate backend account servers, user databases, or behavioral analytics servers for collecting SVMM user data.

## 3. Data Processed Locally on the User’s Device

SVMM must access and process certain data on the user’s Mac in order to provide Mod-management functionality.

Such local processing does not mean that the developer collects that data.

## 3.1 Stardew Valley Game Directory and Mods Directory

After the user configures a Stardew Valley game directory or Mods directory, SVMM may, within the scope authorized by the user, read, create, modify, move, replace, or delete local files related to Mod management.

These files may include:

- Stardew Valley game-related directories;
- the Mods directory;
- Mod files and folders;
- manifest.json;
- Mod configuration files;
- Mod dependency declarations, Unique IDs, versions, and Update Keys;
- Mod update-source information;
- Mod update packages and dependency download packages;
- ZIP files downloaded from Nexus Mods;
- manifests and temporary content extracted while preparing dependency installations;
- multiple Mods in a bundled package when SVMM can validate that they belong to one installation transaction;
- temporary files, staging directories, and transaction backups created during updates or dependency installation;
- local file states required for enabling, disabling, deleting, and switching profiles.

When the user explicitly deletes a Mod through SVMM, the application may also remove that Mod’s profile-membership records from SVMM management data. If a Mod is removed through Finder or another application, SVMM may retain related management records until the user explicitly cleans residual management data.

These operations are performed only to provide Mod management, updating, dependency installation, backup, recovery, enabling, disabling, deletion, and profile features requested by the user. They do not mean that the developer obtains or collects those local files.

## 3.2 Local SVMM Management Data

SVMM stores locally the management information necessary to provide its functionality.

This may include:

- Mod display-name notes and user notes;
- Mod update sources corrected or specified by the user;
- Mod categories and manual category assignments;
- classification schemes and their category structures;
- configuration profiles and their Mod-membership relationships;
- the currently selected configuration profile and classification scheme;
- management records left by uninstalled Mods that the user has not yet cleaned;
- application language, list/card view, sorting, table-column, and other interface preferences;
- identifiers for locally selected Stardew Valley save files;
- system bookmarks or permission data associated with local-directory authorization.

Such information is stored using local macOS storage mechanisms such as SwiftData, UserDefaults, and system authorization mechanisms.

In the current version, dependency-source lookup results are primarily runtime state and may be cached for the current application session to avoid repeating requests for the same Unique ID. The current version does not create a persistent user database mapping “Unique ID → dependency download source,” and finding a dependency source does not by itself cause SVMM to install that dependency.

SVMM does not automatically upload the management data described above to developer-controlled servers.

## 4. Stardew Valley Save Data

To provide farm status, game-progress information, or related overview features, SVMM may read local Stardew Valley save files in read-only mode.

SVMM may locally parse information including:

- player name;
- farm name;
- in-game year;
- season;
- in-game date;
- play time;
- money;
- spouse status;
- family-related in-game status;
- farmhouse upgrade status;
- game progress;
- perfection-related status;
- game version;
- other information needed to generate a local game overview.

This information is used only for SVMM’s local functionality.

SVMM does not intentionally upload Stardew Valley save contents to the developer.

Unless a future version expressly states otherwise and updates this Policy, SVMM also does not send complete save-file contents to Nexus Mods, SMAPI, or other third-party services.

## 5. Local Directory Access Permissions

SVMM requires access to the Stardew Valley game directory and Mods folder in order to function correctly.

Where applicable, when a user actively selects a directory through the macOS system file picker, the user grants SVMM the corresponding scope of local file access.

SVMM should use these permissions only to the extent reasonably necessary to provide the functions requested by the user.

Users may stop such access by changing application settings, selecting a different game directory, clearing related application data, revoking macOS permissions, or uninstalling SVMM.

## 6. Nexus Mods Credentials

If the user enables Nexus Mods functionality, SVMM may need to store Nexus Mods API credentials.

The current version stores Nexus Mods API credentials in the macOS Keychain.

These credentials are not designed to be stored in ordinary UserDefaults, SwiftData, plain JSON files, ordinary configuration files, or SVMM management-data backups.

Nexus Mods API credentials:

- are used only for necessary authorization and API requests to Nexus Mods;
- are not uploaded to developer-controlled servers;
- should not be written to ordinary application logs;
- are not included in SVMM management-data backups.

Users may delete such credentials through relevant SVMM functionality or macOS Keychain-management mechanisms.

## 7. Third-Party Network Services

Some SVMM features require direct communication with third-party servers.

Such communication does not mean that SVMM uploads the user’s data to the developer.

## 7.1 SMAPI

SVMM may communicate with SMAPI-related services to check Mod updates, determine Mod status, obtain Mod metadata, resolve reliable sources for missing or version-problem dependencies, and assist with compatibility-related decisions.

Requests may include:

- Mod Unique IDs;
- current Mod versions;
- Mod Update Keys;
- Mod status;
- one or more dependency Unique IDs submitted in a batch for dependency-source lookup;
- SMAPI/API-related versions;
- Stardew Valley game version;
- macOS platform information;
- other Mod metadata necessary for update or dependency evaluation.

The current dependency-source resolver uses explicit metadata or project pages returned by SMAPI and does not invent unverified third-party download URLs. Resolution results may be cached for the current application session.

SMAPI servers may process ordinary network-request information under their own rules, including IP address, request time, and HTTP headers. The developer does not control SMAPI’s own data-processing practices.

## 7.2 Nexus Mods

When the user uses Nexus Mods features, SVMM may communicate directly with the Nexus Mods API, download services, NXM authorization flow, or related CDNs.

Requests may be used to:

- validate Nexus Mods API credentials;
- query Mod information and file lists;
- obtain Mod versions, thumbnails, and download information;
- query update files or dependency files;
- select installable Nexus Mods files for missing dependencies;
- obtain update files for installed dependencies whose versions are too old;
- obtain temporary download information after NXM authorization for Free accounts;
- obtain direct download links for Premium accounts;
- perform eligible Premium batch updates or batch dependency acquisition;
- determine Nexus Mods API rate limits.

Requests may include:

- Nexus Mods API credentials;
- Mod IDs;
- Mod File IDs;
- application name and SVMM version;
- parameters required by the API request;
- temporary authorization data used by the NXM or download flow.

SVMM does not upload Nexus Mods API credentials to developer-controlled servers. Browser/NXM authorization for Free accounts and direct downloads for Premium accounts are both subject to Nexus Mods service rules.

Nexus Mods processes request, account, and download data under its own privacy policy, terms of service, and platform rules.

## 7.3 Image and Download Servers

SVMM may download Mod thumbnails, update ZIP files, dependency-installation ZIP files, and other resources necessary for Mod-management features from Nexus Mods or related services.

Downloaded files are first stored in temporary or cache locations on the user’s Mac and may be validated locally for format, manifests, Unique IDs, target folders, and installation conflicts. Supported dependency packages are written into the Mods directory only after the user confirms the operation and the relevant checks pass. The current automatic dependency installer handles supported ZIP packages and does not treat RAR or 7z archives as automatic-install formats.

Ordinary internet requests may expose the user’s IP address, request time, HTTP headers, network-connection information, and requested resource identifiers to the relevant third-party server. Those providers process such information under their own policies.

## 8. GitHub and Software Updates

SVMM may use GitHub or other public distribution channels to provide software versions, release notes, and installation files.

The current version uses GitHub's public services for software-update functionality. SVMM may silently access the GitHub Releases API when the application starts in order to obtain information about the latest stable Release; users may also manually check for updates through Help → Update Software. The automatic launch check displays an update notification only when a stable version higher than the currently installed version is detected. If the installed version is already current, the remote version is not higher, the network request fails, or the version information cannot be parsed, the automatic launch check does not display an update notification.

When the user explicitly chooses to download an update, SVMM may download the corresponding DMG disk image directly from the official GitHub Release and store the downloaded file in the application's own local cache directory. Download progress may be shown. When the GitHub Release Asset provides a SHA-256 digest, SVMM calculates the downloaded file's SHA-256 locally on the user's device and compares the values. If the values do not match, SVMM deletes the downloaded file and reports the failure. After successful verification, the user may choose to have macOS open the disk image. The current version does not automatically replace SVMM in `/Applications`, does not automatically overwrite the running application, and does not complete installation without user action.

Software-update requests may contain information required or naturally generated by ordinary HTTP/HTTPS communication, such as the current SVMM version, User-Agent, HTTP headers, the requested Release or Asset identifier, IP address, request time, and network-connection information. These requests are sent directly to GitHub or the relevant public download service and do not pass through a developer-operated software-update server.

Software-update functionality does not thereby upload Stardew Valley save files, Mod files, display-name notes, ordinary notes, categories, classification schemes, configuration profiles, the SVMM management database, or Nexus Mods API Keys to developer-controlled servers.

GitHub processes information related to requests, Release metadata, and download activity under GitHub's own policies.

## 9. Voluntary Donations and Alipay

SVMM is provided free of charge for personal, non-commercial use. The application may provide a voluntary-support option allowing users to support the independent development and maintenance of SVMM through the developer’s personal Alipay payment QR code.

For purposes of this Policy, “voluntary donation” or “voluntary support” means general voluntary support provided by a user to the developer. It is not a charitable solicitation and does not constitute payment for the software, software functionality, a subscription service, or additional license rights.

Voluntary support:

- is entirely optional;
- is not required to download, install, use, or continue using SVMM;
- does not unlock additional functionality;
- does not provide additional software rights;
- does not create a subscription, membership, or paid tier;
- does not reduce the functionality available to users who do not provide support when using the same SVMM version.

In the current version, SVMM only displays a personal Alipay payment QR code provided by the developer. SVMM does not integrate the Alipay payment API and does not process transactions through a developer-controlled payment server. Whether to scan the QR code, whether to make a payment, and the payment amount are determined solely by the user. The actual payment transaction takes place within the payment environment provided by Alipay.

SVMM itself does not process or store bank-card numbers, Alipay login passwords, payment passwords, bank-card authentication information, Alipay account authentication credentials, or other payment authentication secrets.

Alipay and related payment-service providers process payment activity and transaction data under their own service terms, privacy policies, and applicable law. Depending on the information Alipay actually makes available to a payment recipient, the developer, as the recipient, may see ordinary transaction records associated with receiving a payment, such as:

- transaction amount;
- payment time;
- transaction number, payment reference number, or other payment-record identifier;
- other payer or payment information that Alipay makes available to the recipient as required by law or platform rules.

The developer may review such information only to the extent reasonably necessary to confirm or reconcile a payment, respond to an inquiry initiated by the user, or comply with applicable legal requirements. The developer will not use such transaction information for advertising, user profiling, behavioral analytics, cross-service tracking, or sale to third parties.

SVMM does not control Alipay’s collection, retention, use, sharing, or security practices for payment data. Users who provide voluntary support through Alipay are also subject to Alipay’s applicable service agreements and privacy policies.

## 10. Logs and Diagnostic Information

SVMM currently does not operate a remote logging system that automatically collects user behavior for the developer.

Development builds may output local debugging information such as Mod IDs, Unique IDs, file-operation state, dependency-source resolution state, download and file-validation state, network-request state, error information, certain local file paths, scan state, and update diagnostics.

This information is primarily used for local diagnosis and development. Release builds do not automatically send such logs to the developer during normal use.

If a future version provides an “Export Diagnostic Report” feature, it should:

1. be initiated by the user;
2. generate the report locally first;
3. not upload it automatically;
4. allow the user to decide whether to send it to the developer.

Before voluntarily sending diagnostic material by email or another method, users should review it for usernames, local file paths, Mod names, Unique IDs, save names, or other information they do not wish to disclose.

The developer will not ask users to send Nexus API Keys, tokens, payment passwords, account passwords, or other authentication secrets.

## 11. Advertising, Analytics, Telemetry, and Tracking

The current version of SVMM does not include:

- advertising;
- advertising SDKs;
- Firebase Analytics;
- Google Analytics;
- user-behavior analytics services;
- telemetry;
- user profiling;
- cross-app tracking;
- cross-site tracking;
- device fingerprinting for advertising purposes;
- a developer-operated behavioral telemetry system.

If any such mechanism is introduced in the future, this Privacy Policy must be updated before the relevant version is released.

## 12. Caches, Temporary Files, and Update Files

To improve performance or complete safe update, dependency-installation, and file transactions, SVMM may create local:

- Nexus Mods thumbnail caches;
- temporary download files;
- update ZIP files and dependency-installation ZIP files;
- temporary extraction directories;
- update or dependency-installation staging directories;
- temporary backups created by update or dependency-installation transactions;
- hidden temporary directories created for multiple target Mods in a bundled-package installation;
- other temporary management files necessary for validation, installation, rollback, or rescanning.

These data remain on the user's device. SVMM may automatically remove some temporary data after an operation and may also provide cache or residual-management-data cleanup features. If an operation is interrupted abnormally, some temporary files may remain until later cleanup.

In addition, SVMM's own software-update functionality may create or store locally:

- SVMM DMG disk images downloaded from the official GitHub Release;
- temporary files created during software-update downloads;
- local cache data needed for download progress, file movement, and integrity verification.

These software-update files remain on the user's device; the current implementation uses a cache location writable by the application. SHA-256 verification is performed locally and does not upload the DMG to the developer in order to calculate the digest. Cached software-update files may be removed by the operating system, later application workflows, or the user. After a download completes, the current version only offers to open the disk image; it does not automatically replace or install SVMM.

## 13. User-Initiated Data Exports

SVMM may allow users to export certain management information for backup, recovery, migration, or troubleshooting.

The user chooses where the exported file is saved.

SVMM does not automatically send locally created backups to the developer or another third party merely because the user created a backup.

## 14. Data Deletion

Because SVMM primarily follows a local-first data model, users can generally remove corresponding data themselves, for example by:

- deleting notes;
- deleting categories;
- deleting configuration profiles;
- clearing caches;
- cleaning residual management records for uninstalled Mods;
- deleting management data;
- deleting Nexus Mods credentials;
- deleting SVMM application data;
- uninstalling the application.

“Clean residual management records for uninstalled Mods” can remove SVMM management data left by Mods that are no longer present in the current Mods folder, including applicable display-name notes, ordinary notes, user update sources, and configuration-profile membership records. This cleanup does not delete Mods that are still present in the current Mods folder.

When the user explicitly chooses “Delete Mod” in SVMM and the file is successfully moved to the Trash, SVMM may also remove the corresponding configuration-profile memberships. When a Mod is removed externally through Finder or another application, SVMM cannot reliably determine whether the Mod was moved temporarily or deleted permanently, so related management records may remain until the user explicitly cleans them.

For data stored by Alipay, Nexus Mods, SMAPI, GitHub, or other third-party services, users should use the mechanisms provided by those services.

## 15. Data Security

The developer will make reasonable efforts to avoid:

- storing authentication credentials in ordinary plaintext configuration;
- writing API Keys to ordinary logs;
- unnecessarily uploading local files;
- uploading diagnostic reports without user action;
- overwriting an existing Mod with the same Unique ID during dependency installation without validation.

SVMM’s dependency-installation flow performs certain local structure and identity checks on supported downloaded packages and attempts to reduce file-operation risk through temporary directories, staging, and transaction-style writes. These measures do not prove that a third-party Mod itself is safe and cannot guarantee that software or computer systems will never experience errors or data loss.

Users remain responsible for protecting their macOS account, Nexus Mods credentials, game files, Mod files, backups, and payment accounts, and should keep independent backups for important setups.

## 16. Third-Party Content and Trademarks

Stardew Valley, Nexus Mods, SMAPI, and other third-party software, services, names, trademarks, and content remain the property of their respective rights holders.

SVMM is independently developed.

Unless a relevant rights holder expressly states otherwise in writing, SVMM is not affiliated with, officially authorized by, acting as an agent of, sponsored by, or endorsed by those third parties.

## 17. Children’s Privacy

SVMM is not designed as a service for collecting children’s personal information.

The current version does not provide an SVMM account system, social platform, advertising profile, child-directed advertising system, or developer-controlled cloud user profile.

If future product changes materially affect this position, the developer will reassess applicable children’s privacy requirements.

## 18. Changes to This Privacy Policy

The developer should update this Privacy Policy when SVMM makes material changes such as:

- introducing developer-controlled servers;
- introducing an account system;
- introducing cloud synchronization;
- introducing iCloud or other remote synchronization;
- introducing telemetry;
- introducing analytics;
- introducing uploaded crash reporting;
- introducing advertising;
- changing payment methods;
- changing how Nexus credentials are stored;
- introducing additional third-party network services;
- beginning to collect new categories of user data;
- materially changing local-file or save-data processing.

Updated policies should specify a new document version and effective date.

## 19. Contact

Questions about this Privacy Policy or SVMM’s data-processing practices may be sent to:

Developer: Li Wei (李薇)
Email: SVMM@npccare.cn

Users should not send API Keys, passwords, payment passwords, tokens, or other authentication secrets through ordinary email.
