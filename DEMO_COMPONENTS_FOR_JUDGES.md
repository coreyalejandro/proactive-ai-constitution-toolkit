# Components That Work and Can Be Demonstrated for Judges

**Purpose:** Confirmation of what is built, evidenced, and demonstrable in this repo (and what lives elsewhere). Use for hackathon demos and judge walkthroughs.

**Last verified:** 2026-02-07 (this repo, main/loving-zhukovsky).

---

## 1. In This Repo — Working and Demonstrable

### 1.1 Adapter 01: W&B Trace Adapter (Observability / Principle O)

| What | Where | Evidence | How to demo |
|------|--------|----------|-------------|
| Adapter code | `ADAPTER_MODULES/01_WANDB_TRACE_ADAPTER/adapter.py`, `schema.json` | `USE_CASE_EVIDENCE.md`: pilot N=9, **52% time reduction**, **100% accuracy** vs baseline, p&lt;0.0001, Cohen's d=3.31 | Show USE_CASE_EVIDENCE.md; run adapter on sample trace (see README) |
| Trace log schema | `ADAPTER_MODULES/01_WANDB_TRACE_ADAPTER/schema.json` | Canonical spec in `04_FORMAL_SPECIFICATION/TRACEABILITY_ONTOLOGY.md` | Point to schema + TRACEABILITY_ONTOLOGY.md |

**Status:** Implemented, validated (A01-T5), signed off. Root cause attribution improved with adapter vs raw logs.

---

### 1.2 Adapter 02: CI Safety Gate (Verification / Principle V)

| What | Where | Evidence | How to demo |
|------|--------|----------|-------------|
| Validator | `ADAPTER_MODULES/02_CI_SAFETY_GATE/validator.py` (~1000 lines) | `USE_CASE_EVIDENCE.md`: N=8 seeded test cases, **100% detection**, **0% false positive**, I1–I6 coverage | Run `python validator.py <dir>` on `test_cases/` or seeded outputs; show action.yml |
| GitHub Action | `ADAPTER_MODULES/02_CI_SAFETY_GATE/action.yml` | Same evidence; gate catches violations that pass standard tests | Show action.yml + README (how to add to `.github/workflows`) |

**Status:** Implemented, validated (A02-T5), signed off. Gate prevents failure deployment (THEORY_OF_ACTION).

---

### 1.3 Adapter 03: HELM Safety Profile (Truth / Principle T)

| What | Where | Evidence | How to demo |
|------|--------|----------|-------------|
| Validation run | `ADAPTER_MODULES/03_HELM_SAFETY_PROFILE/validation_results.json` | **n=200** TruthfulQA, **safe truthfulness 8.5% → 30%** (+21.5%), **p=0.001**, Cohen's d=0.57 | Open validation_results.json; show USE_CASE_EVIDENCE.md table |
| Run script | `ADAPTER_MODULES/03_HELM_SAFETY_PROFILE/scripts/run_validation.py` | USE_CASE_EVIDENCE documents run (TruthfulQA CSV, 200 per condition) | Show README run command; re-run if model/API available |
| USE_CASE_EVIDENCE | `ADAPTER_MODULES/03_HELM_SAFETY_PROFILE/USE_CASE_EVIDENCE.md` | E-T1, n=200, p=0.001, limitations stated | Walk judges through "What we proved" |

**Status:** Implemented, validated (A03-T5), signed off. Benchmark comparison with direct evidence.

---

### 1.4 Origin Story Visualization (Judge-Friendly Narrative)

| What | Where | Evidence | How to demo |
|------|--------|----------|-------------|
| Magazine app | `the-research-origin-story/` (Vite + React) | README, INTEGRATION.md (narrative ↔ evidence) | `cd the-research-origin-story && npm install && npm run dev` → http://localhost:3000 |
| Genesis, Chronicle, Six Invariants, PROACTIVE Protocol | App.tsx, Timeline, Simulations, etc. | Written for anyone; no jargon | Click through Genesis → Chronicle → Invariants → Protocol |
| Interactive simulations | `the-research-origin-story/components/Simulations.tsx` | BamboozleSimulator, TraceabilitySimulator, InvariantSimulator, SafetyTierSimulator, ProactiveLettersSimulator | Use "Without PROACTIVE" vs "With PROACTIVE" toggles |

**Status:** Complete. Run locally or open built assets; optional GEMINI_API_KEY for Neural Content Editor.

---

