# Agentic LLM Compression Lab

An agent-based framework for evaluating LLM compression techniques using TinyLlama. The project benchmarks compressed and uncompressed models, evaluates response quality, analyzes trade-offs, and visualizes results through an interactive Streamlit dashboard.

---

## Overview

Large Language Models are powerful but computationally expensive. This project explores model compression by comparing a baseline TinyLlama model against a magnitude-pruned version.

The system uses a lightweight multi-agent architecture to:

- Load and manage model variants
- Benchmark performance metrics
- Evaluate output quality
- Analyze trade-offs
- Generate reports
- Visualize results through a dashboard

---

## Features

### Compression Methods

- FP32 Baseline Model
- Magnitude Pruning

### Benchmarking Metrics

- Inference Latency
- Throughput (Tokens/Second)
- RAM Usage
- Parameter Count

### Quality Evaluation

- FP32 reference generation
- Deterministic quality scoring
- Response similarity evaluation
- Completeness scoring
- Length matching

### Agent-Based Workflow

- Experiment Manager Agent
- Compression Agent
- Benchmark Agent
- Quality Evaluator Agent
- Analysis Agent

### Dashboard

- Interactive Streamlit Interface
- Benchmark Results Table
- Quality Comparison
- Latency Visualization
- Throughput Visualization
- Memory Visualization
- Agent Workflow Diagram
- Auto-generated Reports

---

# System Architecture

```text
User
  │
  ▼
Experiment Manager Agent
  │
  ▼
Compression Agent
  ├── FP32 Model
  └── Pruned Model
           │
           ▼
Benchmark Agent
           │
           ▼
Quality Evaluator
           │
           ▼
Analysis Agent
           │
           ▼
Final Report
```

---

# Agent Workflow

### Experiment Manager Agent

Coordinates the complete experiment pipeline and manages execution order.

### Compression Agent

Loads either:

- FP32 TinyLlama
- Magnitude-Pruned TinyLlama

### Benchmark Agent

Measures:

- Latency
- Throughput
- Memory Usage
- Parameter Count

### Quality Evaluator

Compares model outputs against FP32 references and computes quality scores.

### Analysis Agent

Determines:

- Fastest Model
- Smallest Memory Footprint
- Best Throughput
- Highest Quality
- Best Overall Trade-Off

---

# Project Structure

```text
agentic-llm-compression-lab/
│
├── agents/
│   ├── experiment_manager.py
│   ├── compression_agent.py
│   ├── benchmark_agent.py
│   └── analysis_agent.py
│
├── benchmark/
│   ├── comparison.py
│   ├── latency.py
│   ├── throughput.py
│   └── memory.py
│
├── compression/
│   └── pruning.py
│
├── evaluation/
│   ├── quality_evaluator.py
│   └── prompts.json
│
├── dashboard/
│   └── app.py
│
├── results/
│
├── main.py
├── requirements.txt
└── README.md
```

---

# Results

## Benchmark Summary

| Method | Latency (s) | Throughput (tok/s) | Quality Score |
|----------|----------|----------|----------|
| FP32 | 4.478 | 2.6798 | 1.0000 |
| Pruned | 0.7381 | 1.3548 | 0.0572 |

### Key Findings

- Fastest Model → Pruned
- Smallest Memory Usage → Pruned
- Best Throughput → FP32
- Highest Quality → FP32
- Best Overall Trade-Off → Pruned

---

# Dashboard Screenshots

## 1. Dashboard Overview

> Insert Screenshot 1 Here

![Overview Screenshot](images/dashboard_overview.png)

---

## 2. Run Experiment Page

> Insert Screenshot 2 Here

![Run Experiment Screenshot](images/run_experiment.png)

---

## 3. Results Page

> Insert Screenshot 3 Here

![Results Screenshot](images/results.png)

---

## 4. Visualizations Page

> Insert Screenshot 4 Here

![Visualizations Screenshot](images/visualizations.png)

---

## 5. Agent Workflow Page

> Insert Screenshot 5 Here

![Workflow Screenshot](images/agent_workflow.png)

---

# Installation

Clone the repository:

```bash
git clone https://github.com/soumilj2004/agentic-llm-compression-lab.git

cd agentic-llm-compression-lab
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate the environment:

### Windows

```bash
venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

# Running the Project

## Run Compression Experiment

```bash
python agents\experiment_manager.py
```

Outputs:

```text
results/
├── agent_experiment_results.json
├── benchmark_results.json
└── agent_experiment_report.txt
```

---

## Launch Dashboard

```bash
streamlit run dashboard/app.py
```

Open:

```text
http://localhost:8501
```

---

# Technologies Used

- Python
- TinyLlama
- Hugging Face Transformers
- PyTorch
- Streamlit
- psutil
- JSON
- Agent-Based Architecture

---

# Future Improvements

- Structured Pruning
- Quantization Support (INT8, GPTQ, AWQ)
- Multi-Model Benchmarking
- GPU Benchmark Support
- Advanced Quality Metrics
- Automated Report Export

---

# Author

**Soumil Jain**

B.Tech Computer Science Engineering

Bangalore, India

GitHub:
https://github.com/soumilj2004

---

# License

This project is released under the MIT License.
