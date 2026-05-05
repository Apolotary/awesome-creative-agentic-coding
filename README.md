# Awesome Creative Agentic Coding [![Awesome](https://awesome.re/badge-flat.svg)](https://github.com/sindresorhus/awesome)

> A curated list of creative coding that involves agents.

**Creative agentic coding** is what happens when an autonomous agent — an LLM in a loop, with tools, memory, and the ability to act — becomes part of a creative-coding pipeline. It is distinct from "AI for art" (text-to-image, model-only) and from pure creative coding (code-only). The agent is in the loop: picking parameters, chaining tools, judging its own output, and sometimes performing live.

This list intentionally **excludes** generic agent infrastructure (coding agents, agent frameworks, agent theory) unless it has a documented creative-coding usage. For those, see [e2b-dev/awesome-ai-agents](https://github.com/e2b-dev/awesome-ai-agents) and [punkpeye/awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers).

Please read the [contribution guidelines](contributing.md) before contributing.

## Contents

- [Skills, Patterns & Cookbooks](#skills-patterns--cookbooks)
- [MCP Servers for Creative Work](#mcp-servers-for-creative-work)
  - [Image, Video, Audio Generation](#image-video-audio-generation)
  - [3D & Game Engines](#3d--game-engines)
  - [Live Visuals & Compositing](#live-visuals--compositing)
  - [Music & Live Coding](#music--live-coding)
  - [Computer Vision](#computer-vision)
  - [Design, Drawing & Web Surfaces](#design-drawing--web-surfaces)
- [Multi-Agent Creative Pipelines](#multi-agent-creative-pipelines)
- [Projects, Demos & Installations](#projects-demos--installations)
- [Articles](#articles)
- [Papers](#papers)
- [Books](#books)
- [Communities](#communities)
- [Workshops & Education](#workshops--education)
- [Related Lists](#related-lists)
- [Contributing](#contributing)
- [License](#license)

## Skills, Patterns & Cookbooks

Small, declarative bundles of instructions, scripts, and resources that turn a generic agent into a creative-coding collaborator.

- [anthropics/skills](https://github.com/anthropics/skills) — Anthropic's official Skills repo. Creative ones inside: [`algorithmic-art`](https://github.com/anthropics/skills/tree/main/skills/algorithmic-art) (p5.js with seeded randomness, flow fields, particle systems), [`canvas-design`](https://github.com/anthropics/skills/tree/main/skills/canvas-design), [`web-artifacts-builder`](https://github.com/anthropics/skills/tree/main/skills/web-artifacts-builder), [`theme-factory`](https://github.com/anthropics/skills/tree/main/skills/theme-factory), [`slack-gif-creator`](https://github.com/anthropics/skills/tree/main/skills/slack-gif-creator).
- [black-forest-labs/skills](https://github.com/black-forest-labs/skills) — Official FLUX prompting + API skills following the agentskills.io spec; first-party from a generative-image model maker.
- [tlehman/litprog-skill](https://github.com/tlehman/litprog-skill) — Cross-harness literate-programming skill (Claude Code / opencode / Hermes); a clean pattern for documented creative-code notebooks.

## MCP Servers for Creative Work

Model Context Protocol gives agents tools. These let an agent control the actual creative software.

### Image, Video, Audio Generation

- [Replicate MCP](https://replicate.com/docs/reference/mcp) — Official MCP for Replicate's hosted-models API (image, video, audio, ML).
- [Hugging Face MCP Server](https://github.com/huggingface/hf-mcp-server) — Official MCP for Hub search plus thousands of Gradio apps and Spaces.
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
- [Godot MCP](https://github.com/Coding-Solo/godot-mcp) — Godot Engine MCP for launching projects, managing scenes, and capturing debug output.
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
- [MuseScore MCP](https://github.com/ghchen99/mcp-musescore) — WebSocket MCP bridge for composing, editing, and navigating MuseScore notation.

### Computer Vision

- [mcp-vision](https://github.com/groundlight/mcp-vision) — HuggingFace CV models (e.g., zero-shot detection) as agent tools.
- [OpenCV MCP](https://github.com/GongRzhe/opencv-mcp-server) — Image/video processing (filters, edges, face/object detect, tracking).
- [YOLO MCP](https://github.com/GongRzhe/YOLO-MCP-Server) — YOLO detection, segmentation, classification, pose.

### Design, Drawing & Web Surfaces

- [Figma MCP Server](https://developers.figma.com/docs/figma-mcp-server/) — Official Figma MCP for design context and native canvas writes from agentic tools.
- [Cursor Talk to Figma](https://github.com/grab/cursor-talk-to-figma-mcp) — MCP between agentic IDEs and Figma; read & modify designs programmatically.
- [Playwright MCP](https://github.com/microsoft/playwright-mcp) — Official Microsoft MCP for browser control, screenshots, and visual feedback loops.
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

## Projects, Demos & Installations

- [Apolotary/blob-tracker](https://github.com/Apolotary/blob-tracker) — Audio-reactive blob tracking on video; Hermes Agent skill with Kimi-driven creative parameter selection.
- [Sougwen Chung — D.O.U.G.](https://sougwen.com/) — Decade-long human-machine drawing collaborations; *Spectral / DOUG_4* (WEF Davos 2025) couples live EEG biofeedback with an AI trained on her own stroke data driving robotic painting arms.
- [Daito Manabe / Rhizomatiks](https://daito.ws/en/) — Live AV system with 64 AI agents that perceive music and autonomously generate visuals, dance, and reactions; *Latent Body* converts dance into video via diffusion.
- [pkmital/dance2dance](https://github.com/pkmital/dance2dance) — *Discrete Figures*: seq2seq of dance data (Mikiko + Daito Manabe + Kyle McDonald).
- [Holly Herndon — Holly+ / Spawn](https://holly.plus/) — Neural "digital twin" voice and Spawn, an AI vocalist that responds in real time on tour.
- [Memo Akten — ULTRACHUNK](https://www.memo.tv/works/ultrachunk/) — Live improvisational duet between Jennifer Walshe and a real-time generative neural network.
- [BottoDAO](https://botto.com/dao) — Multi-thousand-member community whose entire purpose is co-creating with an autonomous AI artist.
- [a16z-infra/ai-town](https://github.com/a16z-infra/ai-town) — Deployable starter kit for a virtual town where AI characters live, chat, and socialize; the most-forked agentic-simulation-as-art base.

## Articles

- [Claude for Creative Work — Anthropic](https://www.anthropic.com/news/claude-for-creative-work) — MCP connectors that let Claude take actions inside Adobe Creative Cloud, Affinity, Autodesk Fusion, Blender, Resolume Arena/Wire, SketchUp, Splice, Ableton.
- [Creative Coding with Claude 3.5 Sonnet Artifacts and p5.js — sankalp](https://sankalp.bearblog.dev/creative-coding-with-claude-35-sonnet-artifacts-and-p5js/) — Concrete example: A*, Hilbert curves, Perlin noise, all assembled via Claude in minutes.
- [Building a p5.js Editor Controlled by Claude and an MCP Server — Adil Moujahid](https://adilmoujahid.com/posts/2025/06/mcp-server-p5js-editor/) — Full MCP-server walkthrough that turns Claude into a p5.js controller.
- [How it's Made — ShiffBot — Google Developers Blog](https://developers.googleblog.com/en/how-its-made-exploring-ai-x-learning-through-shiffbot-an-ai-experiment-powered-by-the-gemini-api/) — A Gemini-powered tutor agent embedded in the p5.js editor with Daniel Shiffman's persona.

## Papers

- [ComposerX: Multi-Agent Symbolic Music Composition with LLMs](https://arxiv.org/abs/2404.18081) — Leader / melody / harmony / instrument / reviewer / arrangement agents.
- [CREA: A Collaborative Multi-Agent Framework for Creative Image Editing and Generation](https://arxiv.org/abs/2504.05306) — Specialized agents conceptualize → generate → critique → enhance.
- [SketchAgent: Language-Driven Sequential Sketch Generation](https://yael-vinker.github.io/sketch-agent/) — LLM emits stroke sequences directly to a canvas.
- [Live Improvisation with Fine-Tuned Generative AI (NIME 2025)](https://www.nime.org/proc/nime2025_54/index.html) — Stable Audio Open + Ableton + Musical Metacreation.
- [Mixer Metaphors (NIME 2025)](https://www.nime.org/proc/nime2025_47/index.html) — Repurposing analog mixer affordances for tactile control of LLM parameters.
- [NeurIPS Workshop on Creativity & Generative AI](https://creativity-ai.github.io/) — The academic anchor for the field.

## Books

- [The Nature of Code (2nd ed., 2024) — Daniel Shiffman](https://natureofcode.com/) — New edition includes ml5.js machine-learning chapters; the canonical creative-coding-meets-ML primer (full text under Creative Commons).

## Communities

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

## Contributing

See [contributing.md](contributing.md). Pull requests welcome — especially for verified artist projects, MCP servers, and demos. **Please verify URLs before submitting.**

## License

[MIT License](LICENSE) © [Apolotary](https://github.com/Apolotary)
