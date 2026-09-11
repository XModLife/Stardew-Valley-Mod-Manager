# Stardew Valley Mod Manager v1.1.0

发布日期：2026-09-11

Stardew Valley Mod Manager（SVMM）v1.1.0 是在首个公开版本 1.0.0 基础上的功能与维护更新。本版本重点完善 `manifest.json` 维护、分类体验与自动分类，并补齐 SVMM 自身的软件更新检查和 App 内下载流程。

## 下载校验

正式 Release DMG 生成后，必须将下方占位符替换为最终文件的真实 SHA-256：

```text
SHA-256: 1a179c549451f8c4ecb23eab0278d58c10a77b24ceeb8163aeffb9e1282a83bb
```

在 SHA-256 尚未替换前，不应将本文件用于最终 GitHub Release。

## 系统要求

- **最低系统：macOS 15.0**
- **Universal 2：arm64 + x86_64**
- Apple Silicon 为主要直接测试平台
- x86_64 执行路径已通过 Rosetta 2 启动验证；Intel 实机完整回归仍有限
- macOS 版 Stardew Valley
- 正常 Mod 环境通常需要 SMAPI

## v1.1.0 主要更新

### Manifest Editor

- 可从 Mod 库或分类页面编辑单个 Mod 的真实 `manifest.json`；
- 结构化模式与原始 JSON 模式；
- 支持常见 Manifest 字段、UpdateKeys、Dependencies 与 ContentPackFor；
- 保存前验证；
- 保存后重新扫描 Mods；
- 结构化写回尽量保留未知字段。

### Mod 管理与分类

- 分类页面新增搜索；
- Mod 库分类菜单显示当前分类勾选；
- Mod 详细信息面板新增 Nexus 缩略图；
- 自动分类规则进一步扩充 UI、服饰、家具、装饰物、地图、工具与环境类高置信度模式；
- 无法可靠判断的 Mod 继续保持“未识别”。

### SVMM 软件更新

- 启动时静默检查官方 GitHub Releases；
- 只有最新正式版本高于当前版本时才弹出更新提示；
- 已是最新版、远端版本不高于当前版本或自动检查失败时不弹窗；
- “帮助 → 更新软件”继续提供手动检查；
- 新版本 DMG 可直接在 SVMM 内下载并显示进度；
- GitHub 提供 Release Asset SHA-256 digest 时执行本地完整性校验；
- 校验失败时删除下载文件；
- 下载成功后可打开安装镜像；
- 当前不会自动覆盖 `/Applications` 中的 SVMM，也不会自动完成安装；
- GitHub Release 页面保留为备用下载方式。

## 隐私与网络行为

v1.1.0 对软件自身更新行为进行了明确披露：

- 启动时可直接访问 GitHub Releases API；
- 用户主动下载更新时可直接访问 GitHub Release Asset；
- 软件更新请求不经过开发者自建更新服务器；
- 不会因为软件更新上传 Stardew Valley 存档、Mod 文件、名称备注、分类、配置方案、SVMM 管理数据库或 Nexus Mods API Key；
- GitHub 提供 SHA-256 digest 时，摘要计算在用户 Mac 本地完成。

隐私政策版本更新为 **1.1（2026-09-11）**。软件许可协议仍为 **1.0（2026-09-10）**，许可条件没有改变。

## macOS 安全提示

当前官方 GitHub 发行包未使用 Apple Developer ID 证书签名，也未经过 Apple Notarization。首次启动可能触发 Gatekeeper 提示。

请只从本仓库官方 GitHub Release 获取 SVMM，并核对 Release 页面提供的 SHA-256。确认来源后，如 macOS 阻止首次启动，可在：

**系统设置 → 隐私与安全性 → 安全性 → 仍要打开（Open Anyway）**

完成首次授权。

## 已知事项

- macOS 15.0 的“分类”页面在当前虚拟机测试中响应速度低于 macOS 26/27，但核心功能可使用；
- Intel 实机完整回归测试仍有限；
- 极少数非标准第三方 Mod 包仍可能需要人工处理；
- Nexus Mods、SMAPI、GitHub 或相关下载基础设施变化可能影响可选在线功能。

完整列表见 [KNOWN-ISSUES.md](KNOWN-ISSUES.md)。

---

## English

Stardew Valley Mod Manager v1.1.0 is a feature and maintenance update over the initial 1.0.0 release.

Highlights:

- structured and Raw JSON Manifest Editor;
- category search and improved classification workflows;
- Nexus thumbnail in the Mod details panel;
- refined conservative automatic classification;
- silent launch-time checks for newer stable SVMM Releases;
- in-app official DMG downloads with progress;
- local SHA-256 verification when GitHub provides an asset digest;
- **Open Disk Image** after a successful download;
- no automatic replacement of the installed/running app;
- Privacy Policy 1.1 describing the new GitHub update behavior.

**Minimum OS:** macOS 15.0  
**Architecture:** Universal 2 (`arm64 + x86_64`)

The Software License Agreement remains version 1.0 because the licensing terms have not changed.
