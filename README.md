GRC Control Validator

![CI](https://github.com/GabrielThomasPortfolio/GRC-Control-Validator/actions/workflows/ci.yml/badge.svg)

A lightweight, deterministic engine for evaluating technical standards, SOPs, and system documentation against security and compliance requirements. Built to support real‑world GRC work where inputs are messy, untrusted, and need structured, defensible evaluation.

What This Project Does
* Analyzes technical documentation (SOPs, SSPs, engineering standards, configs)
* Compares content against codified controls
* Produces clear compliance/non‑compliance decisions
* Includes rationale that can be reviewed or audited
* Uses OpenAI in a bounded, deterministic way — no creative interpretation, no hallucinated controls

Why I Built It
* Most AI “policy evaluators” fail because policies are too high‑level and subjective.
* This project focuses on technical artifacts, where requirements are concrete and evaluation can be consistent.

It reflects how GRC engineering actually works:
* structured inputs
* predictable logic
* traceable decisions
* zero‑trust handling of user content

Key Features
* Deterministic evaluation pipeline
* Input sanitization to prevent prompt injection
* Lexical keyword routing that matches uploaded documentation to relevant controls across four compliance tracks
* Guardrails to keep outputs grounded and defensible
* Streamlit UI for quick testing and demos

Tech Stack
* Python 3.10+
* Streamlit — UI and orchestration layer
* OpenAI `gpt-4o-mini` at `temperature=0.0` — bounded, deterministic evaluation only
* Pydantic v2 — strict output schema enforcement via `ComplianceAuditFinding`
* pypdf + python-docx — multi-format document ingestion
* Custom RAG knowledge bases (JSONL) — ISO 27001/NIST 800-53, ISO 42001, Statutory Laws
* pytest — automated validation suite

Live Demo
https://grc-control-validator-gabrielthomas.streamlit.app

## Setup

```bash
git clone https://github.com/GabrielThomasPortfolio/GRC-Control-Validator.git
cd GRC-Control-Validator
pip install -r requirements.txt
```

Create a `.env` file in the root:
```
OPENAI_API_KEY=sk-proj-your-key-here
```

Run the app:
```bash
streamlit run app.py
```

> **No API key?** Set `OPENAI_API_KEY=mock` in your `.env` to run in demo mode with simulated evaluations.

What This Project Demonstrates
This repo highlights my focus on:
* GRC engineering
* AI‑assisted control testing
* Deterministic evaluation design
* Practical automation for compliance and audit workflows

It’s part of a broader effort to build tools that make governance work more scalable, consistent, and reliable.
