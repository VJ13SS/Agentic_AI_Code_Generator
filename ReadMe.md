# Agentic AI Code Generator using LangGraph

## Overview

This project implements an **agent-based code generation system** that converts high-level user prompts into executable project code through a structured multi-agent workflow.

Given a prompt such as:

> “Create a calculator web application”

the system decomposes the request into tasks, plans the architecture, and generates code step-by-step, producing actual project files instead of static code snippets.

The goal of this project is to explore how **agentic LLM systems** can be used to orchestrate complex workflows involving reasoning, planning, and tool usage.

---

## Architecture

The system is built using **LangGraph** and follows a multi-agent pipeline:

```
User Prompt
     ↓
Planner Node
     ↓
Architect Node
     ↓
Coder Node (ReAct Agent)
     ↓
Generated Project Files
```

### Components

**1. Planner Node**

* Breaks down the user prompt into high-level tasks
* Example:

  * UI setup
  * Business logic
  * File structure

---

**2. Architect Node**

* Converts tasks into detailed, file-level implementation steps
* Defines:

  * File structure
  * Code responsibilities
  * Execution order

---

**3. Coder Node**

* Executes each step using a tool-enabled agent
* Implements the **ReAct** paradigm:

  * Reasons about the next action
  * Invokes tools (file operations)
* Generates and modifies actual project files iteratively

---

## Execution Flow

```
User Prompt
   → Planner
   → Architect
   → Coder (step-wise execution)
   → Final Project Output
```

* Processes one step at a time
* Uses conditional transitions between steps
* Maintains better control over context and execution

---

## Key Features

* Multi-agent orchestration using LangGraph
* Step-wise code generation for better control
* Tool-integrated agent capable of file operations
* Structured output pipeline (Planner → Architect → Coder)
* Generates real project files instead of static responses

---

## Tech Stack

* Python
* LangGraph
* Groq (LLM inference)
* Open-source LLM models
* File system tools (read/write operations)

---

## Example Use Case

**Input Prompt:**

```
Create a calculator web application
```

**System Output:**

* Generates project structure
* Creates necessary files (HTML, CSS, JS / backend)
* Implements logic step-by-step

---

## Design Considerations

* Step-wise execution to handle limited LLM context
* Clear separation of responsibilities across agents
* Emphasis on deterministic workflow over monolithic generation
* Tool usage to bridge reasoning and real-world execution

---

## Limitations

* Dependent on LLM reasoning quality
* May require refinement for complex, large-scale projects
* Limited error recovery in current version

---

## Future Improvements

* Add validation and testing agent
* Improve error handling and retry mechanisms
* Support multi-file dependency tracking
* Integrate version control for generated code
* Deploy as an API for external usage

---

## Learning Outcomes

This project helped in understanding:

* Agent-based system design
* Workflow orchestration using LangGraph
* ReAct-based reasoning and tool usage
* Step-wise execution strategies for LLM systems

---


## Conclusion

This project demonstrates how **agentic workflows** can be used to transform high-level instructions into structured, executable outputs by combining planning, reasoning, and tool interaction in a controlled pipeline.

---
