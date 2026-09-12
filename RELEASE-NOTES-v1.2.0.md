# Stardew Valley Mod Manager v1.2.0

发布日期：2026-09-12

Stardew Valley Mod Manager（SVMM）v1.2.0 是一次配置方案体验与自动分类能力更新。本版本重点改善大量 Mod 环境下的视觉辨认效率，并继续优化自动分类的准确性。

## 下载校验

```text
SHA-256: 8d10aa394396fb4c8bc8a6f032ecf0fdb20a8a9d717aeb995e597789ee8a481c
```

正式发行文件：

```text
Stardew-Valley-Mod-Manager-v1.2.0-macOS.dmg
```

## 系统要求

- **最低系统：macOS 15.0**
- **Universal 2：arm64 + x86_64**
- Apple Silicon 为主要直接测试平台
- x86_64 执行路径已通过 Rosetta 2 启动验证；Intel 实机完整回归仍有限
- macOS 版 Stardew Valley
- 正常 Mod 环境通常需要 SMAPI

## v1.2.0 主要更新

### 配置方案缩略图

- 配置方案 Mod 列表可以显示已经缓存到本地的 Nexus 缩略图；
- 配置方案页面不会为了显示缩略图额外请求 Nexus Mods；
- 缩略图高度根据当前 Mod 行内容适配，并保持列表布局紧凑；
- 将鼠标悬停在缩略图上可以查看放大预览；
- 支持“靠近 Mod 信息”和“靠近启用状态”两种显示方式；
- Toolbar 提供直接可见的分段切换控件，可以单击切换布局；
- 两个切换按钮使用相呼应的左 / 右对齐图标；
- 当前缩略图位置作为本地界面偏好保存，并在重新启动后恢复；
- 缩略图只用于辅助识别，不改变配置方案的启用 / 停用逻辑；
- 没有已有缩略图缓存的 Mod 仍可正常使用配置方案功能，只是不显示图片。

### 自动分类

- 改进建筑类 Content Pack 的识别；
- 改进地图和路径类 Mod 的识别；
- 补充部分已确认的家具、装饰物与环境美化分类；
- 修复普通 Mod 因 Description 中提到 Stardew Valley Expanded、Ridgeside Village、East Scarp 等大型扩展的兼容性信息，而被错误识别为“大型扩展”的问题；
- 大型扩展识别现在更严格地依赖 Mod 自身的名称、Unique ID、文件夹名等身份信息；
- 无法可靠判断时继续保持“未识别”，不使用低置信度规则强行分类。

## 版本信息

- **Version：1.2.0**
- **Build：3**
- **Minimum macOS：15.0**
- **Architecture：Universal 2 (`arm64 + x86_64`)**

## 隐私与网络行为

v1.2.0 没有新增开发者服务器、遥测、分析服务或新的用户数据上传行为。

配置方案新增的缩略图展示只读取 SVMM 已经保存到本地的 Nexus 缩略图缓存，不会因为进入配置方案页面而额外向 Nexus Mods 请求图片。

- 隐私政策继续使用 **1.1 / 2026-09-11**
- 软件许可协议继续使用 **1.0 / 2026-09-10**

## macOS 安全提示

当前官方 GitHub 发行包未使用 Apple Developer ID 证书签名，也未经过 Apple Notarization。

请只从本仓库官方 GitHub Release 获取 SVMM，并核对 Release 页面提供的 SHA-256。确认来源后，如 macOS 阻止首次启动，可前往：

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

Stardew Valley Mod Manager v1.2.0 focuses on improving the Profiles experience and conservative automatic Mod classification.

### Highlights

- locally cached Nexus thumbnails in Profiles;
- larger thumbnail previews on hover;
- two user-selectable thumbnail placement layouts;
- a one-click segmented toolbar control for switching layouts;
- locally persisted thumbnail-placement preference;
- no additional Nexus Mods requests solely for Profile thumbnail display;
- improved classification for buildings, maps, furniture, decorations, and environmental Mods;
- fixed false “large expansion” classification caused by compatibility text in Mod descriptions;
- expansion detection now relies more strictly on the Mod's own identity fields.

**Version:** 1.2.0  
**Build:** 3  
**Minimum OS:** macOS 15.0  
**Architecture:** Universal 2 (`arm64 + x86_64`)

SHA-256:

```text
8d10aa394396fb4c8bc8a6f032ecf0fdb20a8a9d717aeb995e597789ee8a481c
```

The Privacy Policy remains version 1.1, and the Software License Agreement remains version 1.0.
