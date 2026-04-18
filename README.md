# Agentic AI Care Management Prototype

Research prototype code accompanying the manuscript:

**“A Structured Pre-deployment Evaluation Framework for an Agentic AI Care-Management Prototype”**

This repository contains a CrewAI-based multi-agent prototype developed to support the **pre-deployment, in silico evaluation** of an agentic care-management system. The prototype was used as an instrumented testbed for evaluating a scenario-based framework that combines bounded-correctness review, structured transcript scoring, and internal trace inspection. It is intended as a **research and methods artifact**, not as a production clinical system. :contentReference[oaicite:4]{index=4}

## Purpose

Care management involves longitudinal coordination across clinical, social, behavioral, and operational domains. This prototype was built to explore whether a role-specialized, multi-agent architecture could support realistic synthetic care-management workflows and provide inspectable outputs for structured evaluation.

The repository is meant to support transparency around the system architecture described in the manuscript, including agent roles, orchestration, guideline retrieval, stubbed tool use, and the synthetic scenario framework used for testing. :contentReference[oaicite:5]{index=5}

## What this repository contains

Depending on the final release, this repository may include:

- the multi-agent CrewAI prototype
- agent definitions and behavioral framing
- task definitions and workflow orchestration
- retrieval-augmented guideline support configuration
- synthetic scenario templates and evaluation harness components
- analysis scripts and example outputs
- documentation sufficient to inspect the architecture and reproduce representative runs

## System overview

The prototype uses a **hierarchical multi-agent architecture** with a project manager/orchestrator coordinating several role-specialized agents. Core roles include:

- **Care Manager**: primary workflow executor for patient support and care planning
- **Patient Proxy**: simulated patient respondent parameterized by scenario and psychographic profile
- **Guidelines Expert**: retrieval-augmented guideline interpretation agent
- **Primary Care Physician**: clinical escalation and oversight role
- **Scheduler**: logistics and appointment coordination
- **Pharmacist**: medication-related support
- **Insurance / Medicaid Support**: benefits and coverage support
- **Project Manager**: task routing, coordination, and workflow management

The prototype was designed to reflect division of labor seen in real care-management programs while preserving clear role boundaries and inspectable agent interactions. :contentReference[oaicite:6]{index=6} :contentReference[oaicite:7]{index=7}

## Workflow summary

A typical run combines:

1. patient clinical context  
2. social-needs modifiers  
3. a psychographic profile  
4. retrieval from clinical guidance sources  
5. role-based agent collaboration  
6. a patient-facing care plan and internal trace

The workflow includes care-activity identification, guideline application, elicitation of patient preferences, barrier assessment, implementation planning, plan confirmation, and follow-up specification. :contentReference[oaicite:8]{index=8}

## Knowledge and tools

The prototype uses retrieval-augmented generation to support guideline-informed recommendations. In the study configuration, a care-management knowledge artifact derived from VA/DoD clinical practice guidelines and VA Whole Health clinical tools was attached through CrewAI knowledge sources. Tool use is intentionally bounded and includes stubbed actions for communication and scheduling rather than production integrations. :contentReference[oaicite:9]{index=9} :contentReference[oaicite:10]{index=10}

## Research use only

This code is released for **research, transparency, and methodological inspection** only.

It is **not**:

- a medical device
- validated clinical decision support
- production-ready software
- connected to a live EHR
- configured to send real patient communications
- configured to schedule real appointments
- appropriate for autonomous clinical use

The study used **synthetic scenarios and simulated interactions only**. No real patient data were used. :contentReference[oaicite:11]{index=11}

## Relation to the manuscript

The manuscript’s primary contribution is the **evaluation framework**, not a claim of clinical effectiveness or deployment readiness of the prototype itself. The code in this repository is provided to make the prototype architecture and testing approach inspectable and reusable by other investigators interested in preclinical evaluation of agentic healthcare systems. :contentReference[oaicite:12]{index=12}

If you use this repository in academic work, please cite the associated manuscript.

## Installation

> Update this section to match the released repository structure.

### Requirements

- Python 3.10+ recommended
- API credentials for required model providers and any enabled external tools
- Sufficient permissions and local environment for CrewAI and related dependencies

### Basic setup

```bash
git clone <REPOSITORY_URL>
cd <REPOSITORY_NAME>
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
