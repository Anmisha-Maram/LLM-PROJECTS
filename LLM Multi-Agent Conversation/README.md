# LLM Multi-Agent Conversation

**3 specialized bots debate "Tech vs Sports careers"** using OpenAI + Ollama + Groq APIs.

## Demo
<img width="2006" height="1454" alt="image" src="https://github.com/user-attachments/assets/61f9815b-54c3-408d-a380-c70ece43344d" />


## Tech Stack
- **Bunny**: OpenAI GPT-4.1-nano (Argumentative)
- **Anu**: Groq Llama 3.3 70B (Analytical)  
- **Rushi**: Ollama GPT-OSS 20B (Mediator)

## Run locally
```bash
pip install -r requirements.txt
python user.py
```

## Key Features
- Multi-LLM orchestration (OpenAI-compatible endpoints)
- Turn-taking conversation engine
- Rate limit handling
- Shared conversation memory
