# SubsTracker - 智能订阅管理与提醒系统

基于 Cloudflare Workers 的轻量级订阅管理系统，帮助您轻松跟踪各类订阅服务的到期时间，并通过多种渠道发送及时提醒。

[![Deploy to Cloudflare Workers](https://deploy.cloudflareworkers.com/button)](https://deploy.cloudflareworkers.com/?url=https://github.com/logdns/subpush)

## ✨ 功能特色

### 🎯 核心功能
- **订阅管理**：添加、编辑、删除各类订阅服务
- **智能提醒**：自定义提前提醒天数，自动续订计算
- **农历显示**：支持农历日期显示，可控制开关
- **状态管理**：订阅启用/停用，过期状态自动识别
- **数据统计**：实时显示订阅数量、到期状态等统计信息

### 📱 多渠道通知
- **Telegram**：支持 Telegram Bot 通知
- **NotifyX**：集成 NotifyX 推送服务
- **企业微信应用通知**：支持企业微信应用推送
- **企业微信机器人**：支持企业微信群机器人通知
- **邮件通知**：基于 Resend 的专业邮件服务
- **钉钉通知**：支持钉钉群机器人通知
- **飞书通知**：支持飞书机器人通知
- **Bark 推送**：iOS 设备推送通知
- **自定义 Webhook**：支持自定义请求格式和模板

### 🌙 农历功能
- **农历转换**：支持 1900-2100 年农历转换
- **智能显示**：列表和编辑页面可控制农历显示
- **通知集成**：通知消息中可包含农历信息

### 🎨 用户体验
- **现代化界面**：美观的渐变设计、毛玻璃效果、流畅动画
- **响应式设计**：完美适配桌面端和移动端
- **统计面板**：直观的数据统计和状态展示
- **备注优化**：长备注自动截断，悬停显示完整内容
- **实时预览**：日期选择时实时显示对应农历
- **用户偏好**：记住用户的显示偏好设置

## 🚀 一键部署

### 方法一：使用 Deploy 按钮（推荐）

1. **Fork 本仓库**到您的 GitHub 账户
2. **修改 KV 名称**：将 `SUBSCRIPTIONS_KV` 改为您想要的名称
3. **点击部署按钮**：使用上面的 "Deploy to Cloudflare Workers" 按钮
4. **等待部署完成**：系统会自动创建 Worker 和 KV 存储

### 方法二：手动部署

#### 前提条件
- Cloudflare 账户
- 基本的 Web 开发知识

#### 部署步骤

1. **登录 Cloudflare Dashboard**
   - 访问 [Cloudflare Dashboard](https://dash.cloudflare.com/)
   - 选择您的账户

2. **创建 Worker**
   - 点击左侧菜单 "Workers & Pages"
   - 点击 "Create application"
   - 选择 "Create Worker"
   - 输入 Worker 名称（如：substracker）
   - 点击 "Deploy"

3. **创建 KV 存储**
   - 在 Worker 页面，点击 "Settings" 标签
   - 找到 "Variables" 部分
   - 点击 "Add binding"
   - 变量名：`SUBSCRIPTIONS_KV`
   - KV 命名空间：点击 "Add binding" 创建新的 KV
   - KV 名称：`SUBSCRIPTIONS_KV`

4. **配置定时任务**
   - 在 Worker 页面，点击 "Triggers" 标签
   - 点击 "Add Cron Trigger"
   - Cron 表达式：`0 8 * * *`（每天早上8点执行）
   - 时区：选择您的时区

5. **上传代码**
   - 在 Worker 页面，点击 "Quick edit"
   - 将 `index.js` 文件内容复制粘贴到编辑器中
   - 点击 "Save and deploy"

6. **配置环境变量**
   - 在 Worker 页面，点击 "Settings" 标签
   - 找到 "Environment Variables" 部分
   - 添加以下变量：
     ```
     ADMIN_USERNAME=admin
     ADMIN_PASSWORD=your_password
     JWT_SECRET=your_jwt_secret
     ```

### 方法三：使用 Wrangler CLI

#### 安装 Wrangler
```bash
npm install -g wrangler
```

#### 登录 Cloudflare
```bash
wrangler login
```

#### 创建项目
```bash
wrangler init substracker
cd substracker
```

#### 配置 wrangler.toml
```toml
name = "substracker"
main = "index.js"
compatibility_date = "2024-01-01"

[triggers]
crons = ["0 8 * * *"]

[[kv_namespaces]]
binding = "SUBSCRIPTIONS_KV"
id = "your_kv_id"
preview_id = "your_preview_kv_id"
```

#### 部署
```bash
wrangler deploy
```

## 📋 开始使用

### 1️⃣ 首次登录
- 访问部署后的 Worker 域名
- 默认用户名：`admin`
- 默认密码：`password`

### 2️⃣ 基础配置
1. **修改默认密码**（进入系统配置）
2. **配置通知渠道**（选择一个或多个）
3. **设置提醒参数**（提前提醒天数等）

### 3️⃣ 添加订阅
1. 点击"添加新订阅"按钮
2. 填写订阅信息：
   - 服务名称
   - 到期日期
   - 提醒天数
   - 备注信息
3. 选择是否启用农历显示
4. 保存订阅

### 4️⃣ 享受智能提醒
- 系统会在每天早上8点自动检查
- 即将到期的订阅会通过配置的渠道发送通知
- 支持手动测试通知功能

## 🔧 通知渠道配置

### Telegram
- **Bot Token**: 从 [@BotFather](https://t.me/botfather) 获取
- **Chat ID**: 从 [@userinfobot](https://t.me/userinfobot) 获取

### NotifyX
- **API Key**: 从 [NotifyX官网](https://www.notifyx.cn/) 获取

### 邮件通知 (Resend)
- **API Key**: 从 [Resend官方教程](https://developers.cloudflare.com/workers/tutorials/send-emails-with-resend/) 获取
- **发件人邮箱**: 必须是已在Resend验证的域名邮箱
- **收件人邮箱**: 接收通知的邮箱地址

### 企业微信应用通知
- **推送 URL**: 从 [企业微信应用通知平台](https://push.wangwangit.com) 获取
- 支持自定义请求头和消息模板

### 企业微信机器人
- **推送 URL**: 参考 [官方文档](https://developer.work.weixin.qq.com/document/path/91770) 获取

### 钉钉通知
- **Webhook URL**: 从钉钉群机器人设置获取
- **签名密钥**: 可选，用于安全验证

### 飞书通知
- **Webhook URL**: 从飞书群机器人设置获取
- **签名密钥**: 可选，用于安全验证

### Bark 推送
- **设备 Key**: 从 iOS Bark 应用获取
- **服务器地址**: 默认使用官方服务器，可自定义
- **推送参数**: 支持音效、图标、分组等高级功能

## 🎨 界面预览

### 登录页面
- 现代化渐变设计
- 毛玻璃效果和浮动动画
- 响应式布局

### 管理页面
- 统计卡片展示
- 美观的表格设计
- 状态徽章和悬停效果

### 配置页面
- 分区式配置管理
- 图标化界面设计
- 实时配置切换

## 🔒 安全特性

- **JWT 认证**：安全的用户会话管理
- **HTTPS 强制**：所有通信都通过 HTTPS 加密
- **输入验证**：严格的数据输入验证
- **权限控制**：基于角色的访问控制

## 📱 移动端支持

- **响应式设计**：完美适配各种屏幕尺寸
- **触摸优化**：针对移动设备优化的交互体验
- **PWA 支持**：可安装为移动应用

## 🚀 性能优化

- **边缘计算**：基于 Cloudflare Workers 的全球边缘部署
- **KV 存储**：高性能的键值存储
- **缓存策略**：智能的缓存机制
- **代码分割**：优化的代码加载

## 🤝 贡献指南

欢迎贡献代码、报告问题或提出新功能建议！

### 贡献方式
1. **Fork 本仓库**
2. **创建特性分支**：`git checkout -b feature/AmazingFeature`
3. **提交更改**：`git commit -m 'Add some AmazingFeature'`
4. **推送到分支**：`git push origin feature/AmazingFeature`
5. **创建 Pull Request**

### 开发环境
```bash
# 克隆仓库
git clone https://github.com/yourusername/SubsTracker.git
cd SubsTracker

# 安装依赖
npm install

# 本地开发
wrangler dev
```

## 📄 许可证

本项目基于 [MIT License](LICENSE) 开源协议。

## 🙏 致谢

- 基于 [wangwangit/SubsTracker](https://github.com/wangwangit/SubsTracker) 项目，并进行了功能扩展和界面美化
- 感谢所有贡献者的支持
- 特别感谢 Cloudflare 提供的免费服务

## 📞 支持与反馈

- **GitHub Issues**: [报告问题](https://github.com/logdns/subpush/issues)
- **功能建议**: [功能请求](https://github.com/logdns/subpush/issues/new)
- **讨论交流**: [GitHub Discussions](https://github.com/logdns/subpush/discussions)

## 📊 项目统计

![GitHub stars](https://img.shields.io/github/stars/logdns/subpush)
![GitHub forks](https://img.shields.io/github/forks/logdns/subpush)
![GitHub issues](https://img.shields.io/github/issues/logdns/subpush)
![GitHub license](https://img.shields.io/github/license/logdns/subpush)

---

⭐ 如果这个项目对您有帮助，请给我们一个 Star！ 