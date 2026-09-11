# Frequently Asked Questions / 常见问题

## What macOS versions are supported? / 支持哪些 macOS 版本？

The current official build has a minimum deployment target of **macOS 15.0** and is maintained as one macOS 15+ codebase.

当前正式构建最低支持 **macOS 15.0**，并以同一份 macOS 15+ 代码库继续维护。

Current testing:
- macOS 15.0: core workflows work, but Categories is less responsive in the current VM test environment.
- macOS 26.0: tested smooth.
- macOS 27.0: tested smooth.

当前测试：
- macOS 15.0：核心功能可用，但当前虚拟机测试中“分类”页面响应速度低于新系统；
- macOS 26.0：测试流畅；
- macOS 27.0：测试流畅。

## Does SVMM support Intel Macs? / 支持 Intel Mac 吗？

The Release archive is Universal 2 and includes both `arm64` and `x86_64`. Apple Silicon is directly tested. The x86_64 execution path has been launch-tested through Rosetta 2, but a full physical-Intel regression pass has not yet been completed.

Release Archive 为 Universal 2，包含 `arm64` 与 `x86_64`。Apple Silicon 已直接测试；x86_64 路径已通过 Rosetta 2 验证启动，但尚未完成 Intel 实机的完整回归测试。

## Is SVMM open source? / SVMM 是开源软件吗？

No. SVMM is closed-source, proprietary software. This public repository is used for official releases, user documentation, screenshots, and issue reporting.

不是。SVMM 是闭源、专有软件。本公开仓库用于官方 Release、用户文档、截图与问题反馈。

## Is SVMM free? / SVMM 免费吗？

SVMM is currently free of charge for personal, non-commercial use. Optional support does not unlock features or grant additional license rights.

SVMM 当前免费提供个人、非商业使用。自愿支持不会解锁功能，也不会获得额外许可权利。

## Where should I download SVMM? / 应该从哪里下载？

