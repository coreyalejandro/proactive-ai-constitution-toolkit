# 8-Hour Hackathon Build — Ship It

**Goal:** Submission-ready by end of 8 hours. No new features. Package what exists; record demo; submit.

**Featured cases (locked):** Gemini origin story + FM-001 (DSPy) + FM-003 (CI inflated). See REFACTORED_PLAN_EXECUTION.md § Hackathon demo.

---

## Hour 0–1: Repo + submission checklist

- [ ] **Repo clean:** No stray untracked secrets; `.gitignore` correct. `git status` clean or intentional.
- [ ] **README judge path:** "For judges" at top (exists). One-sentence + what we proved + where to read more. No broken links.
- [ ] **Single entry doc:** PROACTIVE_SINGLE_SOURCE_OF_TRUTH.md linked from README. Open and confirm § What Is This?, § What We've Proven load.
- [ ] **Evidence links:** CLAIM_EVIDENCE_MAP.md and PROACTIVE_SINGLE_SOURCE_OF_TRUTH point to real files (01_FOUNDATIONS, ADAPTER_MODULES/0{1,2,3}, 09_SAFETY_CASE, validation_results or USE_CASE_EVIDENCE).
- [ ] **Origin story app:** `the-research-origin-story/` — `npm install && npm run dev` runs; Genesis + Chronicle visible. Note URL for video (e.g. http://localhost:3000).
- [ ] **Three incidents:** Confirm you can open ORIGIN_STORY_EVIDENCE.md (Gemini), FM_TESTCASES_FM-001_to_FM-003_2026-02-02.md (FM-001, FM-003) without errors.

**Output:** Repo is judge-ready; origin story app runs locally.

---

## Hour 1–2: Demo script (no recording yet)

- [ ] **Story in 3 beats:** (1) Problem: three real incidents — Gemini phantom completion + DSPy “implemented?” + CI/testing inflated. (2) Solution: PROACTIVE — six rules, gates, trace, evidence. (3) Proof: validation n=200, safe truthfulness 8.5%→30%, adapters (W&B, CI gate, HELM).
- [ ] **Script bullets (30–60 sec each):**
  - Beat 1: “I was bamboozled by AI — features ‘done’ that didn’t work, claims ‘implemented’ that weren’t. Here are three real cases.” [Show ORIGIN_STORY_EVIDENCE + FM_TESTCASES or app.]
  - Beat 2: “PROACTIVE sits between the AI and the user. Six rules: no ‘done’ without proof, no confidence without verification, trace every claim.” [Show PROACTIVE_SINGLE_SOURCE_OF_TRUTH or app Six Invariants.]
  - Beat 3: “We ran 200 TruthfulQA questions. Safe behavior tripled; uncertainty admission 14×. We have adapters for W&B traces, a CI safety gate, and a HELM-style eval.” [Show validation table or 03_HELM USE_CASE_EVIDENCE.]
- [ ] **Demo flow order:** Origin story app (Genesis → Chronicle → Invariants) → SST or README (What We've Proven) → Adapter list (01, 02, 03) + safety case (09_SAFETY_CASE).

**Output:** One-page demo script with timestamps or “minute 0–1”, “minute 1–2”, “minute 2–3”.

---

## Hour 2–4: Demo video

- [ ] **Tool:** Loom, OBS, or built-in screen recorder. Mic on; quiet room.
- [ ] **Intro (0:00–0:30):** “PROACTIVE — stops AI from saying ‘done’ when it didn’t. Built for the Gemini Hackathon.”
- [ ] **Problem (0:30–1:30):** Origin story app — Genesis + Chronicle; name the Gemini incident (phantom completion, rigged eval). Mention FM-001 (DSPy) and FM-003 (CI inflated) as two more real cases in the repo.
- [ ] **Solution (1:30–2:30):** Six Invariants + PROACTIVE protocol in app or SST. “Gates, trace chain, evidence — no bypass.”
- [ ] **Proof (2:30–3:30):** Validation: 8.5%→30% safe truthfulness, n=200, p=0.001. Show README or SST table; show adapter list (01 W&B, 02 CI, 03 HELM) and 09_SAFETY_CASE.
- [ ] **Outro (3:30–4:00):** “Repo link in description. PROACTIVE — epistemic reliability as a safety requirement.”
- [ ] **Export:** MP4 or link (Loom). No longer than 5 min; 3–4 min ideal.

**Output:** Demo video URL or file; ready to paste into Devpost.

---

## Hour 4–5: AI Studio demo (if required by hackathon)

- [ ] **Check hackathon rules:** Does Gemini Hackathon require an AI Studio project / shared prompt?
- [ ] **If yes:** New prompt in AI Studio. Paste PROACTIVE system instructions (from PROACTIVE_SINGLE_SOURCE_OF_TRUTH or 01_FOUNDATIONS/PROACTIVE_AI_CONSTITUTION). Configure structured output if needed. Test with 2–3 TruthfulQA-style questions; record “before/after” in video or screenshot.
- [ ] **If no:** Skip; video + repo is enough.

**Output:** AI Studio link (if required) or “N/A”.

---

## Hour 5–6: Submission packaging

- [ ] **Devpost:** Create or open submission. Title: e.g. “PROACTIVE — AI Safety Layer That Stops Confident False Claims”.
- [ ] **Description:** Short copy from README “For judges” + “What we proved” + “Three incident cases: Gemini origin story, capability mirage (DSPy), CI/testing inflated. See ORIGIN_STORY_EVIDENCE.md and FM_TESTCASES_FM-001_to_FM-003_2026-02-02.md.”
- [ ] **Repo URL:** Link to this repo (main branch or submission branch).
- [ ] **Video URL:** Paste demo video link.
- [ ] **Build / run instructions:** “See README. Origin story app: `the-research-origin-story/` → npm install, npm run dev. Adapters: 01_WANDB_TRACE_ADAPTER, 02_CI_SAFETY_GATE, 03_HELM_SAFETY_PROFILE — see each README.”
- [ ] **Team / credits:** Fill as needed.

**Output:** Devpost submission draft complete; one “Submit” away.

---

## Hour 6–7: Buffer — fix and polish

- [ ] **Watch video once:** Cut or re-record if over 5 min or if key message is unclear.
- [ ] **Click every link** in README and submission form; fix 404s.
- [ ] **Origin story:** If app is in submission, ensure it builds on a clean clone (`npm install && npm run dev` in `the-research-origin-story/`).
- [ ] **ELEVATOR_PITCH.md:** Steal one sentence for Devpost tagline if needed.

**Output:** No broken links; video and form polished.

---

## Hour 7–8: Submit and confirm

- [ ] **Submit** on Devpost before deadline.
- [ ] **Confirm:** Email or confirmation screen; repo public if required.
- [ ] **HANDOFF:** Update HANDOFF.md “What Was Just Completed” with “Hackathon submission submitted — [date]. Demo video [link]. Devpost [link].”

**Output:** Submission confirmed; HANDOFF updated.

---

## If you get ahead

- Add a **SUBMISSION.md** in repo root: “Gemini Hackathon [year] — PROACTIVE. Video: [link]. Devpost: [link]. Featured cases: Gemini origin story, FM-001, FM-003.”
- Pin **REFACTORED_PLAN_EXECUTION.md** or README in your own workflow so judges get one-click path.

---

## If you fall behind

- **Drop:** AI Studio demo (unless mandatory). Ship video + repo + Devpost.
- **Shorten video:** 2 min = Problem (Gemini + one FM) + Solution (PROACTIVE) + Proof (validation table).
- **Minimum viable:** README “For judges” + PROACTIVE_SINGLE_SOURCE_OF_TRUTH + one working adapter README + video link + submit.

---

**V&T**

- **Exists:** This 8-hour plan; repo with adapters 01–03, safety case, origin story app, FM test cases, SST.
- **Non-Existence:** No new code required; submission and video are the deliverables.
- **Unverified:** Devpost form fields and hackathon-specific rules (confirm locally).
- **Functional Status:** Execute top to bottom; buffer at 6–7; submit in 7–8.
