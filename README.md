# 本地脱敏 Agent 企业版 — 下载与安装

**让 AI 读卷宗、看合同、核账目，但不让它看到任何一个真名。**

本地脱敏 Agent 是一个**全程在你自己电脑上运行**的文档脱敏工具：把 Word / Excel / PPT / PDF / 扫描件里的姓名、手机号、身份证号、银行账号、公司名等敏感信息自动替换成带编号的占位符，你只把脱敏后的版本交给云端 AI；AI 处理完的结果放回来，本机自动把占位符还原成原文并重新生成 Word / PDF。原始敏感信息只以加密形式保存在你的电脑上，云端永远看不到，日常使用可完全离线。

本仓库只发布**安装包与使用文档**，不含源代码。

## 下载

最新版本见右侧 **Releases**（或直接打开 [Releases 页面](../../releases/latest)）。

| 文件 | 适用机器 |
|---|---|
| `LocalPIISanitizer-<版本>-arm64.dmg` | Apple Silicon（M1 / M2 / M3 / M4 系列） |
| `LocalPIISanitizer-<版本>-x86_64.dmg` | Intel 芯片的 Mac（暂未提供，需要请联系我们） |
| `LocalPIISanitizer-<版本>-win-x64-Setup.exe` | 64 位 Windows 10 / 11（**首版，见下方说明**） |

不确定自己的芯片：点左上角  → 关于本机，「芯片」一栏写 Apple 即选 arm64。

**关于 Windows 版**：这是 Windows 首个版本，已通过自动化构建与启动自检，但**尚未在真实 Windows 电脑上做完整验收**，可能存在我们还没发现的问题，建议先小范围试用。安装包未做代码签名，双击时 Windows SmartScreen 会提示「已阻止未识别的应用」，点「更多信息」→「仍要运行」即可继续。Windows 版还原只输出 Word（docx），不出 PDF。

每个安装包旁边都有同名的 `.sha256` 文件，用于核对下载是否完整（可选）：

```bash
shasum -a 256 -c LocalPIISanitizer-<版本>-arm64.dmg.sha256
```

### 国内加速下载（GitHub 打不开 / 太慢时）

以下直链**始终指向最新版本**（经 `releases/latest/download/` 跳转，发新版无需更换），点不开的线路直接换下一条（第三方公共服务，2026-09-08 实测均可达）：

**macOS（Apple Silicon）**

