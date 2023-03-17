# AI Agents

AI Agents are autonomous entities that use LLMs as their central brain to make decisions, execute tasks using external tools, and adapt their behavior dynamically based on environment feedback.

## Core Concepts

### 1. The ReAct Pattern (Reasoning and Acting)
Agents alternate between reasoning (thinking about what to do next) and acting (invoking tools).

```
Thought: I need to find the population of Paris in 2026. I should search the web.
Action: search_web[population of Paris 2026]
Observation: Paris population in 2026 is approximately 2.1 million.
Thought: I now have the answer. I will formulate the response.
Response: The population of Paris in 2026 is around 2.1 million.
```

### 2. Tool Use (Function Calling)
LLMs are trained to output structured schema representations (usually JSON) of function calls instead of natural language when they determine a tool is needed.

### 3. Agent Frameworks
*   **LangGraph:** Graph-based orchestrator, optimal for stateful, cyclic multi-agent systems.
*   **CrewAI:** Focuses on role-playing, collaborative multi-agent crews.
*   **Autogen:** Microsoft's framework for multi-agent conversation.

## Building a Simple Agent (Pseudo-code)

```python
def run_agent(user_prompt):
    messages = [SystemMessage(content="You are an assistant with tools."), UserMessage(content=user_prompt)]
    while True:
        response = llm.invoke(messages)
        if not response.tool_calls:
            return response.content
        
        for tool_call in response.tool_calls:
            result = execute_tool(tool_call.name, tool_call.args)
            messages.append(ToolMessage(content=result, tool_call_id=tool_call.id))
```
