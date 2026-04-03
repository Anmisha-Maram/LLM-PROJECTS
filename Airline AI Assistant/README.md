# Airline AI Assistant

**AI-powered customer support chatbot** for FlightAI airline with **RAG + Tool Calling**. Built using OpenAI GPT-4.1-mini and Gradio interface.

## Features

- **Retrieval-Augmented Generation (RAG)** for airline-specific knowledge
- **Tool calling** for dynamic pricing lookup from SQLite database
- **Gradio chat interface** with real-time responses
- **Streaming** responses using `yield`
- **Production-ready** error handling and database integration

## How It Works

1. **Customer asks question** → "What's the price to London?"
2. **RAG retrieves** relevant airline docs
3. **Tool calling detects** price query → calls `get_ticket_price()`
4. **Database lookup** → returns accurate pricing
5. **Combined response** streamed back to user

## Demo Flow

```
User: "What's the price to Tokyo?"
↓
RAG finds docs + Tool calls get_ticket_price("Tokyo")
↓
Database returns "Tokyo: $1420"
↓
GPT generates: "The price of a ticket to Tokyo is $1420"
```

## Tech Stack

```
OpenAI GPT-4.1-mini | Gradio | SQLite | RAG | Tool Calling | python-dotenv
```

## Setup Instructions

### 1. Clone & Environment
```bash
git clone https://github.com/yourusername/airline-ai-assistant.git
cd airline-ai-assistant
python -m venv .venv
# Windows: .venv\Scripts\activate
# Mac/Linux: source .venv/bin/activate
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

**requirements.txt:**
```txt
openai
gradio
python-dotenv
jupyter
ipykernel
requests
```

### 3. API Keys (`.env`)
Create `.env` file:

```env
OPENAI_API_KEY=your_openai_key_here
```

### 4. Run
```bash
cursor 
```
Open `Airline-AI-Assistant.ipynb` → run all cells.

## Key Components

### 1. **RAG Pipeline**
Retrieves relevant airline documents before LLM generation.

### 2. **Tool Calling**
```python
def get_ticket_price(city):
    # SQLite lookup for real-time pricing
    return f"Ticket price to {city} is ${price}"
```

### 3. **Streaming Chat**
```python
gr.ChatInterface(fn=chat, title="FlightAI Assistant")
```

### 4. **Database Integration**
SQLite `prices.db` stores dynamic pricing:

```
london  → $799
paris   → $899  
tokyo   → $1420
```

## Skills Demonstrated

✅ **RAG implementation**  
✅ **Tool/function calling**  
✅ **Database integration**  
✅ **Streaming responses**  
✅ **Production Gradio UI**  
✅ **Environment variable management**  
✅ **Error handling**  

## Example Interactions

```
User: "What's the price to Tokyo?"
Bot: "The price of a ticket to Tokyo is $1420."

User: "Do you fly to Sydney?"
Bot: "No price data available for Sydney."
```

## Production Features

- **Close all Gradio servers** before launching new ones
- **Environment-based API keys**
- **Database-backed pricing**
- **Real-time tool calling**
- **Streaming for better UX**

## Notes

- **Ollama alternative** available (uncomment lines in notebook)
- **Database resets** on each run (pricing data re-populated)
- **Tool calling** handles multiple calls in sequence

## Future Improvements

- Persistent database
- Flight booking API integration
- Multi-language support
- Voice input/output

***

**Built as part of LLM engineering learning portfolio** 🎓
