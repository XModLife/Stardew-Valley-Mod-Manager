[**简体中文**](USER-GUIDE.md) | [English](USER-GUIDE.en.md)

# Stardew Valley Mod Manager 使用手册

适用版本：Stardew Valley Mod Manager 1.0.0 及后续版本，直至本手册更新。

Stardew Valley Mod Manager（SVMM）是一款 macOS 本地 Mod 管理工具。它读取并管理您现有的 Stardew Valley Mods，不为游戏创建另一套平行 Mod 环境。多数管理数据保存在本机。

## 快速开始

1. 从官方 GitHub Releases 获取 SVMM。
2. 首次启动如被 Gatekeeper 拦截，确认文件来源和 SHA-256 后按系统提示使用“仍要打开”。
3. 在“设置”中选择实际使用的 Stardew Valley / Mods 位置。
4. 授权应用读取 Mods 文件夹。
5. 先查看“概览”和“扫描诊断”。
6. 再根据需要使用名称备注、分类、配置方案、更新或依赖获取。

## 系统要求

- **macOS 15.0 或更高版本**
- **Universal 2（arm64 + x86_64）**
- Apple Silicon 为主要直接测试平台
- x86_64 路径已通过 Rosetta 2 启动验证；Intel 实机完整回归仍有限
- macOS 版 Stardew Valley
- 正常 Mod 环境通常需要 SMAPI

当前 macOS 15.0 虚拟机测试中，“分类”页面的首次进入和部分选择操作比 macOS 26/27 慢，但核心功能可使用。详情见 [KNOWN-ISSUES.md](KNOWN-ISSUES.md)。

## 界面语言

SVMM 当前正式维护：

- **简体中文**
- **English**
- **跟随系统**（选择模式）

“跟随系统”只会让 macOS 从 SVMM 已提供的本地化资源中选择语言，并不是实时机器翻译。

界面文本已经采用本地化资源 / String Catalog 组织，架构可以继续增加其他语言。开发者不会独立发布自己无法理解和审核的语言；希望协助其他语言翻译、校对和长期维护的用户，可通过 GitHub Issues 或 SVMM@npccare.cn 联系。

修改语言后需要重新启动 SVMM，确保应用内容与 macOS 原生菜单同时切换。

<p align="center">
  <img src="docs/images/zh-CN/settings.png" alt="语言与设置" width="96%">
</p>

## 概览

概览用于快速查看当前 Mod 环境与 Stardew Valley 存档摘要，包括 Mod 总数、启用状态、需更新、需处理、报错、当前配置方案以及可读取的农场信息。

<p align="center">
  <img src="docs/images/zh-CN/overview.png" alt="概览" width="96%">
</p>

状态是管理辅助信息，不应被理解为对第三方 Mod 安全性或兼容性的绝对结论。

## Mod 库

Mod 库是主要管理区域。卡片和列表只改变展示方式，不会产生两套不同的 Mod 数据。

### 卡片视图

更适合快速浏览，可用时显示 Nexus 缩略图。

<p align="center">
  <img src="docs/images/zh-CN/mod-library-card.png" alt="Mod 库卡片视图" width="96%">
</p>

### 列表视图

更适合比较名称、名称备注、版本、类型、依赖、状态与安装时间，并支持排序和多选。

<p align="center">
  <img src="docs/images/zh-CN/mod-library-list.png" alt="Mod 库列表视图" width="96%">
</p>

### 名称备注与普通备注

名称备注是 SVMM 的本地辅助名称。它适合把难以快速识别的英文、缩写或其他语言 Mod 名称记录成自己熟悉的称呼。

- 不修改作者原始名称；
- 不修改 `manifest.json`；
- 不改变 Unique ID；
- 可与普通备注一起导入、导出和备份。

<p align="center">
  <img src="docs/images/zh-CN/mod-name-note.png" alt="Mod 名称备注" width="72%">
</p>

### 多选

- 单击：单选
- ⌘ + 单击：非连续多选
- ⇧ + 单击：连续范围
- ⌘A：全选当前列表

## 分类与配置方案

### 分类

分类回答“怎么整理”。系统默认分类可作为只读参考；用户方案可以新增类目并调整 Mod 分类。

<p align="center">
  <img src="docs/images/zh-CN/categories.png" alt="分类" width="96%">
</p>

### 配置方案

配置方案回答“这次实际使用哪些 Mods”。它保存并应用启用/停用组合。

<p align="center">
  <img src="docs/images/zh-CN/profiles.png" alt="配置方案" width="96%">
</p>

