# 已知问题 / Known Issues

本文件记录 Stardew Valley Mod Manager（SVMM）当前公开版本已经确认、但暂未处理或依赖外部环境的问题。

This file tracks confirmed issues or environment-dependent behaviors that are not fully resolved in the current public release.

## 1. macOS beta / seed 系统的“帮助”菜单可能短暂变化

在部分 macOS beta / seed 环境中，首次打开“帮助”菜单时，macOS 可能动态加入类似：

> 将 Stardew Valley Mod Manager 的使用反馈发送给 Apple

的 Feedback Assistant 系统项目。

因此，“帮助”菜单可能在首次打开时出现一次短暂的项目出现、消失或重新排列。该项目由 macOS 测试版系统注入，不属于 SVMM 自己的“使用手册”功能。

**影响范围：**

- 不影响 Mod 文件；
- 不影响名称备注；
- 不影响分类；
- 不影响配置方案；
- 不影响扫描、更新、依赖或其他核心管理数据。

SVMM 不再通过直接修改 `NSApp.mainMenu`、删除系统菜单项或运行时重写菜单树的方式隐藏该系统项目，因为这类做法曾可能破坏 SwiftUI / AppKit 菜单生命周期稳定性。

### English

On some macOS beta / seed builds, the system may dynamically inject a Feedback Assistant item into the Help menu the first time it is opened. This can cause one brief appearance/disappearance or reordering of Help-menu items.

The injected item is provided by macOS and is separate from SVMM's own User Manual. It does not affect Mod data or core management functions.

SVMM intentionally does not manipulate `NSApp.mainMenu` at runtime to remove this system item.

## 2. 非标准 Mod 目录结构

第三方 Mod 的实际目录结构并不完全统一。SVMM 会尽量诊断嵌套目录、Manifest、依赖和安装包结构，但极少数非标准发布包仍可能需要用户手动确认。

Third-party Mods do not follow one perfectly uniform directory/package structure. Unusual packages may still require manual review.

## 3. 第三方在线服务变化

Nexus Mods、SMAPI、GitHub 或相关 CDN / 下载基础设施的 API、授权流程、页面结构或服务策略发生变化时，SVMM 对应的在线功能可能受到影响。

Changes to Nexus Mods, SMAPI, GitHub, or related download infrastructure may affect optional online workflows.

---

如果发现新的、可稳定复现的问题，请使用 [GitHub Issues](https://github.com/XModLife/Stardew-Valley-Mod-Manager/issues) 提交。

For reproducible issues, use [GitHub Issues](https://github.com/XModLife/Stardew-Valley-Mod-Manager/issues).
