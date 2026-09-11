# Security Policy / 安全政策

If you discover a security vulnerability in Stardew Valley Mod Manager, report it privately:

**SVMM@npccare.cn**

Please do not create a public GitHub Issue for an unpatched vulnerability.

A useful report should include, where possible:

- affected SVMM version;
- macOS version;
- description of the vulnerability;
- reproduction steps or a minimal proof of concept;
- expected security impact;
- whether Nexus Mods or another third-party service is involved.

Do not send real Nexus API Keys, account passwords, payment credentials, tokens, or unrelated personal data. Use redacted or test values whenever possible.

## Software Update Integrity

Official SVMM installation builds are distributed through the project's GitHub Releases.

Starting with v1.1.0, SVMM can download an official Release DMG inside the application. When GitHub provides a SHA-256 digest for the Release Asset, SVMM calculates the downloaded file's SHA-256 locally and compares the values before offering to open the disk image.

If the digest does not match, SVMM deletes the downloaded file and treats the update as failed.

If the version shown by SVMM, the official Release information, update source, or published file digest appears inconsistent, do not continue installation. Report the discrepancy privately to **SVMM@npccare.cn**.

---

如果你发现 Stardew Valley Mod Manager 的安全漏洞，请通过以下邮箱私下报告：

**SVMM@npccare.cn**

对于尚未修复的漏洞，请不要直接创建公开 GitHub Issue。

在条件允许时，建议包含：

- 受影响的 SVMM 版本；
- macOS 版本；
- 清晰的漏洞说明；
- 可复现步骤或最小化概念验证；
- 预期安全影响；
- 是否涉及 Nexus Mods 或其他第三方服务。

请不要发送真实 Nexus API Key、账户密码、支付凭据、Token 或与漏洞无关的个人数据。尽量使用遮盖后的信息或测试值。

## 软件更新完整性

SVMM 官方安装包通过项目的 GitHub Releases 发布。

从 v1.1.0 起，SVMM 可以在应用内下载官方 Release 的 DMG。GitHub 为 Release Asset 提供 SHA-256 digest 时，SVMM 会在本地计算下载文件的 SHA-256，并在允许打开安装镜像前进行比较。

如果摘要不一致，SVMM 会删除下载文件并将本次更新视为失败。

如果 SVMM 显示的版本、官方 Release 信息、更新来源或公开文件摘要之间出现异常不一致，请不要继续安装，并通过 **SVMM@npccare.cn** 私下报告。

