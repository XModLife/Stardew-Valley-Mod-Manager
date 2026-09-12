# 更新记录 / Changelog

## 1.2.0 — 2026-09-12

v1.2.0 是一次配置方案体验与自动分类能力更新，重点提升大量 Mod 环境下的视觉识别效率，并继续完善保守的自动分类策略。

### 配置方案与缩略图

- 配置方案 Mod 列表新增缩略图显示；
- 只读取 SVMM 已有的本地 Nexus 缩略图缓存，不会因为进入配置方案页面额外请求 Nexus Mods；
- 根据当前 Mod 行内容自适应缩略图显示高度；
- 鼠标悬停缩略图时可查看更大的预览；
- 新增两种缩略图位置：
  - 靠近 Mod 信息；
  - 靠近启用 / 停用状态；
- Toolbar 提供直接可见的分段切换控件，可以单击切换两种布局；
- 两种布局使用对应的左 / 右对齐图标；
- 缩略图位置偏好通过本地设置持久保存；
- 缩略图只作为视觉识别辅助，不改变配置方案、Mod 状态或 Nexus 更新逻辑。

### 自动分类

- 继续扩充保守自动分类规则；
- 改进建筑类 Content Pack 识别；
- 改进地图与路径类 Mod 识别；
- 补充部分已确认的家具、装饰物与环境美化分类；
- 修复普通 Mod 因 Description 中出现 Stardew Valley Expanded、Ridgeside Village、East Scarp 等兼容性描述，而被错误归入“大型扩展”的问题；
- 大型扩展识别现在更严格地依赖 Mod 自身身份信息，而不是普通 Description 中的兼容性文字；
- 无法可靠判断的 Mod 继续保留“未识别”。

### 发布信息

- 软件版本更新为 **1.2.0（Build 3）**；
- 最低系统继续为 **macOS 15.0**；
- 正式构建继续提供 **Universal 2（arm64 + x86_64）**；
- 隐私政策继续使用 **1.1 / 2026-09-11**；
- 软件许可协议继续使用 **1.0 / 2026-09-10**。

### English Summary

Version 1.2.0 adds:

- locally cached Mod thumbnails to Profiles;
- larger thumbnail previews on hover;
- two user-selectable thumbnail placement layouts;
- a one-click segmented toolbar control for switching layouts;
- persistent local storage of the selected thumbnail placement;
- no additional Nexus Mods requests from Profiles solely for thumbnail display;
- refined conservative classification for buildings, maps, furniture, decorations, and environmental Mods;
- a fix preventing compatibility descriptions from incorrectly classifying ordinary Mods as large expansions.

The minimum supported system remains macOS 15.0, and the official build remains Universal 2 (`arm64 + x86_64`).

---

## 1.1.0 — 2026-09-11

v1.1.0 是在 1.0.0 基础上的功能与维护更新，重点补充 Manifest 维护、Mod 管理体验、自动分类以及 SVMM 自身更新流程。

### Manifest 与 Mod 管理

- 新增 **Manifest Editor**，可从 Mod 库或分类页面打开单个 Mod 的 `manifest.json`；
- 提供结构化编辑与原始 JSON 两种模式；
- 支持 Name、Author、Version、UniqueID、Description、EntryDll、MinimumApiVersion、MinimumGameVersion、UpdateKeys、Dependencies 与 ContentPackFor；
- 保存前执行内容验证，保存后自动重新扫描 Mods；
- 结构化写回基于完整 JSON 对象，尽量保留与本次修改无关的未知字段；
- 修复 Manifest Editor 模式切换时的 SwiftUI publishing warning；
- Mod 详细信息面板新增 Nexus 缩略图；
- Mod 库分类菜单会标记当前分类；
- 分类页面新增搜索。

### 自动分类

- 扩充 UI / Interface / Cursor 等高置信度身份识别；
- 改进 Fashion Sense 内容包、body type、custom farm、crib、plushie、tree pack、furniture placement 等分类规则；
- 对部分语义不适合泛化的 Mod 使用精确名称映射；
- 保持保守策略：无法可靠判断时继续保留“未识别”，不强行分类。

### SVMM 软件更新

- 启动时可静默检查官方 GitHub Releases 的最新正式版本；
- 只有远端正式版本高于当前版本时才显示启动更新提示；
- 已是最新版、远端版本不高于当前版本、网络失败或版本解析失败时，启动检查保持静默；
- 保留“帮助 → 更新软件”手动检查；
- 支持在 SVMM 内直接下载官方 Release DMG 并显示进度；
- GitHub 提供 Release Asset SHA-256 digest 时执行本地校验；
- 校验失败会删除下载文件；
- 下载成功后可让 macOS 打开安装镜像；
- 当前版本不自动覆盖 `/Applications` 中的 SVMM，不自动完成安装；
- GitHub Release 页面继续作为备用下载入口。

### 文档与隐私

- 软件版本更新为 **1.1.0（Build 2）**；
- 隐私政策更新为 **1.1 / 2026-09-11**，明确说明 GitHub Releases 启动检查、DMG 下载、缓存与本地 SHA-256 校验；
- 软件许可协议继续使用 **1.0 / 2026-09-10**，许可条件未改变。

### English Summary

Version 1.1.0 adds:

- a structured/Raw JSON Manifest Editor with validation and post-save rescanning;
- category search, current-category checkmarks, and a Nexus thumbnail in Mod details;
- refined conservative automatic classification rules;
- silent launch-time checks for newer stable SVMM Releases;
- in-app DMG downloads with progress;
- local SHA-256 verification when GitHub provides an asset digest;
- an **Open Disk Image** workflow without automatic self-replacement or installation;
- Privacy Policy 1.1 describing the new GitHub update behavior.

The Software License Agreement remains version 1.0 because the licensing terms did not change.

---

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
