# Deep Researcher Agent

An AI-powered multi-agent deep research system built using CrewAI, OpenAI models, Exa Search, and web scraping tools.  

This project automatically analyzes user queries, determines whether deep research is required, performs parallelized internet research using multiple AI agents, validates the collected information, and generates a structured research report with citations.

---

# Project Overview

Traditional LLM responses often struggle with:
- hallucinations
- outdated information
- lack of source validation
- shallow answers for complex topics

This project solves that problem by building a modular **multi-agent research workflow** capable of:
- planning research strategically
- performing parallel topic investigation
- validating facts from multiple sources
- generating structured reports with citations
- maintaining memory and persistence across research sessions

The system mimics how a real-world research team operates:
1. A planner defines the research strategy
2. Researchers collect information
3. Fact-checkers validate findings
4. A report writer generates the final report

---

# Key Features

## Multi-Agent Architecture
Uses specialized AI agents with distinct responsibilities:
- Research Planner
- Topic Researcher
- Fact Checker
- Report Writer

---

## Intelligent Query Routing
The system first determines whether a query requires:
- a simple direct response
OR
- a full deep-research pipeline

This reduces unnecessary computation and improves efficiency.

---

## Parallel Research Execution
Research on MAIN topics and SECONDARY topics runs asynchronously for faster execution.

---

## Fact Validation Layer
Collected research is validated to:
- reduce hallucinations
- detect inconsistencies
- cross-check information
- improve source reliability

---

## Automated Report Generation
Generates structured markdown reports containing:
- executive summaries
- detailed findings
- citations
- recommendations
- insights

---

## Persistent Memory
Uses CrewAI Flow persistence and knowledge sources to maintain context between sessions.

---

# Architecture

```text
User Query
    │
    ▼
Query Analyzer (Router)
    │
 ┌──┴─────────────┐
 │                │
 ▼                ▼
Simple Answer   Deep Research Pipeline
                     │
                     ▼
            Research Planner Agent
                     │
        ┌────────────┴────────────┐
        ▼                         ▼
 MAIN Topic Research      SECONDARY Topic Research
        │                         │
        ▼                         ▼
 MAIN Fact Validation    SECONDARY Fact Validation
        │                         │
        └────────────┬────────────┘
                     ▼
              Report Writer Agent
                     │
                     ▼
              Final Research Report
