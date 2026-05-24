# awesome-ai-apps

> **Curated production AI applications — LLM agents, RAG systems, multimodal apps, and multi-agent teams**

<p align="center">
  <img src="https://img.shields.io/github/stars/hmzainjamil/awesome-ai-apps?style=for-the-badge&color=FFD700&labelColor=222" alt="Stars"/>
  <img src="https://img.shields.io/github/forks/hmzainjamil/awesome-ai-apps?style=for-the-badge&color=00BFFF&labelColor=222" alt="Forks"/>
  <img src="https://img.shields.io/github/issues/hmzainjamil/awesome-ai-apps?style=for-the-badge&color=FF4500&labelColor=222" alt="Issues"/>
  <img src="https://img.shields.io/github/issues-pr/hmzainjamil/awesome-ai-apps?style=for-the-badge&color=9B59B6&labelColor=222" alt="PRs"/>
  <img src="https://img.shields.io/github/last-commit/hmzainjamil/awesome-ai-apps?style=for-the-badge&color=2ECC71&labelColor=222" alt="Last Commit"/>
</p>

<p align="center">
  <a href="https://awesome.re"><img src="https://awesome.re/badge.svg" alt="Awesome"/></a>
  <img src="https://img.shields.io/badge/OpenAI-412991?style=flat&labelColor=555&logo=openai&logoColor=white" alt="OpenAI"/>
  <img src="https://img.shields.io/badge/Anthropic-CC785C?style=flat&labelColor=555" alt="Anthropic"/>
  <img src="https://img.shields.io/badge/Google_Gemini-4285F4?style=flat&labelColor=555&logo=googlegemini&logoColor=white" alt="Gemini"/>
  <img src="https://img.shields.io/badge/LangChain-1C3C3C?style=flat&labelColor=555" alt="LangChain"/>
  <img src="https://img.shields.io/badge/CrewAI-FF4F00?style=flat&labelColor=555" alt="CrewAI"/>
  <img src="https://img.shields.io/badge/Agno-6C47FF?style=flat&labelColor=555" alt="Agno"/>
</p>

---

## Why This Exists

Most "awesome AI" lists are just GitHub links with no context. This repo is different: every app includes a working implementation, documented architecture, model config, and a description of what business problem it solves. It targets developers who want to **run** AI apps, not just read about them.

100+ complete applications planned. 5 categories. Real code.

---

## At a Glance

| Category | Apps | Stack | Best For |
|----------|------|-------|----------|
| Starter Agents | 8 | OpenAI, Claude, Gemini, Llama | Learning LLM integration patterns |
| Advanced Agents | 3 | Gemini, multi-step workflows | Complex reasoning + video analysis |
| Multi-Agent Teams | 2 | CrewAI, Agno | Parallel specialized agent work |
| RAG Applications | 4 | Gemini + vector search | Knowledge-base Q&A systems |
| Multimodal Apps | 5 | Gemini, ElevenLabs, Hedra | Vision, audio, video generation |
| Total apps | 22+ active | — | — |
| Target by end 2025 | 100+ | — | — |
| License | MIT | — | — |

---

## 🧠 CONCEPTS

| Concept | Explanation |
|---------|-------------|
| **LLM Agent** | LLM + tools + memory + planning loop — goes beyond single Q&A |
| **RAG** | Retrieval-Augmented Generation — inject relevant docs before model call |
| **Multi-agent team** | Multiple specialized LLMs coordinating on a shared task |
| **Multimodal** | Models that accept text + images + video + audio as input |
| **Streaming** | Token-by-token response — UX feels real-time vs waiting for full answer |
| **Tool calling** | Model returns structured JSON → app executes function → result fed back |
| **CrewAI** | Python framework for orchestrating teams of specialized agents |
| **Agno** | Lightweight multi-agent framework — minimal overhead |
| **Vector search** | Semantic similarity search over embeddings — core of RAG |
| **Contextual RAG** | RAG with reranking + compression — more accurate than naive chunking |

### 🔥 Hot

