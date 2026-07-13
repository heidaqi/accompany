# Accompany — 桌面智能陪伴聊天机器人

> **[⬇ 下载 V1.0（46MB）](Accompany-V1.0.zip)**  |  解压 → 双击 `SETUP.bat` → 配 `.env` API Key → 双击 `START_ACCOMPANY.bat`

豆包是一个住在你屏幕右下角的桌面 AI 陪伴伙伴，粉色兔耳少女，来自星海的包子精灵。

- **陪伴模式**：摄像头定时读取你的表情 → 豆包自动做出对应表情和动作 → 弹出温暖气泡 → 不打扰你
- **聊天模式**：点击豆包 → 展开聊天窗口 → 深度情感对话，带长期记忆

豆包的模型直接使用 [VRoid Studio](https://vroid.com/en/studio) 官方免费预设角色，未做二次建模，渲染为 2D 精灵动画（PyQt6 QPainter 双轨合成）。

## 快速开始

1. 下载 `Accompany-V1.0.zip` 并解压
2. 双击 `SETUP.bat`（自动检测 Python → 创建虚拟环境 → 安装依赖，约 2-3 分钟）
3. 将 `.env.example` 重命名为 `.env`，用记事本填入你的 LLM API Key
4. 双击 `START_ACCOMPANY.bat`

> 最少配置一个 API Key 即可运行，推荐火山方舟豆包。摄像机可选，没有也能正常聊天。

命令行备选：

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
copy .env.example .env
# 编辑 .env 填入 API Key
python main.py
```

调试模式：`START_ACCOMPANY_DEBUG.bat` — 关闭后保留控制台，打印最近日志。

## 设计系统

```
accent:      #D96B8B   深玫瑰 — 标题、按钮、链接
bg:          #FFF7F4   暖腮红 — 主背景
surface:     #FFFFFF   卡片、工具栏
text:        #2F282C   暖深色
muted:       #8F7F86   次要文字
border:      #E8DAD7   柔和分割线
radius:      12px      全局圆角（输入框、气泡、卡片）
btn-radius:  16px      胶囊形按钮
font:        "Microsoft YaHei", "Segoe UI", sans-serif
```

- 年轻人模式：正常字号，活泼语气
- 老年人模式：16px+ 基础字体，高对比度，更温暖的措辞

## 技术栈

| 层级 | 技术 | 说明 |
|------|------|------|
| 桌面 | [PyQt6](https://www.riverbankcomputing.com/software/pyqt/) | 系统托盘 + 无边框窗口 + 信号总线 |
| Agent | [LangGraph](https://github.com/langchain-ai/langgraph) ReAct | Observer-Guard-Retry 循环 |
| LLM | 火山方舟 / DeepSeek / 通义千问 | 三级降级链 |
| 记忆 | deque 短期 + [ChromaDB](https://github.com/chroma-core/chroma) 向量长期 | ONNX MiniLM 本地 Embedding |
| 表情识别 | [EmotiEffLib](https://github.com/sb-ai-lab/EmotiEffLib) ONNX | 摄像头面部表情识别 |
| 数字人 | [VRoid Studio](https://vroid.com/en/studio) 预设模型 | 512×512 精灵图序列帧，PyQt QPainter 合成 |
| 配置 | [python-dotenv](https://github.com/theskumar/python-dotenv) + [loguru](https://github.com/Delgan/loguru) | .env 配置 + 日志 |

## 项目结构

```
accompany/
├── main.py                  主入口（托盘 + 数字人窗口 + 摄像头 + 陪伴循环）
├── SETUP.bat                一键配置环境
├── START_ACCOMPANY.bat      一键启动
├── .env.example             配置文件模板
├── eye/                     摄像头 + 表情识别（独立子进程）
├── brain/                   LangGraph Agent、LLM 降级链、记忆系统
├── face/                    数字人窗口、精灵动画引擎、对话气泡
│   └── sprites_vroid/       512×512 精灵帧（8 表情 × 4 帧）
├── chat/                    聊天窗口、消息气泡、设置面板、情绪图表
├── utils/                   配置、日志、信号总线
├── tests/                   回归测试
├── tools/                   导出/检查脚本
├── My project/              Unity 3D 工程（预留，开发中）
├── doubaoo.vrm              角色模型（VRM 1.0）
├── model.vroid              VRoid Studio 工程源文件
├── THIRD_PARTY_NOTICES.md   第三方许可证声明
└── 方案文档.md               完整技术设计文档
```

## 文档

- **[方案文档.md](方案文档.md)** — 完整技术设计、数据流、架构决策
- **[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)** — 开源许可证声明
- **[face/角色设定书.md](face/角色设定书.md)** — 豆包角色设计母板（配色、表情、动作、精灵规格）

## 许可证

Apache License 2.0 — 第三方授权详见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。
