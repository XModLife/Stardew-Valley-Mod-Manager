[**简体中文**](USER-GUIDE.md) | [English](USER-GUIDE.en.md)

# Stardew Valley Mod Manager 使用手册

适用版本：Stardew Valley Mod Manager 1.2.0 及后续版本，直至本手册更新。

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
  <img src="docs/images/zh-CN/mod-name-note.png" alt="Mod 名称备注与详细信息面板" width="52%">
</p>

### 多选

- 单击：单选
- ⌘ + 单击：非连续多选
- ⇧ + 单击：连续范围
- ⌘A：全选当前列表

### Manifest Editor

从 v1.1.0 起，可以在 Mod 库或分类页面对单个 Mod 使用“编辑 manifest…”打开 Manifest Editor。

结构化模式支持常见字段：

- `Name`、`Author`、`Version`、`UniqueID`、`Description`；
- `EntryDll`；
- `MinimumApiVersion`、`MinimumGameVersion`；
- `UpdateKeys`；
- `Dependencies`；
- `ContentPackFor`。

需要直接检查或修改完整 JSON 时，可以切换到原始 JSON 模式。保存前会重新验证内容，保存成功后 SVMM 会重新扫描 Mods。结构化写回基于完整 JSON 对象，尽量保留与本次修改无关的未知字段。

Manifest Editor 修改的是 Mod 自己的真实 `manifest.json`。它与“名称备注”和“用户更新来源覆盖”是不同功能。修改 Unique ID、依赖或其他关键字段可能改变 SMAPI 与其他 Mod 对该 Mod 的识别关系，因此应以 Mod 作者的真实发布信息为依据。

<p align="center">
  <img src="docs/images/zh-CN/manifest-editor.png" alt="Manifest Editor" width="92%">
</p>

## 分类与配置方案

### 分类

分类回答“怎么整理”。系统默认分类可作为只读参考；用户方案可以新增类目并调整 Mod 分类。

v1.1.0 起分类页面支持搜索；v1.2.0 继续完善保守自动分类，增强建筑、地图、家具、装饰物与环境美化等类型的识别，并修复普通 Mod 因兼容性描述提及大型扩展而被错误归类的问题。大型扩展识别现在更严格地依赖 Mod 自身身份信息。

无法可靠判断的 Mod 仍会保持“未识别”。

<p align="center">
  <img src="docs/images/zh-CN/categories.png" alt="分类" width="96%">
</p>

### 配置方案

配置方案回答“这次实际使用哪些 Mods”。它保存并应用启用/停用组合。

从 v1.2.0 起，配置方案中的 Mod 可以显示 SVMM 已经缓存到本地的 Nexus 缩略图，以便在只看名称不容易辨认 Mod 时快速确认内容。

- 小缩略图用于列表中的快速识别；
- 将鼠标悬停在缩略图上，可以查看更大的图片预览；
- Toolbar 中可以直接切换两种缩略图位置；
- “靠近 Mod 信息”会把缩略图放在名称、名称备注和作者信息之后；
- “靠近启用状态”会把缩略图放在右侧已启用 / 已停用状态附近；
- 当前选择会作为本地界面偏好保存，重新启动 SVMM 后继续使用；
- 配置方案页面只读取已有本地缩略图缓存，不会为了显示这些图片额外向 Nexus Mods 发起请求；
- 没有已有缩略图缓存的 Mod 可以正常使用配置方案功能，只是不显示图片。

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

## SVMM 软件更新

SVMM 1.1.0 起可以检查和下载 **SVMM 自身**的新版本，这与 Mod 更新是两套不同流程。

### 启动自动检查

应用启动后会静默查询官方 GitHub Releases 的最新正式版本。

- 最新版本高于当前安装版本：显示更新提示；
- 最新版本等于当前版本：不弹窗；
- 最新版本低于当前版本：不弹窗；
- 网络失败、API 返回异常或版本信息无法解析：启动检查保持静默。

### 手动检查

随时可以使用：

**帮助 → 更新软件**

手动窗口会显示当前安装版本、最新正式版本，以及检查失败等状态。

### App 内下载

发现新版本后，可以直接在更新窗口中选择“下载更新”。

SVMM 会：

1. 从官方 GitHub Release 下载对应 DMG；
2. 在应用自己的本地缓存位置保存文件；
3. 显示下载进度；
4. 如果 GitHub Release Asset 提供 SHA-256 digest，在本地计算并校验；
5. 校验不一致时删除下载文件并停止；
6. 下载成功后提供“打开安装镜像”。

当前版本不会自动覆盖 `/Applications` 中正在使用的 SVMM，也不会自动完成安装。打开 DMG 后，仍由用户按照正常 macOS 安装方式完成版本替换。

“打开下载页面”继续保留为备用方式。

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
