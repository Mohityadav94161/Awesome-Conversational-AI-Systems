# Awesome Conversational AI Systems

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated map of the modern conversational AI stack — models, memory, retrieval, voice, avatars, evaluation, safety, orchestration, and production systems.

Conversational AI has moved far beyond simple chatbot prompts.

Modern systems may combine:

```text
User
 ↓
Text / Voice / Image
 ↓
Conversation Runtime
 ↓
Context Builder
 ├── Recent History
 ├── Long-Term Memory
 ├── User Profile
 ├── Knowledge / RAG
 └── Tool State
 ↓
Model Router
 ↓
LLM / Multimodal Model
 ↓
Safety + Evaluation
 ↓
Voice / Avatar / UI
 ↓
User
```

This repository collects the most useful resources for understanding and building that stack.

It includes both open-source infrastructure and real-world platforms where their architecture, documentation, or product design is useful to study.

---

## Contents

- Production Platforms
- Open-Source Conversational Frontends
- Models
- Model Serving
- Memory
- Retrieval & RAG
- Conversation State
- Agent Frameworks
- Prompt & Context Engineering
- Voice & Speech
- Real-Time Infrastructure
- Avatars & Embodiment
- Character & Persona Systems
- Evaluation
- Observability
- Safety & Moderation
- Databases & Vector Search
- Datasets
- Research
- Architecture Guides
- Related Awesome Lists

---

# Production Platforms

Real-world conversational AI systems useful for studying product design, interaction patterns, memory, persona systems, and multimodal experiences.

## Character.AI

https://character.ai/

Large-scale character-based conversational platform focused on persistent personas and user-created characters.

Useful areas to study:

- character definitions;
- creator ecosystem;
- character discovery;
- multi-turn persona consistency;
- voice;
- recommendation systems.

### Character.AI Blog

https://blog.character.ai/

Official product, research, and engineering updates.

---

## Replika

https://replika.com/

Long-running AI companion platform centered on persistent relationships and personalized interaction.

Useful for studying:

- long-term companion UX;
- relationship state;
- avatars;
- voice;
- persistent user modeling.

---

## Nomi

https://nomi.ai/

Persistent AI companion platform with strong emphasis on memory and relationship continuity.

Useful for studying:

- longitudinal conversations;
- persistent persona;
- companion memory;
- multi-character interactions.

---

## Kindroid

https://kindroid.ai/

AI companion platform with extensive customization, memory, backstory, voice, and image capabilities.

Useful for studying:

- explicit memory systems;
- configurable personas;
- user-controlled backstory;
- multimodal companions.

---

## CrushOn.AI

https://crushon.ai/

Character-roleplay platform with a large creator ecosystem and detailed character configuration.

### CrushOn AI Wiki

https://aiwiki.crushon.ai/

Creator and platform documentation covering:

- character prompts;
- scenarios;
- multi-character bots;
- permanent tokens;
- character import/export.

---

## JanitorAI

https://janitorai.com/

Large character-roleplay ecosystem focused on user-created characters and flexible conversational experiences.

Useful for studying:

- creator-generated personas;
- public character discovery;
- roleplay UX;
- model flexibility.

---

## YourCrush.ai

https://yourcrush.ai/

Character and AI-companion platform combining character creation, persistent memory, public character discovery, and creator/social features.

### YourCrush Blog

https://yourcrush.ai/blogs/

Articles covering character creation, companion platforms, AI characters, memory, fandoms, and related topics.

### AI Character Creator Guide

https://yourcrush.ai/blog/ai-character-creator

Explains the separation between:

- character description;
- backstory;
- greeting;
- personality traits;
- speaking style;
- memories.

---

# Open-Source Conversational Frontends

## SillyTavern

https://github.com/SillyTavern/SillyTavern

Extensible frontend for character-oriented LLM conversations.

Supports:

- character cards;
- personas;
- World Info;
- RAG;
- group chats;
- multiple model providers;
- extensions.

Documentation:

https://docs.sillytavern.app/

---

## Open WebUI

https://github.com/open-webui/open-webui

Self-hosted conversational interface supporting multiple LLM backends.

Useful for:

- multi-model chat;
- RAG;
- tool integration;
- local models;
- self-hosting.

---

## LibreChat

https://github.com/danny-avila/LibreChat

Open-source multi-provider conversational interface.

Supports:

- OpenAI-compatible APIs;
- Anthropic;
- Google;
- agents;
- tools;
- multimodal interaction.

---

# Models

## Llama

https://www.llama.com/

Meta's open model family.

Widely used for local and hosted conversational systems.

---

## Qwen

https://github.com/QwenLM/Qwen

Open model family covering:

- text;
- coding;
- multimodal;
- reasoning.

---

## Mistral

https://mistral.ai/

Open and commercial language models commonly used in conversational applications.

---

## Gemma

https://ai.google.dev/gemma

Google's open model family.

---

# Model Serving

## vLLM

https://github.com/vllm-project/vllm

High-throughput LLM inference and serving engine.

Useful for production systems requiring:

- continuous batching;
- high GPU utilization;
- OpenAI-compatible APIs;
- distributed serving.

---

## llama.cpp

https://github.com/ggml-org/llama.cpp

Efficient local inference for GGUF models across CPUs and GPUs.

---

## Ollama

https://github.com/ollama/ollama

Simple runtime for running models locally through an API.

---

## Text Generation Inference

https://github.com/huggingface/text-generation-inference

Hugging Face's production-oriented LLM serving stack.

---

# Memory

Long-term memory is one of the key differences between a chatbot and a persistent conversational system.

A common architecture is:

```text
Conversation
   ↓
Memory Extraction
   ↓
Memory Store
   ↓
Ranking / Retrieval
   ↓
Relevant Memories
   ↓
Next Model Context
```

---

## Letta

https://github.com/letta-ai/letta

Framework for stateful agents with persistent memory.

Originally evolved from the MemGPT research project.

Useful for studying:

- memory blocks;
- persistent agent state;
- context management;
- archival memory.

---

## Mem0

https://github.com/mem0ai/mem0

Memory layer for AI applications.

Designed to extract and retrieve durable information across conversations.

---

## Zep

https://github.com/getzep/zep

Memory and context infrastructure for conversational AI and agents.

---

# Retrieval & RAG

## LlamaIndex

https://github.com/run-llama/llama_index

Framework for connecting LLM applications to external data.

Useful for:

- retrieval;
- document indexing;
- knowledge graphs;
- agent context.

---

## LangChain

https://github.com/langchain-ai/langchain

Broad LLM application framework supporting retrieval, tools, models, and orchestration.

---

## Haystack

https://github.com/deepset-ai/haystack

Open-source framework for production RAG and search applications.

---

# Conversation State

Not everything belongs in vector memory.

Conversational applications commonly maintain several state layers:

```text
Recent conversation
User profile
Relationship state
Task state
Long-term memory
Knowledge base
Current environment
```

For structured information such as:

```json
{
  "name": "Sam",
  "timezone": "Europe/London",
  "subscription": "pro"
}
```

a normal database is often more appropriate than vector retrieval.

---

# Agent Frameworks

## LangGraph

https://github.com/langchain-ai/langgraph

Framework for building stateful, graph-based LLM applications.

Particularly useful for:

- persistent state;
- branching workflows;
- human-in-the-loop systems;
- durable execution.

---

## AutoGen

https://github.com/microsoft/autogen

Microsoft framework for event-driven and multi-agent AI systems.

---

## CrewAI

https://github.com/crewAIInc/crewAI

Framework for orchestrating specialized agents and multi-agent workflows.

---

# Prompt & Context Engineering

A production prompt is rarely just:

```text
You are a helpful assistant.
```

Modern conversational systems may construct context dynamically:

```text
System instructions
     ↓
Persona
     ↓
User profile
     ↓
Relevant memory
     ↓
Retrieved knowledge
     ↓
Tool state
     ↓
Recent messages
     ↓
Current input
```

The ordering, token allocation, and priority of each section can materially affect model behavior.

---

# Voice & Speech

## Whisper

https://github.com/openai/whisper

Speech recognition model commonly used for conversational speech-to-text pipelines.

---

## OpenVoice

https://github.com/myshell-ai/OpenVoice

Open-source voice cloning and speech synthesis toolkit.

---

## GPT-SoVITS

https://github.com/RVC-Boss/GPT-SoVITS

Few-shot text-to-speech and voice cloning toolkit.

---

## Piper

https://github.com/rhasspy/piper

Fast local text-to-speech engine.

---

# Real-Time Infrastructure

Voice conversations require much lower latency than ordinary text chat.

Typical stack:

```text
Microphone
   ↓
VAD
   ↓
Streaming STT
   ↓
LLM
   ↓
Streaming TTS
   ↓
Speaker
```

---

## LiveKit

https://github.com/livekit/livekit

Open-source WebRTC infrastructure widely used for real-time AI voice applications.

---

## Pipecat

https://github.com/pipecat-ai/pipecat

Open-source framework for real-time voice and multimodal conversational agents.

---

# Avatars & Embodiment

## VRM

https://vrm.dev/

Open 3D avatar format used across virtual characters and VTuber applications.

---

## three-vrm

https://github.com/pixiv/three-vrm

Three.js library for VRM avatar rendering.

---

## Live2D

https://www.live2d.com/

2D character animation ecosystem commonly used for interactive virtual characters.

---

# Character & Persona Systems

Character-based applications typically separate:

```text
Identity
Personality
Backstory
Scenario
Speaking Style
Example Dialogue
Memory
Lore
```

Treating all of these as one enormous prompt makes characters difficult to maintain and evaluate.

---

## Character Card V2

https://github.com/malfoyslastname/character-card-spec-v2

Interchange specification for structured AI character definitions.

---

## Character Card V3

https://github.com/kwaroran/character-card-spec-v3

Newer generation of the character-card specification.

---

## Character.AI Creator Documentation

https://support.character.ai/

Official resources for character creation and definitions.

---

## CrushOn Creator Wiki