- [加速线路 1：ghfast.top](https://ghfast.top/https://github.com/halfmoon82/local-pii-sanitizer-releases/releases/latest/download/LocalPIISanitizer-arm64.dmg)
- [加速线路 2：gh-proxy.com](https://gh-proxy.com/https://github.com/halfmoon82/local-pii-sanitizer-releases/releases/latest/download/LocalPIISanitizer-arm64.dmg)
- [加速线路 3：ghproxy.net](https://ghproxy.net/https://github.com/halfmoon82/local-pii-sanitizer-releases/releases/latest/download/LocalPIISanitizer-arm64.dmg)

**Windows（64 位）**

- [加速线路 1：ghfast.top](https://ghfast.top/https://github.com/halfmoon82/local-pii-sanitizer-releases/releases/latest/download/LocalPIISanitizer-win-x64-Setup.exe)
- [加速线路 2：gh-proxy.com](https://gh-proxy.com/https://github.com/halfmoon82/local-pii-sanitizer-releases/releases/latest/download/LocalPIISanitizer-win-x64-Setup.exe)
- [加速线路 3：ghproxy.net](https://ghproxy.net/https://github.com/halfmoon82/local-pii-sanitizer-releases/releases/latest/download/LocalPIISanitizer-win-x64-Setup.exe)

加速链路经过第三方服务器中转，下载完成后**请务必核对哈希**，确认文件与 GitHub 官方包完全一致：

1. 下载安装包对应的 `.sha256` 文件（把上面直链末尾的 `.dmg` / `.exe` 换成 `.dmg.sha256` / `.exe.sha256` 即可），与安装包放在同一文件夹；
2. macOS：在该文件夹打开终端，执行 `shasum -a 256 -c LocalPIISanitizer-arm64.dmg.sha256`，输出 `OK` 即官方原版，可放心安装；
3. Windows：在该文件夹打开 PowerShell，执行 `Get-FileHash .\LocalPIISanitizer-win-x64-Setup.exe -Algorithm SHA256`，把输出的哈希与 `.sha256` 文件里的字符串比对，一致即官方原版；
4. 任何不一致或其它输出，都请不要使用该文件。

## 三步安装（macOS）

1. 双击 dmg，把 **本地脱敏 Agent 企业版** 图标拖到旁边的「应用程序」文件夹。
2. 在「应用程序」里双击 **LocalPIISanitizer**。第一次打开 macOS 会提示「无法验证开发者」，这是系统对所有未签名软件的统一提醒，按 [《如何打开未签名版本》](如何打开未签名版本.md) 里的四步操作一次即可（不需要关闭任何系统安全设置）。
3. 首次启动会出现「首次准备」页面，点「开始下载」，一次性下载约 3.4 GB 的本地识别模型（只存本机，不上传任何文件）。下载完成后即可使用。

## 三步安装（Windows）

1. 双击 `LocalPIISanitizer-<版本>-win-x64-Setup.exe`。安装在当前用户目录下，**不需要管理员权限**。
2. 安装包未做代码签名，SmartScreen 会提示「已阻止未识别的应用」——点「更多信息」→「仍要运行」。
3. 从开始菜单打开 **本地脱敏 Agent 企业版**，按「首次准备」页面提示下载约 3.4 GB 本地识别模型即可使用。

## 系统要求

| 项 | macOS | Windows |
|---|---|---|
| 系统 | macOS 14 (Sonoma) 及以上 | Windows 10 1809 / Windows 11（64 位；ARM 版 Windows 未验证） |
| 磁盘 | 约 5 GB（应用约 1 GB + 本地模型约 3.4 GB） | 约 5 GB（同左） |
| 内存 | 建议 16 GB | 建议 16 GB |
| 网络 | 只在首次下载模型、激活 / 续费校验时需要；脱敏与还原完全离线 | 同左 |
| 其它 | — | 需系统自带的 Edge WebView2 运行时（Win11 与近期 Win10 已内置）；还原只输出 Word（docx），不出 PDF |

两个平台都不需要安装 Homebrew、Python 或任何其它软件。

## 试用与购买

- 安装后可免费试用 30 次（脱敏 / 还原共用一个额度）。
- 购买激活码：<https://lic.socialmore.cn/buy>（微信扫码，付款后页面直接显示激活码；`.cn` 打不开可用 <https://lic.socialmore.net/buy>）。
- 一个激活码绑定一台电脑，换机请联系我们换绑。

## 文档

- [安装与使用说明（macOS）](INSTALL.md)：系统要求、首次准备、从旧版导入、数据目录、端口占用、激活与续费、卸载、常见问题。
- [安装与使用说明（Windows）](INSTALL-windows.md)：同上，外加 SmartScreen 提示、WebView2 运行时、与 macOS 版的差异。
- [如何打开未签名版本](如何打开未签名版本.md)：第一次打开被 macOS 拦住时的四步操作。
- [最终用户许可协议（LICENSE.txt）](LICENSE.txt)、[第三方组件许可证声明](THIRD_PARTY_LICENSES.md)。

## 隐私承诺

软件运行期不上传任何文档内容。唯一的联网请求是激活 / 续费校验，请求体只有 激活码、设备指纹哈希、软件版本 三个字段。加密映射表的密钥只在你的电脑上，我们不掌握、不存储、不提供找回服务——`vault` 文件夹请务必备份、勿分享。

## 反馈

使用中遇到问题，请在本仓库 [Issues](../../issues) 留言（**不要**在 Issue 里贴任何含真实姓名、证件号等敏感信息的文档或截图），或通过购买页面上的联系方式找我们。
