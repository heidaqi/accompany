# Accompany V1.0 快速启动指南

## 环境要求

| 项目 | 要求 |
|------|------|
| 操作系统 | Windows 10/11 64-bit |
| Python | 3.10 - 3.14（需加入系统 PATH） |
| 摄像头 | 可选（无摄像头也能聊天） |
| LLM API Key | 至少配置 1 个（推荐火山方舟豆包） |

## 三步启动

### 第 1 步：双击 SETUP.bat

自动检测 Python → 创建虚拟环境 → 安装依赖。大约 2-3 分钟。

### 第 2 步：配置 API Key

复制 `.env.example` 为 `.env`，用记事本打开填入你的 LLM API Key：

```ini
LLM_PRIMARY_PROVIDER=volcano
LLM_PRIMARY_MODEL=doubao-pro-32k
LLM_PRIMARY_BASE_URL=https://ark.cn-beijing.volces.com/api/v3
LLM_PRIMARY_API_KEY=你申请的key
```

最少填一项即可。更多模型选项见 `.env.example` 中注释。

### 第 3 步：双击 START_ACCOMPANY.bat

豆包出现在屏幕右下角！左键点击聊天，右键退出。

## 常见问题

**Q: 双击 BAT 闪退？**
→ 用管理员打开 cmd，cd 到 V1.0 目录，运行 `START_ACCOMPANY.bat` 看报错信息

**Q: pip 安装失败？**
→ 升级 pip：`python -m pip install --upgrade pip`，然后重试 SETUP.bat

**Q: 摄像头打不开？**
→ 在 `.env` 中设置 `ENABLE_PASSIVE_MONITORING=false`，只使用聊天模式

**Q: 提示缺少 chromadb？**
→ 手动执行：`.venv\Scripts\pip.exe install chromadb`
