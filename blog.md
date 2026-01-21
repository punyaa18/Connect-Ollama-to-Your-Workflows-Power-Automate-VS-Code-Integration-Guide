# Connect Ollama to Your Workflows: Power Automate + VS Code Integration Guide

**By Punyaa Dixit | Published: July 30th, 2025**

![Artificial Intelligence Banner](assets/ai-banner.jpg)

---

## Introduction

AI is evolving rapidly, and the ability to install Ollama local models on your machine opens up powerful new possibilities for developers, hobbyists, and builders. Whether you're working on automation, development tools, or privacy-sensitive applications, cloud-based models aren't always ideal.

That's where **Ollama** comes in.

Ollama makes it easy to run, customize, and serve LLMs directly from your machine — no GPU setup or Docker needed. You can run models like LLaMA2, Mistral, or Gemma, or even build your own using a simple Modelfile.

To take it further, you can integrate Ollama with **Power Automate** to trigger real-time, AI-powered workflows — all while keeping your data local and secure. This integration lets you automate tasks like generating email replies, summarizing content, or logging AI responses to SharePoint or Teams — without relying on cloud APIs.

In this blog, I'll walk you through everything you need to get started with Ollama — from downloading and interacting with models in VS Code to integrating responses into Power Automate flows.

---

## What is Ollama?

Ollama is a **local LLM (Large Language Model) runtime** that can be installed directly on your PC, making it completely cloud independent. You can use it as your personal AI assistant with the added benefit of enhanced security and privacy since everything runs locally.

---

## Why Do We Need Ollama?

✅ **Works without internet** — ideal for offline or network-restricted environments  
✅ **No cloud dependency** — full control over your data and usage  
✅ **Acts like a custom assistant** tailored to your tasks  
✅ **Allows you to build your own models** using a simple Modelfile

---

## Steps to Download and Install Ollama

### 1. Download Ollama

Visit the official site: [https://ollama.com/download](https://ollama.com/download)

You can install Ollama local models on **Windows, macOS, or Linux**, depending on your OS.

### 2. Install Ollama

Run the downloaded installer (`.exe` or `.dmg`)

### 3. Verify Installation

Once you install Ollama local models, you can run them directly in your command prompt but first check whether it was installed or not with:

```bash
ollama --version
```

or

```bash
ollama
```

### 4. Explore Commands

Explore the available commands using:

```bash
ollama --help
```

![Command Prompt](assets/command-prompt.png)

---

## Ollama Command Reference (Terminal Commands)

| Command | Context | Description | Example |
|---------|---------|-------------|---------|
| `ollama run` | Terminal | Runs the specified model for chat interaction. | `ollama run mistral` |
| `ollama pull` | Terminal | Downloads the model to your machine. | `ollama pull llama2` |
| `ollama list` | Terminal | Shows all downloaded models locally. | `ollama list` |
| `ollama create -f Modelfile` | Terminal | Creates a new model from a custom Modelfile. | `ollama create mistral_assistant -f Modelfile` |
| `ollama serve` | Terminal | Starts the Ollama API server for integrations. | `ollama serve` |

---

## Downloading a Model / Choosing a Model

### 1. Browse the Model Library

Visit the model library: [https://ollama.com/library](https://ollama.com/library) — here, you can explore model usage, specialties, and space requirements.

### 2. Choose a Model

Choose a model (e.g., `mistral`)

### 3. Pull the Model

Pull the model by running:

```bash
ollama pull mistral
```

or

```bash
ollama pull <model_name>
```

### 4. Confirm Download

Confirm the download with:

```bash
ollama list
```

### 5. Interact with the Model

To interact with the model, use:

```bash
ollama run mistral
```

or

```bash
ollama run <model_name>
```

![Terminal Command for Run](assets/terminal-run.png)

When you're done, type `/bye` to end the session — otherwise, it will keep running in the background.

Inside the model session, use `/help` or `/?` to see available commands.

---

## In-Model Commands

When you're interacting inside a model session (after running `ollama run <model>`), the following shortcuts and commands are available:

| Command | Description | Example |
|---------|-------------|---------|
| `/?` or `/help` | Lists all available chat commands. | `/?` |
| `/bye` | Ends the current model session. | `/bye` |
| `/system` | Sets a system prompt to guide the model's behavior. | `/system You are a polite assistant.` |
| `/reset` | Clears the current conversation history. | `/reset` |

---

## Using Ollama in VS Code

### 1. Install the Python Package

```bash
pip install ollama
```

### 2. Ensure Ollama is Running

Ensure Ollama is running in the background by either:

- Running `ollama serve` in the terminal, or
- Searching for "Ollama" and clicking on its icon.

### 3. Use this Sample Python Script

Use this sample Python script to interact with a model:

```python
import ollama

response = ollama.chat(
    model='mistral',
    messages=[
        {
            'role': 'user',
            'content': 'Explain quantum computing in simple terms'
        }
    ],
    options={
        'temperature': 0.8
    }
)

print(response['message']['content'])
```

---

## Understanding the Code

Now let's understand what each part of the code means:

| Code Line | Explanation |
|-----------|-------------|
| `import ollama` | Imports the Ollama Python library to interact with local language models. |
| `model='mistral', options={'temperature': 0.8}` | Specifies the model to use (`mistral`) and sets the temperature option.<br><br>**temperature = 0.8** means the output will be more creative and diverse.<br><br>Lower values (e.g., 0.2) produce more focused and predictable answers. |
| `messages=[{'role': 'user', 'content': 'Explain quantum computing in simple terms'}]` | Defines the user message you want to send to the model.<br><br>You can add multiple messages in a list to maintain chat context. |
| `print(response['message']['content'])` | Displays only the model's reply (text content) in the console. |

---

## Next Steps

Now that you have Ollama running locally and integrated with VS Code, you can:

1. **Build custom models** using Modelfiles
2. **Create Power Automate flows** that call Ollama APIs
3. **Automate business processes** with local AI
4. **Experiment with different models** for various use cases

---

## Conclusion

Ollama represents a significant shift in how we can leverage AI — bringing powerful language models directly to your machine without cloud dependencies. Combined with Power Automate and VS Code, you have a complete toolkit for building intelligent, automated, and privacy-focused applications.

Start experimenting today and discover what's possible when AI runs locally on your terms.

---

**Have questions or want to share your Ollama projects?** Connect with me or leave a comment below!

**Tags:** #ArtificialIntelligence #Ollama #PowerAutomate #VSCode #LocalAI #LLM #Automation #Python
