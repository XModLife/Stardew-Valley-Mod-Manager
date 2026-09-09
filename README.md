<p align="center">
  <img src="docs/images/SVMM.png" width="150" alt="Stardew Valley Mod Manager">
</p>

<h1 align="center">Stardew Valley Mod Manager</h1>

<p align="center">
  <strong>专用于 macOS 的中文友好型《星露谷物语》Mod 管理器。</strong><br>
  A Chinese-friendly native Stardew Valley Mod manager for macOS.
</p>

<p align="center">
  <img alt="最低系统" src="https://img.shields.io/badge/最低系统-macOS%2027.0%2B-111111?logo=apple&logoColor=white">
  <img alt="版本" src="https://img.shields.io/badge/版本-1.0.0-0969da">
  <img alt="语言" src="https://img.shields.io/badge/语言-简体中文%20%7C%20English-8250df">
  <img alt="数据" src="https://img.shields.io/badge/数据-本地优先-1a7f37">
  <img alt="许可" src="https://img.shields.io/badge/许可-专有软件-d97706">
</p>

<p align="center">
  开发者：<strong>李薇（Li Wei）</strong>
</p>

<p align="center">
  <strong>简体中文</strong>
  ·
  <a href="README.en.md">English</a>
  ·
  <a href="https://github.com/XModLife/Stardew-Valley-Mod-Manager/releases">Releases</a>
  ·
  <a href="USER-GUIDE.md">使用手册</a>
  ·
  <a href="https://github.com/XModLife/Stardew-Valley-Mod-Manager/issues">问题反馈</a>
</p>

---

## 软件定位

**Stardew Valley Mod Manager（SVMM）** 是一款面向 macOS 的原生 Stardew Valley Mod 管理工具。

**中文友好是 SVMM 的核心定位之一，也是这个项目诞生的初衷。**  
SVMM 从设计阶段就把简体中文界面、中文文档和中文玩家的实际使用体验作为基础能力，而不是在完成英文界面后再附加一层翻译。

它的核心思路很直接：

> **管理你已经在使用的 Mods，而不是额外创建另一套平行 Mod 库。**

SVMM 重点关注：

- **中文友好**：简体中文优先呈现，同时提供 English，并支持跟随系统语言。
- **原生 macOS 体验**：Sidebar、Toolbar、菜单、窗口、快捷键，以及与 Finder 使用习惯相匹配的操作方式。
- **本地优先（Local-first）**：核心 Mod 管理数据保存在用户自己的 Mac 上。
- **实用的组织能力**：名称备注、分类、配置方案、诊断、依赖与更新流程集中在一个桌面应用中。
- **保守的文件操作**：受支持的更新和依赖安装会尽量执行校验、备份、回滚，并在适用时保留配置文件。

<p align="center">
  <img src="docs/images/zh-CN/overview.png" alt="SVMM 概览" width="100%">
</p>

<p align="center"><sub>概览 —— 农场状态、Mod 状态、更新检查与当前配置方案。</sub></p>

## 当前版本说明与已知问题

SVMM 仍处于首次公开版本阶段。虽然核心功能已经可以正常使用，但不同 Mod 结构、第三方服务和 macOS 系统行为仍可能带来尚未覆盖的边缘情况。

当前已知事项包括：

- **macOS beta / seed 系统的“帮助”菜单可能短暂变化。** 在部分 macOS 测试版环境中，系统可能在首次打开“帮助”菜单时动态加入“将 Stardew Valley Mod Manager 的使用反馈发送给 Apple”等 Feedback Assistant 项目，因此菜单内容可能出现一次短暂的出现 / 消失或重新排列。这是 macOS 测试版系统提供的反馈入口，不属于 SVMM 自己的“使用手册”，也不会影响 Mod 数据、分类、配置方案或其他核心功能。
- **非标准 Mod 目录结构仍可能存在边缘兼容情况。** SVMM 会尽量诊断特殊目录结构、Manifest 与依赖信息，但第三方 Mod 的目录组织和发布方式并不完全统一。
- **第三方服务可能发生变化。** Nexus Mods、SMAPI、GitHub 或相关下载基础设施的 API、页面和授权机制变化，可能影响对应的在线功能。

完整列表参阅 [KNOWN-ISSUES.md](KNOWN-ISSUES.md)。

