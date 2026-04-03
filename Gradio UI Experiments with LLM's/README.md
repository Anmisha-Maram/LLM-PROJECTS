# Gradio UI Experiments with LLMs

This project contains my hands-on practice with **Gradio** for building interactive LLM-powered user interfaces.

## Project Overview

This notebook explores how to build Gradio interfaces from simple input/output demos to more advanced authenticated and streaming applications.

The notebook covers:
- Basic Gradio interfaces
- Launching apps locally and in the browser
- Public sharing with `share=True`
- Authentication with username and password
- Dark mode and default theme behavior
- Markdown outputs
- Streaming outputs using `yield`
- Multi-model selection
- A company brochure generator app

## What I Learned

### 1. Basic Gradio Interfaces
Started with a very simple function and wrapped it in a Gradio interface using:

```python
gr.Interface(...)
```

This helped me understand:
- inputs
- outputs
- launching a UI
- testing functions interactively

### 2. Launch Options
I learned how different Gradio launch options work:

- `launch()` → runs locally
- `launch(inbrowser=True)` → opens automatically in browser
- `launch(share=True)` → creates a public shareable link

### 3. Authentication
The notebook also includes **authenticated Gradio apps** using:

```python
auth=("username", "password")
```

This allows access control so only users with the correct login can open the interface.

### 4. Dark Mode and Light Mode
Gradio normally follows the browser or system theme automatically, so it may appear in **light mode** or **dark mode** depending on your machine settings.

This notebook also demonstrates how to **force dark mode** using custom JavaScript so the interface always opens in dark theme when needed.

### 5. Markdown Output
Instead of returning plain text only, I learned how to display model responses in **Markdown** format for cleaner and richer output.

This improves readability for:
- bullet points
- headings
- formatted explanations

### 6. Streaming with `yield`
One of the most important things I learned was how to use **`yield`** for streaming.

### What is `yield`?
`yield` is a Python keyword used in **generator functions**.  
Instead of returning the full result at once, it sends back partial results step by step.

In this Gradio project, `yield` is used to:
- stream LLM responses live
- show text as it is being generated
- create a more real-time chatbot experience

So instead of waiting for the full answer, the UI updates gradually while the model is responding.

### 7. Multi-Model Usage
The notebook also shows how to connect multiple providers, including:
- OpenAI
- Groq
- Anthropic
- Google / Gemini
- Ollama 

This helped me understand how Gradio can be used as a frontend layer for different LLM backends.

### 8. Company Brochure Generator
A more advanced app in the notebook generates a **company brochure** from a website URL.

This combines:
- website content fetching
- prompt design
- model response generation
- Gradio interface building

It is a good example of moving from a toy interface to a more practical LLM use case.

## Tech Stack

- Python
- Gradio
- OpenAI API
- Groq API
- Anthropic API
- Google / Gemini API
- Ollama
- python-dotenv
- Jupyter Notebook

## Setup Instructions

### 1. Clone the repository
```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### 2. Create and activate a virtual environment

**Windows**
```bash
python -m venv .venv
.venv\Scripts\activate
```

**Mac/Linux**
```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install required libraries
```bash
pip install -r requirements.txt
```

Suggested `requirements.txt`:

```txt
gradio
openai
python-dotenv
requests
jupyter
ipykernel
beautifulsoup4
```

## API Keys

Create a file named `.env` in the project root and store your keys there.

Example:

```env
OPENAI_API_KEY=your_openai_key_here
GROQ_API_KEY=your_groq_key_here
ANTHROPIC_API_KEY=your_anthropic_key_here
GOOGLE_API_KEY=your_google_key_here
```

### Important
- Never hardcode API keys in the notebook
- Never upload `.env` to GitHub
- Add `.env` to `.gitignore`

Example `.gitignore`:

```txt
.env
.venv/
__pycache__/
.ipynb_checkpoints/
```

## Loading Environment Variables

The notebook uses `python-dotenv` to load keys from `.env`.

Example:

```python
from dotenv import load_dotenv
import os

load_dotenv(override=True)

openai_api_key = os.getenv("OPENAI_API_KEY")
groq_api_key = os.getenv("GROQ_API_KEY")
anthropic_api_key = os.getenv("ANTHROPIC_API_KEY")
google_api_key = os.getenv("GOOGLE_API_KEY")
```

## Notes

- If Gradio becomes slow, close old running servers before launching a new one.
- The notebook includes a helper to close all active Gradio apps.
- Public sharing may require additional setup depending on your system.
- Dark mode can be forced using JavaScript customization.
- Streaming responses are implemented using Python generators and `yield`.

## Learning Credit

This notebook was learned from **Edward Donner's Udemy course**.  
A significant portion of the notebook structure and examples are based on his teaching material, and I used them to practice and understand how to build Gradio interfaces for LLM applications.

## Outcome

By completing this notebook, I learned how to:
- build Gradio apps from scratch
- connect LLM providers to UI components
- secure apps with authentication
- style or control theme behavior
- stream model responses with `yield`
- move from simple demos to practical mini-applications
