# 💼 Enterprise Agents - Starter Kit

**Track**: Enterprise Agents with M365 Agents Toolkit  
**Time Limit**: 90 minutes

Welcome to the Enterprise Agents track! In this challenge, you'll build intelligent agents that extend **Microsoft 365 Copilot** to address real-world enterprise scenarios using the M365 Agents Toolkit.

---

## 💡 Project Ideas

Given the 90-minute time constraint, here are some achievable project ideas:

### Quick Wins (Recommended for beginners)
- **Declarative FAQ Agent** - Answer questions about a specific topic using SharePoint/web content
- **Meeting Prep Agent** - Summarize relevant documents before meetings
- **Policy Assistant** - Help employees find HR/IT policies quickly
- **Onboarding Buddy** - Answer common new employee questions

### Intermediate Projects
- **Expense Helper Agent** - Guide users through expense submission
- **IT Helpdesk Agent** - Troubleshoot common IT issues
- **Project Status Agent** - Pull project updates from various sources
- **Knowledge Base Agent** - Search and summarize internal documentation

### Advanced Projects (If you're fast!)
- **Multi-Source Research Agent** - Aggregate info from multiple data sources
- **Approval Workflow Agent** - Guide users through approval processes
- **Connected Agent Architecture** - Multiple agents working together

---

## 🚀 Quick Start

### Development Approaches

Choose the approach that matches your skill level and time:

| Approach | Difficulty | Time to MVP | Best For |
|----------|------------|-------------|----------|
| **Declarative Agents** | ⭐ Easy | 15-20 min | Beginners, quick demos |
| **Copilot Studio** | ⭐⭐ Medium | 20-30 min | No-code/low-code fans |
| **Custom Engine Agents** | ⭐⭐⭐ Advanced | 45+ min | Full control needed |

---

### 🔹 Option 1: Declarative Agents (Recommended for 90 min)

Build quickly using Microsoft 365 Agents Toolkit in VS Code:

#### Prerequisites
- VS Code with [M365 Agents Toolkit](https://marketplace.visualstudio.com/items?itemName=TeamsDevApp.ms-teams-vscode-extension)
- Node.js (LTS version)
- Microsoft 365 developer tenant

#### 10-Minute Setup

1. **Open VS Code** and ensure M365 Agents Toolkit is installed

2. **Create a new Declarative Agent**
   - Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on Mac)
   - Select **M365 Agents Toolkit: Create a New App**
   - Choose **Agent** → **Declarative Agent**
   - Follow the wizard to configure your agent

3. **Configure your agent's instructions**

Edit the declarative manifest to define your agent's behavior:

```json
{
  "name": "My Enterprise Agent",
  "description": "Helps employees with [your use case]",
  "instructions": "You are a helpful assistant that helps employees with [specific task]. Always be professional and cite sources when possible.",
  "capabilities": {
    "web_search": true,
    "code_interpreter": false
  },
  "conversation_starters": [
    "How do I submit an expense report?",
    "What is the vacation policy?",
    "Help me find information about..."
  ]
}
```

4. **Test your agent**
   - Press `F5` to launch in Microsoft 365 Copilot
   - Test with sample queries

---

### 🔹 Option 2: Microsoft Copilot Studio (No-Code)

Build using the visual designer:

1. **Go to [copilotstudio.microsoft.com](https://copilotstudio.microsoft.com)**

2. **Create a new agent**
   - Click **Create** → **New agent**
   - Name your agent and describe its purpose

3. **Add knowledge sources**
   - SharePoint sites
   - Uploaded documents
   - Website URLs

4. **Configure conversation topics**
   - Create topics for specific user intents
   - Add trigger phrases
   - Design conversation flows

5. **Test and publish**
   - Use built-in test chat
   - Publish to Microsoft 365 Copilot

---

### 🔹 Option 3: Custom Engine Agents (Advanced)

Full code control with C# or TypeScript:

#### Prerequisites
- Visual Studio 2022 or VS Code
- .NET 8 SDK
- M365 Agents Toolkit extension

#### Quick Setup

1. **Create a new Custom Engine Agent project**
   - In Visual Studio: File → New → Project → search "Microsoft 365 Agent"
   - In VS Code: Use M365 Agents Toolkit to scaffold

2. **Implement your agent logic**

```csharp
// Example: Simple response handler
public async Task<string> HandleMessageAsync(string userMessage)
{
    // Add your custom logic here
    var response = await _aiService.GenerateResponseAsync(
        systemPrompt: "You are a helpful enterprise assistant...",
        userMessage: userMessage
    );
    
    return response;
}
```

3. **Test locally with Bot Framework Emulator**

---

## 🛡️ Security Reminders

⚠️ **Important for enterprise agents:**

- Never hardcode API keys or secrets
- Use managed identities when possible
- Don't expose sensitive company data in demos
- Follow least-privilege principles

---

## 📋 Requirements & Evaluation

### Core Requirements

1. **Use M365 Agents Toolkit** - Your agent must integrate with Microsoft 365
2. **Enterprise scenario** - Address a real business need
3. **Working demo** - Functional and demoable in 2 minutes

### Evaluation Criteria

| Criterion | Weight | Description |
|-----------|--------|-------------|
| Enterprise Value | 30% | Solves a real business problem |
| M365 Integration | 25% | Effective use of M365 ecosystem |
| Functionality | 25% | Does it work? Is it useful? |
| Presentation | 20% | Clear demo, good documentation |

### Bonus Points

| Bonus | Points | Description |
|-------|--------|-------------|
| Adaptive Cards UI | +5 | Rich, interactive UI |
| Multiple data sources | +5 | Integrates various knowledge sources |
| Connected agents | +10 | Multi-agent architecture |

---

## 📚 Resources

### Official Documentation
- [M365 Agents Toolkit](https://aka.ms/m365-agents-toolkit)
- [Copilot Dev Camp](https://aka.ms/copilotdevcamp)
- [Declarative Agents Docs](https://aka.ms/declarative-agents-docs)
- [Copilot Studio](https://learn.microsoft.com/microsoft-copilot-studio/)

### Quick References
- [Agent Academy](https://aka.ms/agentacademy) - Learning paths
- [Extend M365 Copilot](https://microsoft.github.io/copilot-camp/pages/extend-m365-copilot/)
- [Adaptive Cards Designer](https://adaptivecards.io/designer/)

---

## ❓ FAQ

### Do I need a Microsoft 365 Copilot license?

No! Your agent can target **Copilot Free** and doesn't require a paid license.

### What if I don't have a dev tenant?

Talk to a roaming expert - we can help you get access or find an alternative approach.

### Can I use vibe-coding/AI assistance?

Yes! Using GitHub Copilot and other AI tools is encouraged.

### What's the fastest path to a working demo?

Declarative Agents with M365 Agents Toolkit. You can have a working agent in 15-20 minutes.

---

**Good luck! Build something that makes work easier! 💼**
