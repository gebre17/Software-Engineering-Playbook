# Prompt Engineering

Prompt engineering is the practice of structured input design to guide Large Language Models (LLMs) toward generating accurate, relevant, and contextually appropriate outputs.

## Core Techniques

### 1. System Prompts vs. User Prompts
*   **System Prompts:** Define the model's persona, boundaries, instructions, and default behavior.
*   **User Prompts:** The specific instruction or query representing the current task.

### 2. Few-Shot Prompting
Providing examples of input-output pairs to help the model learn the style, format, or logic of the expected output.

```
Example 1:
Input: The weather is gloomy.
Sentiment: Negative

Example 2:
Input: I got a promotion today!
Sentiment: Positive

Input: The movie was average.
Sentiment:
```

### 3. Chain-of-Thought (CoT) Prompting
Encouraging the model to explain its reasoning step-by-step before outputting the final answer. This is highly effective for math, logic, and reasoning tasks.

*   *Prompt suffix:* "Let's think step-by-step."

### 4. Structured Output with XML/JSON Tags
Using tags (e.g., `<thought>`, `<output>`, `<json>`) to segment parts of the prompt or direct the model to format its output cleanly.

```xml
You are a translation assistant. Translate the following text into Spanish.
Place your translation inside the <translation> tag.

<text>Hello, how are you today?</text>
```

## Best Practices
*   **Be Specific:** Explicitly state the format, constraints, and length of the output.
*   **Negative Constraints:** Tell the model what *not* to do (e.g., "Do not include any explanation outside the JSON format").
*   **XML Formatting:** Use XML tags to separate instructions from dynamic content/variables.
