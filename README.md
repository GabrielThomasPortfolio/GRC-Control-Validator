# 🛡️ Deterministic GRC Control Validator

[![Live Application](https://img.shields.io/badge/Launch-Live_Application-success?style=for-the-badge&logo=streamlit)](https://grc-control-validator-gabrielthomas.streamlit.app/)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![License: Proprietary](https://img.shields.io/badge/License-Proprietary-red.svg)](#license--intellectual-property)

**An enterprise-grade, privacy-preserving architecture designed to deterministically evaluate technical engineering standards, System Security Plans (SSPs), and baseline configurations against codified regulatory frameworks.**

---

## 🎯 Executive Summary
For Security Architects, CISOs, and Compliance Engineering Leads, bridging the gap between written technical standards and evolving regulatory frameworks (like ISO 27001, ISO 42001, or NIST 800-53) is traditionally a manual, error-prone process. 

This engine automates that gap analysis. By utilizing a hybrid Retrieval-Augmented Generation (RAG) pipeline paired with strict deterministic output gates, the application ingests untrusted corporate standards, routes them semantically to the correct compliance baseline, and generates a granular, objective gap analysis—without risking prompt injection, data exfiltration, or LLM hallucinations.

---

## 🏗️ Core Architectural Value
This application is built with a "Secure-by-Design" and "Zero-Trust" mindset, demonstrating production-ready engineering suitable for Fortune 500 risk environments.

* **Deterministic Circuit Breakers:** Eliminates LLM hallucination risk. Responses are passed through strict Pydantic schema validation; malformed JSON or structurally invalid outputs are instantly dropped before reaching downstream matrices.
* **Adversarial Input Firewall:** Employs regex-based active scanning to intercept and neutralize prompt injection attempts (e.g., "ignore previous instructions") from untrusted user uploads.
* **Zero-Trust UI & Data Routing:** Eliminates Local File Inclusion (LFI) and Path Traversal vulnerabilities by mapping user intent to immutable backend constants, completely abstracting the file system from the frontend.
* **Token-Weighted Semantic Routing:** Replaces rigid keyword matching with an advanced intersection matrix to dynamically route technical configurations to overlapping statutory laws (e.g., mapping NIST technical controls to EU AI Act requirements).

> 🔍 **Deep Technical Dive:** For a comprehensive breakdown of the threat-modeling, context fencing, and regulatory cross-walking methodologies, please review the formal [System & Architecture Card (about.txt)](about.txt).

---

## 🚀 Run the Application Locally

For engineers and reviewers who wish to run the evaluation engine in a local, isolated sandbox environment, follow these steps:

### 1. Prerequisites
* Python 3.10 or higher
* Git

### 2. Clone the Repository

git clone [https://github.com/yourusername/your-repo-name.git](https://github.com/GabrielThomasPortfolio/GRC-Control-Validator/)
cd your-repo-name
3. Install Dependencies
It is recommended to use a virtual environment.


python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
pip install -r requirements.txt
4. Environment Configuration
This application utilizes OpenAI's models for semantic reasoning. You must provide an active API key via a secure .env file.

Create a file named .env in the root directory.

Add the following variables:

Code snippet
OPENAI_API_KEY="sk-your-actual-api-key"
COMPLIANCE_MODEL_NAME="gpt-4o-mini"
(Note: The .env file is explicitly included in the .gitignore to prevent secret leakage.)

5. Launch the Engine

streamlit run app.py
The UI will automatically deploy to http://localhost:8501.

⚖️ License & Intellectual Property
All Rights Reserved.

This repository and its contents, including but not limited to the source code, architecture design, semantic routing logic, and system prompt structures, are the intellectual property of the author.

This code is provided publicly strictly for portfolio review, technical demonstration, and hiring evaluation purposes. You may not copy, modify, distribute, sell, or use this code for commercial purposes, internal corporate compliance auditing, or deployment within any organization without express written consent from the author.