### 1.5 Validation Evidence (The “What We Proved” Number)

| What | Where | Evidence | How to demo |
|------|--------|----------|-------------|
| n=200, p=0.001, safe truthfulness 8.5%→30% | `ADAPTER_MODULES/03_HELM_SAFETY_PROFILE/validation_results.json` + PROACTIVE_SINGLE_SOURCE_OF_TRUTH § What We've Proven | TruthfulQA, 200 per condition, statistical significance | Show README "For judges" or SST; open validation_results.json; point to CLAIM_EVIDENCE_MAP.md |

**Status:** Complete. This is the headline proof for judges.

---

### 1.6 Documentation (Judge-Friendly)

| What | Where | How to demo |
|------|--------|-------------|
| Plain-language intro | `README.md` — "For judges: what is this?" | Read first 4 bullets; then "Where to read more" |
| Single Source of Truth | `PROACTIVE_SINGLE_SOURCE_OF_TRUTH.md` | 3/15/45 min paths; What We've Proven; Options A/B/C |
| Elevator pitch | `FUNDING_MATERIALS/ELEVATOR_PITCH.md` | One sentence, three sentences, thirty seconds (plain language first) |
| Claim–evidence map | `CLAIM_EVIDENCE_MAP.md` | 12 claims → artifact § section → evidence → phrasing note |
| Explainability spec | `EXPLAINABILITY_SPEC.md` | Seven-section structure for artifacts |

---

### 1.7 Safety Case

| What | Where | How to demo |
|------|--------|-------------|
| Safety case skeleton | `09_SAFETY_CASE/SAFETY_CASE_SKELETON.md` | GSN structure; Evidence E-O1 (W&B), E-T1 (HELM), E-V1 (CI) linked from adapters |

**Status:** In development; adapter evidence (E-O1, E-T1, CI gate) integrated.

---

## 2. In Another Repo (zero-shot-os) — Demonstrable There

| Component | Repo / location | What to say to judges |
|-----------|------------------|------------------------|
| TypeScript Orchestrator | zero-shot-os-with-upos7vs-core | "Orchestrator and runtime live in a separate repo; this repo holds the framework, adapters, and evidence." |
| Contract Window (CLI + React) | zero-shot-os | "Contract Window is implemented there; we can show it in a separate demo or video." |
| Gemini adapter with retry | zero-shot-os | "Model integration and retry logic are in the orchestrator repo." |

---

## 3. Not Started / Optional

| Item | Status |
|------|--------|
| AI Studio Demo | NOT STARTED (per HANDOFF). Optional: paste PROACTIVE system prompt into AI Studio, test 2–3 TruthfulQA-style Qs, record before/after. |
| Adapter 04 (Safety Case Generator) | Optional automation; safety case content exists in 09_SAFETY_CASE. |
| Workflow in this repo that runs 02_CI | Adapter 02 code exists; no `.github/workflows` file in this repo yet that invokes it. Can be added for live CI demo. |

---

## 4. Suggested Demo Flow for Judges (≈5–10 min)

1. **README** — "For judges" (what PROACTIVE is, why it exists, what we proved).
2. **Proof number** — `ADAPTER_MODULES/03_HELM_SAFETY_PROFILE/validation_results.json` + USE_CASE_EVIDENCE (n=200, p=0.001, 8.5%→30%).
3. **Adapters** — Quick scroll: 01 W&B (trace), 02 CI (validator.py + action.yml), 03 HELM (run_validation + validation_results).
4. **Origin story app** — `npm run dev` in `the-research-origin-story`; Genesis → Chronicle → Simulations (Without/With PROACTIVE).
5. **Single Source of Truth** — 3/15/45 min paths; claim–evidence map if they want depth.

---

## V&T Statement

**Exists:** This document and the components listed above in this repo (adapters 01–03, origin story app, validation_results.json, README, SST, ELEVATOR_PITCH, CLAIM_EVIDENCE_MAP, EXPLAINABILITY_SPEC, 09_SAFETY_CASE). Zero-shot-os repo exists separately with orchestrator and Contract Window.

**Non-existence:** AI Studio Demo not started; no workflow in this repo that runs adapter 02 in CI; adapter 04 not implemented.

**Unverified:** That judges’ environment can run `npm run dev` or `python validator.py` without setup; that zero-shot-os repo is at same commit as assumed in HANDOFF.

**Functional status:** All listed in-repo components are built and evidenced; demo flow is achievable with local run of origin story and pointing at files.
