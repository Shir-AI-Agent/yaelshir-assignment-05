# 🤖 Autonomous AI Research Orchestration Agent

## 👥 Submitted by: Shir Sharon & Yael Persky
**Academic Institution:** Bar-Ilan University  
**Course:** Technology Management Laboratory – Artificial Intelligence Agents  
**Lecturer:** Dr. Yoram Segal  

---

## 🎯 Project Overview

This project implements an autonomous, multi-agent AI framework based on the **CrewAI orchestration engine**. The system manages a structured pipeline designed to perform end-to-end knowledge discovery, synthesis, and dissemination of emerging artificial intelligence breakthroughs.

The system utilizes the **Sequential Task Architecture**, which separates the research ingestion layer from the creative synthesis and editorial validation layers, ensuring high-fidelity outputs suitable for executive management.

### 💡 Our Creative Twist: Contextual Sequential Orchestration

To prevent information fragmentation and ensure the integrity of technical facts, we implemented a **Context-Aware Chaining Mechanism**. Unlike standard agentic workflows that might operate in silos, our system forces each agent (Writer, QA, Publisher) to inherit the full knowledge-base context (`expected_output`) of its predecessor. This "Contextual Persistence" ensures that technical facts, company entity names, and specific breakthrough details discovered by the Scanner Agent are carried through to the final Executive Report without data loss or hallucination.

---

## ⚙️ Agent Architecture and Assignment Requirements

1. **Orchestration Layer (Sequential Pipeline):**
   The system employs `Process.sequential` to manage the lifecycle of a research task. This simulates a professional research department where data flows linearly through specialized agents: **Scanner** → **Writer** → **QA Editor** → **Publisher**.

2. **Targeted Information Retrieval:**
   The `Technology Research Scanner` agent leverages the `SerperDevTool`. It does not perform broad, non-specific queries; it is constrained by a system prompt to focus on high-impact, technical, and industry-specific breakthroughs of the current week.

3. **LLM Inference & Determinism:**
   The agents utilize the **`llama-3.3-70b-versatile`** model hosted via Groq Cloud. To ensure deterministic results and avoid the "randomness" typically associated with LLMs, we set the `temperature` parameter to **0**. This enforces strict adherence to structural requirements and technical fact-checking.

4. **Factual Integrity & QA Gatekeeping:**
   The `Quality Assurance Editor` acts as a non-negotiable gatekeeper. It is programmed with a "Police" persona, tasked with verifying the final output against the raw notes retrieved by the scanner. If factual depth is lacking, the agent has the authority to trigger a validation failure loop.

5. **Credentials & Security:**
   The system utilizes environment-variable abstraction for all sensitive API keys (`GROQ_API_KEY`, `SERPER_API_KEY`). The project is orchestrated through an `OPENAI_API_BASE` tunnel to integrate Groq's high-throughput engine into the CrewAI ecosystem seamlessly.

---

## 🚀 Installation & Execution

### Install Dependencies
```bash
pip install crewai crewai-tools langchain-groq litellm
Configuration
Create an environment file or export the following keys:

GROQ_API_KEY

SERPER_API_KEY

Run
Execute the Jupyter Notebook environment (Colab/JupyterLab) cells sequentially. The crew.kickoff_async interface will trigger the multi-agent pipeline.

🛠 Technologies Used
Python 3.12

CrewAI 1.14.7 (Orchestration Framework)

Llama-3.3-70b-versatile (via Groq Cloud)

Google Serper API (Real-time web retrieval)

Sequential Context Chaining (Data Pipeline)

📂 Repository Structure
notebook.ipynb – The orchestration engine containing the agent definitions, task logic, and execution loop.

PRD.md – Product Requirements Document (System architecture & scope).

PLAN.md – Project roadmap and implementation phases.

TODO.md – Operational status and sprint progress.

📧 Example Workflow
Input (The Trigger)
inputs={'topic': 'AI in Healthcare 2026'}

Processing (The Chain)
Scanner: Fetches technical facts on AI-driven diagnostics.

Writer: Synthesizes facts into a professional report.

QA: Validates medical fact accuracy.

Publisher: Formats report with actionable insights.

Output (The Executive Report)
A structured executive-ready report featuring:

Key Breakthroughs (Technical details & credible sources)

Companies Making Waves (Entity extraction)

Actionable Insights (Managerial roadmap)
