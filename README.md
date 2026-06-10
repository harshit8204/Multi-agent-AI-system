# 🔬 ResearchMind — Multi-Agent AI Research System

> Four specialized AI agents collaborate — searching, scraping, writing, and critiquing — to deliver a polished research report on any topic.

---

## 🌐 Live Demo

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://your-app-url.streamlit.app)

> 🔗 **Deployed Link:** [https://your-app-url.streamlit.app](https://multi-agent-ai-system-cpgpzelnnlslk9scwvgcps.streamlit.app/)
> 

---

## 📸 Screenshots

> *(Add your screenshots in a `/screenshots` folder in the repo root and update the paths below)*

### 🏠 Home Page
![Home Page](Demo/Demo1.jpg)

### ⚡ Pipeline Running
![Pipeline Running](Demo/Demo4.jpg)

### 📄 Research Report Output
![Research Report](Demo/Demo5.jpg)

### 🧐 Critic Feedback
![Critic Feedback](Demo/Demo6.jpg)

---

## 🧠 How It Works

ResearchMind runs a 4-step agentic pipeline:

```
User Input (Topic)
      │
      ▼
┌─────────────────┐
│  01 Search Agent │  ← Tavily API: finds recent, reliable web results
└────────┬────────┘
         ▼
┌─────────────────┐
│  02 Reader Agent │  ← Scrapes the most relevant URL for deep content
└────────┬────────┘
         ▼
┌─────────────────┐
│  03 Writer Chain │  ← Mistral AI: drafts a structured research report
└────────┬────────┘
         ▼
┌─────────────────┐
│  04 Critic Chain │  ← Mistral AI: scores and reviews the report
└─────────────────┘
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| LLM | Mistral AI (`mistral-small-2603`) |
| Agent Framework | LangChain + LangGraph |
| Web Search | Tavily API |
| Web Scraping | BeautifulSoup4 + Requests |
| Frontend | Streamlit |
| Environment | Python-dotenv |

---

## 📁 Project Structure

```
Multi-agent-research-system/
├── app.py               # Streamlit UI
├── pipeline.py          # Core research pipeline logic
├── agents.py            # Agent & chain definitions
├── tools.py             # web_search & scrape_url tools
├── requirements.txt     # Python dependencies
├── .env                 # API keys (not committed)
├── .gitignore
└── screenshots/         # Add your screenshots here
    ├── home.png
    ├── pipeline_running.png
    ├── report_output.png
    └── critic_feedback.png
```

---

## 🚀 Getting Started (Local Setup)

### 1. Clone the repository
```bash
git clone https://github.com/harshit8204/multi-agent-research-system.git
cd multi-agent-research-system
```

### 2. Create and activate virtual environment
```bash
# Windows
python -m venv .venv
.\.venv\Scripts\Activate.ps1

# Mac/Linux
python -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Set up environment variables

Create a `.env` file in the project root:
```env
MISTRAL_API_KEY=your_mistral_api_key_here
TAVILY_API_KEY=your_tavily_api_key_here
```

Get your API keys:
- 🔑 Mistral API Key → [https://console.mistral.ai/api-keys](https://console.mistral.ai/api-keys)
- 🔑 Tavily API Key → [https://app.tavily.com](https://app.tavily.com)

### 5. Run the Streamlit app
```bash
streamlit run app.py
```

Or run the pipeline directly in the terminal:
```bash
python pipeline.py
```

---

## ☁️ Deploying to Streamlit Cloud

1. Push your project to GitHub (make sure `.env` is in `.gitignore`)
2. Go to [https://share.streamlit.io](https://share.streamlit.io) and sign in with GitHub
3. Click **New app** → select your repo → set main file to `app.py`
4. Under **Settings → Secrets**, add:
```toml
MISTRAL_API_KEY = "your_mistral_api_key_here"
TAVILY_API_KEY = "your_tavily_api_key_here"
```
5. Click **Deploy** 🚀

---

## ✨ Features

- 🔍 **Real-time web search** powered by Tavily
- 🌐 **Intelligent URL scraping** for deep content extraction
- 📝 **Structured report generation** with Introduction, Key Findings & Conclusion
- 🧐 **Automated quality critique** with score, strengths and improvement areas
- ⬇️ **Download report** as a Markdown file
- 🎨 **Beautiful dark UI** with live pipeline status updates

---

## 🔮 Future Improvements

- [ ] Add support for multiple LLM providers (OpenAI, Groq)
- [ ] Export reports as PDF
- [ ] Add memory/history for past research sessions
- [ ] Support for multi-URL parallel scraping
- [ ] Add citation formatting (APA/MLA)

---

## 👨‍💻 Author

**Harshit Pal**
- GitHub: [@harshit8204](https://github.com/harshit8204)
- Project: [Multi-Agent Research System](https://github.com/harshit8204/multi-agent-research-system)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