如果配置方案里保存的 Mod 已经被外部删除，SVMM 会保留无法匹配的历史管理记录，用户可以在设置中检查并按需清理。

## 更新与 Nexus Mods

Nexus Mods 连接是可选功能。本地扫描、备注、分类、配置方案和备份不要求 Nexus 账户。

### Free 账户更新

Free 账户在需要 Nexus 下载时通过浏览器 / NXM 授权，随后由 SVMM 接续本次授权对应的下载、校验与受支持安装事务。

<p align="center">
  <img src="docs/images/zh-CN/update-free.png" alt="Free 账户更新" width="96%">
</p>

### Premium 批量更新

符合条件的 Premium 账户可获取直接下载链接，并处理受支持的批量更新队列。

<p align="center">
  <img src="docs/images/zh-CN/update-premium-batch.png" alt="Premium 批量更新" width="96%">
</p>

### 更新事务与组合 Mod 包

更新前 SVMM 会验证下载文件、ZIP 结构、Manifest、Unique ID、版本与目标路径。

当作者把多个必须共同发布的 Mod 组件打包在一个 ZIP 中时，SVMM 可以在结构能够可靠验证的前提下，把它们作为同一 bundled multi-Mod transaction：

- 更新已安装组件；
- 安装同包缺失组件；
- 尽可能保留受支持的 `config.json`；
- 失败时回滚整个事务；
- 重复 Unique ID、目录冲突、降级风险或身份不明确时停止。

## 依赖与获取

SVMM 会读取 Manifest 的依赖声明，并区分缺失、已安装但停用、版本过低、版本未知、重复 Unique ID 等情况。

### Free 账户获取依赖

<p align="center">
  <img src="docs/images/zh-CN/dependencies-free.png" alt="Free 账户获取依赖" width="96%">
</p>

### Premium 批量获取依赖

<p align="center">
  <img src="docs/images/zh-CN/dependencies-premium-batch.png" alt="Premium 批量获取依赖" width="96%">
</p>

对于包含多个必需 Mod 的依赖 ZIP，只有在能够证明它们属于同一 bundled package 时才会按一个事务安装。RAR / 7z 当前不进入自动安装流程。

SVMM 不递归自动安装无限依赖树。新安装依赖如果还有自己的依赖，请重新扫描后再次检查。

## 设置、存储与备份

设置页集中管理游戏位置、Mods 授权、语言、Nexus 连接，以及管理器本地数据。

<p align="center">
  <img src="docs/images/zh-CN/settings.png" alt="设置" width="96%">
</p>

### 存储与缓存

- 查看 / 清理 Nexus 缩略图缓存；
- 查看 / 清理 SVMM 管理的 Mod 临时文件和更新事务残留；
- 刷新占用统计；
- 缓存清理不会卸载正常 Mod。

### 管理器数据

- 重新扫描 Mods；
- 检查已卸载 Mod 的残留管理记录；
- 导入 / 导出 Mod 名称备注与普通备注；
- 创建管理器数据备份；
- 从备份选择性恢复受支持的管理数据。

<p align="center">
  <img src="docs/images/zh-CN/data-cache-backup.png" alt="数据缓存与备份管理" width="96%">
</p>

重要 Mod 环境仍建议保留独立的游戏/Mods 备份。SVMM 的更新事务临时备份不应被当作长期备份方案。

## 扫描诊断

“工具 > 扫描诊断”用于查看目录结构、Manifest 或解析问题。诊断信息用于缩小问题范围，不等于自动判定 Mod 已损坏。

修正外部文件后应重新扫描验证。

## 存档概览

SVMM 可以只读解析本地 Stardew Valley 存档中的部分信息，用于概览显示玩家、农场、游戏日期、游玩时间、金币、配偶、子女、房屋升级和版本等摘要。

该功能不会因为查看而修改存档。

## 问题排查

建议顺序：

1. 确认 Stardew Valley / Mods 目录正确且可访问；
2. 重新扫描 Mod；
3. 查看扫描诊断；
4. 打开相关 Mod 详情，核对 Unique ID、依赖与更新来源；
5. 对更新/依赖问题确认作者发布说明；
6. 仍无法判断时提交可复现 Issue。

提交兼容性或性能问题时，请提供：

- SVMM 版本；
- macOS 版本；
- Mac 型号 / 芯片架构；
- 物理 Mac 或虚拟机；
- Stardew Valley / SMAPI 版本；
- 相关 Mod 名称、版本、Unique ID；
- 复现步骤、实际结果、预期结果。

不要公开 Nexus API Key、Token、密码、支付凭据或其他秘密信息。

**联系：SVMM@npccare.cn**
