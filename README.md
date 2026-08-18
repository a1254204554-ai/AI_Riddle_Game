# 🪄 汉字谜盒

一款基于 AI 的中文猜字谜互动游戏。玩家与 DeepSeek 大模型驱动的 AI 机器人进行猜字挑战，在轻松有趣的互动中感受汉字的无穷魅力。

![Python](https://img.shields.io/badge/Python-3.14-blue)
![FastAPI](https://img.shields.io/badge/FastAPI-latest-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

## ✨ 功能特色

- **智能判题** — AI 精准判断答案是否正确，答对即获即时夸奖
- **贴心提示** — 猜错时提供线索引导，不会直接透露答案
- **无限挑战** — 每次出题完全随机，永不重复
- **会话记忆** — 游戏记录自动保存，随时回顾精彩对局
- **主题切换** — 支持亮色 / 暗黑两种主题，本地持久化
- **多会话管理** — 新建、切换、删除游戏记录，互不干扰

## 🎮 核心玩法

1. 打开游戏后，AI 会自动出一道经典字谜（如「一口咬掉牛尾巴」）
2. 根据谜面提示，输入你猜的汉字
3. AI 判断对错：答对夸奖并揭晓谜底，答错给出提示鼓励继续
4. 可随时说「提示一下」「换一题」「公布答案」来推进游戏

## 🏗️ 技术架构

| 层级 | 技术栈 |
|------|--------|
| 前端 | HTML5 + CSS3 + 原生 JavaScript |
| 后端 | Python 3.14 + FastAPI + Uvicorn |
| AI | DeepSeek Chat API (deepseek-chat) |
| 数据存储 | JSON 文件（sessions 目录） |

## 📁 项目结构

```
猜谜游戏/
├── main.py              # FastAPI 后端入口，API 路由 & AI 交互
├── static/
│   ├── index.html       # 前端页面
│   ├── app.js           # 前端交互逻辑
│   └── style.css        # 样式文件
├── sessions/            # 会话数据存放目录（自动生成）
├── .gitignore
└── README.md
```

## 🚀 快速开始

### 1. 克隆项目

```bash
git clone https://github.com/a1254204554-ai/AI_Riddle_Game.git
cd AI_Riddle_Game
```

### 2. 创建虚拟环境并安装依赖

```bash
python -m venv .venv
.venv\Scripts\activate        # Windows
pip install fastapi uvicorn openai pydantic
```

### 3. 配置 API Key

设置环境变量 `DEEPSEEK_API_KEY`：

```powershell
# PowerShell
$env:DEEPSEEK_API_KEY = "your_deepseek_api_key"
```

### 4. 启动服务

```bash
python main.py
```

服务启动后访问 **http://127.0.0.1:8000** 即可开始游戏。

## 📡 API 接口

| 方法 | 路径 | 说明 |
|------|------|------|
| `GET` | `/` | 访问首页 |
| `POST` | `/api/sessions` | 创建新会话 |
| `GET` | `/api/sessions` | 获取会话列表 |
| `GET` | `/api/sessions/{session_id}` | 获取指定会话详情 |
| `DELETE` | `/api/sessions/{session_id}` | 删除指定会话 |
| `POST` | `/api/chat` | 发送消息并与 AI 交互 |

## 📄 开源协议

MIT License
