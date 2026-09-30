# 🧠 ResearchMind — Multi-Agent AI Research System

ResearchMind is a **Python-based multi-agent AI research assistant** that automates web research, content extraction, report generation, and AI-powered review.

It uses **LangChain, Tavily, BeautifulSoup, and LLMs** to transform a research topic into a structured report with critic feedback.

## ✨ Features

* 🤖 Multi-agent AI research workflow
* 🔎 Web search using Tavily
* 🌐 Web scraping with Requests + BeautifulSoup
* 📝 Automated research report generation
* 🔍 AI-powered report critique and scoring
* 🖥️ Streamlit web interface
* 💻 CLI-based execution
* 🔄 Support for multiple LLM providers
* 📥 Downloadable Markdown reports
* 🔐 `.env`-based API key configuration

## 🏗️ Architecture

```text
User Topic
    ↓
Search Agent
    ↓
Web Scraper / Reader
    ↓
Research Writer
    ↓
Critic Agent
    ↓
Final Report + Feedback
```

### Workflow

1. **Search Agent** — Uses Tavily to find relevant web sources.
2. **Reader Agent** — Scrapes and extracts content from a selected source.
3. **Writer Chain** — Uses the search results and extracted content to generate a structured report.
4. **Critic Chain** — Reviews the report and provides a score, strengths, improvements, and verdict.

## 🛠️ Tech Stack

* **Python**
* **LangChain**
* **Streamlit**
* **Tavily Search**
* **BeautifulSoup**
* **Requests**
* **python-dotenv**
* **Google Generative AI**
* Optional: OpenAI, Groq, Mistral, OpenRouter, NVIDIA

## 📁 Project Structure

```text
multi_agent_research_system/
├── README.md
├── app.py
├── agents.py
├── pipeline.py
├── tools.py
├── requirements.txt
├── .env
└── .venv/
```

| File               | Purpose                                |
| ------------------ | -------------------------------------- |
| `app.py`           | Streamlit application and UI           |
| `agents.py`        | LLM configuration, prompts, and chains |
| `pipeline.py`      | CLI research pipeline                  |
| `tools.py`         | Tavily search and web scraping tools   |
| `requirements.txt` | Python dependencies                    |

## 🚀 Installation

Clone the repository:

```bash
git clone https://github.com/Faizal-Mistry/multi_agent_research_system.git
cd multi_agent_research_system
```

Create and activate a virtual environment:

### Windows

```bash
python -m venv .venv
.venv\Scripts\activate
```

### macOS/Linux

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## 🔐 Environment Variables

Create a `.env` file in the project root:

```env
TAVILY_API_KEY=your_tavily_api_key
GOOGLE_API_KEY=your_google_api_key
OPENAI_API_KEY=your_openai_api_key
```

`TAVILY_API_KEY` is required for web search, while the key for the selected LLM provider is required for report generation.

> Never commit your `.env` file or API keys to GitHub.

## ▶️ Running the Project

### Streamlit UI

```bash
streamlit run app.py
```

### CLI

```bash
python pipeline.py
```

Example research topic:

```text
Quantum computing breakthroughs in 2025
```

The system searches the web, extracts relevant content, generates a report, and evaluates the result.

## 🧩 LLM Integration

The default configuration uses Google Generative AI through LangChain:

```python
llm = ChatGoogleGenerativeAI(
    model="gemini-3.8-flash",
    temperature=0
)
```

Other providers can be configured in `agents.py`.

## ⚠️ Important Notes

* API keys are required to use external services.
* Web scraping depends on the target website and may be blocked.
* Respect website Terms of Service and scraping policies.
* Tavily and LLM providers may have rate limits or usage costs.
* This project is intended as a **learning and rapid-prototyping project**, not a production-grade research platform.

## 🚀 Future Improvements

* Multi-source research and source verification
* Fact-checking agent
* Search-result caching
* Better error handling and retries
* Automated testing
* Research history
* Docker and CI/CD support
* Parallel/async research agents

## 📊 Project Status

**Status: 🟢 Working Prototype**

ResearchMind demonstrates how multiple AI agents and external tools can be combined to build an automated research workflow using LangChain.

## 👨‍💻 Author

**Faizal Mistry**

* GitHub: https://github.com/Faizal-Mistry
* Repository: https://github.com/Faizal-Mistry/multi_agent_research_system

## 📄 License

No explicit license is currently included in this repository. Consider adding an MIT or Apache 2.0 license if you plan to distribute the project publicly.
