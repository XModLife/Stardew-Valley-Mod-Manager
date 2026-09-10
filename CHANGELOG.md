# 更新记录 / Changelog

## 1.0.0 — 2026-09-10

Stardew Valley Mod Manager（SVMM）首次公开发布。

### 平台与兼容性

- 最低部署目标调整为 **macOS 15.0**；
- 使用单一正式代码库维护 macOS 15.0 及更高版本；
- Release Archive 为 **Universal 2（arm64 + x86_64）**；
- Apple Silicon 原生运行已测试；
- x86_64 执行路径已通过 Rosetta 2 启动验证；
- macOS 15.0 核心功能可用；当前虚拟机测试中“分类”页面响应速度低于 macOS 26/27；
- macOS 26.0 与 macOS 27.0 当前测试流畅。

### 主要功能

- 原生 macOS Mod 管理界面；
- Mod 库卡片视图与列表视图；
- Mod 名称备注与普通备注，不修改作者原始 `manifest.json`；
- 系统默认分类与用户分类方案；
- 配置方案及启用/停用组合管理；
- Mod 扫描诊断与状态管理；
- Stardew Valley 农场 / 存档只读概览；
- SMAPI 更新与依赖元数据检查；
- 可选 Nexus Mods 连接；
- Free 浏览器 / NXM 下载流程；
- 符合条件的 Premium 直接下载、批量更新与批量依赖获取；
- 受支持的 Mod 更新 / 依赖安装事务校验、备份、回滚与配置保留；
- 支持经过验证的 **bundled multi-Mod ZIP** 更新与依赖安装，避免作者将多个必需组件共同打包时被简单拒绝；
- Nexus 缩略图缓存与 Mod 临时事务数据管理；
- 已卸载 Mod 残留管理记录清理；
- Mod 备注导入 / 导出；
- 管理器数据备份创建与恢复；
- 简体中文、English、跟随系统；
- 界面语言在重新启动后完整应用，使应用主体与 macOS 原生菜单保持一致；
- 本地化架构保留扩展更多语言的空间，但当前由开发者正式维护/审核的语言仅为简体中文与 English。

### 已知事项

请参阅 [KNOWN-ISSUES.md](KNOWN-ISSUES.md)。

---

## English

Version 1.0.0 is the first public release of SVMM.

Highlights include:

- minimum deployment target: **macOS 15.0**;
- one official macOS 15+ codebase;
- Universal 2 Release archive (`arm64 + x86_64`);
- native Mod-library management with card/list views;
- display-name notes and personal notes;
- categories and enable/disable profiles;
- scan diagnostics and read-only save/farm overview;
- SMAPI metadata checks and optional Nexus Mods workflows;
- Free NXM workflows and eligible Premium direct/batch workflows;
- conservative update/dependency transactions with validation, backup, rollback, and configuration preservation where applicable;
- validated bundled multi-Mod ZIP support for both dependency installation and Mod updates;
- storage/cache maintenance, residual-record cleanup, note import/export, and manager-data backup/restore;
- Simplified Chinese, English, and System Default language selection.

macOS 15.0 is supported, although the Categories page is less responsive in the current macOS 15 VM tests than on macOS 26/27. See [KNOWN-ISSUES.md](KNOWN-ISSUES.md).
