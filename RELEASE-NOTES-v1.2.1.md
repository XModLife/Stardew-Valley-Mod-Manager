# Stardew Valley Mod Manager v1.2.1

发布日期：2026-09-12

Stardew Valley Mod Manager（SVMM）v1.2.1 是一次软件自更新下载流程的维护修复。本版本重点解决 v1.2.0 在 App Sandbox 环境下使用内置更新下载器取得 DMG 后，安装镜像中的 App 可能无法正常打开的问题。

## 下载校验

正式发行文件：

```text
Stardew-Valley-Mod-Manager-v1.2.1-macOS.dmg
```

SHA-256：

```text
80aa9cc360ee6ee7031347a02b0e1dc18b3e2a9ba8a09f586f5b3113a2d0385f
```

## 系统要求

- **最低系统：macOS 15.0**
- **Universal 2：arm64 + x86_64**
- Apple Silicon 为主要直接测试平台
- x86_64 执行路径已通过 Rosetta 2 启动验证；Intel 实机完整回归仍有限
- macOS 版 Stardew Valley
- 正常 Mod 环境通常需要 SMAPI

## v1.2.1 主要修复

### 修复 App Sandbox 下的软件更新 DMG

v1.2.0 的应用内更新下载器会把 DMG 自动保存到 SVMM 自己的 Sandbox Cache。实际测试确认，在部分 macOS 环境中，这类 DMG 会获得表示“由 App Sandbox 创建且缺少明确用户授权”的隔离状态。DMG 本身的 SHA-256 可以完全正确，但其中的 SVMM.app 仍可能被 macOS 拒绝执行。

v1.2.1 将软件更新下载流程调整为：

1. 用户点击“下载更新”；
2. macOS 显示原生保存面板；
3. 用户明确选择 DMG 文件名和保存位置；
4. SVMM 在应用内继续下载并显示实时进度；
5. GitHub 提供 Release Asset SHA-256 digest 时，SVMM 在本地完成校验；
6. 校验成功后可以直接选择“打开安装镜像”。

同时：

- SVMM **继续启用 App Sandbox**；
- 新增 `com.apple.security.files.user-selected.executable` entitlement，只用于用户通过系统保存面板明确选择的软件更新文件位置；
- 更新 DMG 不再自动保存到 App 自己的 `Caches/SoftwareUpdates`；
- 下载完成时不会直接复制 URLSession 临时文件的扩展属性到最终 DMG；
- SHA-256 校验失败仍会删除错误下载文件；
- “重新检查更新”不会删除用户已经保存到自己位置的 DMG；
- SVMM 不会自动覆盖 `/Applications` 中的 App，也不会自动完成安装。

## v1.2.0 用户：本次请通过浏览器升级

**如果当前安装的是 v1.2.0，请不要使用 v1.2.0 自己的“下载更新”按钮获取 v1.2.1。**

v1.2.0 本身仍包含旧下载器，它无法在下载 v1.2.1 之前先获得本次修复。因此请：

1. 在 v1.2.0 的更新窗口选择“打开下载页面”；
2. 进入本仓库官方 GitHub Release；
3. 通过浏览器下载 `Stardew-Valley-Mod-Manager-v1.2.1-macOS.dmg`；
4. 核对本页 SHA-256；
5. 按正常 macOS 安装方式替换旧版本。

安装 v1.2.1 后，未来的软件内更新下载会使用新的用户授权保存流程。

## 版本信息

- **Version：1.2.1**
- **Build：4**
- **Minimum macOS：15.0**
- **Architecture：Universal 2 (`arm64 + x86_64`)**

## 隐私与权限

v1.2.1 没有新增开发者服务器、遥测、分析服务或新的用户数据上传行为。

本版本新增的 user-selected executable 沙盒权限用于软件更新 DMG：只有用户主动点击下载，并通过 macOS 原生保存面板明确选择文件位置后，SVMM 才使用该用户授权位置写入更新文件。

- 隐私政策继续使用 **1.1 / 2026-09-11**
- 软件许可协议继续使用 **1.0 / 2026-09-10**

## macOS 安全提示

当前官方 GitHub 发行包未使用 Apple Developer ID 证书签名，也未经过 Apple Notarization。

请只从本仓库官方 GitHub Release 获取 SVMM，并核对本页提供的 SHA-256。对于正常的互联网下载首次启动限制，在确认文件来源后可按照 macOS 的系统安全提示完成授权。

## 其他已知事项

本版本没有改变以下既有边界：

- macOS 15.0 的“分类”页面在当前虚拟机测试中响应速度低于 macOS 26/27，但核心功能可使用；
- Intel 实机完整回归测试仍有限；
- 极少数非标准第三方 Mod 包仍可能需要人工处理；
- Nexus Mods、SMAPI、GitHub 或相关下载基础设施变化可能影响可选在线功能。

完整列表见 [KNOWN-ISSUES.md](KNOWN-ISSUES.md)。

---

## English

Stardew Valley Mod Manager v1.2.1 is a maintenance release that fixes the in-app software-update download path under macOS App Sandbox.

### What was fixed

In v1.2.0, the in-app updater automatically stored the downloaded DMG inside SVMM's Sandbox cache. On some macOS environments, that file could receive a quarantine state indicating executable content created by a sandboxed app without explicit user authorization. The DMG bytes and SHA-256 could still be correct, while macOS refused to execute the app inside it.

Starting with v1.2.1:

- **Download Update** first presents the native macOS Save panel;
- the user explicitly chooses the DMG destination;
- SVMM keeps its in-app download progress UI;
- GitHub SHA-256 asset-digest verification remains enabled when available;
- verified DMGs can still be opened directly from SVMM;
- SVMM remains sandboxed;
- the user-selected executable entitlement is used only for the update file explicitly authorized through the Save panel;
- SVMM still does not automatically replace the installed app or complete installation.

### One-time note for v1.2.0 users

If you are currently running v1.2.0, use **Open Download Page** and download v1.2.1 through your web browser for this one upgrade. v1.2.0 itself still contains the old downloader and cannot receive the v1.2.1 fix before downloading it.

After v1.2.1 is installed, later in-app software-update downloads use the new Save-panel workflow.

**Version:** 1.2.1  
**Build:** 4  
**Minimum OS:** macOS 15.0  
**Architecture:** Universal 2 (`arm64 + x86_64`)

SHA-256:

```text
80aa9cc360ee6ee7031347a02b0e1dc18b3e2a9ba8a09f586f5b3113a2d0385f
```

The Privacy Policy remains version 1.1 and the Software License Agreement remains version 1.0.
