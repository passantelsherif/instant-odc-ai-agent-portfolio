# 🤖 Instant × Orange Digital Center — AI Agent Developer Portfolio

This repository contains six automation and AI-agent projects built during the **30-hour AI Agent Developer Program** run by [Instant](https://instant.org) in partnership with [Orange Digital Center Egypt](https://orangedigitalcenters.com/country/EG/home).

---

## 📁 Repository Structure

```
.
├── n8n/
│   ├── 01_get_content.json            # Research agent: reads questions from Google Sheets, searches via Tavily, writes answers back
│   ├── 02_telegram_bot.json           # Executive PA bot: Telegram → AI Agent → Gmail
│   └── 03_weekly_ai_opportunities.json # Weekly digest: scrapes internships/hackathons/training → HTML email every Monday
│
├── flowise/
│   ├── 01_web_scraping_exa_search.json # Conversational agent with live web search via Exa Search + Google Gemini
│   ├── 02_general_conversational_agent.json # Simple chat agent with memory (OpenRouter + BufferMemory)
│   └── 03_techies_cafe_rag.json        # Knowledge-base JSON for Techies Café RAG chatbot
│
├── .gitignore
├── LICENSE
└── README.md
```

---

## 🛠️ Projects

### n8n Workflows

#### 01 — Content Research Agent (`01_get_content.json`)
Reads a list of questions from a Google Sheet, searches the web via the **Tavily API**, passes results to an **OpenRouter LLM** (Gemma 4), and writes researched answers back into the sheet.

**Stack:** n8n · Google Sheets · Tavily Search API · OpenRouter (Gemma 4 26B)

---

#### 02 — Telegram Executive PA Bot (`02_telegram_bot.json`)
A personal-assistant bot that listens to Telegram messages, reasons with an AI agent, sends polished emails via **Gmail**, and replies back on Telegram with a confirmation summary.

**Stack:** n8n · Telegram Bot API · OpenRouter (Gemma 4 26B) · Gmail

---

#### 03 — Weekly AI Opportunities Digest (`03_weekly_ai_opportunities.json`)
Runs every **Monday at 8 AM** (Cairo time). Fires 17 SerpAPI queries across internships, training programs, and hackathons; deduplicates results; formats a styled HTML email; and sends it automatically.

**Stack:** n8n · Schedule Trigger · SerpAPI · OpenRouter · Gmail

---

### Flowise Chatflows

#### 01 — Web Scraping Agent with Exa Search (`01_web_scraping_exa_search.json`)
A conversational agent that uses **Exa Search** as a live-search tool, powered by **Google Gemini**, with session memory via BufferMemory.

**Stack:** Flowise · Google Gemini (gemini-3.1-flash-lite) · Exa Search · BufferMemory

---

#### 02 — General Conversational Agent (`02_general_conversational_agent.json`)
A friendly, memory-enabled chat agent using **OpenRouter** (Cohere north-mini-code) and a standard ConversationChain.

**Stack:** Flowise · OpenRouter (Cohere north-mini-code) · BufferMemory · ConversationChain

---

#### 03 — Techies Café RAG Knowledge Base (`03_techies_cafe_rag.json`)
A structured JSON knowledge base for **Techies Café** (New Giza, Egypt) covering the menu, services, hours, policies, and FAQs — designed to back a RAG chatbot for café customer queries.

**Stack:** Flowise · JSON knowledge base (used as RAG document store)

---

## 🚀 How to Import & Run

### n8n Workflows

1. Open your [n8n](https://n8n.io) instance (cloud or self-hosted).
2. Go to **Workflows → Import from File**.
3. Select any JSON file from the `n8n/` folder.
4. After import, open each node that requires credentials and connect your own:
   - **Google Sheets / Gmail** → OAuth2 (connect via n8n credentials manager)
   - **Telegram** → Bot token (create a bot via [@BotFather](https://t.me/BotFather))
   - **Tavily** → API key from [tavily.com](https://tavily.com)
   - **SerpAPI** → API key from [serpapi.com](https://serpapi.com)
   - **OpenRouter** → API key from [openrouter.ai](https://openrouter.ai)
5. Activate the workflow.

### Flowise Chatflows

1. Open your [Flowise](https://flowiseai.com) instance.
2. Go to **Chatflows → Import**.
3. Select any JSON file from the `flowise/` folder.
4. Click the credential field on each node that requires one and connect:
   - **Exa Search** → API key from [exa.ai](https://exa.ai)
   - **Google Gemini** → API key from [Google AI Studio](https://aistudio.google.com)
   - **OpenRouter** → API key from [openrouter.ai](https://openrouter.ai)
5. Save and start chatting.

---

## 🔑 Credentials & Environment Variables

**No API keys or secrets are stored in this repository.** All sensitive values have been removed from the workflow files and must be added through your platform's credential manager.

| Service | Where to Get It |
|---|---|
| Tavily API Key | [app.tavily.com](https://app.tavily.com) |
| SerpAPI Key | [serpapi.com/manage-api-key](https://serpapi.com/manage-api-key) |
| OpenRouter API Key | [openrouter.ai/keys](https://openrouter.ai/keys) |
| Exa Search API Key | [dashboard.exa.ai](https://dashboard.exa.ai) |
| Google Gemini API Key | [aistudio.google.com](https://aistudio.google.com/app/apikey) |
| Telegram Bot Token | [@BotFather](https://t.me/BotFather) on Telegram |
| Google OAuth2 (Sheets/Gmail) | [Google Cloud Console](https://console.cloud.google.com) |

---

## 👩‍💻 Author

**Passant Shaaban Abd-Elazeem**  
AI Engineering Student — Cairo University (Class of 2027)  
[LinkedIn](https://www.linkedin.com/in/passantelsherif)

Built as part of the **Instant × Orange Digital Center AI Agent Developer Program** (30 hours).

---

## 📄 License

This project is licensed under the MIT License — see [LICENSE](./LICENSE) for details.
