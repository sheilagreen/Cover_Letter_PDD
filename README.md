# Multi-Agent Cover Letter Automation Engine

[![Architecture](https://img.shields.io/badge/Architecture-Multi--Agent_Pipeline-blue.svg)](#system-architecture)
[![Safety](https://img.shields.io/badge/Governance-Anti--Hallucination_&_Injection_Defense-green.svg)](#safety--governance)
[![Status](https://img.shields.io/badge/Deliverable-Process_Design_Document_(PDD)_V3.0-purple.svg)](#overview)

> An enterprise-grade, multi-node generative AI workflow designed to automate high-fidelity, hallucination-free cover letter synthesis with structured critic loops and human-in-the-loop governance.

---

## Executive Overview

Writing tailored, high-converting cover letters is a high-friction, repetitive bottleneck for job seekers and career professionals—often consuming 3–5 hours per week. Off-the-shelf generative AI tools frequently fail in professional hiring contexts because they hallucinate qualifications, inject hyperbolic corporate buzzwords, and lack contextual reasoning.

This project outlines an intelligent, deterministic **Process Design Document (PDD)** that decouples cover letter drafting into specialized agent nodes: **structured fact extraction**, **strategic logic reasoning**, **parallel draft generation**, and **dual-persona evaluation loops** with automated anti-inflation critics.

---

## System Architecture

The pipeline processes four primary unstructured inputs (Resume, Job Posting, Company Culture Research, and Historical Writing Voice) through an iterative 7-stage engine with integrated safety protocols and multi-agent evaluation.

---

## Core Pipeline Components

### 1. Defense Layer (Intake & Sanitization)

**Protocol 0 — Input Sanitization & Injection Filter**

Scans and neutralizes adversarial prompt injections (e.g., hidden instructions attempting to force-pass candidates or alter system rules). Detects instruction-data smearing using Python sanitization to identify and redact text enclosed in brackets, braces, or high-risk directives.

**Protocol 1 — Hard Constraint Validation**

Validates location, work authorization, and required minimum experience before downstream LLM invocation. Flags mismatches in Location, Work Authorization, or Years of Experience. Detects logical impossibilities such as overlapping work dates or corrupted document formatting.

### 2. Extraction Engine (Gatekeeper + Critic Loop)

Converts unstructured documents into an exact JSON schema (job_intelligence, candidate_evidence, voice_profile).

**Verbatim Locality Constraint:** Prevents narrative promotion—skills and achievements are only extracted if explicitly present in labeled sections without semantic stitching.

**Failure Mode:** If required data is missing from a clearly labeled section, outputs null for that field. No inference. No stitching. No scoring. No evaluation.

### 3. Reasoning & Compliance (Judge + Anti-Inflation Critic Loop)

Outputs strategic alignment logic in XML format.

**Requirement-Language Quarantine:** Strictly prohibits upgrading candidate experience (e.g., converting "desire to learn Excel" into "Mastery of Excel").

**Gap Analysis:** Identifies critical skill gaps and pairs them with authentic narrative pivots.

**Design Philosophy:** Integrity > Extraction > Personalization.

### 4. Parallel Draft Generator (Worker Router)

Produces three stylistically distinct drafts concurrently:

**Draft A (Enthusiasm Mode):** Mission alignment and forward-looking energy.

**Draft B (Personality Mode):** Conversational warmth anchored in verified leadership experiences.

**Draft C (Fit Mode):** Analytical, evidence-first requirement mapping.

### 5. Multi-Persona Evaluation & Synthesis

**Hiring Manager Persona:** Audits for credibility, overall structure, and culture fit.

**Team Lead Persona:** Audits for operational realism, conciseness, and execution signals.

**Final Worker:** Synthesizes the highest-scoring structural elements into one polished, truth-anchored artifact.

---

## Business Impact & ROI

| Metric | Current State (Manual) | Target State (Automated Pipeline) | Estimated Impact |
| :--- | :--- | :--- | :--- |
| Drafting Time | ~60–90 min / letter | < 2 min (execution) + 15 min review | ~75% time reduction |
| Cognitive Load | Rated 9/10 (High friction) | Automated Extraction & Strategic Mapping | Significant burnout reduction |
| Hallucination Rate | 15–25% (Single prompt) | < 5% (Multi-step critic audits) | ~60–70% risk reduction |
| Annual Reclaimed Time | Baseline | 1,560 hours saved (Enterprise scale) | Net Profit: $148,056/yr |

---

## Robustness & Red-Teaming Validation

The system was stress-tested against deliberate prompt injection and requirement-smearing attacks:

| Attack Scenario | Threat Vector | Defense Mechanism | Result |
| :--- | :--- | :--- | :--- |
| Metadata Hijack | Directive instructing AI to reject specific candidates | Defense Layer scans for directive verbs (IGNORE, OVERRIDE) | Blocked |
| Requirement Inflation | Job requires "Mastery of Excel" candidate only has basic skills | Judge Critic enforces strict source grounding & quarantines buzzwords | Neutralized |
| Data Pollution | Fabricated experience blocks injected into plain text | Strict JSON locality & Gatekeeper Critic structural validation | Filtered |

---

## Tech Stack & Methodology

- **Frameworks:** Multi-Agent Orchestration, R.A.F.T. Prompt Engineering Framework
- **Data Formats:** JSON Schema Enforcement, XML Strategic Modeling
- **Governance:** Human-in-the-Loop (HITL), Defensive Pre-processing, Critic-Loop Evaluation

---

## Authors & Project Info

- **Project Title:** AI Automated Cover Letters
- **Team:** Sheila Green, Molly Lowell, and Whitney Robinson
- **Deliverable:** Process Design Document (PDD) — Final Release (V3.0)
