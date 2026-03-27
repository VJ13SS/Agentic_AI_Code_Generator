Built an Agentic AI Code Generator using LangGraph

I recently worked on a project to better understand how agent-based LLM systems operate in practice. The objective was to design a system that can take a high-level prompt (for example, “create a calculator web application”) and translate it into an executable sequence that generates the project step by step.

Architecture:

The system is built using LangGraph and follows a structured multi-agent pipeline:

• Planner Node – Decomposes the user prompt into high-level tasks
• Architect Node – Translates tasks into detailed, file-level implementation steps
• Coder Node – Executes each step using a tool-enabled agent

The coder is implemented using the ReAct paradigm (ReAct (Reasoning and Acting)), allowing it to reason about actions and invoke tools such as file read/write operations. This enables actual file creation and modification rather than returning static code snippets.

Execution Flow:

User Prompt → Planner → Architect → Coder (iterative execution with conditional transitions) → Generated Project Files

The system processes one implementation step at a time, ensuring controlled execution and better handling of limited context.

Implementation Notes:

• Integrated with Groq for LLM inference using an open-source model
• Emphasis on step-wise execution and structured outputs to maintain consistency
• Designed primarily as a learning project to explore agent orchestration, tool usage, and workflow design
