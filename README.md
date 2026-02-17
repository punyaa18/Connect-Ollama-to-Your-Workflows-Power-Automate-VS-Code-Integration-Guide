# Ollama Integration: Power Automate + VS Code

> **Run local AI models seamlessly with Power Automate workflows and VS Code development**  

[![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)](https://www.python.org/downloads/)
[![Ollama](https://img.shields.io/badge/Ollama-Local%20LLM-green.svg)](https://ollama.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## Overview

This repository demonstrates how to integrate **Ollama** — a local Large Language Model (LLM) runtime — with **Power Automate** and **VS Code** to create powerful, privacy-focused AI workflows. Run models like LLaMA2, Mistral, or Gemma entirely on your machine without cloud dependencies.

### Why This Matters

- **Privacy-First**: Keep sensitive data local — no cloud APIs required
- **Real-Time Automation**: Trigger AI-powered workflows with Power Automate
- **Developer-Friendly**: Full VS Code integration with Python
- **Offline Capable**: Works without internet connectivity
- **Custom Models**: Build and deploy your own models using Modelfiles

## Features

- Complete Ollama installation and setup guide
- Terminal command reference for model management
- VS Code Python integration examples
- Power Automate workflow templates
- Model interaction best practices
- Local API server configuration

## Quick Start

## Simple Flowchart

```mermaid
flowchart TD
   A[User or system event] --> B[Power Automate flow]
   B --> C[Python script in VS Code]
   C --> D[Ollama local model]
   D --> E[Model response]
   E --> F["Automated action (email, Teams, SharePoint, approval)"]
```

### Prerequisites

- Windows, macOS, or Linux
- Python 3.7 or higher
- VS Code (recommended)
- 8GB+ RAM (16GB recommended for larger models)

### Installation

1. **Install Ollama**
   ```bash
   # Visit https://ollama.com/download
   # Run the installer for your OS
   
   # Verify installation
   ollama --version
   ```
<img width="640" height="254" alt="image" src="https://github.com/user-attachments/assets/627da39f-d4ab-4386-b8bc-8ed4b52608f3" />

2. **Download a Model**
   ```bash
   # Pull a model (e.g., Mistral)
   ollama pull mistral
   
   # Verify download
   ollama list
   ```
<img width="750" height="252" alt="image" src="https://github.com/user-attachments/assets/c3d5d55f-4f20-4bc9-adda-05111d4b1838" />

3. **Install Python Package**
   ```bash
   pip install ollama
   ```

4. **Run Your First Query**
   ```bash
   ollama run mistral
   ```

## Usage Examples

### Python Integration (VS Code)

```python
import ollama

response = ollama.chat(
    model='mistral',
    messages=[{
        'role': 'user',
        'content': 'Explain quantum computing in simple terms'
    }],
    options={
        'temperature': 0.8  # More creative responses
    }
)

print(response['message']['content'])
```

### Terminal Commands

| Command | Description | Example |
|---------|-------------|---------|
| `ollama run <model>` | Start interactive chat | `ollama run mistral` |
| `ollama pull <model>` | Download a model | `ollama pull llama2` |
| `ollama list` | List installed models | `ollama list` |
| `ollama serve` | Start API server | `ollama serve` |

### In-Chat Commands

While interacting with a model:

- `/?` or `/help` - Show available commands
- `/bye` - Exit chat session
- `/system` - Set system prompt
- `/reset` - Clear conversation history

<img width="750" height="421" alt="image" src="https://github.com/user-attachments/assets/b85496be-df0e-4b5a-87d6-4734f98b2c80" />

## Documentation

**Main Guides:**
- **[blog.md](blog.md)** - Complete tutorial and walkthrough
- **[POWER_AUTOMATE_SETUP.md](POWER_AUTOMATE_SETUP.md)** - Detailed Power Automate integration guide


## Available Models
(make sure you have enough space to download and run the model, choose smaller ones in the beginning.)
Explore models at [ollama.com/library](https://ollama.com/library):

- **llama2** - Meta's powerful open-source model
- **mistral** - Fast and efficient 7B parameter model (recommeded)
- **gemma** - Google's lightweight AI model


## Power Automate Integration

This project enables you to:

1. Trigger AI responses from Power Automate flows
2. Generate automated email replies
3. Summarize content for SharePoint
4. Log AI interactions to Teams
5. Create custom approval workflows
6. Basically you can customize it to do and say whatever you want!



**Connection issues?**
- Verify Ollama is running on port 11434 (default) or try running ollama serve on your cmd
- Check firewall settings for localhost connections


## Resources

- [Ollama Official Documentation](https://ollama.com/)
- [Ollama GitHub Repository](https://github.com/ollama/ollama)
- [Model Library](https://ollama.com/library)
- [Python Package Documentation](https://github.com/ollama/ollama-python)

-https://blogs.perficient.com/2025/07/30/ollama-power-automate-integration/
