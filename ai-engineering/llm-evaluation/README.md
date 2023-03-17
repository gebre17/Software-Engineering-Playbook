# LLM Evaluation

Evaluating Large Language Models is critical for ensuring reliability, safety, and alignment with user expectations. Unlike traditional software, LLM outputs are non-deterministic and require specialized validation frameworks.

## Types of Evaluation

### 1. Traditional Metrics
Mainly used for translation, summarization, and similarity tasks.
*   **BLEU (Bilingual Evaluation Understudy):** Measures n-gram overlap between generated text and reference text.
*   **ROUGE (Recall-Oriented Understudy for Gisting Evaluation):** Focuses on recall; measures n-gram overlap, specifically designed for summarization.
*   **Cosine Similarity:** Embeds the texts and calculates the cosine distance between vectors.

### 2. Model-as-a-Judge (G-Eval / LLM-as-a-Judge)
Using a more capable model (like GPT-4) to evaluate another model's output based on a detailed rubrics-based prompt.
*   **Faithfulness / Groundedness:** Does the output contain facts not supported by the source text?
*   **Answer Relevance:** Does the output directly address the user query?
*   **Toxicity and Bias:** Flags harmful, offensive, or biased content.

### 3. Human Evaluation
The gold standard, but expensive and slow. Used to calibrate automated evaluation metrics.

## Evaluation Frameworks

*   **Ragas:** Popular framework for RAG evaluation (evaluates retrieval precision/recall and generation faithfulness/relevance).
*   **TruLens:** Offers tools to trace and evaluate LLM applications.
*   **Promptflow:** Suite of developer tools designed to streamline the end-to-end development cycle of LLM-based AI applications.
