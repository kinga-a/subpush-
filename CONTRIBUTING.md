# 贡献指南

感谢您对 SubsTracker 项目的关注！我们欢迎所有形式的贡献，包括但不限于：

- 🐛 Bug 报告
- 💡 功能建议
- 📝 文档改进
- 🔧 代码贡献
- 🌍 国际化支持

## 🤝 如何贡献

### 1. 报告 Bug

如果您发现了 Bug，请：

1. 在 [GitHub Issues](https://github.com/logdns/subpush/issues) 中搜索是否已有相关报告
2. 如果没有，请创建新的 Issue
3. 使用 Bug 报告模板，并提供以下信息：
   - 详细的 Bug 描述
   - 重现步骤
   - 预期行为和实际行为
   - 环境信息（浏览器、操作系统等）
   - 截图或录屏（如果适用）

### 2. 功能建议

如果您有功能建议，请：

1. 在 Issues 中搜索是否已有类似建议
2. 创建新的 Issue，使用 "Feature Request" 标签
3. 详细描述您的想法和用例
4. 讨论实现方案和优先级

### 3. 代码贡献

如果您想贡献代码，请：

1. Fork 本仓库
2. 创建特性分支：`git checkout -b feature/AmazingFeature`
3. 提交更改：`git commit -m 'Add some AmazingFeature'`
4. 推送到分支：`git push origin feature/AmazingFeature`
5. 创建 Pull Request

### 4. 文档改进

文档改进同样重要！您可以：

- 修正拼写错误
- 改进说明文字
- 添加示例代码
- 翻译文档
- 添加截图或图表

## 📋 开发环境设置

### 前提条件

- Node.js 18+ 
- npm 或 yarn
- Git

### 本地开发

```bash
# 克隆仓库
git clone https://github.com/logdns/subpush.git
cd subpush

# 安装依赖
npm install

# 安装 Wrangler CLI
npm install -g wrangler

# 登录 Cloudflare
wrangler login

# 本地开发
wrangler dev
```

### 代码规范

- 使用 2 空格缩进
- 遵循现有的代码风格
- 添加适当的注释
- 确保代码通过基本测试

## 🏗️ 项目结构

```
SubsTracker/
├── .github/          # GitHub Actions 工作流
├── index.js          # 主要代码文件
├── README.md         # 项目说明
├── DEPLOY.md         # 部署教程
├── QUICKSTART.md     # 快速开始指南
├── CONTRIBUTING.md   # 贡献指南
├── LICENSE           # MIT 许可证
├── package.json      # 项目配置
├── wrangler.toml     # Wrangler 配置
└── .gitignore        # Git 忽略文件
```

## 🧪 测试

在提交代码前，请确保：

1. 代码在本地正常运行
2. 没有明显的语法错误
3. 功能按预期工作
4. 界面在不同设备上正常显示

## 📝 提交规范

请使用清晰的提交信息：

```
feat: 添加新的通知渠道支持
fix: 修复农历日期计算错误
docs: 更新部署说明
style: 改进界面样式
refactor: 重构通知逻辑
test: 添加测试用例
chore: 更新依赖版本
```

## 🔄 Pull Request 流程

1. **创建分支**：从 `main` 分支创建新分支
2. **开发功能**：在分支上开发您的功能
3. **测试验证**：确保代码正常工作
4. **提交代码**：使用清晰的提交信息
5. **创建 PR**：描述您的更改和原因
6. **代码审查**：等待维护者审查
7. **合并代码**：审查通过后合并

## 📞 获取帮助

如果您在贡献过程中遇到问题：

- 查看 [Issues](https://github.com/logdns/subpush/issues)
- 查看 [Discussions](https://github.com/logdns/subpush/discussions)
- 联系项目维护者

## 🎯 贡献优先级

我们优先考虑以下贡献：

1. **Bug 修复**：影响核心功能的 Bug
2. **安全改进**：安全相关的修复和改进
3. **性能优化**：提升系统性能的改进
4. **用户体验**：改善用户界面的改进
5. **文档完善**：帮助用户更好地使用系统

## 🏆 贡献者荣誉

所有贡献者都将被列在项目的贡献者列表中。我们感谢每一位为项目做出贡献的人！

## 📄 许可证

通过贡献代码，您同意您的贡献将在 MIT 许可证下发布。

---

再次感谢您的贡献！让我们一起让 SubsTracker 变得更好！🚀 