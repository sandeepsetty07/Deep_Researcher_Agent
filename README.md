# Deep Researcher Agent

An AI-powered multi-agent deep research system built using CrewAI.  
This project automates the complete research workflow — from query analysis and planning to parallel research, fact-checking, and final report generation.

The system is designed to simulate how a real research team operates by assigning specialized responsibilities to different AI agents.

---

# Project Overview

Most AI research assistants generate responses directly from a single prompt, which often leads to:
- hallucinations,
- shallow analysis,
- poor source validation,
- and unreliable outputs.

This project solves that problem by implementing a structured multi-agent research pipeline.

The system:
1. Analyzes the user query
2. Decides whether deep research is required
3. Breaks the query into research areas
4. Runs parallel research tasks
5. Verifies collected information
6. Generates a structured research report
7. Saves and summarizes the final output

---

# Architecture

```text
User Query
    │
    ▼
Query Analyzer (Router)
    │
    ├── SIMPLE → Direct LLM Response
    │
    └── RESEARCH
            │
            ▼
    Research Planner Agent
            │
            ▼
 ┌─────────────────────────┐
 │ Parallel Research Layer │
 └─────────────────────────┘
      │              │
      ▼              ▼
Main Topic      Secondary Topic
Research        Research
      │              │
      ▼              ▼
Fact Checker  Fact Checker
      │              │
      └──────┬───────┘
             ▼
      Report Writer

---

# Key Features

## Multi-Agent Architecture
Specialized AI agents handle different responsibilities independently.

## Parallel Research Execution
Main and secondary research topics run asynchronously for faster execution.

## Query Classification
The system intelligently determines whether a query requires:
- direct response
- or deep research workflow.

## Fact Validation Layer
Research outputs are validated to reduce hallucinations and misinformation.

## Source-Based Research
Uses Exa Search and web scraping tools to collect information from external sources.

## Persistent Memory
Flow state persistence allows conversation continuity and context retention.

## Automated Report Generation
Produces structured markdown research reports with citations.

## Modular Design
Agents, tasks, tools, and workflows are separated for scalability and maintainability.

---

# Agents

## 1. Research Planner
Responsible for:
- breaking down complex queries,
- defining main and secondary topics,
- generating research strategy.

---

## 2. Topic Researcher
Responsible for:
- internet research,
- extracting information from multiple sources,
- validating information across websites,
- collecting citations.

### Tools Used
- Exa Search Tool
- Website Scraper

---

## 3. Fact Checker
Responsible for:
- identifying inconsistencies,
- detecting hallucinations,
- validating source credibility,
- ensuring research quality.

---

## 4. Report Writer
Responsible for:
- synthesizing validated information,
- creating structured reports,
- generating final summarized answers.

---

# Workflow

## Step 1 — Query Analysis
The system analyzes whether the query is:
- SIMPLE
- or RESEARCH-level.

---

## Step 2 — Clarification
If the query is ambiguous, the system asks follow-up questions.

---

## Step 3 — Research Planning
The planner agent creates:
- main topics,
- secondary topics,
- research priorities,
- key research questions.

---

## Step 4 — Parallel Research
Two asynchronous research pipelines execute simultaneously:
- Main topic research
- Secondary topic research

---

## Step 5 — Validation
Fact-checking agents validate:
- consistency,
- reliability,
- source credibility,
- unsupported claims.

---

## Step 6 — Report Generation
The report writer synthesizes all validated information into:
- a detailed research report,
- citations,
- key insights,
- recommendations,
- summarized final answer.

---

# Example Use Cases

- Market Research
- AI Industry Analysis
- Competitor Research
- Technology Trend Analysis
- Startup Research
- Cybersecurity Research
- Academic Topic Exploration
- Investment Research
- Product Research
             │
             ▼
      Final Research Report
