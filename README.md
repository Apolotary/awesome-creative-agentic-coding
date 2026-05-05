# Awesome Creative Agentic Coding [![Awesome](https://awesome.re/badge-flat.svg)](https://github.com/sindresorhus/awesome)

> A curated list of resources at the intersection of agentic AI and creative coding for media art.

**Creative agentic coding** is what happens when an autonomous agent — an LLM in a loop, with tools, memory, and the ability to act — becomes part of a creative-coding pipeline. It is distinct from "AI for art" (text-to-image, model-only) and from pure creative coding (code-only). The agent is in the loop: picking parameters, chaining tools, judging its own output, and sometimes performing live.

A canonical example that motivated this list: [blob-tracker](https://github.com/Apolotary/blob-tracker) — a Hermes Agent skill that runs audio-reactive blob tracking on video, with Kimi (Moonshot) choosing the visual algorithm and composing matching music.

Please read the [contribution guidelines](contributing.md) before contributing.

## Contents

- [Coding Agents (Harnesses)](#coding-agents-harnesses)
- [Agent Frameworks & SDKs](#agent-frameworks--sdks)
- [Skills, Patterns & Cookbooks](#skills-patterns--cookbooks)
- [MCP Servers for Creative Work](#mcp-servers-for-creative-work)
  - [Image, Video, Audio Generation](#image-video-audio-generation)
  - [3D & Game Engines](#3d--game-engines)
  - [Live Visuals & Compositing](#live-visuals--compositing)
  - [Music & Live Coding](#music--live-coding)
  - [Computer Vision](#computer-vision)
  - [Design & Drawing](#design--drawing)
- [Multi-Agent Creative Pipelines](#multi-agent-creative-pipelines)
- [Notable Projects, Demos & Installations](#notable-projects-demos--installations)
- [Creative Coding Substrates](#creative-coding-substrates)
- [Articles](#articles)
- [Talks](#talks)
- [Papers](#papers)
- [Books](#books)
- [Podcasts & Newsletters](#podcasts--newsletters)
- [Communities](#communities)
- [Workshops & Education](#workshops--education)
- [Related Lists](#related-lists)
- [Contributing](#contributing)
- [License](#license)

## Coding Agents (Harnesses)

The harnesses through which artists and creative coders most often drive everything else on this list.

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) — Anthropic's terminal-native agentic coding tool; Skills + MCP make it the most common substrate for creative agentic pipelines.
- [Hermes Agent](https://github.com/NousResearch/hermes-agent) — Nous Research's "agent that grows with you"; ships with creative skills (`p5js`, `comfyui`, `touchdesigner-mcp`, `manim-video`, `ascii-video`, `pixel-art`) and is the harness behind [blob-tracker](https://github.com/Apolotary/blob-tracker).
- [Cursor](https://www.cursor.com/) — Agentic IDE; the canonical pairing for human-AI generative-art labs (e.g., Cursor + p5.js workshops).
- [OpenAI Codex](https://github.com/openai/codex) — Lightweight terminal coding agent from OpenAI.
- [Gemini CLI](https://github.com/google-gemini/gemini-cli) — Google's open-source Gemini agent for the terminal.
- [Kimi CLI](https://github.com/MoonshotAI/kimi-cli) — Moonshot AI's official CLI agent; pairs naturally with Hermes for cheap, fast creative loops.
- [opencode](https://github.com/anomalyco/opencode) — Open-source coding agent.
- [Aider](https://github.com/Aider-AI/aider) — Open-source AI pair programmer in your terminal; model-agnostic.
- [Cline](https://github.com/cline/cline) — Autonomous coding agent inside VS Code with Plan/Act modes and MCP support.
- [Roo Code](https://github.com/RooCodeInc/Roo-Code) — "Whole dev team of AI agents" inside your editor.
- [Claudine](https://github.com/xemantic/claudine) — Kotlin pre-Claude-Code harness; useful for learning *how* a creative-coding agent works underneath.

## Agent Frameworks & SDKs

For when the harness above is not enough and you want to build your own creative agent loop.

- [Claude Agent SDK — Python](https://github.com/anthropics/claude-agent-sdk-python) — Build Claude-Code-style agents (tool use, file access, exec) in Python.
- [Claude Agent SDK — TypeScript](https://github.com/anthropics/claude-agent-sdk-typescript) — Same, for JS/TS.
- [LangGraph](https://github.com/langchain-ai/langgraph) — Stateful, long-running agent graphs; useful when a creative pipeline has memory, branches, or human-in-the-loop checkpoints.
- [CrewAI](https://github.com/crewAIInc/crewAI) — Role-based multi-agent orchestration ("art director / generator / critic" maps cleanly).
- [Microsoft AutoGen](https://github.com/microsoft/autogen) — Multi-agent conversational framework with strong human-in-the-loop primitives.
- [OpenAI Agents SDK](https://github.com/openai/openai-agents-python) — Lightweight successor to Swarm, with first-class Realtime/voice handoffs for live installations.
- [Mastra](https://github.com/mastra-ai/mastra) — TypeScript framework for AI agents and workflows; native MCP authoring.
- [Pydantic AI](https://github.com/pydantic/pydantic-ai) — Type-safe structured outputs; convenient when an agent must emit validated parameters for shaders, DAWs, or render configs.
- [DSPy](https://github.com/stanfordnlp/dspy) — Stanford's *programming* (not prompting) framework with optimisable modules; tune creative pipelines as compiled programs.
- [Letta](https://github.com/letta-ai/letta) — Stateful agents with long-term memory; for collaborator-agents that remember a project across sessions.
- [smolagents](https://github.com/huggingface/smolagents) — HuggingFace "agents that think in code" — pairs naturally with Processing / p5 / Blender Python APIs.
- [Pipecat](https://github.com/pipecat-ai/pipecat) — Real-time voice and multimodal agents over WebRTC; useful for interactive sound installations.
- [LiveKit Agents](https://github.com/livekit/agents) — Real-time voice/video agents that "see, hear, and understand" — telematic performance, multi-user installations.
- [Vercel AI SDK](https://github.com/vercel/ai) — Provider-agnostic TS toolkit with `ToolLoopAgent`; common choice for browser-based creative tools.
- [Inngest AgentKit](https://github.com/inngest/agent-kit) — Multi-agent networks with deterministic routing.
- [mcp-agent](https://github.com/lastmile-ai/mcp-agent) — Compose agents from the MCP servers below using the *Building Effective Agents* patterns.

## Skills, Patterns & Cookbooks

The format that powers most creative agentic coding today: small, declarative bundles of instructions, scripts, and resources an agent loads on demand.

- [agentskills.io](https://agentskills.io/) — The open spec for portable agent skills.
- [anthropics/skills](https://github.com/anthropics/skills) — Anthropic's official Skills repo. Creative ones inside: [`algorithmic-art`](https://github.com/anthropics/skills/tree/main/skills/algorithmic-art) (p5.js with seeded randomness, flow fields, particle systems), [`canvas-design`](https://github.com/anthropics/skills/tree/main/skills/canvas-design), [`web-artifacts-builder`](https://github.com/anthropics/skills/tree/main/skills/web-artifacts-builder), [`theme-factory`](https://github.com/anthropics/skills/tree/main/skills/theme-factory), [`slack-gif-creator`](https://github.com/anthropics/skills/tree/main/skills/slack-gif-creator).
- [black-forest-labs/skills](https://github.com/black-forest-labs/skills) — Official FLUX prompting + API skills following the agentskills.io spec; first-party from a generative-image model maker.
- [anthropics/claude-cookbooks](https://github.com/anthropics/claude-cookbooks) — Reference implementations of orchestrator-workers, evaluator-optimizer, and other patterns from *Building Effective Agents*.
- [tlehman/litprog-skill](https://github.com/tlehman/litprog-skill) — Cross-harness literate-programming skill (Claude Code / opencode / Hermes); a clean pattern for documented creative-code notebooks.

## MCP Servers for Creative Work

Model Context Protocol gives agents tools. These let an agent control the actual creative software.

### Image, Video, Audio Generation

- [Replicate MCP](https://replicate.com/docs/reference/mcp) — Official MCP for Replicate's hosted-models API (image, video, audio, ML).
- [PiAPI MCP](https://github.com/apinetwork/piapi-mcp-server) — One-stop MCP for Midjourney, Flux, Kling, Luma, Udio, Chirp, Trellis.
- [Nano Banana MCP](https://github.com/ConechoAI/Nano-Banana-MCP) — Server for Google Gemini 2.5 Flash Image generation/editing.
- [Stability AI MCP](https://github.com/tadasant/mcp-server-stability-ai) — Stability generate / edit / upscale.
- [ElevenLabs MCP](https://github.com/elevenlabs/elevenlabs-mcp) — Official ElevenLabs TTS, voice cloning, transcription, conversational AI.
- [Runway API MCP](https://github.com/runwayml/runway-api-mcp-server) — Official Runway text-to-image, image-to-video, upscaling.
- [Suno MCP](https://github.com/AceDataCloud/SunoMCP) — Suno music + lyrics + cover workflows.
- [ComfyUI Cloud MCP](https://github.com/Comfy-Org/comfy-cloud-mcp) — Official ComfyUI Cloud MCP for workflow execution.
- [ComfyUI MCP (local)](https://github.com/joenorton/comfyui-mcp-server) — Lightweight Python MCP for a local ComfyUI instance.
- [FFmpeg / Video-Audio MCP](https://github.com/misbahsy/video-audio-mcp) — FFmpeg-powered trimming, transitions, overlays.

### 3D & Game Engines

- [Blender MCP — ahujasid](https://github.com/ahujasid/blender-mcp) — The de-facto Blender MCP. Two-way Claude/Blender bridge: objects, materials, scene inspection, Python eval.
- [meshgen](https://github.com/huggingface/meshgen) — Hugging Face addon for using AI agents directly inside Blender.
- [Blender MCP — Common Sense Machines](https://github.com/CommonSenseMachines/blender-mcp) — Text-to-4D-worlds variant.
- [Houdini MCP](https://github.com/healkeiser/fxhoudinimcp) — Comprehensive SideFX Houdini MCP (168 tools, 19 categories).
- [Unity MCP — CoplayDev](https://github.com/CoplayDev/unity-mcp) — Unity Editor bridge for AI assistants; assets, scenes, scripts, automation.
- [Unity MCP — IvanMurzak](https://github.com/IvanMurzak/Unity-MCP) — Develop+test loop; any C# method becomes a tool with one line.
- [Unreal MCP](https://github.com/chongdashu/unreal-mcp) — Unreal Engine over natural language for Cursor / Claude Desktop / Windsurf.

### Live Visuals & Compositing

- [TouchDesigner MCP — 8beeeaaat](https://github.com/8beeeaaat/touchdesigner-mcp) — Agents create/connect operators, run Python live in TD.
- [TouchDesigner MCP — satoruhiga](https://github.com/satoruhiga/claude-touchdesigner) — Claude Code plugin for TouchDesigner from Satoru Higa (Rhizomatiks-affiliated).
- [After Effects MCP](https://github.com/Dakkshin/after-effects-mcp) — Drives AE via ExtendScript: comps, text, shapes, properties.
- [OBS MCP](https://github.com/royshil/obs-mcp) — OBS scenes, sources, recording, streaming — useful for AI-directed live streams.

### Music & Live Coding

- [Ableton MCP — ahujasid](https://github.com/ahujasid/ableton-mcp) — Reference Ableton Live MCP; tracks, clips, MIDI, devices via natural language.
- [REAPER MCP](https://github.com/bonfire-audio/reaper-mcp) — Comprehensive REAPER MCP for fully mixed/mastered tracks via agent calls.
- [SuperCollider MCP](https://github.com/Tok/SuperColliderMCP) — MCP over OSC; agents write and evaluate synthesis code live.
- [Sonic Pi MCP](https://github.com/abhishekjairath/sonic-pi-mcp) — Natural language to Sonic Pi over OSC.
- [Strudel MCP — live-coding-music-mcp](https://github.com/williamzujkowski/live-coding-music-mcp) — Direct Claude control of Strudel.cc with audio analysis.
- [Strudel — strands-strudel](https://github.com/cagataycali/strands-strudel) — Real-time Strudel pattern generation via Strands Agents + WebSocket playback.
- [Strudel — apfelstrudel](https://github.com/rcarmo/apfelstrudel) — Strudel environment with embedded AI chat partner.
- [Strudel — param-strudels](https://github.com/Paramstr/param-strudels) — Autonomous AI agent that reads, writes, and evaluates Strudel in a browser IDE.
- [MIDI MCP](https://github.com/tubone24/midi-mcp-server) — Generate MIDI from text-based music data via any agent.
- [music21 MCP](https://github.com/brightlikethelight/music21-mcp-server) — Symbolic music analysis and generation via FastMCP.

### Computer Vision

- [mcp-vision](https://github.com/groundlight/mcp-vision) — HuggingFace CV models (e.g., zero-shot detection) as agent tools.
- [OpenCV MCP](https://github.com/GongRzhe/opencv-mcp-server) — Image/video processing (filters, edges, face/object detect, tracking).
- [YOLO MCP](https://github.com/GongRzhe/YOLO-MCP-Server) — YOLO detection, segmentation, classification, pose.

### Design & Drawing

- [Cursor Talk to Figma](https://github.com/grab/cursor-talk-to-figma-mcp) — MCP between agentic IDEs and Figma; read & modify designs programmatically.
- [tldraw — make-real](https://github.com/tldraw/make-real) — "Draw a UI, make it real" reference repo and agent starter kit.
- [p5.js AI Editor + MCP](https://github.com/adilmoujahid/p5js-ai-editor) — Web-based p5.js IDE controlled entirely through Claude via 13-tool MCP server.

## Multi-Agent Creative Pipelines

Where the agentic part *is* the artwork.

- [microsoft/muzic — MusicAgent](https://github.com/microsoft/muzic) — LLM-driven autonomous agent orchestrating HuggingFace + GitHub + Web-API music tools.
- [magenta-realtime](https://github.com/magenta/magenta-realtime) — Open-weights live-music model from the Lyria RealTime research line; performed live by Toro y Moi at Google I/O 2025.
- [HKUDS/VideoAgent](https://github.com/HKUDS/VideoAgent) — Agentic video understanding + editing + remaking with self-evaluation loops.
- [HKUDS/ViMax](https://github.com/HKUDS/ViMax) — Director / Screenwriter / Producer / Generator multi-agent video pipeline.
- [vrch.io — Agentic VJ System](https://www.vrch.io/aivj) — Multimodal AI agent generates audio/camera-reactive visuals with MIDI/OSC/keyboard control; deployed at CES, SIGGRAPH ASIA, Outernet London. Backend: [`comfyui-web-viewer`](https://github.com/VrchStudio/comfyui-web-viewer).
- [janvanwassenhove/MusicAgent](https://github.com/janvanwassenhove/MusicAgent) — Multi-agent system that programs full songs in Sonic Pi.
- [lllindsey0615/ComposerX](https://github.com/lllindsey0615/ComposerX) — Multi-agent symbolic music composition (Leader / Melody / Harmony / Reviewer).
- [AIDC-AI/ComfyUI-Copilot](https://github.com/AIDC-AI/ComfyUI-Copilot) — LLM multi-agent assistant for automatic ComfyUI workflow generation.
- [comfyui_LLM_party](https://github.com/heshengtao/comfyui_LLM_party) — Full LLM agent framework as ComfyUI nodes (MCP, GPT-sovits, FLUX prompt nodes).
- [Limbicnation/hermes-asset-pipeline](https://github.com/Limbicnation/hermes-asset-pipeline) — Hermes-driven asset pipeline integrating ComfyUI, Blender, Godot 4.x, Python.

## Notable Projects, Demos & Installations

- [Apolotary/blob-tracker](https://github.com/Apolotary/blob-tracker) — Audio-reactive blob tracking on video; Hermes Agent skill, Kimi-driven creative parameter selection. The motivating example for this list.
- [Sougwen Chung — D.O.U.G.](https://sougwen.com/) — Decade-long human-machine drawing collaborations; *Spectral / DOUG_4* (WEF Davos 2025) couples live EEG biofeedback with an AI trained on her own stroke data driving robotic painting arms.
- [Daito Manabe / Rhizomatiks](https://daito.ws/en/) — Live AV system with 64 AI agents that perceive music and autonomously generate visuals, dance, and reactions; *Latent Body* converts dance into video via diffusion.
- [pkmital/dance2dance](https://github.com/pkmital/dance2dance) — *Discrete Figures*: seq2seq of dance data (Mikiko + Daito Manabe + Kyle McDonald).
- [Holly Herndon — Holly+ / Spawn](https://holly.plus/) — Neural "digital twin" voice and Spawn, an AI vocalist that responds in real time on tour.
- [Memo Akten — ULTRACHUNK](https://www.memo.tv/works/ultrachunk/) — Live improvisational duet between Jennifer Walshe and a real-time generative neural network.
- [BottoDAO](https://botto.com/dao) — Multi-thousand-member community whose entire purpose is co-creating with an autonomous AI artist.
- [a16z-infra/ai-town](https://github.com/a16z-infra/ai-town) — Deployable starter kit for a virtual town where AI characters live, chat, and socialize; the most-forked agentic-simulation-as-art base.

## Creative Coding Substrates

The things agents drive when they make art.

- [p5.js](https://github.com/processing/p5.js) — JS creative-coding library; the most common output target for agentic visual sketches.
- [Processing](https://processing.org/) — The original; canonical Java/Python creative-coding environment.
- [openFrameworks](https://openframeworks.cc/) — C++ creative-coding toolkit.
- [OPENRNDR](https://github.com/openrndr/openrndr) — Kotlin/JVM creative-coding library; backbone of Xemantic's agentic creative-coding workshops.
- [Hydra](https://hydra.ojack.xyz/) — Olivia Jack's livecoded networked browser visuals.
- [Strudel](https://strudel.cc/) — Browser TidalCycles; the canonical surface targeted by the Strudel agent projects above.
- [TidalCycles](https://tidalcycles.org/) — Pattern-based live coding for music.
- [Magenta](https://github.com/magenta/magenta) — Google Brain's foundational creative-AI music/art research repo.

## Articles

- [Building Effective Agents — Anthropic](https://www.anthropic.com/engineering/building-effective-agents) — Foundational distinction between workflows and agents; the orchestrator-workers and evaluator-optimizer patterns map cleanly onto creative pipelines.
- [Claude for Creative Work — Anthropic](https://www.anthropic.com/news/claude-for-creative-work) — MCP connectors that let Claude take actions inside Adobe Creative Cloud, Affinity, Autodesk Fusion, Blender, Resolume Arena/Wire, SketchUp, Splice, Ableton.
- [Designing agentic loops — Simon Willison](https://simonwillison.net/2025/Sep/30/designing-agentic-loops/) — How to shape the loop and tools; directly applicable when an agent is iterating on a sketch or audio patch.
- [Agents are models using tools in a loop — Simon Willison](https://simonwillison.net/2025/May/22/tools-in-a-loop/) — Cleanest one-line definition.
- [Not all AI-assisted programming is vibe coding — Simon Willison](https://simonwillison.net/2025/Mar/19/vibe-coding/) — Useful when delineating creative throwaways from production engineering.
- [The Unreasonable Effectiveness of an LLM Agent Loop with Tool Use — sketch.dev](https://sketch.dev/blog/agent-loop) — Demonstrates how compact a useful agent loop can be.
- [LLM Powered Autonomous Agents — Lilian Weng](https://lilianweng.github.io/posts/2023-06-23-agent/) — Standard reference architecture (planning + memory + tool use).
- [Why Tool AIs Want to Be Agent AIs — Gwern](https://gwern.net/tool-ai) — Long-form theoretical case for autonomy over tool use.
- [Writing with the Machine — Robin Sloan](https://www.robinsloan.com/notes/writing-with-the-machine/) — Pre-LLM pioneering "inhuman collaborator" inside an editor; the spiritual ancestor.
- [Malleable software in the age of LLMs — Geoffrey Litt](https://www.geoffreylitt.com/2023/03/25/llm-end-user-programming.html) — Why LLMs make personal/expressive software possible.
- [Home-Cooked Software and Barefoot Developers — Maggie Appleton](https://maggieappleton.com/home-cooked-software) — Cultural shift toward creative-coder-as-agent-orchestrator.
- [One Developer, Two Dozen Agents, Zero Alignment — Maggie Appleton](https://maggieappleton.com/zero-alignment) — On managing many concurrent agents in a creative workspace.
- [Creative Coding with Claude 3.5 Sonnet Artifacts and p5.js — sankalp](https://sankalp.bearblog.dev/creative-coding-with-claude-35-sonnet-artifacts-and-p5js/) — Concrete example: A*, Hilbert curves, Perlin noise, all assembled via Claude in minutes.
- [Building a p5.js Editor Controlled by Claude and an MCP Server — Adil Moujahid](https://adilmoujahid.com/posts/2025/06/mcp-server-p5js-editor/) — Full MCP-server walkthrough that turns Claude into a p5.js controller.
- [How it's Made — ShiffBot — Google Developers Blog](https://developers.googleblog.com/en/how-its-made-exploring-ai-x-learning-through-shiffbot-an-ai-experiment-powered-by-the-gemini-api/) — A Gemini-powered tutor agent embedded in the p5.js editor with Daniel Shiffman's persona.

## Talks

- [Collaborative AI Engineering: One Dev, Two Dozen Agents, Zero Alignment — Maggie Appleton (GitHub)](https://www.youtube.com/watch?v=ClWD8OEYgp8) — Talk version of the *Zero Alignment* essay; introduces the ACE multi-agent workspace.

## Papers

- [ComposerX: Multi-Agent Symbolic Music Composition with LLMs](https://arxiv.org/abs/2404.18081) — Leader / melody / harmony / instrument / reviewer / arrangement agents.
- [CREA: A Collaborative Multi-Agent Framework for Creative Image Editing and Generation](https://arxiv.org/abs/2504.05306) — Specialized agents conceptualize → generate → critique → enhance.
- [SketchAgent: Language-Driven Sequential Sketch Generation](https://yael-vinker.github.io/sketch-agent/) — LLM emits stroke sequences directly to a canvas.
- [Live Improvisation with Fine-Tuned Generative AI (NIME 2025)](https://www.nime.org/proc/nime2025_54/index.html) — Stable Audio Open + Ableton + Musical Metacreation.
- [Mixer Metaphors (NIME 2025)](https://www.nime.org/proc/nime2025_47/index.html) — Repurposing analog mixer affordances for tactile control of LLM parameters.
- [NeurIPS Workshop on Creativity & Generative AI](https://creativity-ai.github.io/) — The academic anchor for the field.

## Books

- [The Nature of Code (2nd ed., 2024) — Daniel Shiffman](https://natureofcode.com/) — New edition includes ml5.js machine-learning chapters; the canonical creative-coding-meets-ML primer (full text under Creative Commons).
- [Generative Deep Learning, 2nd Edition — David Foster (O'Reilly, 2023)](https://www.oreilly.com/library/view/generative-deep-learning/9781098134174/) — The model side of teaching machines to paint, write, compose, and play.

## Podcasts & Newsletters

- [Latent Space](https://www.latent.space/podcast) — The canonical AI-engineering podcast; routinely covers coding agents.
- [Machine Learning Street Talk](https://www.mlst.ai/) — Deep technical episodes on creativity, open-endedness, and agents.
- [The Cognitive Revolution](https://www.cognitiverevolution.ai/) — Builder-focused interviews; covers creative AI tooling alongside research.
- [The Creative Coding Podcast](https://creativecodingpodcast.com/) — Iain Lobb & Seb Lee-Delisle; predates LLMs but recent episodes intersect.

## Communities

- [Hydra](https://hydra.ojack.xyz/) — The Discord linked from the Hydra docs is one of the most active LLM-aware creative-coding communities.
- [openFrameworks community](https://openframeworks.cc/community/) — Forum, GitHub, Slack — the C++ creative-coding center of gravity.
- [TOPLAP](https://blog.toplap.org/) — Live-coding home (Algorave, TidalCycles, etc.); the natural home for agentic music experiments.
- [AI Music Creativity (AIMC)](https://aimusiccreativity.org/) — Conference + community; 2025 theme: "The Artist in The Loop."
- [BottoDAO](https://botto.com/dao) — The community organized around an autonomous AI artist.

## Workshops & Education

- [Xemantic — Agentic AI & Creative Coding](https://xemantic.com/ai/workshops/) — Berlin workshops by Kazik Pogoda; OPENRNDR + Claude. Companion repo: [`xemantic-ai-workshop`](https://github.com/xemantic/xemantic-ai-workshop).
- [Anthropic — Claude for Creative Work academic partners](https://www.anthropic.com/news/claude-for-creative-work) — RISD (Art & Computation), Ringling, Goldsmiths MA/MFA Computational Arts.

## Related Lists

- [terkelg/awesome-creative-coding](https://github.com/terkelg/awesome-creative-coding) — The canonical creative-coding list; this list is its agentic descendant.
- [vibertthio/awesome-machine-learning-art](https://github.com/vibertthio/awesome-machine-learning-art) — ML-for-art (pre-agentic, heavy people/projects overlap).
- [filipecalegario/awesome-generative-ai](https://github.com/filipecalegario/awesome-generative-ai) — Generative AI tools, works, models, refs.
- [jonathandinu/ai4artists](https://github.com/jonathandinu/ai4artists) — AI art courses, tools, libraries, places.
- [ml4a/ml4a](https://github.com/ml4a/ml4a) — Gene Kogan's ML-for-Artists library + notebooks.
- [toplap/awesome-livecoding](https://github.com/toplap/awesome-livecoding) — Live-coding tools and languages.
- [e2b-dev/awesome-ai-agents](https://github.com/e2b-dev/awesome-ai-agents) — The largest agent list — agent-side counterpart to this one.
- [hyp1231/awesome-llm-powered-agent](https://github.com/hyp1231/awesome-llm-powered-agent) — LLM-agent papers / repos / blogs.
- [punkpeye/awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers) — Largest MCP server index (creative tools live downstream).
- [modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers) — Official MCP reference servers.
- [VoltAgent/awesome-agent-skills](https://github.com/VoltAgent/awesome-agent-skills) — 1000+ cross-harness agent skills.
- [hesreallyhim/awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code) — Skills, hooks, slash-commands, agent orchestrators for Claude Code.
- [ComposioHQ/awesome-claude-skills](https://github.com/ComposioHQ/awesome-claude-skills) — Curated Claude Skills.
- [0xNyk/awesome-hermes-agent](https://github.com/0xNyk/awesome-hermes-agent) — Skills / tools / integrations for Hermes Agent.

## Contributing

See [contributing.md](contributing.md). Pull requests welcome — especially for verified artist projects, MCP servers, and demos. **Please verify URLs before submitting.**

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, [Apolotary](https://github.com/Apolotary) has waived all copyright and related or neighboring rights to this work.
