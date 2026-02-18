# 🧠 Nexus: Autonomous Data Agent

[![Status](https://img.shields.io/badge/status-active-success.svg)]()
[![License](https://img.shields.io/badge/license-MIT-blue.svg)]()

## 📖 Overview
Nexus is a frictionless, AI-driven autonomous agent designed to interact with structured business data and local files in the background. Moving away from traditional complex dashboards, Nexus acts as a "Data Analyst in your pocket." It interprets natural language instructions, dynamically generates and executes Python code (Code Interpreter pattern), and modifies databases or spreadsheets (Excel/CSV) safely and seamlessly.

Inspired by frictionless UI paradigms like Raycast or Spotlight, Nexus operates invisibly until summoned via a global keyboard shortcut, keeping you in your flow state.

## 🏗️ System Architecture
Nexus operates on a local client-server model, strictly separating the user interface from the artificial intelligence engine.

1. **The Brain (Python Backend):** A local background daemon/service. It handles agentic logic, connections to GitHub Models (LLM gateway), secure background code execution, and direct manipulation of files and SQLite databases.
2. **The Interface (Electron Frontend):** A native desktop application. It provides a minimalist, floating command bar invoked by a global shortcut, communicating with the Brain via local HTTP/WebSockets.

## 🛠️ Tech Stack
**Frontend (UI/UX Desktop)**
* **Framework:** Electron + Astro / React
* **Styling:** Tailwind CSS

**Backend (AI Agent & Data)**
* **Core:** Python
* **LLM Gateway:** GitHub Models (OpenAI SDK compatible for A/B testing models like GPT-4o, Llama 3.1, Mistral)
* **Database:** SQLite (`nexus.db`)
* **File Manipulation:** Pandas / Openpyxl (via LLM Code Interpreter)

## 💼 Core Use Cases
Nexus is designed to execute complex, multi-step data workflows:

* 📈 **Financial Data Analysis:** *"Nexus, read my investment portfolio CSV, calculate the percentage yield of my stocks over the last 30 days, and tell me which one had the highest growth."*
* 🎯 **Marketing Optimization:** *"Review the performance campaign report. Filter out ads with a CTR lower than 2% and save them in a new Excel file called 'ads_to_improve.xlsx'."*
* 🏢 **Administration & Management:** *"Cross-reference the expenses in 'team_budget.xlsx' with the public relations records in `nexus.db` and tell me how much budget we have left."*
* 🧹 **Data Wrangling (Cleaning):** *"Open the client database, standardize all date formats to DD/MM/YYYY, and capitalize all names."* (In-place file modification).
* 📝 **Report Generation:** *"Analyze this week's sales in `nexus.db` and write an executive summary in Markdown highlighting the top 3 best-selling products."*

## 🎯 Scope
### What Nexus DOES (In Scope):
* **Database Interaction:** Translates natural language into SQL queries to interact with local databases.
* **Background File Manipulation:** Uses the *Code Interpreter* pattern to read, clean, and format local documents without opening standard spreadsheet software.
* **Model Agnostic:** Natively integrates with GitHub Models to easily switch and test different LLMs without changing the core business logic.

### What Nexus DOES NOT DO (Out of Scope):
* **UI Automation (RPA):** It does not hijack your mouse, interact with screen pixels, or modify active windows in real-time. All work is done robustly in the data layer.
* **Complex Graphical Interfaces:** It does not rely on traditional dashboards. Communication is purely conversational and agentic.
