# Perplexity 2.0

A Perplexity-like AI-powered search and chat application that combines language models with real-time web search capabilities.

## Features

- Real-time web search integration
- AI-powered responses with source citations
- Streaming chat interface
- Conversation history with checkpoints
- Visual search process indicators (searching, reading, writing)

## Tech Stack

- **Frontend**: Next.js with React
- **Backend**: FastAPI with LangGraph
- **LLM**: Groq (Llama 3.1 8B)
- **Search**: Tavily AI Search
- **Deployment**: Render

## Architecture

The application consists of two main components:

1. **Client**: A Next.js frontend with a chat interface
2. **Server**: A FastAPI backend with LangGraph workflow

## Installation

### Backend (Server)

```bash
cd Server
pip install -r requirements.txt
```

Create a `.env` file with your API keys:

```env
GROQ_API_KEY=your_groq_api_key_here
TAVILY_API_KEY=your_tavily_api_key_here
```

Run the backend:

```bash
cd Server
uvicorn app:app --reload
```

### Frontend (Client)

```bash
cd Client
npm install
npm run dev
```

## Environment Variables

- `GROQ_API_KEY`: API key for Groq LLM service
- `TAVILY_API_KEY`: API key for Tavily search service
- `NEXT_PUBLIC_API_URL`: URL of the backend API (for deployment)

## API Endpoints

- `GET /chat_stream/{message}`: Streamed chat responses with search results

## Deployment

The application is designed to be deployed on Render:
- Backend: FastAPI application
- Frontend: Next.js application

## How It Works

1. User submits a query
2. The LLM decides whether to use search tools
3. If search is needed, Tavily is called
4. Results are processed and formatted
5. Response is streamed back to the frontend
6. Frontend displays search stages and final answer

## License

MIT# perplexity2.0
