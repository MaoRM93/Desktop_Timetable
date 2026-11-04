# 桌面备忘录

一个基于 Electron + React + Vite 的桌面备忘录小组件，适合放在桌面角落作为轻量便签、提醒和临时记录工具。

它具有透明窗口、无边框、置顶、锁定/解锁编辑、开机自启动、记住窗口位置等桌面小组件特性，适合日常快速记事。

## 功能特点

- 透明无边框桌面小组件
- 支持新增、编辑、删除备忘录
- 支持锁定/解锁状态切换
- 支持“始终置顶”与桌面层级控制
- 支持窗口位置记忆，重开后保留位置
- 备忘录数据保存在本地，支持本地持久化
- 支持开机自启设置
- 适配 Windows / macOS / Linux 打包构建

## 技术栈

- Electron 39
- Electron-Vite
- React 19
- Vite 7
- Tailwind CSS 3
- Lucide React
- ESLint + Prettier

## 项目结构

```text
Desktop_Timetable/
├── .github/                  # GitHub 配置
├── .vscode/                 # VS Code 配置
├── build/                   # 构建输出目录
├── resources/                # 应用资源（如图标）
├── src/
│   ├── main/                # Electron 主进程
│   │   └── index.js         # 窗口创建、IPC、应用生命周期管理
│   ├── preload/            # 预加载脚本
│   │   └── index.js
│   └── renderer/            # 渲染进程（前端界面）
│       ├── index.html
│       └── src/
│           ├── App.jsx      # 主界面与备忘录逻辑
│           ├── main.jsx
│           └── components/
├── .editorconfig
├── .gitignore
├── .npmrc
├── .prettierignore
├── .prettierrc.yaml
├── electron-builder.yml
├── electron.vite.config.mjs
├── eslint.config.mjs
├── package.json
├── postcss.config.js
├── tailwind.config.js
├── README.md
├── package-lock.json
└── LICENSE (如有)
```

## 运行方式

### 1. 安装依赖

```bash
npm install
```

### 2. 启动开发模式

```bash
npm run dev
```

### 3. 生产构建

```bash
npm run build
```

## 打包发布

### Windows

```bash
npm run build:win
```

### macOS

```bash
npm run build:mac
```

### Linux

```bash
npm run build:linux
```

## 使用说明

1. 启动后，应用会以透明桌面小组件形式显示在桌面上。
2. 点击锁头按钮可切换“锁定/解锁”状态。
3. 在未锁定状态下可以新增、编辑、删除备忘录。
4. 点击右键菜单可设置“全局置顶”、开机自启动以及退出应用。
5. 备忘录内容会写入本地存储，关闭后能保留。

## 备注

当前应用的核心逻辑位于 `src/renderer/src/App.jsx`，主要负责：

- 备忘录列表数据维护
- 锁定状态控制
- 右键菜单与关于弹窗
- 窗口置顶/位置保存
- 本地存储和交互行为

主进程位于 `src/main/index.js`，用于创建无边框窗口、管理 Electron 生命周期、接收渲染进程 IPC 指令。

## License

本项目采用 [MIT 许可证](LICENSE)，详见仓库根目录的 LICENSE 文件。
