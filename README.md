# Ollama Demo - Interactive Agent with Web Search

This repository demonstrates how to build an intelligent agent using Ollama that can interact with users and perform web searches to answer questions.

## What is Ollama?

Ollama is a tool that allows you to run open-source large language models (LLMs) locally on your machine. It supports a variety of models, including Llama 2, Code Llama, Qwen, and others, bundling model weights, configuration, and data into a single package defined by a Modelfile.

## Project Features

### Interactive AI Agent (agent.py)
- **Multi-turn conversations**: Engage in ongoing dialogues with the AI
- **Web search integration**: Agent can search the web and fetch content to answer questions
- **Robust error handling**: Graceful handling of connection issues and API errors
- **Type-safe implementation**: Full type hints and proper error handling
- **User-friendly interface**: Clear progress indicators and formatted output
- **Context management**: Smart truncation of results to prevent token overflow

### Available Tools
- **Web Search**: Search the internet for current information
- **Web Fetch**: Retrieve and analyze content from specific URLs
- **Thinking Mode**: See the AI's reasoning process

## Quick Start

### Option 1: Using Docker (Recommended)

1. **Start Ollama container**:
   ```bash
   docker-compose up -d
   ```

2. **Access the container**:
   ```bash
   docker exec -it ollama bash
   ```

3. **Install required model**:
   ```bash
   ollama pull gpt-oss
   ```

4. **Run the agent**:
   ```bash
   python agent.py
   ```

### Option 2: Local Installation

1. **Install Ollama**: Visit [ollama.com/download](https://ollama.com/download)

2. **Start Ollama service**:
   ```bash
   ollama serve
   ```

3. **Install required model**:
   ```bash
   ollama pull gpt-oss
   ```

4. **Install Python dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

5. **Run the agent**:
   ```bash
   python agent.py
   ```

## Usage Examples

### Basic Interaction
```
Enter your question (or press Enter for default): What is the latest news about AI?

Thinking: I need to search for recent AI news to provide current information...
Tool calls: 1
  Tool 1: web_search
    Arguments: {'query': 'latest AI news 2024'}
    Result (first 200 chars): Recent developments in artificial intelligence include...
Response: Based on my search, here are the latest developments in AI...
```

### Multi-turn Conversation
```
Final response received. Would you like to ask another question?

Enter your next question (or 'quit'/'exit' to stop): Tell me more about that company

Thinking: The user wants more details about the company mentioned...
```

## Dependencies

See [requirements.txt](requirements.txt) for the complete list of Python dependencies:

- `ollama==0.6.0` - Official Ollama Python SDK
- `httpx==0.28.1` - HTTP client for web requests
- `pydantic==2.11.9` - Data validation and type safety
- Other supporting libraries for async operations and type checking

## Project Structure

```
├── agent.py              # Main interactive agent with web search
├── docker-compose.yml    # Docker setup for Ollama service
├── requirements.txt      # Python dependencies
├── README.md             # This file
└── .gitignore            # Git ignore rules
```

## Key Features of the Agent

- **Robust Error Handling**: Handles connection issues, API errors, and tool failures
- **Interactive Loop**: Supports multi-turn conversations with context retention
- **Web Integration**: Can search and fetch web content in real-time
- **Thinking Mode**: Shows the AI's reasoning process
- **Performance Optimized**: Smart context management and result truncation
- **User-Friendly**: Clear feedback, progress indicators, and easy exit options

## Troubleshooting

### Common Issues

1. **Connection Error**: Ensure Ollama is running (`ollama serve`)
2. **Model Not Found**: Install the required model (`ollama pull gpt-oss`)

### Getting Help

- Verify Ollama installation at [ollama.com](https://ollama.com)
- Ensure all dependencies are installed: `pip install -r requirements.txt`
- Check Ollama service status: `docker compose up -d` or local service status

## References

- [Ollama Official Repository](https://github.com/ollama/ollama)
- [Ollama Python SDK Documentation](https://github.com/ollama/ollama-python)
- [Available Models](https://ollama.com/library)