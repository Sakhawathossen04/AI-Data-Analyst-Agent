# AI Data Analyst Agent

An intelligent multi-agent data analysis system powered by DeepSeek R1 and built with Streamlit.
Upload any CSV file, ask questions in natural language, and get instant insights, charts, and AI-generated explanations.

---

## Project Overview

This project is an **AI-powered Data Analyst Agent** that automates the complete data analysis workflow using multiple AI agents.

The system can:

*  Upload and analyze CSV datasets
*  Convert user questions into structured analysis plans
*  Execute analysis using pandas
*  Generate beautiful charts automatically
*  Explain results in simple human language
*  Use reasoning-based LLM planning with DeepSeek R1

---

## 🧠 Multi-Agent Architecture

The project follows a modular **AI Agent Pipeline**:

```text
User Question
      │
      ▼
┌──────────────────┐
│ Planner Agent    │
│ (DeepSeek R1)    │
└──────────────────┘
      │ JSON Plan
      ▼
┌──────────────────┐
│ Data Worker      │
│ (Pandas Engine)  │
└──────────────────┘
      │ Results
      ▼
┌──────────────────┐
│ Chart Generator  │
│ (Matplotlib)     │
└──────────────────┘
      │
      ▼
┌──────────────────┐
│ Explainer Agent  │
│ (DeepSeek R1)    │
└──────────────────┘
      │
      ▼
Final Insights
```

---

#  Features

##  CSV Upload Support

* Upload any structured CSV dataset
* Auto-detect numeric and date columns
* Preview data instantly

##  AI Planning Agent

* Converts natural language questions into structured JSON analysis plans
* Uses reasoning-based planning with DeepSeek R1

##  Automated Data Analysis

Supports:

* Group By Analysis
* Aggregations
* Filtering
* Comparisons
* Statistical summaries

##  Smart Visualization

Automatically generates:

* Bar Charts
* Line Charts
* Pie Charts

##  AI Insight Generation

The Explainer Agent:

* Summarizes findings
* Highlights trends
* Provides business recommendations
* Explains results in simple language

##  Reasoning Transparency

* Shows AI reasoning process
* Displays generated analysis plan
* Useful for debugging and learning

---

#  Tech Stack

| Technology        | Purpose                         |
| ----------------- | ------------------------------- |
| Python            | Core programming language       |
| Streamlit         | Interactive web UI              |
| Pandas            | Data processing                 |
| Matplotlib        | Visualization                   |
| Seaborn           | Enhanced chart styling          |
| DeepSeek R1       | Reasoning LLM                   |
| OpenAI Python SDK | API integration                 |
| dotenv            | Environment variable management |

---

#  Project Structure

```bash
AI-Data-Analyst-Agent/
│
├── app.py
├── requirements.txt
├── .env
├── README.md
│
├── agents/
│   ├── planner_agent.py
│   ├── explainer_agent.py
│   └── worker_agent.py
│
├── charts/
│
├── utils/
│   ├── preprocessing.py
│   ├── filters.py
│   └── visualization.py
│
└── datasets/
```

---

#  Installation

## 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/AI-Data-Analyst-Agent.git

cd AI-Data-Analyst-Agent
```

---

## 2️⃣ Create Virtual Environment

### Windows

```bash
python -m venv venv

venv\Scripts\activate
```

### Linux / Mac

```bash
python3 -m venv venv

source venv/bin/activate
```

---

## 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 4️⃣ Add DeepSeek API Key

Create a `.env` file:

```env
DEEPSEEK_API_KEY=your_api_key_here
```

Get API key from:

[DeepSeek Platform](https://platform.deepseek.com?utm_source=chatgpt.com)

---

# ▶️ Run the Application

```bash
streamlit run app.py
```

The app will start locally at:

```text
http://localhost:8501
```

---

#  Example Questions

You can ask questions like:

```text
Which product category generated the highest sales?

Show monthly revenue trends.

Which region has the maximum profit?

Top 10 customers by revenue.

