
# 🌐 MCP Multi-Tool Chatbot

An AI-powered chatbot that connects to multiple microservices (MCP servers) for executing specialized tasks like **math operations** and **weather retrieval** using **LangChain MCP Adapters**, **LangGraph**, and **Groq's Qwen-32B** model.

---

## 🚀 Features

* 🤖 LangGraph-powered agent with ReAct framework
* 🔧 Supports multiple tools: Math (Add, Multiply), Weather
* 🔌 Interoperable tool access via `MultiServerMCPClient`
* ⚡ Groq-hosted Qwen-32B model for fast LLM inference
* 🧩 Seamlessly integrates local (stdio) and HTTP-streamed MCP tools

---

## 🛠️ Tech Stack

* `mcp`
* `langchain-groq`
* `langchain-mcp-adapters`
* `langgraph`
* `Python 3.10+`
* `.env` (for `GROQ_API_KEY`)

---

## 📁 Project Structure

```
.
├── mathserver.py         # MCP server for Math tools
├── weatherserver.py      # MCP server for Weather tool
├── main.py               # Chatbot agent with LangGraph + MCP client
├── .env                  # Contains GROQ_API_KEY
├── README.md
```

---

## 📦 Installation

```bash
git clone https://github.com/Hari-Kec/MCP-Chatbot.git
cd MCP-Chatbot

pip install -r requirements.txt
```

Add a `.env` file:

```
GROQ_API_KEY=your_groq_api_key
```

---

## 📜 Usage

### 🧮 Math Server (stdio)

```bash
python mathserver.py
```

### 🌦 Weather Server (streamable HTTP)

```bash
uvicorn weatherserver:app --port 8000
```

### 🧠 LangGraph Agent

```bash
python main.py
```

---

## 🧪 Sample Output

```bash
Math response: The answer is 96
Weather response: It's always raining in California
```

---

## 📚 Tools Defined

### Weather Tool

```python
@mcp.tool()
async def get_weather(location: str) -> str:
    return "It's always raining in California"
```

### Math Tools

```python
@mcp.tool()
def add(a: int, b: int) -> int:
    return a + b

@mcp.tool()
def multiple(a: int, b: int) -> int:
    return a * b
```

---

## 🔮 Future Enhancements

* ✅ Add real-time weather API integration
* ✅ Add more advanced math functions
* ✅ Implement memory and context in LangGraph

---

## 📝 License

MIT License

---

## 🙌 Acknowledgements

* [LangChain](https://www.langchain.com/)
* [Groq](https://www.groq.com/)
* [LangGraph](https://docs.langgraph.io/)
* [MCP](https://github.com/langchain-ai/mcp)


