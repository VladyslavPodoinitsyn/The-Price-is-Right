# 🏷️ The Price Is Right – Autonomous Deal-Hunting Agents

An **AI-powered bargain hunter** that scrapes the web for new deals, estimates true market prices using multiple large-language-model (LLM) agents, and highlights the biggest discounts in a live interactive dashboard.

---

## ✨ Features

### 🔍 Deal Scraping
- `deals.py` pulls **electronics, computer, automotive, smart-home, and home-garden** offers from DealNews RSS feeds.
- Cleans HTML and builds structured `Deal` and `Opportunity` objects for downstream analysis.

### 🤖 Multi-Agent Price Estimation
- **Frontier Agent (`frontier_agent.py`)**  
  - Retrieval-augmented generation (RAG) pipeline with **ChromaDB** + **SentenceTransformers**.  
  - Uses OpenAI or DeepSeek to estimate fair prices from similar products.
- **Specialist Agent (`specialist_agent.py`)**  
  - Calls a fine-tuned LLM served on **Modal** for a second, expert opinion.

### 📲 Push Notifications
- Sends **real-time alerts** whenever a high-discount opportunity is found, so you never miss a great deal.

### 🖥️ Interactive Web App
- `app.py` (main file) launches a **Gradio** interface:
  - **Deals Table**: live list of discovered opportunities with price, estimate, discount, and direct URL.
  - **Real-Time Logs**: scrollable log panel showing agent activity.
  - **3-D Vector Map**: Plotly visualization of ChromaDB embeddings for retrieved products.

---

## 📂 Repository Layout