Compare sales between 2022 and 2023.
```

---

#  How It Works

## Step 1 — Dataset Understanding

The system reads:

* Column names
* Data types
* Sample rows
* Date columns

---

## Step 2 — Planner Agent

The AI converts the user query into structured JSON:

```json
{
  "operation": "group_by_summary",
  "group_by": ["Category"],
  "target_column": "Sales",
  "metric": "sum",
  "need_chart": true,
  "chart_type": "bar"
}
```

---

## Step 3 — Data Worker

The worker executes the plan using:

* pandas groupby
* filtering
* aggregation
* sorting

---

## Step 4 — Visualization

Charts are automatically generated using:

* Matplotlib
* Seaborn

---

## Step 5 — AI Explanation

The Explainer Agent:

* Interprets results
* Creates summaries
* Gives actionable insights

---

#  Key Highlights

* ✅ Multi-Agent AI Workflow
* ✅ Reasoning-Based Planning
* ✅ Fully Automated Data Analysis
* ✅ Natural Language Querying
* ✅ Explainable AI Outputs
* ✅ Interactive Dashboard
* ✅ Business-Friendly Insights
* ✅ Streamlit Web Application
* ✅ Automatic Chart Generation
* ✅ CSV Export Support

---

#  Screenshots

##  Dashboard UI

![Image](https://images.openai.com/static-rsc-4/rS-29oUpBmt7uFMuO_4aVJ6SEmAkwTkIGNvJYd12zTZ95SVsoved0GLGcmxM72WaDTx8644AM4StHLeYtaV3J1mo32uLyVBVkzX5v8H2buafSgTMuHshG_wH_k4vDYLFJXcF-C8ueSninTpH9XMi2TttC7nT6z5Asv3j-NMnLI9r1cvHVgyLGRFAj7OxVPy1?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/pUp9VGvEbb3jDCMJwXclGK22rr4IqMOWsAYs-X6B1ckMyDeUPqWyoFmOGamJf67T5E7JhtTM6bFBY7Eh3LQjmF97kYrugL1z82DZv6CDyVLPp9OdvH2IexZMT9N03zzgchQOHwVpNa7P0gs5NwijZjyz3nIswxvl1yQ-iEBVI1OT-QUsRQrDT2hzyKKGpwdt?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/yOwFaXcUSjJxylDqljQ3G3Nj0WDQb0j_eylW7igXtQhM4EqJHvImRLAk7WGpMUdO-DewTlZPKSPPLx-TTsLfTvRF4O2ktmAQsc01100NU9e6Yz5SqK00Sklu9Hugblmd7pXd6uOW7lvdzUfwYUUSkd9XW79caCR2e4v2L7nxnKzsLINTNpMXfzsmy9b9MUG1?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/wb2pA_qNGzdbAj9I7oPF1XveOxaMzdKmAvzhOWAIitzWzJk69xXDFPZsiC7XuxXQ6faWrrIXibdUFtlXSplH1bccYEP0wEe1NUr9nsSZVUFf58FoFYP1BFYbWmfWjRSFCWqDqb8cumZxkXwUGOPEZbjQB8gWax-Gb_ix_v-XZWHq78a8qX8X8FuvghUfTmMz?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/WnWhbxv1Y9-L1xKYwxahewi3tLArv709Jlh5Oz9V-nbd-pTGitJhwIFGlVNmzBDvFhupgdekQHdXweHOF0Hq4WbBwp2wq_mmsPUEpPXFdtQk6xvQBV4LJ4LffN0O25ZxTPxKoqLfsCc8lBCxjvWzByIIVz2xnJ1iveytKeoBL9RhfkGuoVZkv3Y50UNOBSMR?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/Ae7D6p0UVdDqbEM3vbqdGfYCb9JwWWudcYYpD76OR2KIZIwqHbdqb8fb8m2KQTD4WYXLjzs-EBVsMI7dHfieLttGYllF5KY8bqcAPdgDFzjsrXWrcvYgEYP4aHcCYhJCvf6VS-mjq6zthC6i_JkvyuIajMwy13211iTAbIdFig0_Nl9LEGyihmCb4qgdCT00?purpose=fullsize)

## 📈 Data Visualization

![Image](https://images.openai.com/static-rsc-4/q78FPCeXEC7SBBgByiRjfJaep6W0jMODdqIjBf4ePrwkpELbGjYQFMYXrxmsvnfNscJ-Mm_QZ0K2BQ8zaabQQ_7g4Q7Wno1QKOCpqX-gF_E1aUSB2Dt-q69RJSVA6SHYkRtoLPj-Tht6WRGtn4kojBL-jcUPbKvjR2hUnOr9FEpYMDPOFOuOrx0BB98PFgiw?purpose=fullsize)


---

#  Future Improvements

*  SQL Query Support
*  PDF Report Generation
*  RAG-based Knowledge Integration
*  Advanced Statistical Analysis
*  Autonomous AI Agent Collaboration
*  Cloud Deployment
*  Voice-based Query System
*  Forecasting & Predictive Analytics
*  Automated Insight Reports
*  Custom Fine-Tuned LLM

---

#  Real-World Use Cases

* Business Intelligence
* Sales Analytics
* HR Analytics
* Financial Reporting
* Customer Insights
* Marketing Performance Analysis
* E-commerce Analytics
* Research & Academic Projects

---

#  Learning Objectives

This project demonstrates:

* AI Agent Design
* LLM Reasoning Pipelines
* Data Engineering
* Data Visualization
* Prompt Engineering
* Explainable AI
* Human-AI Interaction
* End-to-End AI Application Development

---

#  Contributing

Contributions are welcome!

If you'd like to improve the project:

1. Fork the repository
2. Create a feature branch
3. Commit changes
4. Open a pull request

---

#  License

This project is licensed under the MIT License.

---

#  Author

**Sakhwat Hossen**
Machine Learning & AI Enthusiast

* LinkedIn: https://www.linkedin.com/in/sakhawathossenofficial/
* GitHub: https://github.com/Sakhawathossen04

---

#  Support

If you found this project helpful:

⭐ Star the repository
🍴 Fork the project
📢 Share with others

---

# 🧠 Final Note

This project is more than a simple dashboard — it is an experimental step toward building fully autonomous AI Data Analyst systems capable of understanding, analyzing, visualizing, and explaining data with minimal human intervention.
