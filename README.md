# StockSage 📈

StockSage is a powerful, multi-agent financial analysis tool built with the `phidata` library. It leverages the speed of Groq's LLaMA 3 model and the power of specialized tools to provide real-time stock market insights. The system uses two distinct agents: a **Finance Agent** to fetch financial data and a **Web Search Agent** to gather the latest news and information from the internet.

This project offers two ways to interact with the agents:
1.  A command-line interface (`backend.py`) for direct, scripted queries.
2.  An interactive web UI (`playground.py`) powered by phidata's Playground for a chat-based experience.

---
## ✨ Key Features

* **Multi-Agent System:** Combines a specialized finance agent and a web search agent for comprehensive analysis.
* **Real-time Financial Data:** Fetches stock prices, analyst recommendations, company fundamentals, and news using `YFinanceTools`.
* **Live Web Search:** Uses `DuckDuckGo` to get the most up-to-date information and includes sources in its responses.
* **High-Speed LLM:** Powered by Groq's `llama-3-70b-versatile` model for fast, high-quality responses.
* **Dual-Mode Operation:** Run analysis directly in your terminal or interact with the agents through a user-friendly web interface.
* **Structured Output:** Formats financial data in clean, easy-to-read markdown tables.

---
## 🎬 Demo

Watch a live demo of the StockSage Playground in action. Click the image below to view the video.

[![StockSage Demo Video](https://drive.google.com/uc?export=view&id=1bW8Mak_9MJdmMaHerhTb8Z_5pX9N0T6-)](https://drive.google.com/file/d/1bPNq32rFBOsU4PKrWw8FLhFw_Gr-2el_/view?usp=sharing)

***Note:*** *To make the demo link work, you must replace `YOUR_GOOGLE_DRIVE_SHARE_LINK_HERE` with the actual shareable link to your `demo.mp4` file. You can also replace the image URL with a screenshot from your video.*

---
## 🛠️ Getting Started

Follow these steps to set up and run the project on your local machine.

### Prerequisites

* [Anaconda](https://www.anaconda.com/products/distribution) or [Miniconda](https://docs.conda.io/en/latest/miniconda.html) installed.
* API keys from [Groq](https://console.groq.com/keys), [OpenAI](https://platform.openai.com/api-keys), and [phidata](https://phidata.com/).

### 1. Clone the Repository

First, clone the project repository to your local machine.

```bash
git clone [https://github.com/YOUR_GITHUB_USERNAME/StockSage.git](https://github.com/YOUR_GITHUB_USERNAME/StockSage.git)
cd StockSage
```
**Note:** Remember to replace `YOUR_GITHUB_USERNAME` with your actual GitHub username.

### 2. Create and Activate Conda Environment

Create a dedicated Conda environment for the project. This project was built using Python 3.12.

```bash
conda create -n stocksage python=3.12 -y
conda activate stocksage
```

### 3. Install Dependencies

Install all the required Python packages using the `requirements.txt` file.

```bash
pip install -r requirements.txt
```

### 4. Set Up Environment Variables

You need to provide your API keys for the services used in this project.

1.  Create a file named `.env` in the root directory of the project.
2.  Copy and paste the following content into the `.env` file and replace the placeholder text with your actual API keys.

```env
# Get from [https://phidata.com/](https://phidata.com/)
PHI_API_KEY="ph-..."

# Get from [https://console.groq.com/keys](https://console.groq.com/keys)
GROQ_API_KEY="gsk_..."

# Get from [https://platform.openai.com/api-keys](https://platform.openai.com/api-keys)
OPENAI_API_KEY="sk-..."
```
---
## 🚀 Usage

StockSage can be run in two different modes.

### 1. Terminal Mode (`backend.py`)

This mode runs a pre-defined query directly in your terminal and prints the results. It's great for automated tasks or quick checks.

To run it, execute the `backend.py` script:

```bash
python backend.py
```

The script will run the query `"Summarize analyst recommendation and share the latest news for Axis Bank"` and stream the agent's response directly to your console.

#### Example Output in Terminal:

```text
> Team Starting Task: Summarize analyst recommendation and share the latest news for Axis Bank

... (Tool calls and agent thoughts will be displayed here) ...

**Axis Bank Analyst Recommendations & Latest News**

Here is a summary of analyst recommendations and the latest news for Axis Bank (AXISBANK.NS).

**Analyst Recommendations**

| Category            | Recommendation |
| ------------------- | -------------- |
| To Grade            | Buy            |
| From Grade          |                |
| Firm                | Morgan Stanley |
| Action              | main           |

**Latest News**

* **Title:** Axis Bank board to consider quarterly results, fundraising on July 24
    * **Link:** [[https://www.moneycontrol.com/news/business/markets/axis-bank-board-to-consider-quarterly-results-fundraising-on-july-24-127244.html](https://www.moneycontrol.com/news/business/markets/axis-bank-board-to-consider-quarterly-results-fundraising-on-july-24-127244.html)]
    * **Published:** 2024-07-19
    * **Publisher:** Moneycontrol

Sources:
1. Yahoo Finance
2. DuckDuckGo Search Results
```

### 2. Interactive Playground Mode (`playground.py`)

This mode launches a local web server with the phidata Playground, allowing you to chat with the agents interactively.

To start the web application, run the `playground.py` script:

```bash
python playground.py
```

You will see output in your terminal indicating that the server is running, usually on port 8000.

```bash
INFO:     Uvicorn running on [http://127.0.0.1:8000](http://127.0.0.1:8000) (Press CTRL+C to quit)
INFO:     Started reloader process [12345] using StatReload
INFO:     Started server process [54321]
INFO:     Waiting for application startup.
INFO:     Application startup complete.
```

Now, open your web browser and navigate to **[http://127.0.0.1:8000](http://127.0.0.1:8000)**. You can select an agent from the dropdown and start a conversation.

---
## 📂 Project Structure

```
.
├── backend.py            # Script for terminal-based agent interaction
├── playground.py         # Script to launch the interactive web UI
├── requirements.txt      # Python dependencies
├── .env                  # File for API keys (you need to create this)
└── README.md             # This file
