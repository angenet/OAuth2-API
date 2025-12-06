# 微软 OAuth2 API 无服务器版本

> **原始项目**: [HChaoHui/msOauth2api](https://github.com/HChaoHui/msOauth2api)  
> **服务器版本在vps分支**

🌟 **简化微软 OAuth2 认证流程，轻松集成到你的应用中！** 🌟

本项目基于原始项目 [HChaoHui/msOauth2api](https://github.com/HChaoHui/msOauth2api) 进行优化和改进，将微软的 OAuth2 认证取件流程封装成一个简单的 API，并部署在 Vercel 的无服务器平台上。

## ✨ 主要功能

- **双重协议支持**: 自动检测并使用 Graph API，失败时回退到 IMAP
- **验证码自动提取**: 🔥 新功能！自动提取邮件中的6位数字验证码
- **多种邮件操作**: 获取、清空、发送邮件
- **安全认证**: OAuth2 + 密码保护
- **无服务器部署**: Vercel 平台，自动扩展

## 🚀 快速开始

### 1. Star 原始项目
首先给原始项目点个赞：[HChaoHui/msOauth2api](https://github.com/HChaoHui/msOauth2api)

### 2. Fork 项目
点击右上角的 `Fork` 按钮，将项目复制到你的 GitHub 账户下。

### 3. 部署到 Vercel
- 点击下面的按钮，一键部署到 Vercel

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/angenet/OAuth2-API/tree/main)

- 在 Vercel 部署页面，填写你的项目名称，然后点击 `Deploy` 按钮
- 部署完成后访问: `https://mail.150420.xyz` 查看 API 文档

### 4. 配置环境变量
在 Vercel 控制台设置以下环境变量：
- `PASSWORD`: 邮件读取 API 访问密码
- `SEND_PASSWORD`: 邮件发送 API 访问密码

## 📚 API 文档

### 🔥 新功能：验证码自动提取
所有邮件 API 现在都会自动提取邮件中的6位数字验证码，并在响应中包含 `verification_code` 字段。

### 📧 获取最新的一封邮件
- **方法**: `GET`
- **URL**: `/api/mail-new`
- **描述**: 获取最新的一封邮件，自动提取验证码
- **基础地址**: `https://mail.150420.xyz`

**完整URL示例**:
```
https://mail.150420.xyz/api/mail-new?refresh_token=YOUR_TOKEN&client_id=YOUR_CLIENT_ID&email=your@email.com&mailbox=INBOX
```

**响应示例**:
```json
{
  "send": "\"KlingAI\" <klingai@user-support.klingai.com>",
  "subject": "KlingAI Account Verification",
  "text": "您是KlingAI的验证码...",
  "html": "<div>验证码: 233645</div>",
  "date": "2025-12-01T09:58:25.000Z",
  "verification_code": "233645"  // 🔥 自动提取的验证码
}
```

### 📨 获取全部邮件
- **方法**: `GET`
- **URL**: `/api/mail-all`
- **描述**: 获取全部邮件，自动提取验证码

### 🗑️ 清空收件箱
- **方法**: `GET`
- **URL**: `/api/process-inbox`
- **描述**: 清空收件箱

### 🗑️ 清空垃圾箱
- **方法**: `GET`
- **URL**: `/api/process-junk`
- **描述**: 清空垃圾箱

### ✉️ 发送邮件
- **方法**: `GET`
- **URL**: `/api/send-mail`
- **描述**: 使用 OAuth2 发送邮件

## 🔧 部署说明

### Vercel 部署
1. Fork [原始项目](https://github.com/HChaoHui/msOauth2api)
2. 使用 Vercel 部署
3. 配置环境变量：
   - `PASSWORD`: 你的读取密码
   - `SEND_PASSWORD`: 你的发送密码

### 本地开发
```bash
# 安装依赖
npm install

# 本地测试
vercel dev

# 部署到生产
vercel --prod
```

## 🆕 更新内容

### v2.0.0 (2025-12-06)
- ✨ **新增验证码提取功能**: 自动提取邮件中的6位数字验证码
- 🔧 **优化搜索范围**: 支持文本、主题和HTML内容中的验证码提取
- 🎯 **提升兼容性**: 支持各种格式的验证码邮件（KlingAI、GitHub等）
- 📋 **完善文档**: 新增HTML API文档界面
- 🌐 **更新API地址**: 使用 `https://mail.150420.xyz`

## 🖼️ 效果图

![Demo](https://raw.githubusercontent.com/HChaoHui/msOauth2api/refs/heads/main/img/demo.png)

## 🤝 贡献

### 原始项目贡献
欢迎大家为 [原始项目](https://github.com/HChaoHui/msOauth2api) 贡献代码！

### 问题反馈
- 原始项目 Issue: [HChaoHui/msOauth2api/issues](https://github.com/HChaoHui/msOauth2api/issues)
- 原始作者邮箱: **[z@unix.xin]**
- 技术支持: 请通过原始项目渠道反馈

## 📜 许可证

本项目基于 MIT 许可证，详见原始项目 [LICENSE](https://github.com/HChaoHui/msOauth2api/blob/main/LICENSE)。

## 💖 支持

### 支持原始项目
如果这个项目对你有帮助，请给原始项目一个 Star ⭐️：

[![Star HChaoHui/msOauth2api](https://img.shields.io/github/stars/HChaoHui/msOauth2api?style=social)](https://github.com/HChaoHui/msOauth2api)

### 赞助支持
![Buy](https://github.com/HChaoHui/msOauth2api/blob/main/img/Buy.JPG?raw=true)

---

**基于原始项目改进，保留原始出处** ❤️  
**Happy Coding!** 🎉

