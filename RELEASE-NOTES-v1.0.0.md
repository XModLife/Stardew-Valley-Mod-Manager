# Stardew Valley Mod Manager v1.0.0

Stardew Valley Mod Manager（SVMM）首次公开发布。

**专用于 macOS 的中文友好型《星露谷物语》Mod 管理器。**

## 系统要求

- **macOS 27.0 或更高版本**
- **Apple Silicon Mac（arm64）**
- **当前 v1.0.0 不支持 Intel Mac**
- macOS 版 Stardew Valley
- 正常 Mod 环境推荐配合 SMAPI 使用

## 主要功能

- 原生 macOS Mod 管理界面
- Mod 库卡片 / 列表视图
- 名称备注
- 分类
- 配置方案
- Mod 扫描诊断
- Stardew Valley 农场 / 存档只读概览
- SMAPI Mod 更新与依赖信息检查
- 可选 Nexus Mods 连接
- Free 浏览器 / NXM 工作流
- 符合条件的 Premium 直接下载、批量更新与批量依赖获取
- 受支持的 Mod 更新 / 依赖安装校验、备份、回滚与配置保留
- 简体中文 / English / 跟随系统

## 界面语言

中文友好是 SVMM 的核心定位之一，也是项目诞生的初衷。

当前语言顺序：

1. **简体中文**
2. **English**
3. **跟随系统**

修改语言后需要重新启动 SVMM，以确保应用主体和 macOS 原生菜单完整切换到同一语言。

## 已知事项

在部分 macOS beta / seed 系统中，首次打开“帮助”菜单时，macOS 可能动态加入 Feedback Assistant 系统项目，使菜单内容出现一次短暂变化。该项目由 macOS 提供，不影响 Mod 数据或 SVMM 核心管理功能。

完整列表参阅仓库中的 `KNOWN-ISSUES.md`。

## macOS 安全提示

当前 v1.0.0 安装包未使用 Apple Developer ID 签名，也未经过 Apple Notarization。

首次启动可能触发 macOS Gatekeeper 提示。请确认 DMG 来自本仓库官方 Release，并核对同时提供的 SHA-256。确认来源后，可在“系统设置 → 隐私与安全性 → 安全性”中使用“仍要打开（Open Anyway）”完成首次启动授权。

## 下载与分发

请只从本仓库的官方 GitHub Release 获取 SVMM 安装文件。

SVMM 当前免费提供个人、非商业使用。软件为闭源、专有软件；具体权利和限制以软件许可协议为准。

---

## English

Stardew Valley Mod Manager v1.0.0 is the first public release of SVMM, a Chinese-friendly native Stardew Valley Mod manager for macOS.

**Minimum system:** macOS 27.0 or later.  
**Architecture:** Apple Silicon Mac (arm64).  
**Intel Macs are not supported by this v1.0.0 build.**

SVMM provides native Mod-library management, notes, categories, profiles, diagnostics, save/farm overview, SMAPI metadata checks, optional Nexus Mods workflows, conservative update/dependency transactions, and Simplified Chinese / English localization.

See the English documentation in the repository for full details.
