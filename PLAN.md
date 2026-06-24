# Project Execution Plan (PLAN) - Autonomous AI Research Orchestrator
**Group Name:** yaelshir  
**Course:** Advanced Artificial Intelligence Systems: Introduction to LLMs, Agents & Multi-Agent Systems  
**Lecturer:** Dr. Yoram Segal  

---

## 1. Project Overview & Methodology
This document outlines the step-by-step execution strategy for developing and deploying the Autonomous AI Research Orchestrator. The methodology follows an iterative Software Development Life Cycle (SDLC), evolving from infrastructure configuration and LLM API integration to the autonomous orchestration of a specialized multi-agent pipeline designed for high-fidelity technical reporting.

---

## 2. Execution Phases

### Phase 1: Environment & Infrastructure Setup
* **Objective:** Establish a robust runtime environment for multi-agent execution.
* **Tasks:**
  * Configure Google Colab runtime for Python 3.12 execution.
  * Install and upgrade core dependencies: `crewai`, `crewai-tools`, `langchain-groq`, and `litellm` to resolve version compatibility conflicts.
  * Validate API credential security for `GROQ_API_KEY` (Llama-3.3-70b-versatile) and `SERPER_API_KEY` using environment variable abstraction to prevent exposure and ensure secure runtime access.

### Phase 2: Agent Behavioral Design & Intelligence Layer
* **Objective:** Architect the multi-agent personality matrix and task-specific constraints.
* **Tasks:**
  * **Research Scanner Agent:** Programmed for deep web-mining using the SerperDevTool to aggregate raw technical facts.
  * **Technical Writer Agent:** Engineered to employ professional, insight-driven narrative styles, transforming raw input into coherent business reports.
  * **QA Editor Agent:** Implementing a "Police" layer to perform factual cross-referencing and ensure output adheres to high organizational standards.
  * **Content Publisher Agent:** Responsible for the structural finalization, including executive summary formatting and the extraction of actionable business insights.

### Phase 3: Multi-Agent Orchestration Development
* **Objective:** Code the decentralized intelligence layer to autonomously manage the research lifecycle.
* **Tasks:**
  * **Contextual Chaining:** Program the task dependency logic (`context` parameters) to ensure the Writer receives research output, the QA Editor receives the draft, and the Publisher receives the full artifact.
  * **Deterministic Control:** Implement `temperature=0` across all agents to force non-stochastic, factually precise outputs.
  * **Master Orchestrator:** Program the `Sequential` process loop to chain the 4 agents and 4 tasks into a single autonomous pipeline.

### Phase 4: System Scaling & Pipeline Stabilization
* **Objective:** Expand the operational capability to ensure multi-topic scalability.
* **Tasks:**
  * Standardize inputs for dynamic topic insertion (e.g., "AI in Healthcare 2026") via the `kickoff_async` interface.
  * Remove volatile/deprecated agent configuration parameters that trigger Pydantic `ValidationError` traces.
  * Optimize the internal JSON-repair logic to ensure the Groq API can parse tool calls consistently without `tool_use_failed` errors.

### Phase 5: Testing, QA & Compilation (The "Debugging Iterations")
* **Objective:** Ensure zero-error execution across the full pipeline.
* **Tasks:**
  * **Pass 1:** Execute research retrieval; validate Serper API payload stability.
  * **Pass 2:** Execute synthesis and drafting; validate organizational tone and narrative flow.
  * **Pass 3:** Execute QA validation; ensure no factual hallucinations occur during the review phase.
  * *Validation:* Confirm output `result.raw` meets all executive report structural criteria (Breakthroughs, Companies, Technical Facts, Actionable Insights).

### Phase 6: Final Deployment & Submission
* **Objective:** Package the final deliverables for Dr. Yoram Segal's grading system.
* **Tasks:**
  * Finalize metadata across Markdown docs (`README.md`, `PRD.md`, `PLAN.md`, `TODO.md`).
  * Push all code, artifacts, and documentation to the public GitHub repository.
  * Populate the official Word/PDF Moodle submission template with the GitHub URL and assign the correct self-grade (Target: 100).