# Anticipated Objections & Interview Prep

*Prepared responses to tough questions from Adoption Strategy Lead interviews.*

**Context:** Based on interviewer profile - deeply process-oriented, data-driven, focused on scalability, and experienced in operationalizing Sales/Dev requests.

---

## Interviewer Profile Summary

| Trait | Evidence | How They'll Challenge You |
|-------|----------|---------------------------|
| **Process Builder** | Created Practice Lead motion, Feature Intake Process | "Does this scale? Is it repeatable?" |
| **Data Steward** | Performance analyst, built ETLs, dashboards | "Where's the data? Single source of truth?" |
| **Cross-functional Operator** | PM ↔ Sales alignment, Security programs | "Who owns what? How do you get buy-in?" |
| **Risk Mitigator** | Defined DoD, risk identification | "What can go wrong? Contingency plan?" |
| **Influence Without Power** | Stakeholder management across orgs | "How do you drive action without authority?" |

---

## Section 1: On the 3-6-12 Plan

### Q1: "What's your baseline? How do you know 'strategic wins' moved the needle?"

**Answer:**
> We capture baseline in Month 1: FE confidence survey (Week 2), retention data by segment (Week 3), and attach rate definition with Finance (Week 4). Phase 1 success requires +20% FE confidence improvement and 3-5 documented strategic wins with business value narratives.

**Source:** `40_execution/01_action_plan.md` - Month 1 deliverables

**Gap to Address:** ⚠️ Specific numeric baselines not yet defined. Add target numbers to action plan.

---

### Q2: "How does this scale beyond lighthouse accounts?"

**Answer:**
> The plan has explicit scaling phases:
> - **P1 (Prove It):** 10-15 lighthouse accounts, prove the playbook works
> - **P2 (Scale It):** Regional rollout (Month 5), vertical playbooks, 5+ additional wins
> - **P3 (Expand It):** Coverage campaign (Month 7), SI partners, 50+ accounts by Month 12
>
> The lighthouse accounts are the test bed—we document what works, build playbooks, then scale through enablement and partners.

**Source:** `40_execution/01_action_plan.md` - Phase structure

**Gap to Address:** ⚠️ Add explicit "lighthouse → vertical → regional" transition criteria.

---

### Q3: "What happens if Phase 1 hypotheses are invalidated at Month 3?"

**Answer:**
> Every hypothesis has explicit "If Validated / If Invalidated" pivot logic. For example:
> - **H3 (FE Enablement):** If invalidated → Investigate product blockers, not just enablement
> - **H6 (Metrics Align BUs):** If invalidated → Revise metric definitions, start qualitative
> - **H8 (Quality Motion):** If invalidated → Investigate other retention drivers beyond PS engagement
>
> We don't fail—we learn and pivot. The plan is designed for hypothesis testing, not certainty.

**Source:** `40_execution/01_action_plan.md` - Phase 1 Hypothesis Decisions table

**Gap to Address:** ✅ Strong - well covered in action plan

---

### Q4: "Who owns what? I see a lot of 'AA' ownership—what about Field Ops, Enablement, PM?"

**Answer:**
> The Adoption Architect is the orchestrator, not the sole owner. Key partnerships:
> - **Enablement:** Training delivery, content creation
> - **Field Ops:** SFDC instrumentation, pipeline tracking
> - **Analytics:** Dashboard creation, data collection
> - **PM:** Feature prioritization, roadmap influence
> - **PS:** Quality motion delivery for lighthouse accounts
>
> The action plan shows "AA + [Partner]" for shared deliverables.

**Source:** `40_execution/01_action_plan.md` - Owner column

**Gap to Address:** 🔴 Add formal **RACI matrix** showing Responsible, Accountable, Consulted, Informed for each major deliverable.

---

### Q5: "How do you close the loop with requesters when things change?"