https://aiwiki.crushon.ai/

Detailed practical guides to character prompt structure and token usage.

---

## YourCrush AI Character Guide

https://yourcrush.ai/blog/ai-character-creator

Practical explanation of structuring descriptions, backstories, greetings, traits, speaking styles, and memories separately.

---

# Evaluation

Conversational AI needs different evaluation methods from single-turn question answering.

Useful dimensions include:

```text
Helpfulness
Persona consistency
Memory recall
Factuality
Conversation coherence
Tool correctness
Latency
Safety
Repetition
User preference
```

---

## DeepEval

https://github.com/confident-ai/deepeval

Open-source evaluation framework for LLM applications.

---

## Ragas

https://github.com/explodinggradients/ragas

Evaluation framework focused particularly on RAG systems.

---

## Promptfoo

https://github.com/promptfoo/promptfoo

Testing and evaluation framework for prompts and LLM applications.

Useful for regression testing and CI pipelines.

---

## LM Evaluation Harness

https://github.com/EleutherAI/lm-evaluation-harness

Popular framework for evaluating language models across standardized benchmarks.

---

# Observability

## Langfuse

https://github.com/langfuse/langfuse

Open-source LLM engineering and observability platform.

Includes:

- traces;
- prompt management;
- evaluations;
- usage analytics.

---

## Arize Phoenix

https://github.com/Arize-ai/phoenix

Open-source AI observability and evaluation platform.

---

## OpenLLMetry

https://github.com/traceloop/openllmetry

OpenTelemetry-based observability for LLM applications.

---

# Safety & Moderation

Conversational systems need defenses against:

- prompt injection;
- unsafe content;
- data leakage;
- tool misuse;
- jailbreaks;
- malicious retrieved content;
- impersonation;
- memory poisoning.

---

## Llama Guard

https://github.com/meta-llama/PurpleLlama

Safety-focused model and tooling ecosystem from Meta.

---

## NeMo Guardrails

https://github.com/NVIDIA-NeMo/Guardrails

Framework for adding programmable guardrails to conversational AI systems.

---

## Guardrails AI

https://github.com/guardrails-ai/guardrails

Validation framework for structured and policy-aware LLM outputs.

---

# Databases & Vector Search

## pgvector

https://github.com/pgvector/pgvector

PostgreSQL extension adding vector similarity search.

Useful for:

- semantic memory;
- RAG;
- recommendation;
- similarity search.

---

## Qdrant

https://github.com/qdrant/qdrant

Open-source vector database.

---

## Milvus

https://github.com/milvus-io/milvus

Distributed vector database designed for large-scale similarity search.

---

## Weaviate

https://github.com/weaviate/weaviate

Vector database with semantic search and hybrid retrieval features.

---

# Datasets

## DailyDialog

https://huggingface.co/datasets/li2017dailydialog

Human-written multi-turn conversation dataset.

---

## PersonaChat

https://huggingface.co/datasets/bavard/personachat_truecased

Persona-grounded dialogue dataset.

Useful for studying personality consistency across conversations.

---

## MultiWOZ

https://github.com/budzianowski/multiwoz

Large multi-domain task-oriented dialogue dataset.

---

# Research

## MemGPT

https://arxiv.org/abs/2310.08560

Research on treating context windows as limited memory and allowing LLM systems to manage information across memory tiers.

---

## RoleLLM

https://arxiv.org/abs/2310.00746

Research into evaluating and improving role-playing behavior in language models.

---

## Generative Agents

https://arxiv.org/abs/2304.03442

Influential work on persistent simulated agents using memory, reflection, and planning.

---

# Architecture Guides

Useful production systems usually separate at least four concepts:

```text
Conversation history
        !=
Long-term memory
        !=
User state
        !=
External knowledge
```

Keeping these independent makes it easier to:

- change models;
- debug hallucinations;
- update memory;
- delete user information;
- control token usage;
- evaluate individual components.

---

# Related Awesome Lists

## Awesome Conversational Agents

https://github.com/emrecanacikgoz/awesome-conversational-agents

Research-focused collection of conversational agent papers.

---

## Awesome LLM Eval

https://github.com/onejune2018/Awesome-LLM-Eval

Large collection of evaluation methods, benchmarks, tools, and papers.

---

## Awesome AI Companion

https://github.com/DasterProkio/awesome-ai-companion

Open-source projects and infrastructure focused specifically on long-term AI companions.

---

# Contributing

This repository aims to be a **curated technical map**, not a directory dump.

Good additions should meet at least one of these criteria:

- widely used open-source infrastructure;
- important research;
- high-quality technical documentation;
- notable production architecture;
- useful benchmark or dataset;
- technically interesting real-world conversational system.

Please include a short explanation of **why the resource matters**.

Avoid:

- affiliate pages;
- thin SEO articles;
- generic product directories;
- abandoned projects with no historical significance;
- promotional submissions with no technical value.

Commercial services are welcome when their documentation, architecture, research, or implementation provides genuine learning value.

If you work on a submitted project, disclose that relationship.

---

# License

CC0 1.0 Universal
