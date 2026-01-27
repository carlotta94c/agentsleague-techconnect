# 🧠 Reasoning Agents - Starter Kit

**Track**: Reasoning Agents with Microsoft Foundry  
**Time Limit**: 90 minutes

Welcome to the Reasoning Agents track! In this challenge, you'll build intelligent agents using **Microsoft Foundry** (formerly Azure AI Foundry) that can solve complex problems through multi-step reasoning.

---

## 💡 Project Ideas

Given the 90-minute time constraint, here are some achievable project ideas:

### Quick Wins (Recommended for beginners)
- **Research Assistant Agent** - An agent that can research a topic and summarize findings
- **Decision Helper Agent** - Help users make decisions by analyzing pros/cons
- **Fact Checker Agent** - Verify claims by searching and cross-referencing information
- **Meeting Notes Summarizer** - Extract action items and key points from meeting transcripts

### Intermediate Projects
- **Multi-Step Problem Solver** - An agent that breaks down complex problems into steps
- **Code Explanation Agent** - Explain code step-by-step with reasoning
- **Travel Planning Agent** - Plan trips with logical reasoning about constraints
- **Recipe Recommender Agent** - Suggest recipes based on available ingredients

### Advanced Projects (If you're fast!)
- **Multi-Agent Debate System** - Multiple agents discuss and refine answers
- **Reasoning Chain Visualizer** - Show the agent's thought process visually
- **Self-Correcting Agent** - An agent that validates and corrects its own responses

---

## 🚀 Quick Start

### Prerequisites

1. **Azure Subscription** - Access to Azure AI services
2. **Python 3.10+** - Recommended for most examples
3. **VS Code** - With Python extension

### 5-Minute Setup (Python)

1. **Create a new project folder and virtual environment**

```bash
mkdir my-reasoning-agent
cd my-reasoning-agent
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

2. **Install dependencies**

```bash
pip install azure-ai-projects azure-identity openai
```

3. **Set up environment variables**

```bash
# Create a .env file (don't commit this!)
AZURE_OPENAI_ENDPOINT=https://your-endpoint.openai.azure.com/
AZURE_OPENAI_API_KEY=your-api-key
AZURE_OPENAI_DEPLOYMENT=gpt-4o
```

4. **Create your first agent**

```python
# agent.py
import os
from openai import AzureOpenAI

client = AzureOpenAI(
    azure_endpoint=os.getenv("AZURE_OPENAI_ENDPOINT"),
    api_key=os.getenv("AZURE_OPENAI_API_KEY"),
    api_version="2024-02-15-preview"
)

def reasoning_agent(question: str) -> str:
    """A simple reasoning agent that thinks step by step."""
    
    response = client.chat.completions.create(
        model=os.getenv("AZURE_OPENAI_DEPLOYMENT"),
        messages=[
            {
                "role": "system",
                "content": """You are a reasoning agent. When answering questions:
                1. Break down the problem into steps
                2. Think through each step carefully
                3. Show your reasoning process
                4. Provide a clear final answer"""
            },
            {"role": "user", "content": question}
        ],
        temperature=0.7,
        max_tokens=1000
    )
    
    return response.choices[0].message.content

# Example usage
if __name__ == "__main__":
    question = "Should I take an umbrella today if there's a 30% chance of rain?"
    print(reasoning_agent(question))
```

---

## 🧠 Reasoning Patterns & Best Practices

### Chain-of-Thought Prompting

```python
CHAIN_OF_THOUGHT_PROMPT = """
Let's solve this step by step:

Step 1: [First step of reasoning]
Step 2: [Second step of reasoning]
...
Final Answer: [Your conclusion]
"""
```

### ReAct Pattern (Reasoning + Acting)

```python
REACT_PROMPT = """
Thought: [What you're thinking about the problem]
Action: [What action to take - e.g., search, calculate, lookup]
Observation: [What you learned from the action]
... (repeat as needed)
Final Answer: [Your conclusion based on all observations]
"""
```

### Self-Reflection Pattern

```python
REFLECTION_PROMPT = """
Initial Answer: [Your first attempt]
Reflection: [What could be wrong or improved?]
Revised Answer: [Improved answer after reflection]
Confidence: [How confident are you in this answer?]
"""
```

---

## 📋 Requirements & Evaluation

### Core Requirements

1. **Use Microsoft Foundry/Azure AI** - Your agent must use Azure AI services
2. **Demonstrate reasoning** - Show clear multi-step thinking
3. **Working demo** - Your agent must be functional

### Evaluation Criteria

| Criterion | Weight | Description |
|-----------|--------|-------------|
| Reasoning Quality | 30% | Clear, logical multi-step thinking |
| Problem Solving | 25% | Effectively solves the target problem |
| Technical Implementation | 25% | Clean code, good patterns |
| Presentation | 20% | Clear demo, good documentation |

---

## 📚 Resources

### Microsoft Foundry Documentation
- [Azure AI Foundry](https://learn.microsoft.com/en-us/azure/ai-studio/)
- [Azure OpenAI Service](https://learn.microsoft.com/en-us/azure/ai-services/openai/)
- [Prompt Engineering Guide](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/prompt-engineering)

### Reasoning Patterns
- [Chain-of-Thought Prompting](https://www.promptingguide.ai/techniques/cot)
- [ReAct Pattern](https://www.promptingguide.ai/techniques/react)
- [Self-Consistency](https://www.promptingguide.ai/techniques/consistency)

### Code Samples
- [Azure AI Samples](https://github.com/Azure-Samples/azure-ai-samples)
- [Azure OpenAI Samples](https://github.com/Azure-Samples/openai)

---

## ❓ FAQ

### What models can I use?

Any models available in Azure OpenAI or Azure AI services. GPT-4o is recommended for complex reasoning.

### Do I need to use Python?

No, but Python has the best SDK support. TypeScript/JavaScript and C# are also fully supported.

### What if I don't have Azure access?

Talk to a roaming expert - we can help you get access or pair you with someone who has access.

### Can I use LangChain or other frameworks?

Yes! Use whatever frameworks help you build faster.

---

**Good luck! Build an agent that thinks! 🧠**