**Answer:**
> Multiple feedback loops:
> - **Weekly:** Apps Adoption Council with signal triage, PM feedback queue
> - **Monthly:** Loss analysis review, BU newsletter with status updates
> - **Quarterly:** PM feedback synthesis, exec readout with hypothesis status
>
> Field signals captured → triaged weekly → escalated to PM → status communicated back through newsletter.

**Source:** `40_execution/02_operating_cadence.md`

**Gap to Address:** ⚠️ Add explicit "Signal → Action → Outcome" closed-loop tracker document.

---

### Q6: "What's the communication cadence to leadership? Weekly? Bi-weekly?"

**Answer:**
> | Cadence | Forum | Audience |
> |---------|-------|----------|
> | Weekly | Apps Adoption Council summary | FE leadership |
> | Monthly | BU+1 Newsletter | SVPs, VPs |
> | Quarterly | Exec Readout (30 min) | SVP/VP Field Engineering |
>
> Templates exist for newsletter and exec readout.

**Source:** `40_execution/02_operating_cadence.md`

**Gap to Address:** ✅ Strong - well defined

---

### Q7: "Where's the single source of truth for tracking progress?"

**Answer:**
> Currently, metrics are dispersed across documents. The plan includes:
> - **Signal Log:** Qualitative feedback tracking (Priority action)
> - **Dashboard specs:** GTM Leaders, PM, and AA dashboards defined
> - **SFDC:** Strategic win tracking, pipeline health
>
> Consolidation is in progress—metrics framework document outlines the integration plan.

**Source:** `parking_lot/metrics.md`

**Gap to Address:** 🔴 Metrics are dispersed. Priority action: Create consolidated tracker/dashboard by Month 2.

---

## Section 2: On Sales Play Robustness

### Q8: "How does an FE actually USE this playbook day-to-day? What's the trigger?"

**Answer:**
> Guided selling triggers identify when to bring up Apps:
> - Customer mentions "business user analytics"
> - Existing Unity Catalog deployment
> - Model serving in production
> - Frustration with current BI tools
>
> These become trigger cards that FEs can reference during discovery calls.

**Source:** `10_field/03_sales_plays_and_patterns.md`

**Gap to Address:** 🔴 Triggers exist in docs but not operationalized. Create **Guided Selling Trigger Cards** (1-pager/printable) - listed in `parking_lot/deliverables.md`.

---

### Q9: "What's the 'definition of done' for a sales play?"

**Answer:**
> A complete sales play requires:
> 1. **Target criteria** - Who this play applies to
> 2. **Trigger** - When to use it
> 3. **Positioning** - What to say
> 4. **Objection handling** - How to respond to pushback
> 5. **Qualification questions** - How to validate fit
> 6. **Success criteria** - How we know it worked

**Source:** Implied in `10_field/03_sales_plays_and_patterns.md`

**Gap to Address:** 🔴 Not explicitly defined. Add formal **Sales Play Definition of Done** to field enablement docs.

---

### Q10: "How do you handle conflicting priorities between Apps and other products?"

**Answer:**
> Apps is positioned as "tip of the spear"—it opens doors for other products, not competes with them. The attach rate metric measures how Apps leads to UC, DBSQL, Model Serving expansion.
>
> For FE time, we:
> 1. Focus on lighthouse accounts (not all accounts)
> 2. Leverage SI partners for delivery capacity
> 3. Prioritize verticals where Apps has highest fit (regulated, data-heavy)

**Source:** `08_hypotheses_and_beliefs.md` (H1), `40_execution/01_action_plan.md` (Risk mitigation)

**Gap to Address:** ⚠️ Add prioritization framework: "When to lead with Apps vs. Core vs. AI"

---

### Q11: "What training exists? Who delivers it? When?"

**Answer:**
> | Training | Timeline | Delivery |
> |----------|----------|----------|
> | Security/governance patterns | M2 W5-6 | AA + Enablement |
> | App discovery workshop | M2 W7 | AA + Enablement |
> | Competitive talk tracks | M2 W7 | AA |
> | Guided selling triggers | M2 W8 | AA |
>
> Training completion is a P1 KR2 metric (target: 80%+).

