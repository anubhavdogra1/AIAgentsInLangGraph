# AI Agents with LangGraph

A comprehensive guide to building agentic AI systems using **LangGraph**—from foundational ReAct patterns to production-ready multi-step workflows with state management and web interfaces.

---

## Overview

Learn how to build intelligent agents that can reason, act, and interact with tools in a structured way. This repository progresses from basic agent patterns to complex multi-agent workflows with persistent state, human-in-the-loop checkpoints, and interactive GUI applications.

### Key Topics

* **ReAct Pattern Fundamentals:** Build agents that reason, act, and observe.
* **LangGraph Components:** Master state graphs, nodes, edges, and conditional routing.
* **Tool Integration:** Connect search APIs and external execution tools.
* **State Persistence:** Checkpoint, save, and resume agent state across sessions.
* **Streaming & Async:** Manage real-time token streaming and long-running operations.
* **Human-in-the-Loop:** Implement interruption points for human review and state modification.
* **Production GUIs:** Deploy interactive Gradio interfaces for real-time monitoring and debugging.

---

## Quick Start

### Prerequisites

* Python 3.11+
* OpenAI API Key
* Tavily API Key (for web search)
* Graphviz (optional, for graph visualization)

### Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/anubhavdogra1/AIAgentsWithLangGraph.git
   cd AIAgentsWithLangGraph
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Configure environment variables:**
   ```bash
   # Create a .env file or export directly
   export OPENAI_API_KEY="your-openai-key"
   export TAVILY_API_KEY="your-tavily-key"
   ```

4. **Install Graphviz (optional):**
   ```bash
   # macOS
   brew install graphviz

   # Ubuntu/Debian
   sudo apt-get install graphviz
   ```

---

## Project Structure

```text
AIAgentsWithLangGraph/
├── SimpleReActAgent/
│   └── Simple_ReAct_Agent.ipynb
├── LangGraphComponents/
│   └── LangGraph_Components.ipynb
├── AgenticSearch/
│   └── Agentic_Search.ipynb
├── PersistenceAndStreaming/
│   └── Persistence_and_Streaming.ipynb
├── HumanInTheLoop/
│   └── Human_in_the_Loop.ipynb
├── EssayWriter/
│   ├── Essay_Writer.ipynb
│   ├── helper.py          # Core agent implementation
│   └── temp_test_gradio.ipynb
├── requirements.txt
└── README.md
```

---

## Curriculum

* **Lesson 1: Simple ReAct Agent from Scratch**  
  Implement the Reason-Act-Observe pattern without high-level abstractions to understand decision-making, action routing, and message synthesis.

* **Lesson 2: LangGraph Core Components**  
  Construct state graphs using `TypedDict`, configure node functions, apply tool schemas, and implement dynamic conditional edges.

* **Lesson 3: Agentic Search**  
  Integrate the Tavily Search API to execute iterative search chains, parse multi-source results, and extract grounded facts.

* **Lesson 4: Persistence and Streaming**  
  Implement SQLite checkpoints to save thread states, resume interrupted conversations, and stream token-by-token responses.

* **Lesson 5: Human-in-the-Loop Workflows**  
  Configure manual breakpoints to inspect, edit, and validate intermediate agent state before proceeding.

* **Lesson 6: Full-Stack Essay Writer with Gradio GUI**  
  Build a multi-agent system featuring Planner, Research, Writer, and Reflection nodes with a live interactive web dashboard.

```python
# Launch the Essay Writer GUI
from 6_Essay_Writer.helper import ewriter, writer_gui

agent = ewriter()
gui = writer_gui(agent.graph)
gui.launch(share=False)  # Opens at http://localhost:7860
```

---

## Technology Stack

| Component | Version | Purpose |
| :--- | :--- | :--- |
| **LangGraph** | 0.0.53 | State machine orchestration |
| **LangChain** | 0.2.0 | LLM tool chaining & abstractions |
| **OpenAI** | 1.30.1 | Language model inference |
| **Tavily** | 0.3.3 | Real-time web search tool |
| **Gradio** | 4.31.3 | Web dashboard interface |
| **FastAPI** | 0.111.0 | Backend web services |
| **SQLite** | Built-in | Thread checkpoint persistence |

---

## Architecture Patterns

**ReAct Loop**
```text
Thought ──► Action ──► Observation ──► Thought ──► Final Answer
```

**Essay Writer Multi-Node Pipeline**
```text
Planner ──► Research ──► Generate ──► Reflect ──► Should Continue?
                             ▲                          │
                             │                          ├──► [YES] ──► Research Critique
                             └──────────────────────────┘
                                                        └──► [NO]  ──► END
```

---

## Troubleshooting

* **Missing API Keys:** Verify `.env` formatting or load keys explicitly via `python-dotenv`.
* **Port Conflicts:** Gradio defaults to port `7860`. Override via `export PORT1=8000` or allow automatic incrementing.
* **SQLite Thread Errors:** Ensure `check_same_thread=False` is set when running persistence checks in notebook environments.

---
✅ **Course Completed** — [AI Agents in LangGraph Certificate
](https://www.deeplearning.ai/accomplishments/8698a64d-7f95-4362-9749-1a40edbdce1d?accomplishmentId=8698a64d-7f95-4362-9749-1a40edbdce1d&usp=sharing)

---

## References & Acknowledgments

* **Course:** [AI Agents in LangGraph](https://www.deeplearning.ai/courses/ai-agents-in-langgraph) by [DeepLearning.AI](https://www.deeplearning.ai/)
* **Documentation:** [LangGraph Docs](https://langchain-ai.github.io/langgraph/) | [LangChain Docs](https://python.langchain.com/) | [Tavily API](https://tavily.com/)

---

## Contact

**Anubhav Dogra**
anubhavdogra7@gmail.com
