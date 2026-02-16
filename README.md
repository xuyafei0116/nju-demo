# NJU Demo 项目

这是一个前端技术演示项目，包含多个独立的技术演示页面。

## 项目结构

```
/
├── index.html              # 主页，列出所有demo
├── clarity-demo/           # Clarity 演示
│   └── index.html
├── vue-demo/               # Vue 演示
│   └── index.html
├── canvas-demo/            # Canvas 演示
│   └── index.html
└── README.md
```

## 演示内容

### Clarity Demo
展示 VMware Clarity Design System 的 UI 组件，包括：
- 按钮组件
- 表单组件
- 卡片组件
- 徽章组件
- 警告提示

### Vue Demo
展示 Vue.js 3 的核心功能，包括：
- 响应式数据（计数器示例）
- 待办事项列表
- 计算属性
- 条件渲染和列表渲染

### Canvas Demo
展示 HTML5 Canvas 的绘图能力，包括：
- 粒子动画效果
- 交互式绘图板
- 几何图形绘制

## 使用方法

直接在浏览器中打开 `index.html` 即可查看所有演示。

```bash
# 使用 Python 启动本地服务器
python -m http.server 8080

# 或使用 Node.js 的 http-server
npx http-server -p 8080
```

然后访问 http://localhost:8080

## 技术栈

- **Clarity**: VMware 开源设计系统
- **Vue.js 3**: 渐进式 JavaScript 框架
- **HTML5 Canvas**: 原生图形绘制 API

## 许可证

MIT License
