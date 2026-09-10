# Stardew Valley Mod Manager v1.0.0

Stardew Valley Mod Manager（SVMM）首次公开发布。

**专用于 macOS 的中文友好型《星露谷物语》Mod 管理器。**

## 下载校验

正式发布时请在此处填入最终 DMG 的 SHA-256：

```text
SHA-256: 7983ab8e9f2cb1fae73db7b11f3865ea457255cad4407a9cf83c82d17c8dc77c
```

## 系统要求与兼容性

- **最低系统：macOS 15.0**
- **Universal 2：arm64 + x86_64**
- Apple Silicon 为主要实际测试平台
- x86_64 slice 已通过 Rosetta 2 启动验证
- Intel 实机完整回归测试尚未完成
- macOS 版 Stardew Valley
- 正常 Mod 环境推荐配合 SMAPI 使用

当前测试状态：

- **macOS 15.0**：核心功能可正常使用；当前虚拟机环境中“分类”页面比新系统更慢；
- **macOS 26.0**：测试流畅；
- **macOS 27.0**：测试流畅。

## 主要功能

- 原生 macOS Mod 管理界面
- Mod 库卡片 / 列表视图
- 名称备注与普通备注
- 分类与用户分类方案
- 配置方案
- Mod 启用 / 停用
- 扫描诊断
- Stardew Valley 农场 / 存档只读概览
- SMAPI Mod 更新与依赖信息检查
- 可选 Nexus Mods 连接
- Free 浏览器 / NXM 工作流
- 符合条件的 Premium 直接下载、批量更新与批量依赖获取
- 更新 / 依赖安装事务校验、备份、回滚与配置保留
- **bundled multi-Mod ZIP** 更新与依赖安装支持
- Nexus 缩略图与临时事务缓存管理
- 已卸载 Mod 残留管理记录清理
- Mod 备注导入 / 导出
- 管理器数据备份创建 / 恢复
- 简体中文 / English / 跟随系统

## 中文友好与本地化

中文友好是 SVMM 的核心定位之一。

“名称备注”允许用户用自己熟悉的语言给 Mod 增加一个本地显示名称，同时保留作者原始名称、Unique ID 与 `manifest.json` 不变。

SVMM 当前正式维护的界面本地化为 **简体中文与 English**。“跟随系统”会在应用实际提供的语言资源中由 macOS 选择合适语言，不代表机器翻译。

代码与 String Catalog 架构保留继续增加其他语言的空间。开发者无法独立制作和审核自己不掌握的语言；如果希望协助新的语言翻译、校对或长期维护，可通过 GitHub Issues 或 SVMM@npccare.cn 联系。

## Bundled multi-Mod 更新

一些 Mod 作者会把多个必须共同安装/更新的组件放在一个 ZIP 中。

v1.0.0 的正式事务机制支持在能够安全验证时：

- 识别多个 `manifest.json`；
- 验证目标 Mod 与同包组件身份；
- 同时更新已安装组件；
- 安装同包缺失组件；
- 尽可能保留受支持配置；
- 在失败时整体回滚。

存在 Unique ID 冲突、路径冲突、降级风险或无法可靠判断结构时，自动更新会停止。

## 已知事项

- macOS 15.0 的“分类”页面在当前虚拟机测试中响应速度低于 macOS 26/27，但核心功能可使用，未发现相关数据完整性问题；
- Intel 实机完整测试尚未完成；
- macOS beta / seed 环境可能动态向“帮助”菜单注入 Feedback Assistant 项目；
- 极少数非标准 Mod 发布包仍可能要求手动处理；
- Nexus Mods、SMAPI、GitHub 或相关下载基础设施变化可能影响可选在线功能。

完整列表见 `KNOWN-ISSUES.md`。

## macOS 安全提示

当前 v1.0.0 GitHub 发布包未使用 Apple Developer ID 签名，也未经过 Apple Notarization。

首次启动可能触发 Gatekeeper 提示。请确认安装文件来自本仓库官方 Release，并核对发布页提供的 SHA-256。确认来源后，可在：

**系统设置 → 隐私与安全性 → 安全性 → 仍要打开（Open Anyway）**

完成首次授权。

---

## English

Stardew Valley Mod Manager v1.0.0 is the first public release of SVMM, a Chinese-friendly native Stardew Valley Mod manager for macOS.

**Minimum OS:** macOS 15.0  
**Architecture:** Universal 2 (`arm64 + x86_64`)

Apple Silicon is the primary directly tested platform. The x86_64 execution path has been launch-tested under Rosetta 2, while a full physical-Intel regression pass is still pending.

macOS 15.0 is supported; in the current VM test environment the Categories page is less responsive than on macOS 26/27. macOS 26.0 and macOS 27.0 currently test smoothly.

Key features include native Mod-library management, display-name notes, categories, profiles, diagnostics, save/farm overview, SMAPI metadata checks, optional Nexus Mods workflows, conservative update/dependency transactions, validated bundled multi-Mod ZIP support, cache maintenance, note import/export, manager backup/restore, and Simplified Chinese / English localization.

See `KNOWN-ISSUES.md` and the User Manual for full details.