| App | Why It's Referenced Everywhere | Source |
|-----|-------------------------------|--------|
| YouTube Shorts Autopilot | WAN video gen → edit → upload, zero human touch | [HMZ](https://github.com/hmzainjamil) |
| Competitive Intelligence Platform | Live market + competitor insights via RAG | [HMZ](https://github.com/hmzainjamil) |
| Gemini Sketch-to-Video | Draw a sketch → Veo generates animated video | [HMZ](https://github.com/hmzainjamil) |

---

## ⚙️ HOW IT WORKS

Each app is a self-contained directory:

```
<category>/<app-name>/
├── README.md          ← app-specific docs
├── main.py            ← entry point
├── requirements.txt   ← dependencies
├── .env.example       ← required env vars
└── src/               ← app source code
```

Apps are independent — no shared global state. Pick one, cd in, pip install, run.

**Architecture pattern per category:**

```
Starter Agents:      prompt → LLM → response (no tools)
Advanced Agents:     prompt → LLM → tool → LLM → response
Multi-Agent Teams:   task → orchestrator → [agent1 ‖ agent2 ‖ agent3] → synthesis
RAG Apps:            query → embed → vector search → context inject → LLM
Multimodal Apps:     file/url → parse frames/audio → LLM with vision → output
```

---

## 🚀 INSTALL

### Run any app

```bash
git clone https://github.com/hmzainjamil/awesome-ai-apps
cd awesome-ai-apps

# Example: run the Claude conversation agent
cd starter-agents/claude-3-conversation-agent
pip3 install -r requirements.txt
cp .env.example .env
# Edit .env with your ANTHROPIC_API_KEY
python3 main.py
```

### Common dependencies

```bash
# Most apps need these
pip3 install anthropic openai google-generativeai langchain
pip3 install faiss-cpu chromadb      # for RAG apps
pip3 install crewai agno              # for multi-agent apps
pip3 install elevenlabs               # for voice apps
```

---

## 📟 USAGE

### Starter Agents

```bash
# Claude conversation agent
cd starter-agents/claude-3-conversation-agent
ANTHROPIC_API_KEY=sk-... python3 main.py

# OpenAI chat assistant
cd starter-agents/openai-chat-assistant
OPENAI_API_KEY=sk-... python3 main.py

# Voice chatbot (ElevenLabs)
cd starter-agents/elevenlabs-voice-assistant
ELEVENLABS_API_KEY=... OPENAI_API_KEY=... python3 main.py
```

### RAG Apps

```bash
# Competitive Intelligence Platform
cd rag-applications/competitive-intelligence-platform
pip3 install -r requirements.txt
cp .env.example .env   # set GOOGLE_API_KEY
python3 main.py --company "Acme Corp" --competitors "Rival1,Rival2"
```

### Multi-Agent Teams

```bash
# Content Creation Team
cd multi-agent-teams/content-creation-team
pip3 install crewai
OPENAI_API_KEY=... python3 main.py --topic "AI trends 2026"
```

### Multimodal Apps

```bash
# Sketch to video
cd multimodal-apps/gemini-veo-sketch2video
GOOGLE_API_KEY=... python3 main.py --sketch ./my-sketch.png
```

---

## ⚙️ CONFIGURATION

| App | Required Keys | Optional Keys | Notes |
|-----|--------------|---------------|-------|
| Claude Conversation | `ANTHROPIC_API_KEY` | — | Supports all Claude models |
| OpenAI Chat | `OPENAI_API_KEY` | — | GPT-4o default |
| Voice Chatbot | `ELEVENLABS_API_KEY`, `OPENAI_API_KEY` | `VOICE_ID` | ElevenLabs TTS |
| Brand Video Monitor | `GOOGLE_API_KEY` | `BRAND_KEYWORDS` | Gemini 2.0 Flash |
| Blog Video Writer | `GOOGLE_API_KEY` | `BLOG_URL` | Multi-agent pipeline |
| Competitive Intel | `GOOGLE_API_KEY` | `CHROMA_PATH` | Gemini + ChromaDB |
| Content Creation Team | `OPENAI_API_KEY` | `CREWAI_TELEMETRY=false` | CrewAI framework |
| Contextual Video RAG | `GOOGLE_API_KEY` | `FAISS_INDEX_PATH` | Gemini embeddings |
| Gemini Sketch-to-Video | `GOOGLE_API_KEY` | — | Requires Veo API access |
| AI Girlfriend | `HEDRA_API_KEY`, `OPENAI_API_KEY` | `ELEVENLABS_API_KEY` | Adult content — review TOS |

---

## 💡 TIPS AND TRICKS

### Starting Out
| Tip | Detail | Source |
|-----|--------|--------|
| Start with Starter Agents | Simpler code, same patterns — build intuition before multi-agent | [HMZ](https://github.com/hmzainjamil) |
| Use Gemini Flash first | Free tier, fast, vision-capable — most apps support it | [HMZ](https://github.com/hmzainjamil) |
| Read .env.example | Tells you exactly what you need before installing anything | [HMZ](https://github.com/hmzainjamil) |

### RAG Apps
| Tip | Detail | Source |
|-----|--------|--------|
| Chunk size matters | 512 tokens works for most — smaller for precise retrieval | [HMZ](https://github.com/hmzainjamil) |
| Add metadata to chunks | Include source URL, date in chunk metadata — improves citation quality | [HMZ](https://github.com/hmzainjamil) |
| Rerank results | Top-5 semantic + rerank to top-3 beats top-3 semantic alone | [HMZ](https://github.com/hmzainjamil) |

### Multi-Agent
| Tip | Detail | Source |
|-----|--------|--------|
| Define clear agent roles | Vague roles = agents duplicating work — be specific in role description | [HMZ](https://github.com/hmzainjamil) |
| Limit agent count | 3-4 agents outperforms 10 — communication overhead grows quadratically | [HMZ](https://github.com/hmzainjamil) |
| Use cheaper models for sub-agents | Route synthesis to Sonnet, research to Flash, saves 60%+ | [HMZ](https://github.com/hmzainjamil) |

### Multimodal
| Tip | Detail | Source |
|-----|--------|--------|
| Downsample before sending | 720p is enough for most vision tasks — 4K wastes tokens | [HMZ](https://github.com/hmzainjamil) |
| Batch frames | Send 4-8 frames per call vs 1 at a time — 4x fewer API calls | [HMZ](https://github.com/hmzainjamil) |
| Use timestamps in prompts | "At 2:15, what is on screen?" improves temporal accuracy | [HMZ](https://github.com/hmzainjamil) |

---

## 🔧 TROUBLESHOOTING

| Issue | Cause | Fix |
|-------|-------|-----|
| API quota exceeded | Too many calls in short time | Add `time.sleep(1)` between calls or use batch API |
| ChromaDB error on ARM Mac | Incompatible binary | `pip3 install chromadb --no-binary chromadb` |
| Gemini 404 | Model name changed | Check [ai.google.dev](https://ai.google.dev) for current model IDs |
| CrewAI version conflicts | Breaking changes in 0.x | Pin: `crewai==0.28.0` in requirements.txt |
| ElevenLabs audio static | Wrong audio format | Set `output_format="mp3_44100_128"` |
| RAG returns wrong docs | Chunk size too large | Reduce to 256 tokens, re-embed |
| Multi-agent loop | No termination condition | Add `max_iterations=10` to crew config |
| Hedra 429 | Rate limit | Hedra limits concurrent generations — add queue |

---

## 📊 ARCHITECTURE

```
awesome-ai-apps/
├── starter-agents/
│   ├── ai21-studio-chat/
│   ├── elevenlabs-voice-assistant/
│   ├── claude-3-conversation-agent/
│   ├── google-palm-chat/
│   ├── local-llama-chat/
│   ├── openai-chat-assistant/
│   ├── claude-code-reviewer/
│   └── together-ai-chat/
├── advanced-agents/
│   ├── brand-video-monitor/
│   └── blog-video-writer/
├── multi-agent-teams/
│   └── content-creation-team/
├── rag-applications/
│   ├── contextual-video-rag/
│   ├── content-management-system/
│   ├── competitive-intelligence-platform/
│   └── corrective-video-rag/
├── multimodal-apps/
│   ├── gemini-video-analyzer/
│   ├── gemini-veo-sketch2video/
│   ├── multi-modal-chatbot/
│   ├── hedra-live-avatars-demo/
│   └── talk-to-ai-girlfriend/
├── Roadmap.md
└── README.md
```

---

## 🗺️ ROADMAP

| Status | Milestone | ETA |
|--------|-----------|-----|
| ✅ Done | 22 apps across 5 categories | May 2026 |
| ✅ Done | Daily releases cadence started | Q1 2026 |
| 🔄 In progress | 50 apps total | Jun 2026 |
| 📋 Planned | Voice AI agent category | Jun 2026 |
| 📋 Planned | Computer use agent category | Jul 2026 |
| 📋 Planned | Code generation agent category | Jul 2026 |
| 📋 Planned | 75 apps total | Aug 2026 |
| 💡 Goal | 100+ apps by end 2025 | Q4 2026 |
| 💡 Goal | Enterprise solutions category | Q4 2026 |
| 💡 Goal | Community submission pipeline | Q1 2027 |

---

## ☠️ STARTUPS / BUSINESSES

What this collection helps you build vs buy:

| SaaS Product | Price/mo | App in This Repo | Build Time |
|-------------|----------|-----------------|-----------|
| Brand24 (brand monitoring) | $99 | brand-video-monitor | 2 hours |
| Competitive intelligence tools | $200 | competitive-intelligence-platform | 4 hours |
| Content repurposing SaaS | $79 | blog-video-writer | 3 hours |
| AI customer support | $300 | claude-3-conversation-agent | 1 hour |
| AI voice assistant | $200 | elevenlabs-voice-assistant | 2 hours |
| Custom RAG knowledge base | $500 | contextual-video-rag | 6 hours |
| **Total monthly saving** | **~$1,378/mo** | | |

---

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=hmzainjamil/awesome-ai-apps&type=Date)](https://star-history.com/#hmzainjamil/awesome-ai-apps&Date)

---

Built by [HMZ](https://github.com/hmzainjamil)

---

## 📋 FULL APP CATALOG

### 🎯 Starter Agents (8 apps)

| App | Model | Key Tech | Use Case |
|-----|-------|---------|---------|
| AI21 Studio Chat | Jurassic-2 | AI21 SDK | Evaluate AI21 models |
| Voice-Enabled Chatbot | GPT-4o | ElevenLabs TTS | Voice UX |
| Claude 4 Conversation Agent | Claude Sonnet | Anthropic SDK | Multi-turn chat |
| Google PaLM Chat | PaLM 2 | Google AI SDK | Google model eval |
| Local Llama Chat | Llama 3 | Ollama | Privacy-first, offline |
| OpenAI Chat Assistant | GPT-4o | OpenAI SDK | General assistant |
| Claude Code Reviewer | Claude Sonnet 4 | Anthropic + AST | Automated code review |
| Streaming Response Chatbot | Together AI | Server-sent events | Real-time streaming UX |

### 🧠 Advanced Agents (3 apps)

| App | Model | Pipeline | Output |
|-----|-------|---------|--------|
| Brand Video Monitor | Gemini 2.0 Flash | Video → analyze → alert | Brand mention reports |
| Blog Video Writer | Gemini + multi-agent | Video → transcript → blog | Published blog posts |
| [Coming soon] | — | — | — |

### 👥 Multi-Agent Teams (2 apps)

| App | Agents | Framework | Task |
|-----|--------|-----------|------|
| Content Creation Team | Researcher + Writer + Editor | CrewAI | Full content workflow |
| [Coming soon] | — | — | — |

### 📚 RAG Applications (4 apps)

| App | Retrieval | Embedding | Storage |
|-----|-----------|----------|---------|
| Contextual Video RAG | Semantic + rerank | Gemini | ChromaDB |
| Content Management System | Full-text + semantic | Gemini | ChromaDB |
| Competitive Intelligence | Web + vector | Gemini | FAISS |
| Corrective Video RAG | 3-tier evaluation | Gemini | ChromaDB |

### 🎨 Multimodal Apps (5 apps)

| App | Modalities | Model | Output |
|-----|-----------|-------|--------|
| Gemini Video Analyzer | Video → text | Gemini 2.0 Pro | Analysis report |
| Sketch-to-Video | Image → video | Gemini + Veo | MP4 animation |
| Multi-Modal Chatbot | Text + image + video | Gemini | Chat response |
| Hedra Live Avatars | Text → video avatar | Hedra API | Live avatar video |
| AI Girlfriend | Text + voice + avatar | GPT-4o + Hedra | Interactive companion |

---

## 🤝 CONTRIBUTING

```bash
# Fork → add your app → PR

# App requirements:
# 1. Working main.py (tested)
# 2. requirements.txt with pinned versions
# 3. .env.example with all required vars
# 4. App-level README.md with setup + usage
# 5. No hardcoded API keys

# Directory naming: kebab-case
# Example: advanced-agents/my-research-agent/
```

Apps reviewed on: code quality, novelty, documentation, security (no key leaks).

---

## 📈 COLLECTION GROWTH

| Date | Apps | Categories |
|------|------|-----------|
| Jan 2026 | 5 | 2 |
| Feb 2026 | 12 | 4 |
| Mar 2026 | 18 | 5 |
| Apr 2026 | 22 | 5 |
| May 2026 | 22+ | 5 |
| Target Q4 2026 | 100+ | 7+ |


---

## 🗂️ REPO STRUCTURE

```
awesome-ai-apps/
├── starter-agents/
│   ├── ai21-studio-chat/
│   │   ├── README.md
│   │   ├── main.py
│   │   ├── requirements.txt
│   │   └── .env.example
│   └── ...
├── advanced-agents/
├── multi-agent-teams/
├── rag-applications/
├── multimodal-apps/
├── Roadmap.md
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

---

## 📜 CHANGELOG

| Date | Update |
|------|--------|
| May 2026 | 22 apps, 5 categories, daily release cadence started |
| Apr 2026 | RAG category added (4 apps) |
| Mar 2026 | Multi-agent team category added |
| Feb 2026 | Advanced agents + multimodal added |
| Jan 2026 | Initial release — 5 starter agents |

---

## 🙏 ACKNOWLEDGMENTS

| Project | Contribution |
|---------|-------------|
| OpenAI | GPT models + tools API |
| Anthropic | Claude models + vision |
| Google | Gemini 2.0 Flash/Pro + Veo |
| Meta | Llama 3 family (local models) |
| LangChain | Agent framework patterns |
| CrewAI | Multi-agent orchestration |
| Agno | Lightweight agent framework |
| ElevenLabs | Voice synthesis |
| Hedra | Live avatar generation |
| Awesome LLM Apps | Inspiration |

---

## ⭐ STAR THIS REPO

Every star helps more developers discover production AI app patterns.
Watch for updates — new apps added daily through 2026.
Open Issues to suggest new apps or report problems.
