# Frequently Asked Questions / 常见问题

## Is SVMM open source? / SVMM 是开源软件吗？

No. SVMM is closed-source, proprietary software. This public repository is used for official releases, user documentation, screenshots, and issue reporting.

不是。SVMM 是闭源、专有软件。本公开仓库用于官方 Release、用户文档、截图与问题反馈。

## Is SVMM free? / SVMM 免费吗？

SVMM is currently free of charge for personal, non-commercial use. Optional support does not unlock features or grant additional license rights.

SVMM 当前免费提供个人、非商业使用。自愿支持不会解锁功能，也不会获得额外许可权利。

## Where should I download SVMM? / 应该从哪里下载？

Use the official [GitHub Releases page](https://github.com/XModLife/Stardew-Valley-Mod-Manager/releases).

请通过官方 [GitHub Releases](https://github.com/XModLife/Stardew-Valley-Mod-Manager/releases) 获取。

## Does SVMM upload my Mods or saves? / SVMM 会上传我的 Mods 或存档吗？

The current version does not operate a developer-controlled server for uploading users' Mods, save files, or SVMM management databases. Optional features may communicate directly with third-party services such as SMAPI, Nexus Mods, and GitHub.

当前版本不运营用于接收用户 Mods、存档或 SVMM 管理数据库的开发者服务器。部分可选功能会直接访问 SMAPI、Nexus Mods、GitHub 等第三方服务。

## Do I need Nexus Mods? / 必须连接 Nexus Mods 吗？

No. Local scanning, notes, categories, profiles, and other offline management functions do not require a Nexus Mods account.

不需要。本地扫描、名称备注、分类、配置方案等离线管理功能不要求 Nexus Mods 账户。

## Categories vs Profiles? / “分类”和“配置方案”有什么区别？

**Categories** organize Mods. **Profiles** define an actual enable/disable combination.

**分类**用于整理 Mods；**配置方案**用于保存并应用实际启用 / 停用组合。

## Why does changing language require a restart? / 为什么修改语言需要重启？

Native macOS menu localization is established as part of the application launch environment. SVMM therefore applies a complete language change after restart so the app content and native menu bar stay consistent.

macOS 原生菜单的本地化状态在应用启动阶段确定。SVMM 因此在重新启动后完整应用语言，使应用内容与原生菜单保持一致。

## Can SVMM guarantee third-party Mod compatibility? / SVMM 能保证第三方 Mod 兼容吗？

No. SVMM can scan, organize, diagnose, and perform supported management operations, but compatibility ultimately depends on the Mod, Stardew Valley, SMAPI, other Mods, and the user's environment.

不能。SVMM 可以扫描、整理、诊断并执行受支持的管理操作，但兼容性最终取决于 Mod 本身、Stardew Valley、SMAPI、其他 Mods 和用户环境。

## Where should I report a bug? / Bug 在哪里反馈？

Use [GitHub Issues](https://github.com/XModLife/Stardew-Valley-Mod-Manager/issues) for ordinary bugs and compatibility reports. For security vulnerabilities, follow [SECURITY.md](SECURITY.md).

## macOS 为什么提示无法验证开发者或无法检查 App？ / Why does macOS warn that it cannot verify the developer?

SVMM v1.0.0 当前没有 Apple Developer ID 签名，也没有 Apple Notarization，因此从互联网下载后可能触发 Gatekeeper 提示。请只使用官方 GitHub Release，并核对发布页提供的 SHA-256；确认来源后，可通过“系统设置 → 隐私与安全性 → 安全性 → 仍要打开（Open Anyway）”进行首次授权。

SVMM v1.0.0 is not Developer ID-signed or Apple-notarized. Download only from the official GitHub Release, verify the published SHA-256, and use macOS “Open Anyway” only after confirming the file's source.
