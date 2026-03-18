# RetailAgentEvalOps: Observability and Evaluation Framework for Sales Analytics Agents

## Overview
RetailAgentEvalOps is a production-oriented framework for tracing, evaluating, and improving a multi-tool sales analytics AI agent.

The agent answers business queries by dynamically selecting tools for data retrieval, analysis, and visualization. This project introduces structured observability and evaluation pipelines to systematically measure and improve agent decision-making, reasoning quality, and efficiency.

## Key Features
- Multi-tool AI agent for sales analytics (SQL retrieval, analysis, visualization)
- Step-level observability with execution tracing
- Component-wise evaluation (routing, tool usage, outputs)
- Trajectory-level evaluation for multi-step reasoning
- LLM-as-a-judge and code-based evaluators
- Convergence metrics for efficiency measurement
- Experiment-driven iteration framework

## System Architecture

### Agent Layer
- Router: Selects appropriate tool based on user query
- Tools:
  - SQL-based data retrieval from sales dataset
  - LLM-driven analysis of results
  - Visualization generation via code synthesis
- Iterative execution loop until final response

### Observability Layer
- Captures full execution traces of agent steps
- Logs:
  - Tool selection decisions
  - Inputs and outputs per step
  - Intermediate reasoning flow
- Enables debugging and evaluation dataset creation

### Evaluation Layer

#### Component-Level Evaluation
- Router correctness (tool selection accuracy)
- SQL retrieval quality
- Analysis output quality
- Evaluated using:
  - Code-based checks
  - LLM-as-a-judge

#### Trajectory-Level Evaluation
- Evaluates complete multi-step execution paths
- Measures:
  - Final answer correctness
  - Logical consistency across steps
  - Efficiency of reasoning

#### Convergence Metric
- Measures whether the agent reaches correct answers in minimal steps
- Used to assess efficiency and control computational cost

### Experimentation Framework
- Structured experiments to evaluate:
  - Prompt changes
  - Model variations
  - Tool logic improvements
- Enables systematic iteration using measurable metrics

## Notebooks

- `1 Agent Code.ipynb`  
  Implements a multi-tool sales analytics agent with routing, SQL retrieval, analysis, and visualization.

- `2 Tracing your Agent.ipynb`  
  Adds observability by capturing and analyzing execution traces of agent steps.

- `3 Adding Router & Skill Evaluations.ipynb`  
  Evaluates routing decisions and tool outputs using code-based and LLM evaluators.

- `4 Adding Trajectory Evaluations.ipynb`  
  Evaluates full multi-step reasoning paths and agent trajectories.

- `5 Adding Structure to your Evaluations.ipynb`  
  Organizes evaluations into structured experiments for iterative improvement.

## Tech Stack
- Python
- LLM APIs with tool/function calling
- DuckDB for SQL execution
- LLM-as-a-Judge evaluation
- Prompt engineering and structured evaluation design

## Use Cases
- Business intelligence and sales analytics agents
- Evaluation pipelines for tool-using AI agents
- Agent reliability and debugging systems
- Production monitoring of multi-step LLM workflows

## Why This Matters
AI agents are non-deterministic and difficult to debug, especially when they involve multi-step reasoning and tool usage.

RetailAgentEvalOps introduces a structured, metrics-driven workflow to:
- Diagnose agent failures
- Quantify performance across components
- Improve reasoning efficiency and reliability through experiments

## Future Work
- Online evaluation pipelines with real-time monitoring
- Human-in-the-loop feedback integration
- Automated dataset generation from traces
- Reinforcement learning using evaluation signals
