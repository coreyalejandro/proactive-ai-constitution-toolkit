# Steps to Complete 1.5 and Phase 2 Sign-Offs

**Goal:** Resolve non-existence (no 1.5 sign-off; no 2.3/2.6 sign-offs) and unverified items (product/lead asked; 02_CI/03_HELM formally verified and signed off).

**Prerequisite:** 1.1–1.4 done; 2.2 and 2.5 USE_CASE_EVIDENCE verified in tracker. Human is product/lead or delegate with authority to sign off.

---

## Part A — Ask product/lead and complete human read-through (1.5)

1. **Request 1.5 sign-off from product/lead**
   - Send: "We need product/lead sign-off on the first publishable unit (Adapter 01 + mini-research report per REFACTORED_PLAN_EXECUTION.md row 1.5). The human run sheet is in `READ_THROUGH_RESULTS.md`; code-assistant run is already Pass. Please complete the human steps (≈15 min) and fill the sign-off at the bottom."
   - Or schedule a 15–20 min slot to do it together.

2. **Human completes the run sheet**
   - Open `README.md` (project root).
   - Open `READ_THROUGH_RESULTS.md`.
   - Execute **Human run sheet** (Steps 1–5): open `PROACTIVE_SINGLE_SOURCE_OF_TRUTH.md`, `EXPLAINABILITY_SPEC.md`, `CLAIM_EVIDENCE_MAP.md`; do each check; note any issues.
   - In **Step 5 — Sign-off**: check the appropriate box (Satisfied vs Not satisfied).
   - Fill **Human reviewer result**: Completed by, Date, Result (Pass/Fail), Blocking issues (if any).

3. **If Pass (or only non-blocking caveats)**
   - Record 1.5 sign-off in the tracker (Part C below).

---

## Part B — Formal verify and sign off Phase 2 rigor (2.3, 2.6)

4. **Verify 02_CI rigor (2.3)**
   - Open `01_FOUNDATIONS/THEORY_OF_ACTION.md` and identify the claim that a verification gate prevents failure deployment.
   - Open `ADAPTER_MODULES/02_CI_SAFETY_GATE/USE_CASE_EVIDENCE.md`.
   - Confirm: evidence (seeded violations caught, 100% detection, 0% FP) directly tests that the gate blocks non-compliant outputs from passing.
   - If satisfied: product/lead notes "2.3 verified — evidence tests THEORY_OF_ACTION" (e.g. in HANDOFF or in a short comment in REFACTORED_PLAN_EXECUTION.md or this file). Then record 2.3 SIGN-OFF (Part C).

5. **Verify 03_HELM rigor (2.6)**
   - Open `ADAPTER_MODULES/03_HELM_SAFETY_PROFILE/USE_CASE_EVIDENCE.md`.
   - Confirm: "compared to what?" is answered (baseline vs PROACTIVE/COL); direct evidence (n=200, p=0.001, effect size, safe truthfulness 8.5%→30%) is documented.
   - If satisfied: product/lead notes "2.6 verified — benchmark comparison with direct evidence." Then record 2.6 SIGN-OFF (Part C).

---

## Part C — Record sign-offs in the tracker

6. **Update `REFACTORED_PLAN_EXECUTION.md`**
   - **Row 1.5:** Change `☐ SIGN-OFF` → `✅ SIGN-OFF`. Notes: e.g. "Product/lead sign-off — [date]. Human read-through complete per READ_THROUGH_RESULTS.md."
   - **Row 2.3:** Change `☐ SIGN-OFF` → `✅ SIGN-OFF`. Notes: e.g. "Product/lead sign-off — evidence tests THEORY_OF_ACTION; gate prevents failure deployment. [date]."
   - **Row 2.6:** Change `☐ SIGN-OFF` → `✅ SIGN-OFF`. Notes: e.g. "Product/lead sign-off — benchmark comparison with direct evidence (n=200, TruthfulQA). [date]."

7. **Update Next concrete actions**
   - Replace the first two bullets with:
     - "**Phase 1 sign-off:** 1.5 SIGN-OFF complete (product/lead — [date])."
     - "**Phase 2 closure:** 2.3 and 2.6 SIGN-OFF complete (product/lead — [date])."

8. **Update V&T Statement**
   - **Exists:** Add "1.5, 2.3, 2.6 SIGN-OFF complete (product/lead [date])."
   - **Unverified:** Remove or replace with "None for 1.5 / Phase 2 sign-offs; all three sign-offs completed."

---

## Part D — Optional: HANDOFF and READ_THROUGH_RESULTS

9. **HANDOFF.md**
   - In "What Was Just Completed" or "Current Project State", add: "1.5 SIGN-OFF and Phase 2 rigor sign-offs (2.3, 2.6) completed — [date]."
   - Remove or update any line that says "1.5 SIGN-OFF still pending" or "Phase 2 verification pending."

10. **READ_THROUGH_RESULTS.md**
    - Ensure "Human reviewer result" is filled (Completed by, Date, Result). No file edit needed if already done in Part A.

---

## Checklist (quick ref)

- [ ] Product/lead asked for 1.5 sign-off (request sent or meeting scheduled).
- [ ] Human run sheet in `READ_THROUGH_RESULTS.md` completed (Steps 1–5 + Human reviewer result).
- [ ] 2.3 verified: 02_CI evidence tests THEORY_OF_ACTION (gate prevents failure deployment).
- [ ] 2.6 verified: 03_HELM "compared to what?" with direct evidence.
- [ ] Tracker updated: 1.5, 2.3, 2.6 → ✅ SIGN-OFF with notes and date.
- [ ] Tracker "Next concrete actions" and V&T updated.
- [ ] HANDOFF.md updated (no pending 1.5 / Phase 2 sign-off).

---

**V&T**

- **Exists:** This step list (`.planning/SIGN_OFF_STEPS.md`); REFACTORED_PLAN_EXECUTION.md with 2.2/2.5 verified; READ_THROUGH_RESULTS.md with code-assistant Pass and human run sheet.
- **Non-Existence:** No completed 1.5/2.3/2.6 sign-offs until Part A–C are done.
- **Unverified:** Whether product/lead has been asked and will complete Parts A–C.
- **Functional Status:** Steps are ordered and sufficient to close 1.5 and Phase 2 sign-offs once executed.
