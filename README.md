# SpringBlog - 现代化博客系统

一个基于 Vue 3 + Spring Boot 的现代化博客平台，专注于编程学习和技术交流，提供丰富的功能和优秀的用户体验。

## ✨ 特性

### 🎨 用户界面
- 🌓 **暗黑模式支持** - 完整的明暗主题切换
- 📱 **响应式设计** - 适配各种设备屏幕
- 🎯 **现代化UI** - 基于 Element Plus 组件库
- 🚀 **流畅动画** - 页面切换和交互动画

### 📝 博客功能
- ✍️ **Markdown 编辑器** - 基于 Vditor 的富文本编辑
- 🏷️ **标签系统** - 文章分类和标签管理
- 👍 **点赞评论** - 用户互动功能
- 🔍 **搜索功能** - 全文搜索和筛选
- 📊 **文章管理** - 完整的CRUD操作

### 👥 用户系统
- 🔐 **用户认证** - 注册、登录、密码重置
- 🎭 **角色权限** - 普通用户和管理员权限
- 👤 **个人资料** - 用户信息管理
- 🔗 **OAuth 登录** - 第三方登录支持

### 🤖 AI 功能
- 💬 **AI 聊天** - 集成大语言模型对话
- 📚 **知识库管理** - RAG 知识库创建和管理
- 🧠 **智能问答** - 基于知识库的智能回答

### 📁 资源管理
- 📂 **文件上传** - 图片和文档上传
- 🗂️ **资源分类** - 资源库管理
- 🔗 **链接分享** - 资源链接管理

## 🛠️ 技术栈

### 前端技术
- **Vue 3** - 渐进式 JavaScript 框架
- **Vite** - 下一代前端构建工具
- **Vue Router 4** - 官方路由管理器
- **Pinia** - 状态管理库
- **Element Plus** - Vue 3 组件库
- **Axios** - HTTP 客户端
- **Sass** - CSS 预处理器

### 编辑器和工具
- **Vditor** - Markdown 编辑器
- **Prism.js** - 代码高亮
- **Day.js** - 日期处理库
- **NProgress** - 页面加载进度条
- **Vue Advanced Cropper** - 图片裁剪

### 开发工具
- **Unplugin Auto Import** - 自动导入
- **Unplugin Icons** - 图标自动导入
- **ESLint** - 代码规范检查

## 📦 安装和运行

### 环境要求
- Node.js >= 16.0.0
- npm >= 8.0.0

### 安装依赖
```bash
npm install
```

### 开发环境运行
```bash
npm run dev
```

### 生产环境构建
```bash
npm run build
```

### 预览构建结果
```bash
npm run preview
```

## 🔧 配置说明

### 后端服务配置
项目通过 Vite 代理配置连接多个后端服务：

```javascript
server: {
  port: 5000,
  proxy: {
    '/api': {
      target: "http://localhost:58080",  // 用户认证服务
      changeOrigin: true
    },
    '/llm': {
      target: "http://localhost:58070",  // AI 服务
      changeOrigin: true
    },
    '/resources': {
      target: "http://localhost:58012",  // 资源管理服务
      changeOrigin: true
    },
    '/blogs': {
      target: "http://localhost:58050",  // 博客服务
      changeOrigin: true
    }
  }
}
```

### 环境变量
创建 `.env.local` 文件配置环境变量：

```env
# API 基础地址
VITE_API_BASE_URL=http://localhost:5000

# 应用标题
VITE_APP_TITLE=SpringBlog
```

## 📁 项目结构

```
src/
├── api/                 # API 接口定义
│   ├── auth.js         # 认证相关接口
│   ├── blog.js         # 博客相关接口
│   ├── comment.js      # 评论相关接口
│   ├── like.js         # 点赞相关接口
│   ├── user.js         # 用户相关接口
│   ├── ai.js           # AI 相关接口
│   └── resource.js     # 资源相关接口
├── components/          # 可复用组件
│   ├── blog/           # 博客相关组件
│   └── layout/         # 布局组件
├── router/             # 路由配置
│   └── index.js        # 路由定义
├── stores/             # 状态管理
│   ├── user.js         # 用户状态
│   ├── blog.js         # 博客状态
│   └── theme.js        # 主题状态
├── styles/             # 样式文件
│   ├── index.scss      # 全局样式
│   └── dark-mode.scss  # 暗黑模式样式
├── utils/              # 工具函数
│   └── avatar.js       # 头像处理
├── views/              # 页面组件
│   ├── Home.vue        # 首页
│   ├── Blog.vue        # 博客列表
│   ├── BlogDetail.vue  # 博客详情
│   ├── auth/           # 认证页面
│   ├── user/           # 用户页面
│   ├── admin/          # 管理员页面
│   └── ai/             # AI 功能页面
├── App.vue             # 根组件
└── main.js             # 应用入口
```

## 🎯 主要功能模块

### 1. 用户认证系统
- 用户注册和登录
- 邮箱验证
- 密码重置
- OAuth 第三方登录
- JWT Token 管理

### 2. 博客管理系统
- Markdown 文章编写
- 文章发布和编辑
- 标签和分类管理
- 文章搜索和筛选
- 热门文章推荐

### 3. 用户交互功能
- 文章点赞和收藏
- 评论系统
- 用户关注
- 消息通知

### 4. 管理员功能
- 用户管理
- 文章管理
- 评论管理
- 系统统计

### 5. AI 智能功能
- 多模型 AI 对话
- 对话历史管理
- 知识库创建和管理
- RAG 智能问答

### 6. 资源管理
- 文件上传和管理
- 图片处理和裁剪
- 资源分类和搜索

## 🎨 主题和样式

### 暗黑模式
项目支持完整的暗黑模式，包括：
- 自动主题切换
- 组件样式适配
- Markdown 内容样式
- 代码高亮主题

### 响应式设计
- 移动端优先设计
- 平板和桌面端适配
- 弹性布局和网格系统

## 🔒 安全特性

- JWT Token 认证
- 路由权限控制
- XSS 防护
- CSRF 防护
- 输入验证和过滤

## 🚀 性能优化

- 路由懒加载
- 组件按需导入
- 图片懒加载
- 代码分割
- 缓存策略

## 📱 浏览器支持

- Chrome >= 87
- Firefox >= 78
- Safari >= 14
- Edge >= 88

## 🤝 贡献指南

1. Fork 项目
2. 创建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 打开 Pull Request

## 📄 许可证

本项目采用 MIT 许可证 - 查看 [LICENSE](LICENSE) 文件了解详情。

## 📞 联系方式

- 项目地址: [GitHub Repository](https://github.com/your-username/springblog)
- 问题反馈: [Issues](https://github.com/your-username/springblog/issues)
- 邮箱: your-email@example.com

## 🙏 致谢

感谢以下开源项目的支持：
- [Vue.js](https://vuejs.org/)
- [Element Plus](https://element-plus.org/)
- [Vditor](https://github.com/Vanessa219/vditor)
- [Vite](https://vitejs.dev/)
- [Pinia](https://pinia.vuejs.org/)

---

⭐ 如果这个项目对你有帮助，请给它一个星标！
