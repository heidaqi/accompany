# Accompany — Desktop Companion Chatbot

AI desktop companion named "Doubao" (豆包) that lives in the bottom-right corner of your screen.

- **Passive mode**: camera reads your facial expression → companion reacts with matching emotion + warm bubble text
- **Chat mode**: click the companion → chat window opens → deep emotional conversation with memory

Doubao is a pink-haired bunny girl (VRoid Studio preset model) with rose-colored eyes, rabbit ears, and a fluffy tail — sweet and soft, a pastry sprite from the star sea. Rendered as 2D sprite animations composited by PyQt QPainter.

## Quick Start

```powershell
# Step 1: Double-click SETUP.bat (auto-detect Python, create venv, install deps)
# Step 2: Copy .env.example to .env and fill in your LLM API keys
# Step 3: Double-click START_ACCOMPANY.bat
```

Or manually:

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
copy .env.example .env
# Edit .env with your API keys
python main.py
```

Debug mode: `START_ACCOMPANY_DEBUG.bat` — keeps console open after exit, prints recent log.

## Design System

```
accent:      #D96B8B   Deep Rose — headers, buttons, links
bg:          #FFF7F4   Warm Blush — main background
surface:     #FFFFFF   Cards, toolbar
text:        #2F282C   Warm Dark
muted:       #8F7F86   Secondary text
border:      #E8DAD7   Subtle separation
radius:      12px      System-wide (inputs, bubbles, cards)
btn-radius:  16px      Pill-shaped interactive elements
font:        "Microsoft YaHei", "Segoe UI", sans-serif
```

- Young mode: normal sizing, playful tone
- Elderly mode: 16px+ base font, high contrast, warmer phrasing

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Desktop | PyQt6 — tray icon, frameless companion widget, chat window |
| Agent | LangGraph ReAct — Observer-Guard-Retry loop with tools |
| LLM | Volcano Ark / DeepSeek / Qwen — 3-tier fallback chain |
| Memory | Short-term (deque 20-round) + ChromaDB vector long-term (ONNX MiniLM-L6-v2) |
| Emotion | EmotiEffLib ONNX — camera-based facial expression recognition |
| Avatar | VRoid Studio preset model → 512×512 sprite sheets, PyQt QPainter compositing |
| Config | python-dotenv (.env), loguru logging |

## Project Structure

```
accompany/
├── main.py                  App entry (tray + companion + camera + loop)
├── SETUP.bat                One-click environment setup
├── START_ACCOMPANY.bat      One-click launcher
├── .env.example             Configuration template
├── eye/                     Camera + emotion recognition (multiprocessing)
├── brain/                   LangGraph Agent, LLM fallback, prompts, memory
├── face/                    Companion widget, sprite animator, speech bubble
│   └── sprites_vroid/       512×512 sprite frames (8 expr × 4)
├── chat/                    Chat window, message bubbles, settings, emotion chart
├── utils/                   Config singleton, logger, signal bus
├── tests/                   Pipeline regression tests
├── tools/                   Export/inspect scripts
├── skills/                  AI skill definitions
├── My project/              Unity 3D project (future development, not yet ready)
├── doubaoo.vrm              Character model (VRM 1.0, VRoid Studio preset)
├── model.vroid              VRoid Studio source project
├── THIRD_PARTY_NOTICES.md   License attributions
└── 方案文档.md               Full technical design document (Chinese)
```

## Documentation

- **[方案文档.md](方案文档.md)** — Complete technical design, data flow, architecture decisions
- **[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)** — Open-source license attributions
- **[face/角色设定书.md](face/角色设定书.md)** — Character design bible (colors, expressions, actions, sprite specs)

## License

Apache License 2.0 — see [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) for third-party attributions.
