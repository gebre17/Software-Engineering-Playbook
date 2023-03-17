# Fine-Tuning LLMs

Fine-tuning is the process of modifying an existing LLM's weights by training it on a specific, domain-targeted dataset.

## Fine-Tuning Methods

### 1. Full Fine-Tuning
All model parameters are updated during backpropagation.
*   *Pros:* High performance, maximum adaptability.
*   *Cons:* Very high hardware requirements (VRAM), prone to catastrophic forgetting.

### 2. PEFT (Parameter-Efficient Fine-Tuning)
Updating only a small subset of parameters while freezing the base model weights.
*   **LoRA (Low-Rank Adaptation):** Adds small trainable rank decomposition matrices to transformer layers (e.g., query/value projection layers).
*   **QLoRA:** Quantizes the base model to 4-bit (NormalFloat4), then performs LoRA over the quantized weights, drastically reducing VRAM usage.

## Alignment & Post-Training

*   **SFT (Supervised Fine-Tuning):** Teaching the model to follow instructions using prompt-response pairs.
*   **DPO (Direct Preference Optimization):** Direct optimization using pairwise feedback (preferred vs. dispreferred responses), bypassing the need for a separate reward model.
*   **RLHF (Reinforcement Learning from Human Feedback):** Training a reward model based on human choices, and using PPO to optimize the LLM policy.

## Hardware & Optimization Tools
*   **Hugging Face TRL / PEFT:** Library interfaces for fine-tuning.
*   **Unsloth:** Highly optimized wrappers for training Llama/Mistral models up to 80% faster.
*   **DeepSpeed / FSDP:** Distributed training libraries for sharding models across multiple GPUs.