如果遇到可以稳定复现的问题，请通过 [GitHub Issues](https://github.com/XModLife/Stardew-Valley-Mod-Manager/issues) 反馈，并尽量附上 SVMM、macOS、Stardew Valley 与 SMAPI 版本信息。

## 核心功能

### Mod 库

支持**卡片视图与列表视图**、状态筛选、排序、多选、名称备注、依赖信息与更新状态查看。

| 卡片视图 | 列表视图 |
| --- | --- |
| ![Mod 库卡片视图](docs/images/zh-CN/mod-library-card.png) | ![Mod 库列表视图](docs/images/zh-CN/mod-library-list.png) |

### 分类与配置方案

**分类**用于整理 Mods。  
**配置方案**用于保存并应用实际的启用 / 停用组合。

| 分类 | 配置方案 |
| --- | --- |
| ![分类](docs/images/zh-CN/categories.png) | ![配置方案](docs/images/zh-CN/profiles.png) |

### 更新与依赖

SVMM 可以结合 SMAPI 元数据以及可选的 Nexus Mods 连接，辅助处理受支持的 Mod 更新与依赖获取。

- Nexus Mods 连接是**可选功能**。
- 免费账户可使用受支持的浏览器 / NXM 流程。
- 符合条件的 Premium 账户可使用受支持的直接下载流程。
- 自动安装采用保守策略；来源不明确或不受支持的情况继续由用户手动处理。
- 受支持的安装事务会校验包结构，并尽可能保留备份与回滚信息。

更详细的 Free / Premium 操作流程放在[使用手册](USER-GUIDE.md)中。

### 设置

在原生 macOS 设置页中配置 Stardew Valley 路径、Mods 目录、Nexus Mods 连接、界面语言以及本地维护工具。

<p align="center">
  <img src="docs/images/zh-CN/settings.png" alt="SVMM 设置" width="92%">
</p>

## 界面语言

SVMM 当前支持：

1. **简体中文**
2. **English**
3. **跟随系统**

修改语言后需要重新启动应用才能完整应用。这样可以让应用主体与 macOS 原生菜单一次性统一切换，避免运行过程中出现部分中英混排。

## 系统要求

当前 1.0.0 Build 的**最低部署目标为 macOS 27.0**。

- **支持：macOS 27.0 及更高版本**
- **不支持：macOS 26 及更早版本（当前构建无法直接启动）**
- 更高版本的 macOS 原则上属于兼容目标，但尚未发布或未实际测试的未来系统版本不能提前保证完全兼容。
- macOS 版 Stardew Valley
- 正常的 Mod 游戏环境通常需要 SMAPI
- 用户授权 SVMM 访问实际使用的 Stardew Valley 游戏 / `Mods` 位置

> `macOS 27.0+` 的含义是“最低需要 macOS 27.0”，并不是“只能在 macOS 27 上运行”。

如果未来需要支持 macOS 26 或更早版本，需要单独降低项目 Deployment Target，并审查、替换和测试所有依赖较新 macOS API 的代码；仅修改 README 或 Badge 无法获得向下兼容能力。

## 下载

官方版本通过 **GitHub Releases** 发布：

### [下载最新官方版本 →](https://github.com/XModLife/Stardew-Valley-Mod-Manager/releases/latest)

为避免获得被修改或倒卖的软件，请只从开发者明确指定的官方分发渠道获取 SVMM。**不要向第三方支付 SVMM 应用本身的购买费用。**

## 首次使用

1. 从官方 GitHub Releases 下载 SVMM。
2. 打开应用，并按照 macOS 的安全提示完成启动。
3. 在“**设置**”中选择你实际使用的 Stardew Valley 游戏位置 / Mods 目录。
4. 授权 SVMM 扫描 Mods 文件夹。
5. 在执行大规模 Mod 管理操作前，先查看“**概览**”与“**扫描诊断**”。
6. 如需要受支持的 Nexus 元数据和下载流程，可选择连接 Nexus Mods。

> 当用户主动执行启用、停用、更新、安装依赖、删除 Mod 或应用配置方案等操作时，SVMM 会执行对应的本地文件管理。重要的游戏与 Mod 环境仍建议保留独立备份。

## 用户文档

- [使用手册](USER-GUIDE.md) · [User Manual](USER-GUIDE.en.md)
- [已知问题](KNOWN-ISSUES.md)
- [常见问题](FAQ.md)
- [支持与问题反馈](SUPPORT.md)
- [安全政策](SECURITY.md)
- [隐私政策](PRIVACY.md) · [Privacy Policy](PRIVACY.en.md)
- [软件许可协议](SOFTWARE-LICENSE.md) · [Software License Agreement](SOFTWARE-LICENSE.en.md)
- [更新记录](CHANGELOG.md)

## 隐私

SVMM 采用**本地优先（Local-first）**模式。

当前版本不提供 SVMM 用户账户系统，不包含广告系统、用户行为分析 SDK 或遥测后台，也不运营用于接收用户 Mods、存档或 SVMM 管理数据库的开发者服务器。

部分可选功能会直接访问 SMAPI、Nexus Mods、GitHub 及相关下载基础设施。Nexus API 凭据保存在 macOS 钥匙串（Keychain）中。

完整内容请参阅[隐私政策](PRIVACY.md)。

## 软件许可与分发

SVMM 是**闭源、专有软件**，当前免费提供给用户用于**个人、非商业用途**。

在 GitHub 公开发布安装版本与用户文档，并不意味着 SVMM 转为开源软件，也不授予超出[软件许可协议](SOFTWARE-LICENSE.md)范围的源代码、再分发、修改或商业使用权利。

应用可能展示开发者的个人支付宝收款码，用于用户自愿支持独立开发。支持完全可选，不会解锁功能、不会形成订阅，也不会获得额外软件许可权利。

## 问题反馈与支持

普通 Bug、兼容性问题、文档错误和明确的功能建议请使用 [GitHub Issues](https://github.com/XModLife/Stardew-Valley-Mod-Manager/issues)。

提交前请：

- 删除或遮盖 Nexus API Key、密码、Token、支付凭据及其他秘密信息；
- 检查截图和诊断文本中是否包含不希望公开的本机用户名或文件路径；
- 与问题相关时，提供 SVMM 版本、macOS 版本、Stardew Valley 版本和 SMAPI 版本。

安全漏洞请按照 [SECURITY.md](SECURITY.md) 私下报告。

## 第三方项目与商标

SVMM 为独立开发项目。

Stardew Valley、ConcernedApe 相关内容、SMAPI、Nexus Mods、第三方 Mods、GitHub 以及其他第三方名称、软件、服务、商标与内容，均归其各自合法权利人所有。

除非相关权利人另有明确书面说明，SVMM **不隶属于上述第三方，不代表其官方，不是其代理，也未获得其赞助或背书**。

## 联系方式

**开发者：**李薇（Li Wei）  
**邮箱：**SVMM@npccare.cn
