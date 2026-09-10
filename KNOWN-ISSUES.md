# 已知问题 / Known Issues

本文件记录 Stardew Valley Mod Manager（SVMM）当前公开版本已经确认、但暂未处理或依赖外部环境的行为与边界。

This file tracks confirmed issues, compatibility differences, and environment-dependent behavior that are not fully resolved in the current public release.

## 1. macOS 15.0 的“分类”页面响应速度低于 macOS 26 / 27

SVMM 当前正式构建的最低部署目标为 **macOS 15.0**，macOS 15.0 可以正常启动并使用核心 Mod 管理功能。

在当前 macOS 15.0 虚拟机测试中，“分类”页面仍存在可感知的性能差异：

- 首次进入分类页面可能比 macOS 26 / 27 慢；
- 展开分类后进行部分 Mod 行选择时，响应速度不如新系统流畅；
- 经过兼容性与缓存/行身份优化后，功能已经可以正常使用，但交互体验仍低于 macOS 26 / 27；
- 当前没有发现该性能差异会导致 Mod 文件、分类、配置方案或其他管理数据损坏。

同一正式构建在 **macOS 26.0 与 macOS 27.0** 的当前测试中表现流畅。

**测试边界：** 当前 macOS 15.0 结果来自虚拟机环境，因此不能作为所有 macOS 15 实机的绝对性能基准。SVMM 当前不计划仅为旧系统维护另一套专用分类界面。

### English

The current build supports **macOS 15.0 or later**. Core workflows work on macOS 15.0, but the Categories page is less responsive in the current macOS 15 VM test environment than on macOS 26/27. First entry and some Mod-row selection interactions may feel slower.

No related data-integrity problem has been identified. The same build is currently smooth in macOS 26.0 and macOS 27.0 testing.

Because the macOS 15 result comes from a virtual machine, it should not be treated as a universal performance benchmark for every physical macOS 15 Mac.

## 2. Intel 实机测试仍有限 / Physical Intel testing is limited

当前 Release Archive 为 **Universal 2（arm64 + x86_64）**。

- Apple Silicon / arm64 已直接测试；
- x86_64 slice 已在 Apple Silicon 上通过 Rosetta 2 验证启动路径；
- 尚未完成独立 Intel Mac 的完整回归测试。

因此 Intel 用户如遇到可稳定复现的问题，请在 Issue 中同时提供 Mac 型号、macOS 版本与 SVMM 版本。

The release archive is Universal 2. Apple Silicon has been directly tested and the x86_64 execution path has been launch-tested under Rosetta 2, but a full physical-Intel regression pass has not yet been completed.

## 3. macOS beta / seed 系统的“帮助”菜单可能短暂变化

在部分 macOS beta / seed 环境中，首次打开“帮助”菜单时，macOS 可能动态加入类似“将 Stardew Valley Mod Manager 的使用反馈发送给 Apple”的 Feedback Assistant 系统项目。

因此，“帮助”菜单可能短暂出现、消失或重新排列项目。该项目由 macOS 提供，不属于 SVMM 自己的“使用手册”功能，也不影响 Mod 文件、名称备注、分类、配置方案、扫描、更新或依赖数据。

SVMM 不通过运行时重写 `NSApp.mainMenu` 的方式强制删除该系统项目，以避免破坏 SwiftUI / AppKit 原生菜单生命周期。

### English

On some macOS beta/seed builds, macOS may dynamically inject a Feedback Assistant item into the Help menu. This system-provided item can briefly appear/disappear or move while the menu initializes. It is separate from SVMM's User Manual and does not affect Mod data or core management workflows.

## 4. 非标准 Mod 目录与发布包 / Non-standard Mod layouts and packages

第三方 Mod 的实际目录结构与发布方式并不完全统一。

SVMM 会尽量诊断嵌套目录、Manifest、依赖、Unique ID 和安装包结构，并且已经支持经过验证的 bundled multi-Mod ZIP。但以下情况仍可能要求用户手动处理：

- 无法可靠识别实际 Mod 根目录；
- 重复或冲突的 Unique ID；
- 不明确的目标目录；
- 非 ZIP 自动安装格式；
- 作者要求特殊手动安装步骤；
- 无法证明多个组件属于同一个安全事务的组合包。

SVMM 在无法可靠判断时会停止自动化，而不是猜测写入位置。

Third-party Mods do not follow one perfectly uniform layout or release convention. SVMM validates supported packages conservatively and may require manual review when the package cannot be identified safely.

## 5. 第三方在线服务变化 / Third-party service changes

Nexus Mods、SMAPI、GitHub 或相关 CDN / 下载基础设施的 API、授权流程、页面结构、Rate Limit 或服务策略发生变化时，SVMM 对应的可选在线功能可能受到影响。

Changes to Nexus Mods, SMAPI, GitHub, related CDNs, APIs, authorization flows, rate limits, or service policies may affect optional online workflows.

---

如果发现新的、可稳定复现的问题，请使用 [GitHub Issues](https://github.com/XModLife/Stardew-Valley-Mod-Manager/issues) 提交，并说明 SVMM 版本、macOS 版本、Mac 芯片/架构，以及问题发生在物理 Mac 还是虚拟机中。

For reproducible issues, use [GitHub Issues](https://github.com/XModLife/Stardew-Valley-Mod-Manager/issues) and include the SVMM version, macOS version, Mac architecture, and whether the environment is a physical Mac or VM.
