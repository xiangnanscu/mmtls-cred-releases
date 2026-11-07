# mmtls 凭据助手 · Windows 安装包

这是 [mmtls-cred](https://github.com/xiangnanscu/mmtls-cred) 的**二进制发布仓库**，只存放 Windows 安装包、签名与自动更新清单。

## 下载

打开 [最新版本](https://github.com/xiangnanscu/mmtls-cred-releases/releases/latest)，下载 `mmtls-cred-desktop_<版本>_x64-setup.exe`。

- 系统要求：Windows 10 / 11 64 位、微信 4.x、WebView2
- 首次安装时 Windows 可能显示 SmartScreen 提示：选择“更多信息 → 仍要运行”
- 安装包未使用商业代码签名；自动更新使用独立的 minisign 签名校验

## 使用

1. 在 [mmtls 网页控制台](https://mmtls.toreal.site/settings) 登录并生成连接密钥（SK）；
2. 打开客户端，粘贴连接密钥并验证；
3. 点击“开始抓取”，在 90 秒内进入任意公众号的**历史文章列表**并向下滑一次；
4. 客户端自动加密上传，并等待服务端真实拉取验证通过。

客户端只读取文章列表所需的临时通信密钥，不读取聊天内容；上传后清除本机临时文件。

## 自动更新

客户端从本仓库的 `latest.json` 检查更新。`latest.json` 仅供客户端使用，请勿手动安装其中的文件。

## 校验

每个版本附带 `SHA256SUMS.txt`。可在 PowerShell 中校验：

```powershell
Get-FileHash .\mmtls-cred-desktop_<版本>_x64-setup.exe -Algorithm SHA256
```

## 问题反馈

请附上客户端“设置 → 诊断 → 复制诊断信息”的内容。诊断信息已脱敏，不包含连接密钥或会话密钥。
