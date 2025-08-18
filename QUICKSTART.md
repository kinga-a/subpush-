# SubsTracker 快速开始指南

本指南将帮助您在 5 分钟内快速部署 SubsTracker 到 Cloudflare Workers。

## ⚡ 超快速部署（3分钟）

### 1. Fork 仓库
1. 访问 [SubsTracker 仓库](https://github.com/logdns/subpush)
2. 点击右上角 "Fork" 按钮
3. 等待 Fork 完成

### 2. 一键部署
1. 在您的 Fork 仓库中，点击 "Deploy to Cloudflare Workers" 按钮
2. 登录 Cloudflare 账户
3. 点击 "Deploy" 按钮
4. 等待部署完成

### 3. 开始使用
1. 访问部署后的 Worker 域名
2. 使用默认账号登录：
   - 用户名：`admin`
   - 密码：`password`
3. 开始添加您的订阅！

## 🚀 标准部署（5分钟）

### 步骤 1：准备 Cloudflare 账户
- 注册 [Cloudflare 账户](https://dash.cloudflare.com/sign-up)
- 完成邮箱验证

### 步骤 2：创建 Worker
1. 登录 [Cloudflare Dashboard](https://dash.cloudflare.com/)
2. 点击左侧 "Workers & Pages"
3. 点击 "Create application"
4. 选择 "Create Worker"
5. 输入名称：`substracker`
6. 点击 "Deploy"

### 步骤 3：创建 KV 存储
1. 在 Worker 页面，点击 "Settings"
2. 找到 "Variables" 部分
3. 点击 "Add binding"
4. 变量名：`SUBSCRIPTIONS_KV`
5. 创建新的 KV 命名空间
6. 点击 "Save and deploy"

### 步骤 4：配置定时任务
1. 点击 "Triggers" 标签
2. 点击 "Add Cron Trigger"
3. Cron 表达式：`0 8 * * *`
4. 时区：选择您的时区
5. 点击 "Save"

### 步骤 5：上传代码
1. 点击 "Quick edit"
2. 删除默认代码
3. 复制 `index.js` 文件内容并粘贴
4. 点击 "Save and deploy"

### 步骤 6：配置环境变量
1. 点击 "Settings" 标签
2. 找到 "Environment Variables"
3. 添加以下变量：
   ```
   ADMIN_USERNAME=admin
   ADMIN_PASSWORD=your_password
   JWT_SECRET=random_secret_key
   ```

## 🔧 配置通知渠道

### Telegram（推荐）
1. 在 Telegram 中搜索 `@BotFather`
2. 发送 `/newbot` 创建新机器人
3. 获取 Bot Token
4. 在 `@userinfobot` 中获取您的 Chat ID
5. 在系统配置中填入信息

### NotifyX
1. 访问 [NotifyX官网](https://www.notifyx.cn/)
2. 注册账户并获取 API Key
3. 在系统配置中填入

### 其他渠道
- **企业微信**：参考官方文档
- **邮件通知**：使用 Resend 服务
- **钉钉/飞书**：在群设置中添加机器人
- **Bark**：在 iOS 设备上安装 Bark 应用

## 📱 首次使用

### 登录系统
- 访问您的 Worker 域名
- 用户名：`admin`
- 密码：`password`

### 修改密码
1. 登录后点击 "系统配置"
2. 修改管理员密码
3. 点击 "保存配置"

### 添加订阅
1. 点击 "添加新订阅"
2. 填写订阅信息：
   - 服务名称（如：Netflix）
   - 到期日期
   - 提前提醒天数（建议7天）
   - 备注信息
3. 点击 "保存"

### 测试通知
1. 在系统配置中配置通知渠道
2. 点击对应的 "测试" 按钮
3. 检查是否收到通知

## ⚠️ 重要提醒

### 安全设置
- **立即修改默认密码**
- **设置强密码**
- **定期更换 JWT_SECRET**

### 数据备份
- 定期导出订阅数据
- 保存重要配置信息
- 记录 Worker 域名和配置

### 性能优化
- 合理设置提醒天数
- 避免添加过多过期订阅
- 定期清理无用数据

## 🆘 遇到问题？

### 常见问题
1. **无法访问 Worker**
   - 检查 Worker 是否部署成功
   - 确认 KV 存储绑定正确

2. **通知不工作**
   - 检查通知渠道配置
   - 测试 API Key 是否有效

3. **定时任务不执行**
   - 确认 Cron 表达式正确
   - 检查时区设置

### 获取帮助
- [GitHub Issues](https://github.com/logdns/subpush/issues)
- [部署教程](DEPLOY.md)
- [完整文档](README.md)

## 🎉 恭喜！

您已经成功部署了 SubsTracker！现在可以：

- ✅ 管理各种订阅服务
- ✅ 设置智能提醒
- ✅ 享受多渠道通知
- ✅ 使用农历功能

开始管理您的订阅吧！🚀 