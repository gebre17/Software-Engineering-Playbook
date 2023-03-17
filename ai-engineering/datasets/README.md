# Datasets for AI Engineering

Quality of data is the primary driver of performance in LLM alignment and fine-tuning.

## Formats for LLM Fine-Tuning

### 1. Conversational Format (ShareGPT / HuggingFace)
Uses structured list of messages representing conversation history.

```json
[
  {
    "messages": [
      {"role": "system", "content": "You are a helpful assistant."},
      {"role": "user", "content": "What is 2+2?"},
      {"role": "assistant", "content": "4."}
    ]
  }
]
```

### 2. Instruction Format (Alpaca)
Standard prompt-response structure.

```json
{
  "instruction": "Translate the sentence to French.",
  "input": "How are you?",
  "output": "Comment ça va?"
}
```

## Data Curation & Cleaning
*   **Deduplication:** Removing duplicate prompts or text using MinHash/LSH to optimize sample quality.
*   **Formatting Checkers:** Ensuring strict adherence to JSON/JSONL formatting rules.
*   **Filtering:** Removing toxic language, low-quality machine outputs, or short/meaningless samples.

## Python Integration
Use Hugging Face's `datasets` library:

```python
from datasets import load_dataset

# Load a public dataset
dataset = load_dataset("imdb", split="train")

# Tokenize mapping
def tokenize_function(examples):
    return tokenizer(examples["text"], padding="max_length", truncation=True)

tokenized_datasets = dataset.map(tokenize_function, batched=True)
```
