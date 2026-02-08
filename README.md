# Awesome Vibe Computing [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of tools, protocols, agents, and infrastructure for vibe computing — where humans describe intent and AI systems do the rest.

**Vibe coding** is writing apps by talking to an AI. **Vibe computing** is the bigger picture — autonomous agents managing your systems, physical hardware responding to AI decisions, your home and health data flowing into intelligent systems, and automation that runs while you sleep.

This isn't another list of IDEs and coding tools. This is the infrastructure for a life where AI is ambient.

---

## Contents

- [The Big Picture](#the-big-picture)
- [Models — What to Use and When](#models--what-to-use-and-when)
- [Autonomous Agents](#autonomous-agents)
- [CLI Agents](#cli-agents)
- [Agent Frameworks & Orchestration](#agent-frameworks--orchestration)
- [MCP Protocol & Ecosystem](#mcp-protocol--ecosystem)
- [Platforms — Where Agents Run](#platforms--where-agents-run)
- [Voice Interfaces](#voice-interfaces)
- [Life Integrations](#life-integrations)
- [Hardware & Devices](#hardware--devices)
- [The Hard Problems](#the-hard-problems)
- [Resilience & Scaffolding](#resilience--scaffolding)
- [Workflow Automation](#workflow-automation)
- [AI APIs & Gateways](#ai-apis--gateways)
- [Security & Sandboxing](#security--sandboxing)
- [Community & Learning](#community--learning)
- [The Foundational Texts](#the-foundational-texts)

---

## The Big Picture

Vibe computing is what happens when AI stops being a tool you use and becomes infrastructure that runs your life. This list covers the full stack:

```
┌─────────────────────────────────────────────────────────────┐
│                     YOUR INTENT                              │
│            (voice, text, presence, biometrics)               │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                    AGENT LAYER                               │
│     (Claude, GPT, Gemini, local models, orchestration)       │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                  INTEGRATION LAYER                           │
│        (MCP, APIs, webhooks, bridges, protocols)             │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                   PHYSICAL LAYER                             │
│    (home, health, devices, messengers, calendars, email)     │
└─────────────────────────────────────────────────────────────┘
```

The goal: describe what you want. The system figures out how to make it happen.

---

## Models — What to Use and When

*Not all LLMs are equal. Here's what actually works for agentic use cases.*

### For Coding & Tool Use

| Model | Provider | Context | Best For |
|-------|----------|---------|----------|
| Claude Sonnet 4 | Anthropic | 200K | Real-time agentic work, computer use, tool calling |
| Claude Opus 4 | Anthropic | 200K | Complex reasoning, extended thinking |
| GPT-4o | OpenAI | 128K | Strong all-rounder, fast, reliable |
| DeepSeek V3 | DeepSeek | 64K | Open weights, competitive quality, much cheaper |
| Codestral | Mistral | 32K | Purpose-built for code, fast |

### For Long Context

| Model | Context Window | Notes |
|-------|----------------|-------|
| Gemini 2.0 Pro | 1M+ | Can ingest entire codebases |
| Claude 3.5 | 200K | Strong retrieval over full context |
| GPT-4 Turbo | 128K | Good for large documents |

### For Local/Private

- **Llama 3.3 70B** - Best open model at scale
- **Qwen 2.5** - Strong multilingual, good coding
- **Mistral 7B/22B** - Fast, efficient, runs on consumer hardware
- **DeepSeek V3** - Excellent reasoning, runs on consumer GPUs

### Model Selection Heuristic

```
Need speed + low cost?    → Claude Haiku, GPT-4o-mini, Gemini Flash
Need accuracy + tools?    → Claude Sonnet, GPT-4o
Need deep reasoning?      → Claude Opus, o1/o3
Need privacy?             → Llama, Mistral, Qwen (local)
Need huge context?        → Gemini Pro
```

---

## Autonomous Agents

*AI that actually does things. Persistent, agentic, running on your hardware or in the cloud.*

- [OpenClaw](https://github.com/openclaw/openclaw) - Open-source personal AI agent. Runs locally, connects to WhatsApp/Telegram/Slack/Discord/Signal/iMessage, persistent memory, 100+ AgentSkills. The reference implementation for what vibe computing looks like.
- [Lindy](https://lindy.ai) - AI executive assistant. Calendar, email, docs. Talk to it like a teammate.
- [Devin](https://cognition.ai) - Autonomous AI software engineer. Takes tickets, writes code, submits PRs.
- [SWE-agent](https://github.com/princeton-nlp/SWE-agent) - Autonomous agent that resolves real GitHub issues end-to-end.
- [Manus](https://manus.im) - General-purpose agent. Browses, codes, executes multi-step tasks.

---

## CLI Agents

*AI that lives in your terminal.*

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) - Anthropic's agentic CLI. The gold standard for terminal-based coding agents.
- [Gemini CLI](https://github.com/google-gemini/gemini-cli) - Google's terminal agent with 1M+ context and built-in search grounding.
- [aider](https://github.com/paul-gauthier/aider) - AI pair programming in your terminal. Works with any LLM.
- [opencode](https://github.com/opencode-ai/opencode) - AI coding agent built for the terminal.
- [Warp](https://warp.dev) - AI-native terminal with command suggestions and modern UX.

---

## Agent Frameworks & Orchestration

*Frameworks for building and orchestrating AI agents.*

- [LangGraph](https://langchain-ai.github.io/langgraph/) - Stateful, multi-agent workflows with cycles and persistence. Built-in checkpointing for durable execution.
- [CrewAI](https://crewai.com) - Role-based autonomous agent teams.
- [AutoGen](https://github.com/microsoft/autogen) - Microsoft's multi-agent conversation framework.
- [Mastra](https://mastra.ai) - TypeScript-first agent framework.
- [Pydantic AI](https://ai.pydantic.dev) - Type-safe, model-agnostic agent framework.

---

## MCP Protocol & Ecosystem

*Model Context Protocol — connecting AI to everything.*

### Core

- [MCP Specification](https://modelcontextprotocol.io) - The official protocol spec from Anthropic.
- [MCP TypeScript SDK](https://github.com/modelcontextprotocol/typescript-sdk) - Build MCP servers in TypeScript.
- [MCP Python SDK](https://github.com/modelcontextprotocol/python-sdk) - Build MCP servers in Python.

### Directories

- [mcpservers.org](https://mcpservers.org) - Awesome MCP Servers — curated community directory.
- [mcp-awesome.com](https://mcp-awesome.com) - 1,200+ quality-verified MCP servers.

### Key Servers

- [Filesystem MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem) - Secure file access.
- [GitHub MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/github) - Repos, issues, PRs.
- [Slack MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/slack) - Channel messaging.
- [Notion MCP](https://github.com/notionhq/notion-mcp-server) - Pages and databases.
- [Desktop Commander](https://github.com/wonderwhy-er/DesktopCommanderMCP) - Full terminal access and process management.

---

## Platforms — Where Agents Run

*Your options are completely different depending on what you're running on.*

### macOS

The most common platform for vibe computing. Native terminal, strong CLI ecosystem, Apple Silicon for local inference.

- **Local inference**: Ollama runs great on M-series chips. MLX for Apple-optimized models.
- **Advantages**: Unix-like, strong developer tooling, Continuity features.
- **Tools**: Terminal.app, iTerm2, Homebrew ecosystem.

### Linux & Servers

The production choice. Headless agents, VMs, containers.

- **Distros**: Ubuntu Server, Debian for stability. Proxmox for virtualization.
- **Local inference**: Full CUDA support for NVIDIA GPUs. vLLM for high-throughput serving.
- **Advantages**: Most flexible, best for production, full control.

### Windows

Possible but more friction.

- **WSL2**: Run Linux environments inside Windows. Most tools work via WSL.
- **Recommendation**: Develop entirely inside WSL.

### Mobile

Control surfaces, not compute.

- **iOS**: Shortcuts for automation. SSH apps (Termius, Blink) to reach your agents.
- **Android**: Tasker for automation. Termux for a Linux environment on-device.
- **Key insight**: Your phone is how you *reach* your agents, not where they run.

### Virtualization

- **Proxmox** - Free, powerful hypervisor. LXC for lightweight isolation, full VMs for GPU passthrough.
- **Docker** - Containerize agent workloads. Easy to snapshot and restore.

---

## Voice Interfaces

*Talk to your AI systems.*

### Text-to-Speech

| Service | Type | Best For |
|---------|------|----------|
| [ElevenLabs](https://elevenlabs.io) | Cloud | Industry leader. Voice cloning, emotional range, streaming. |
| [Cartesia Sonic](https://cartesia.ai) | Cloud | First streaming TTS with natural laughter/emotion. |
| [OpenAI TTS](https://platform.openai.com) | Cloud | Simple, fast, affordable. |
| [Coqui TTS](https://github.com/coqui-ai/TTS) | Local | Best open-source. 16 languages, voice cloning. |
| [Piper](https://github.com/rhasspy/piper) | Local | Fast, lightweight. Great for home automation. |

### Speech-to-Text

| Service | Type | Best For |
|---------|------|----------|
| [Deepgram Nova-3](https://deepgram.com) | Cloud | Best accuracy + speed. Sub-300ms latency. |
| [Deepgram Flux](https://deepgram.com) | Cloud | Built for conversation. Turn detection for voice agents. |
| [AssemblyAI](https://assemblyai.com) | Cloud | Audio intelligence — summarization, sentiment. |
| [Whisper](https://github.com/openai/whisper) | Local | The gold standard open-source STT. |
| [faster-whisper](https://github.com/SYSTRAN/faster-whisper) | Local | 4x faster than original Whisper. |
| [whisper.cpp](https://github.com/ggerganov/whisper.cpp) | Local | Runs on phones, Raspberry Pi. |

### Voice Agent Frameworks

- [LiveKit Agents](https://github.com/livekit/agents) - Complete framework for realtime voice AI. Semantic turn detection, telephony, MCP support, open-source.
- [Vapi](https://vapi.ai) - Managed voice AI platform. Handles orchestration, interruption handling, telephony.
- [OpenAI Realtime API](https://platform.openai.com) - Native audio in/out. True voice-to-voice.
- [SuperWhisper](https://superwhisper.com) - macOS voice-to-text. What Karpathy used when coining "vibe coding."

---

## Life Integrations

*The glue between AI and your daily life.*

### Messengers

| Platform | API | Difficulty | Notes |
|----------|-----|------------|-------|
| **Telegram** | ✅ Official | Easy | Best-in-class. Full bot API, streaming support. |
| **Discord** | ✅ Official | Easy | Full API. Bots, webhooks, real-time gateway. |
| **Slack** | ✅ Official | Medium | Bolt framework. Socket Mode for dev. |
| **WhatsApp** | ⚠️ Business | Hard | Requires Meta verification. Or use Baileys (risky). |
| **Signal** | ❌ Unofficial | Hard | signal-cli exists but fragile. |
| **iMessage** | ❌ None | Very Hard | Requires Mac running 24/7. BlueBubbles or AppleScript. |

### Calendar

- **Google Calendar API** - Full CRUD, push notifications, free/busy lookup.
- **Microsoft Graph API** - Outlook/365. Also handles Teams meetings.
- **CalDAV** - Universal protocol. Works with Fastmail, Nextcloud, iCloud.

### Email

- **Gmail API** - Full access, Pub/Sub for real-time notifications.
- **IMAP/SMTP** - Universal. Works with any provider.
- **Transactional**: Resend, Postmark, SendGrid for reliable sending.

### Notes & Tasks

- [Notion API](https://developers.notion.com) - Pages, databases, blocks. Good but rate-limited.
- [Todoist API](https://developer.todoist.com) - Simple REST, natural language dates.
- [Linear API](https://developers.linear.app) - GraphQL, real-time subscriptions.
- **Obsidian** - Local markdown files. No API needed — just read/write the files.

---

## Hardware & Devices

*The physical layer.*

### Computing Hardware

- **Apple Silicon Macs** - Great for local inference, native development.
- **Linux workstations** - AMD/Intel + NVIDIA GPU for serious local inference.
- **Home servers** - Always-on agents. Old PCs, NUCs, mini PCs.
- **Cloud VMs** - DigitalOcean, Hetzner, Vultr for cheap always-on compute.

### Wearables & Health

| Device | API | Data Available |
|--------|-----|----------------|
| [Oura Ring](https://cloud.ouraring.com/v2/docs) | ✅ REST | Sleep, readiness, HRV, activity |
| [WHOOP](https://developer.whoop.com) | ✅ REST | Strain, recovery, sleep |
| [Garmin](https://developer.garmin.com) | ✅ REST | Comprehensive fitness data |
| Apple Watch | ⚠️ HealthKit | Requires native app to access |
| [Fitbit](https://dev.fitbit.com) | ✅ REST | Heart rate, sleep, activity |

**Platform aggregators:**
- **Apple HealthKit** - iOS health data hub. Many apps sync here.
- **Google Health Connect** - Android unified health API.

### Home Automation

- [Home Assistant](https://home-assistant.io) - The hub. Open-source, local-first, 2000+ integrations.
- **Home Assistant Assist** - Native voice assistant with LLM personality support.
- **Wyoming Protocol** - Standard for local voice (Whisper + Piper).
- **ESPresense** - Room-level presence via BLE beacons.
- **Matter/Thread** - Cross-platform device standards.

**Key sensors for AI context:**
- Motion/presence → triggers, occupancy
- Temperature/humidity → comfort context
- Power monitoring → appliance state inference
- Door/window → security state

### Cross-Device Access

| Tool | Platforms | Best For |
|------|-----------|----------|
| [Termius](https://termius.com) | All | Cross-platform sync, encrypted vault |
| [Blink Shell](https://blink.sh) | iOS | Power users. Mosh support. |
| [iTerm2](https://iterm2.com) | macOS | The macOS power terminal |
| [Tailscale](https://tailscale.com) | All | Mesh VPN. Reach your network from anywhere. |
| [Mosh](https://mosh.org) | All | SSH that survives network changes |

**Best pattern**: iPad + Blink Shell + Mosh + tmux = full development from anywhere.

---

## The Hard Problems

*The stuff that actually stops people.*

### Context Limits

Every model has a context window. When you hit it, the model forgets.

**Mitigations:**
- **Summarization** - Compress old context into summaries.
- **RAG** - Store externally, retrieve relevant chunks.
- **Prompt caching** - Anthropic/OpenAI cache static prompts, 90% cost reduction.

**Reality**: There's no perfect solution. Plan for context loss.

### Memory & Persistence

AI wakes up fresh every session. Making it "remember" is the core challenge.

**Approaches:**
- **File-based** - MEMORY.md, daily logs. Simple, works, manual.
- **Vector stores** - Embed memories, retrieve semantically. (Chroma, Pinecone)
- [Mem0](https://mem0.ai) - Purpose-built memory layer for AI agents.
- [Letta](https://letta.com) - Agents with self-editing persistent memory.
- **Git for state** - Version control your agent's memory files.

### Multi-Agent Coordination

Multiple agents working together. Harder than it sounds.

**Challenges:**
- Agents can conflict, duplicate work, or loop.
- Handoffs lose context.
- Error propagation across agents.

**Frameworks:** LangGraph (best checkpointing), CrewAI (role-based), AutoGen (conversational).

---

## Resilience & Scaffolding

*Without this, everything crashes and burns.*

### Backups & Version Control

**Git everything.** Your agent's workspace, memory files, configs.

```bash
git add -A && git commit -m "checkpoint: $(date +%Y-%m-%d-%H%M)"
```

**Backup tools:**
- [Restic](https://github.com/restic/restic) - Incremental, encrypted, deduped backups.
- [Syncthing](https://syncthing.net) - Real-time sync across machines.

### Logging & Observability

| Tool | Self-host | Best For |
|------|-----------|----------|
| [LangSmith](https://smith.langchain.com) | No | LangChain users, deep debugging |
| [Langfuse](https://langfuse.com) | Yes | Privacy-conscious, full control |
| [Helicone](https://helicone.ai) | Yes | Gateway approach, cost tracking |

**Track:** Token usage, cost per session, latency, error rates.

### Recovery Patterns

- **Checkpointing** - LangGraph saves state at each step.
- **Idempotent operations** - Safe to retry.
- **Heartbeat + watchdog** - Auto-restart stale agents.
- **Graceful degradation** - Fall back when services fail.

---

## Workflow Automation

*Platforms for connecting services and automating processes.*

- [n8n](https://n8n.io) - Open-source, self-hostable. Native LangChain, MCP support.
- [Zapier](https://zapier.com) - 8,000+ integrations. The most connected platform.
- [Make](https://make.com) - Visual workflow builder.
- [Pipedream](https://pipedream.com) - Developer-first, code-level control.
- [Node-RED](https://nodered.org) - Flow-based automation. Runs on anything.

---

## AI APIs & Gateways

### Providers

- [Anthropic](https://anthropic.com) - Claude models.
- [OpenAI](https://openai.com) - GPT, o1/o3 reasoning models.
- [Google](https://ai.google.dev) - Gemini models.
- [DeepSeek](https://deepseek.com) - High-performance, low-cost.
- [Mistral](https://mistral.ai) - European AI, Codestral.

### Gateways & Routers

- [LiteLLM](https://github.com/BerriAI/litellm) - Unified API for 100+ LLMs.
- [OpenRouter](https://openrouter.ai) - Route to multiple providers.
- [Portkey](https://portkey.ai) - Gateway with fallbacks, caching, observability.

### Local Inference

- [Ollama](https://ollama.com) - Run LLMs locally. Simple.
- [LM Studio](https://lmstudio.ai) - GUI for local models.
- [vLLM](https://github.com/vllm-project/vllm) - High-throughput serving.
- [llama.cpp](https://github.com/ggerganov/llama.cpp) - Run models on CPU.
- [MLX](https://github.com/ml-explore/mlx) - Apple Silicon optimized.

---

## Security & Sandboxing

*Running autonomous agents safely.*

- [E2B](https://e2b.dev) - Cloud sandboxes for AI agents.
- [Docker](https://docker.com) - Containerize agent workloads.
- [Firecracker](https://firecracker-microvm.github.io) - Lightweight microVMs.
- **Principle**: Agents should have minimum necessary access.

---

## Community & Learning

- [MCP Community](https://modelcontextprotocol.io) - Official MCP docs and community.
- [LangChain Discord](https://discord.gg/langchain) - Large ecosystem community.
- [GitHub Topics: vibe-coding](https://github.com/topics/vibe-coding) - 1,800+ repos tagged.

---

## The Foundational Texts

- [Andrej Karpathy — "Vibe Coding"](https://x.com/karpathy/status/1886192184808149383) - The tweet that coined the term (February 2025).
- [Simon Willison — "Not All AI-Assisted Programming is Vibe Coding"](https://simonwillison.net/2025/Mar/19/vibe-coding/) - The important distinctions.
- [MCP Announcement](https://www.anthropic.com/news/model-context-protocol) - Anthropic's introduction of MCP.
- [Vibe Coding — Wikipedia](https://en.wikipedia.org/wiki/Vibe_coding) - Collins Dictionary Word of the Year 2025.

---

## Contributing

Contributions welcome! Please read the [contributing guidelines](CONTRIBUTING.md) before submitting a PR.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)