**Source:** `40_execution/01_action_plan.md` - Month 2 deliverables

**Gap to Address:** ⚠️ Add **Training Calendar** with dates, owners, and delivery method (live vs. async).

---

### Q12: "How do you measure FE confidence before vs. after enablement?"

**Answer:**
> - **Baseline survey:** Week 2 of Month 1
> - **Post-enablement survey:** Week 12 of Month 3
> - **Target:** +20% confidence improvement
> - **Validation:** H3 hypothesis decision at Month 3
>
> If improvement < 20%, we investigate product blockers rather than doubling down on enablement.

**Source:** `40_execution/01_action_plan.md`, `30_framework/02_traceability_matrix.md`

**Gap to Address:** ⚠️ Survey instrument needs to be created. Listed as Priority #1 in `parking_lot/metrics.md`.

---

### Q13: "What's the intake process for field signal? How do you avoid noise?"

**Answer:**
> Signal capture framework:
> 1. **Capture:** FE submits signal via SFDC field or Slack
> 2. **Triage:** Weekly council reviews, categorizes by impact
> 3. **Escalate:** High-impact signals → PM feedback queue
> 4. **Track:** Signal log with status, resolution, timeline
> 5. **Close:** Outcome communicated back to requester
>
> Noise filtered by: deal impact (ACV at risk), frequency (multiple accounts), and strategic alignment.

**Source:** `10_field/07_signal_capture.md`

**Gap to Address:** ⚠️ Signal Log not yet operational. Priority action: Launch in Week 1.

---

## Section 3: On Metrics & Data

### Q14: "These metrics are great—but where does the data actually come from?"

**Answer:**
> | Metric | Data Source | Availability |
> |--------|-------------|--------------|
> | Strategic wins | SFDC + Signal Log | ✅ Available |
> | Attach rate | SFDC + Telemetry | ⚠️ Needs definition |
> | FE confidence | Survey | ⬜ To create |
> | Training completion | LMS | ✅ Available |
> | Loss analysis | Loss Registry | ⬜ To create |
>
> Data gaps are documented with priority actions for instrumentation.

**Source:** `parking_lot/metrics.md` - Data Sources Matrix

**Gap to Address:** 🔴 Many metrics say "Not collected." Add instrumentation timeline to action plan.

---

### Q15: "What's automated vs. manual? Manual won't scale."

**Answer:**
> Current state:
> - **Automated:** SFDC pipeline, LMS training completion, product telemetry
> - **Manual:** Signal capture (until log launched), FE surveys, loss analysis
>
> Priority is automating signal capture through SFDC field + Slack integration.

**Source:** Implied across metrics docs

**Gap to Address:** 🔴 Not explicitly addressed. Add **automation status column** to metrics inventory.

---

### Q16: "How do you prevent gaming the metrics?"

**Answer:**
> Multiple metric types prevent gaming:
> - **Leading indicators** (FE confidence, signals) + **Lagging indicators** (wins, attach rate)
> - **Qualitative** (win narratives) + **Quantitative** (attach %)
> - **Self-reported** (surveys) + **System-captured** (telemetry)
>
> No single metric can be gamed without others showing the inconsistency.

**Source:** `parking_lot/metrics.md` - Leading vs Lagging section

**Gap to Address:** ⚠️ Add explicit **metric definitions** with anti-gaming criteria.

---

### Q17: "What's the refresh cadence? Real-time? Weekly?"

**Answer:**
> | Cadence | Metrics |
> |---------|---------|
> | Weekly | Signals captured, lighthouse progress, actions closed |
> | Monthly | Strategic wins, FE confidence, loss analysis |
> | Quarterly | Attach rate, hypothesis status, coverage |

**Source:** `parking_lot/metrics.md` - Section 8

