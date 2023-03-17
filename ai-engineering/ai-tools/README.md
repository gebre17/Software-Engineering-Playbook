# AI Developer & Inference Tools

A guide to runtime engines, local execution hubs, and AI-enabled IDE extensions.

## Inference Engines

### 1. vLLM
Extremely fast, easy-to-use LLM serving engine. Implements **PagedAttention** to optimize VRAM utilization and serving throughput.
*   *Use-case:* Hosting models on enterprise servers/clouds.

### 2. Ollama
Local runner for models (Llama, Mistral, Gemma, etc.) packaged into simple single-command containerized environments.
*   *Command:* `ollama run llama3`
*   *Use-case:* Local development, offline execution.

### 3. Llama.cpp
C/C++ port of LLM runtime allowing execution on raw CPU and Apple Silicon with heavy GGUF quantization.

## AI Developer Tools & IDEs

*   **Cursor / VS Code with Copilot:** Integrates code generation, debugging, refactoring, and agentic workflows inside your IDE workspace.
*   **LM Studio:** Desktop application to download and interact with local GGUF models via a Chat UI or local server API.