Use the official [GitHub Releases page](https://github.com/XModLife/Stardew-Valley-Mod-Manager/releases).

请通过官方 [GitHub Releases](https://github.com/XModLife/Stardew-Valley-Mod-Manager/releases) 获取。

## Does SVMM check for application updates automatically? / SVMM 会自动检查软件自身更新吗？

Yes. Starting with v1.1.0, SVMM silently checks the official GitHub Releases feed when the app starts. A launch notification appears only when the latest stable version is higher than the installed version. If SVMM is already up to date, the remote version is not higher, or the check fails, the automatic launch check stays silent.

会。从 v1.1.0 起，SVMM 启动时会静默查询官方 GitHub Releases。只有检测到高于当前安装版本的正式版本时才显示更新提示；已是最新版、远端版本不高于当前版本或检查失败时，启动自动检查不会弹出更新提示。

## Can SVMM download its own update inside the app? / 可以直接在 SVMM 内下载软件更新吗？

Yes. When a newer stable Release is available, SVMM can download the official DMG inside the application and show progress. If GitHub provides a SHA-256 asset digest, SVMM verifies the file locally. The current version can open the downloaded disk image but does not automatically overwrite or install itself.

可以。有新的正式版本时，SVMM 可以在应用内直接下载官方 DMG 并显示进度。GitHub 提供 SHA-256 digest 时会在本地校验文件。当前版本可以打开下载完成的安装镜像，但不会自动覆盖或安装自身。

## Can I edit a Mod's `manifest.json` with SVMM? / 可以用 SVMM 修改 Mod 的 `manifest.json` 吗？

Yes. v1.1.0 adds a Manifest Editor with Structured and Raw JSON modes. It edits the Mod's actual `manifest.json`, unlike display-name notes or user update-source overrides. Identity-critical changes such as Unique ID or dependencies should be made only when you have reliable source information.

可以。v1.1.0 新增 Manifest Editor，提供结构化模式和原始 JSON 模式。它修改的是 Mod 的真实 `manifest.json`，与名称备注或用户更新来源覆盖不同。Unique ID、依赖等关键字段应只在有可靠来源信息时修改。

## Does SVMM upload my Mods or saves? / SVMM 会上传我的 Mods 或存档吗？

The current version does not operate a developer-controlled server for uploading users' Mods, save files, or SVMM management databases. Some features communicate directly with third-party services such as SMAPI, Nexus Mods, and GitHub; v1.1.0 can also query GitHub Releases at launch for software updates.

当前版本不运营用于接收用户 Mods、存档或 SVMM 管理数据库的开发者服务器。部分功能会直接访问 SMAPI、Nexus Mods、GitHub 等第三方服务；v1.1.0 还可以在启动时查询 GitHub Releases 检查软件更新。

## Do I need Nexus Mods? / 必须连接 Nexus Mods 吗？

No. Local scanning, notes, categories, profiles, backups, and other offline management functions do not require a Nexus Mods account.

不需要。本地扫描、备注、分类、配置方案、数据备份等离线管理功能不要求 Nexus Mods 账户。

## What are display-name notes for? / “名称备注”有什么作用？

A display-name note lets you record a Mod using a name that is easier for you to recognize—for example, a Chinese name for a long English project title. It is local SVMM metadata and does not modify the Mod author's original name or `manifest.json`.

名称备注用于给 Mod 添加一个自己更容易识别的本地名称，例如把较长的英文项目名备注成熟悉的中文名称。它属于 SVMM 本地管理数据，不修改作者原始名称，也不改写 `manifest.json`。

## Categories vs Profiles? / “分类”和“配置方案”有什么区别？

**Categories** organize Mods. **Profiles** define an actual enable/disable combination.

**分类**用于整理 Mods；**配置方案**用于保存并应用实际启用 / 停用组合。

## Can SVMM update a ZIP that contains multiple Mods? / 更新包包含多个 Mod 时能处理吗？

Yes, when SVMM can safely validate that the package is a bundled multi-Mod release and can unambiguously identify the target and companion components. Supported components are updated/installed as one transaction with rollback protections.

可以。在能够确认这是同一作者/发布包需要共同处理的 bundled multi-Mod package，并能可靠识别目标与同包组件时，SVMM 会以一个事务更新/安装；无法安全判断时不会猜测。

## Why does changing language require a restart? / 为什么修改语言需要重启？

Native macOS menu localization is established as part of the application launch environment. SVMM applies a complete language change after restart so app content and the native menu bar stay consistent.

macOS 原生菜单的本地化状态在应用启动阶段确定。SVMM 因此在重新启动后完整应用语言，使应用内容与原生菜单保持一致。

## Can SVMM support more languages? / 可以支持更多语言吗？

The localization architecture uses dedicated localization resources / String Catalogs and leaves room for additional languages. The currently maintained and reviewed interface languages are **Simplified Chinese and English**.

SVMM 的本地化架构使用独立语言资源 / String Catalog，设计上可以继续增加语言。当前由开发者正式维护与审核的界面语言是 **简体中文和 English**。

“System Default / 跟随系统” only chooses among localizations actually included in SVMM; it does not automatically translate the app.

The developer cannot responsibly create or review languages they do not know. Fluent translators/reviewers who want to collaborate on another language are welcome to open an Issue or contact **SVMM@npccare.cn**.

开发者不会把自己无法理解、无法审核的语言直接标记为官方支持。如希望协助其他语言的翻译、校对与长期维护，可以通过 Issue 或 **SVMM@npccare.cn** 联系。

## What can be backed up? / 设置里的备份功能做什么？

SVMM can export/import Mod note data and can create/restore manager-data backups for supported management information. Storage & Cache controls also let you inspect and clean thumbnail cache, temporary transaction files, and residual records from uninstalled Mods.

SVMM 可以导入/导出 Mod 备注，并创建/恢复受支持的管理器数据备份。“存储与缓存”还可以管理缩略图缓存、临时事务文件以及已卸载 Mod 留下的管理记录。

## Can SVMM guarantee third-party Mod compatibility? / SVMM 能保证第三方 Mod 兼容吗？

No. SVMM can scan, organize, diagnose, and perform supported management operations, but compatibility ultimately depends on the Mod, Stardew Valley, SMAPI, other Mods, and the user's environment.

不能。SVMM 可以扫描、整理、诊断并执行受支持的管理操作，但兼容性最终取决于 Mod 本身、Stardew Valley、SMAPI、其他 Mods 和用户环境。

## Why does macOS warn that it cannot verify the developer? / macOS 为什么提示无法验证开发者？

The current official SVMM GitHub release build is not Developer ID-signed or Apple-notarized. Download only from the official GitHub Release, verify the published SHA-256, and use macOS “Open Anyway” only after confirming the file's source.

当前官方 SVMM GitHub 发行包没有 Apple Developer ID 签名，也没有 Apple Notarization。请只使用官方 GitHub Release，并核对 SHA-256；确认来源后再使用“仍要打开（Open Anyway）”。

## Where should I report a bug? / Bug 在哪里反馈？

Use [GitHub Issues](https://github.com/XModLife/Stardew-Valley-Mod-Manager/issues) for ordinary bugs and compatibility reports. For performance/compatibility issues, include the macOS version, Mac chip/architecture, and whether you are using a physical Mac or VM. For security vulnerabilities, follow [SECURITY.md](SECURITY.md).

普通 Bug 和兼容性问题请使用 GitHub Issues。性能/兼容性问题请额外提供 macOS 版本、Mac 芯片/架构以及物理机/虚拟机信息；安全漏洞请按照 [SECURITY.md](SECURITY.md) 私下报告。