**Gap to Address:** ✅ Strong - well defined

---

## Section 4: On Process & Governance

### Q18: "What happens when you're not here? Does this outlast you?"

**Answer:**
> Built-in sustainability:
> - **Operating cadence** with documented rhythms
> - **Council charter** defining purpose, participants, agenda
> - **Templates** for newsletter, exec readout, PM feedback
> - **Playbooks** that can be executed by any trained FE
>
> Philosophy: "Processes become institutions and outlast people."

**Source:** `40_execution/02_operating_cadence.md`

**Gap to Address:** ⚠️ Add **succession documentation** and **process owner backup** assignments.

---

### Q19: "How do you handle conflict between PM priorities and field signal?"

**Answer:**
> Council structure provides resolution:
> - **Weekly triage:** Categorize signals by impact
> - **PM feedback queue:** Structured handoff to PM
> - **Quarterly synthesis:** Top 5 blockers with deal impact data
> - **Escalation:** If PM doesn't act, escalate to leadership with ACV impact
>
> Field signal is data—when quantified with deal impact, it influences prioritization.

**Source:** `40_execution/02_operating_cadence.md`, `10_field/07_signal_capture.md`

**Gap to Address:** ⚠️ Add formal **escalation matrix** with SLAs (e.g., 7 days to PM response).

---

### Q20: "What's the escalation path when things stall?"

**Answer:**
> | Stall Type | Escalation Path |
> |------------|-----------------|
> | Enablement not adopted | AA → Enablement Lead → VP Enablement |
> | PM not acting on signal | AA → PM Lead → VP Product |
> | BU leader not engaged | AA → FE Director → SVP FE |
> | Account blocked by product gap | Document workaround, add to loss analysis |

**Source:** `40_execution/01_action_plan.md` - Risk mitigation

**Gap to Address:** 🔴 Escalation paths not formalized. Add **escalation ladder with SLAs**.

---

### Q21: "How do you get BU+1 buy-in without direct authority?"

**Answer:**
> Influence tactics:
> 1. **Data-driven:** Strategic wins with business value, attach rate data
> 2. **Executive alignment:** M2 meetings with 2-3 SVP/VPs (H6 validation)
> 3. **Quick wins:** Early lighthouse success builds credibility
> 4. **BU-specific metrics:** Tailor message to what each BU cares about
> 5. **Newsletter:** Regular visibility keeps Apps top-of-mind
>
> H6 hypothesis specifically tests whether metrics will align BU leaders.

**Source:** `40_execution/01_action_plan.md`, `08_hypotheses_and_beliefs.md`

**Gap to Address:** ⚠️ Add **BU Engagement Playbook** with influence tactics by BU type.

---

## Summary: Preparation Checklist

### ✅ Strong Areas (Confident to Answer)

- [ ] Hypothesis validation framework with pivots
- [ ] Operating cadence and communication rhythms
- [ ] Traceability from hypothesis to metric
- [ ] Risk mitigation with contingencies
- [ ] Phased approach with clear decision points

### 🔴 Gaps to Fix Before Interview

| Gap | Fix | Priority |
|-----|-----|----------|
| Baselines undefined | Add specific numeric targets | High |
| No RACI matrix | Create ownership clarity | High |
| No operational cards | Create Trigger Cards, Objection Cards | High |
| No escalation ladder | Add escalation matrix with SLAs | Medium |
| Metrics dispersed | Create consolidated dashboard | Medium |
| No DoD for sales plays | Define completion criteria | Medium |

### 📝 Rehearsal Focus

1. **Walk through the 3-6-12 plan** with hypothesis validation logic
2. **Explain the scaling mechanism:** lighthouse → vertical → regional
3. **Demonstrate data awareness:** Know which metrics exist vs. need instrumentation
4. **Show process thinking:** Operating cadence, feedback loops, escalation
5. **Own the gaps:** "We've identified X gaps and have a plan to address them"

---

*Last Updated: January 2026*

