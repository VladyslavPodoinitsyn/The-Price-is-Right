# 🏷️ The Price Is Right – Autonomous Deal-Hunting Agents

An **AI-powered bargain hunter** that scrapes the web for new deals, estimates true market prices using multiple large-language-model (LLM) agents, and highlights the biggest discounts in a live interface.

---

## ✨ Features

### 🔍 Deal Scraping
- Fetches **electronics, computer, automotive, smart-home, and home-garden** offers from DealNews RSS feeds.
- Cleans HTML and builds structured deal objects for downstream analysis.

### 🤖 Multi-Agent Price Estimation
- **Frontier Agent**  
  - Retrieval-augmented generation (RAG) pipeline with **ChromaDB** + **SentenceTransformers**.  
  - Uses OpenAI or DeepSeek to estimate fair prices from similar products.
- **Specialist Agent**  
  - Calls a fine-tuned LLM served on **Modal** for a second, expert opinion.
- **Ensemble Agent**  
  - Aggregates multiple agent opinions, including random forest predictions.

### 📲 Push Notifications
- Sends **real-time alerts** whenever a high-discount opportunity is found.

### 🖥️ Interactive Web App
- Main interface (typically via Gradio or web) for browsing deals, agent logs, and visualizations.

---

## 📂 Repository Layout

```
src/
├── deal_agent_framework.py
├── ebsemnble_model.pkl
├── price_is_right_final.py
├── pricer_service2.py
└── agents/
    ├── agent.py
    ├── deals.py
    ├── ensemble_agent.py
    ├── frontier_agent.py
    ├── messaging_agent.py
    ├── planning_agent.py
    ├── random_forest_agent.py
    ├── scanner_agent.py
    └── specialist_agent.py
```

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/VladyslavPodoinitsyn/The-Price-is-Right.git
cd The-Price-is-Right
```

### 2. Install Dependencies

It’s recommended to use a virtual environment:

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### 3. Environment Variables

Create a `.env` file in the root directory with your API keys and configuration:

```env
OPENAI_API_KEY=your_openai_api_key
DEEPSEEK_API_KEY=your_deepseek_api_key
MODAL_TOKEN=your_modal_api_token
```

(Adjust according to the models/services you use.)

### 4. Run the Application

The main entry point may be `price_is_right_final.py` or another main script. For example:

```bash
python src/price_is_right_final.py
```

Or, if using the web interface:

```bash
python src/app.py
```

Check the actual main entrypoint in the `src/` folder or project documentation.

---

## 🧑‍💻 Usage

- Use the web interface or CLI to browse live deals, view estimated fair prices, and see the biggest discounts.
- Watch real-time logs to see agent reasoning and processing.
- Click any deal for a direct link to the original offer.

---

## 🤝 Contributing

Contributions, ideas, and bug reports are welcome! Please open an issue or submit a pull request.

---

## 📜 License

MIT License. See [LICENSE](LICENSE) for details.

---

## 🙏 Acknowledgements

- [DealNews](https://dealnews.com/) for RSS feeds and inspiration
- [Gradio](https://www.gradio.app/), [ChromaDB](https://www.trychroma.com/), [SentenceTransformers](https://www.sbert.net/), and [Plotly](https://plotly.com/) for fantastic open-source tools

---

*Happy deal hunting! 🛒*
