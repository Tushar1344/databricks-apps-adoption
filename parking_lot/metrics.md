# Consolidated Metrics Framework

*Parking lot for metrics integration across the playbook.*

**Status:** Analysis complete. Metrics are dispersed across 15+ documents and need consolidation.

---

## Executive Summary

The playbook defines metrics in multiple places but lacks:
- A single source of truth for all metrics
- Clear data source mapping
- Dashboard specifications for different audiences
- Instrumentation priorities

This document consolidates all metrics and proposes an integrated framework.

---

## 1. North Star Metrics by Phase

```
┌─────────────────────────────────────────────────────────────────┐
│                    METRICS PYRAMID                              │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│                      12+ MONTHS                                 │
│                    ┌───────────┐                                │
│                    │ COVERAGE  │                                │
│                    │ Unique    │                                │
│                    │ Accounts  │                                │
│                    └─────┬─────┘                                │
│                          │                                      │
│                    6-9 MONTHS                                   │
│               ┌──────────────────┐                              │
│               │   ATTACH RATES   │                              │
│               │   SKU + Use Case │                              │
│               │   Expansion      │                              │
│               └────────┬─────────┘                              │
│                        │                                        │
│                   3-6 MONTHS                                    │
│          ┌─────────────────────────┐                            │
│          │    STRATEGIC WINS       │                            │
│          │    Decisive account     │                            │
│          │    wins proving value   │                            │
│          └─────────────────────────┘                            │
│                                                                 │
│  Earlier phases MUST succeed for later phases to be meaningful  │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

| Phase | North Star | Definition | Target | Source Doc |
|-------|------------|------------|--------|------------|
| **P1 (M1-3)** | Strategic Wins | Decisive account wins with Apps delivering clear business value | 3-5 wins | 09_strategic_inputs, 10_action_plan |
| **P2 (M4-6)** | Attach Rates | SKU and use case attach driven by Apps | Baseline + improvement | 09_strategic_inputs, 10_action_plan |
| **P3 (M7-12)** | Coverage | Unique accounts with production Apps deployed | 50+ accounts | 09_strategic_inputs, 10_action_plan |

---

## 2. Motion-Specific Metrics

Different metrics apply to different customer profiles and adoption motions.

| Motion | Primary Metrics | Secondary Metrics | Customer Profile | Source Doc |
|--------|-----------------|-------------------|------------------|------------|
| **Quality** | Strategic Wins, Retention Rate | Active Users per App, Business Value Documented | Enterprise, Regulated | 01_icp_and_targeting |
| **Quantity** | Coverage, Apps Created | Active Developers, Self-serve Completion | Digital Native | 01_icp_and_targeting |

### Motion-Phase Alignment

| Phase | Primary Motion | Key Metric |
|-------|----------------|------------|
| P1 (Prove It) | Quality | Strategic Wins |
| P2 (Scale It) | Both | Attach Rates |
| P3 (Expand It) | Quantity | Coverage |

---

## 3. Complete Metrics Inventory

### 3.1 Hypothesis Validation Metrics

| Hypothesis | Metric | Target | Data Source | Current Status | Source Doc |
|------------|--------|--------|-------------|----------------|------------|
| **H1: Tip of Spear** | Attach rate (% expand to other SKUs) | TBD | SFDC + Telemetry | ⬜ Not collected | 08_hypotheses |
| **H1** | Time-to-expansion (days) | TBD | Telemetry | ⬜ Not collected | 08_hypotheses |
| **H1** | Influenced ACV | TBD | Finance | ⬜ Not collected | 08_hypotheses |
| **H2: Ecosystem Moat** | Win rate vs hyperscalers | TBD | SFDC | ⬜ Not collected | 08_hypotheses |
| **H2** | Multi-product correlation | Positive | Telemetry | ⬜ Not collected | 08_hypotheses |
| **H3: FE Enablement** | FE confidence score | +20% improvement | FE Survey | ⬜ Not collected | 08_hypotheses |
| **H3** | Apps conversations per FE | TBD | Activity Tracking | ⬜ Not collected | 08_hypotheses |
| **H3** | Win rate: Enabled vs non-enabled FE | Enabled > non-enabled | SFDC + Training | ⬜ Not collected | 08_hypotheses |
| **H4: Archetypes** | % of wins in 3 archetypes | 80%+ | SFDC Analysis | ⬜ Not collected | 08_hypotheses |
| **H4** | Revenue by archetype | Measurable split | SFDC | ⬜ Not collected | 08_hypotheses |
| **H5: SI vs FDE** | SI time-to-value vs internal | SI ≤ internal | Project Tracking | ⬜ Not collected | 08_hypotheses |
| **H5** | SI-sourced pipeline | TBD | SFDC | ⬜ Not collected | 08_hypotheses |
| **H5** | SI customer satisfaction | ≥ internal | CSAT | ⬜ Not collected | 08_hypotheses |
| **H6: Metrics Align BUs** | BU leader acceptance | 3+ SVP/VPs | Stakeholder Feedback | ⬜ Not collected | 08_hypotheses |
| **H6** | Finance approval | Approved | Finance Team | ⬜ Not submitted | 08_hypotheses |
| **H7: Net-New Focus** | Win rate: Net-new vs migration | Net-new > migration | SFDC | ⬜ Not collected | 08_hypotheses |
| **H7** | CSAT: Net-new vs migration | Net-new > migration | CSAT | ⬜ Not collected | 08_hypotheses |
| **H8: Quality vs Quantity** | Retention by motion type | Motion-matched > mismatched | Telemetry | ⬜ Not collected | 08_hypotheses |
| **H8** | Active users per app by segment | TBD | Telemetry | ⬜ Not collected | 08_hypotheses |

### 3.2 Field Gap Metrics

| Category | Metric | Target | Data Source | Current Status | Source Doc |
|----------|--------|--------|-------------|----------------|------------|
| **Enablement** | Training completion rate | 80%+ | LMS | ⬜ Not tracked | 04_field_enablement |
| **Enablement** | FE confidence survey (baseline) | Establish baseline | Survey | ⬜ Not collected | 04_field_enablement |
| **Enablement** | FE confidence survey (post) | +20% vs baseline | Survey | ⬜ Not collected | 04_field_enablement |
| **Signal Capture** | Signals captured per week | 10+ | Signal Log | ⬜ 0 | 07_signal_capture |
| **Signal Capture** | PM features influenced | 2+ | PM Feedback | ⬜ 0 | 07_signal_capture |
| **Signal Capture** | Signal-to-escalation time | <7 days | Signal Log | ⬜ N/A | 07_signal_capture |
| **Signal Capture** | Field NPS on signal process | >7 | Survey | ⬜ N/A | 07_signal_capture |
| **Incentives** | Signal capture submissions | TBD | SFDC | ⬜ Not tracked | 05_field_incentives |

### 3.3 Product Gap Metrics

| Category | Metric | Target | Data Source | Current Status | Source Doc |
|----------|--------|--------|-------------|----------------|------------|
| **Loss Analysis** | Loss capture rate | 80%+ | Loss Registry | ⬜ 0% | 04_loss_analysis |
| **Loss Analysis** | PM features influenced by loss data | 2+ | PM Feedback | ⬜ 0 | 04_loss_analysis |
| **Loss Analysis** | Recovered deals | 3+ | SFDC | ⬜ 0 | 04_loss_analysis |
| **Loss Analysis** | Churn rate reduction | -20% | Telemetry | ⬜ TBD | 04_loss_analysis |
| **Use Case Tracking** | Use cases in registry | 50+ | Registry | ⬜ 0 | 01_use_case_tracking |
| **Use Case Tracking** | Classification accuracy | 90%+ | Registry | ⬜ N/A | 01_use_case_tracking |
| **Use Case Tracking** | New patterns identified | 1-2 | Registry | ⬜ 0 | 01_use_case_tracking |
| **Feature Adoption** | Features with DBU tracking | All core | Telemetry | ⬜ None | 02_feature_adoption |
| **Feature Adoption** | Features with CSAT tracking | Top 5 | CSAT Survey | ⬜ None | 02_feature_adoption |

### 3.4 Phase Key Results (Action Plan)

| Phase | KR | Target | Measurement | Source Doc |
|-------|-----|--------|-------------|------------|
| **P1** | KR1 | 3-5 strategic wins | Win narratives | 01_action_plan |
| **P1** | KR2 | FE enablement complete | Training completion | 01_action_plan |
| **P1** | KR3 | Council launched | Weekly cadence | 01_action_plan |
| **P1** | KR4 | 3+ BU leader alignment | Sponsorship | 01_action_plan |
| **P1** | KR5 | Quality motion piloted | 3 lighthouse accounts | 01_action_plan |
| **P2** | KR1 | Attach tracking live | Dashboard | 01_action_plan |
| **P2** | KR2 | Playbook v1 published | Field adoption | 01_action_plan |
| **P2** | KR3 | 5+ additional wins | Win narratives | 01_action_plan |
| **P2** | KR4 | PM influence demonstrated | Features prioritized | 01_action_plan |
| **P2** | KR5 | Both motions piloted | Retention improvement | 01_action_plan |
| **P3** | KR1 | 50+ unique accounts | Telemetry | 01_action_plan |
| **P3** | KR2 | Attach rate improvement | Dashboard | 01_action_plan |
| **P3** | KR3 | SI pilot complete | 1-2 SIs engaged | 01_action_plan |
| **P3** | KR4 | Playbook v2 published | Field adoption | 01_action_plan |

---

## 4. Data Sources Matrix

### 4.1 Data Source Overview

| Data Source | Description | Owner | Availability |
|-------------|-------------|-------|--------------|
| **SFDC** | Deals, pipeline, competitive, win/loss | Sales Ops | ✅ Available |
| **Product Telemetry** | App creation, usage, features, retention | PM/Analytics | ⚠️ Partial |
| **Field Signal Log** | Qualitative feedback, blockers | Adoption Architect | ⬜ To create |
| **FE Surveys** | Confidence, enablement effectiveness | Enablement | ⬜ To create |
| **PS Engagement Data** | Deep implementation details | PS | ⚠️ Partial |
| **Finance** | Revenue, influenced ACV | Finance | ⚠️ Requires ask |
| **LMS** | Training completion | Enablement | ✅ Available |
| **CSAT Survey** | Customer satisfaction by feature | CS | ⚠️ Partial |

### 4.2 Metric-to-Source Mapping

| Metric Category | SFDC | Telemetry | Signal Log | Survey | Finance | LMS |
|-----------------|:----:|:---------:|:----------:|:------:|:-------:|:---:|
| Strategic Wins | ✅ | | ✅ | | | |
| Attach Rates | ✅ | ✅ | | | ✅ | |
| Coverage | | ✅ | | | | |
| FE Confidence | | | | ✅ | | |
| Training Completion | | | | | | ✅ |
| Loss Analysis | ✅ | | ✅ | | | |
| Feature Adoption | | ✅ | | ✅ | | |
| Retention | | ✅ | | | | |
| Influenced Revenue | ✅ | | | | ✅ | |

### 4.3 Data Availability Status

| Status | Metrics Count | Examples |
|--------|---------------|----------|
| ✅ **Available** | 5 | Training completion, SFDC pipeline |
| ⚠️ **Partial** | 8 | Telemetry (some), CSAT (some features) |
| ⬜ **Not Collected** | 25+ | Most hypothesis validation metrics |
| ❌ **Not Instrumented** | 10+ | Attach rate, influenced ACV |

---

## 5. Dashboard Specifications

### 5.1 GTM Leaders Dashboard

**Audience:** SVPs, VPs of Field Engineering
**Frequency:** Monthly (newsletter) + Quarterly (exec readout)

```
┌─────────────────────────────────────────────────────────────────┐
│                    GTM LEADERS DASHBOARD                        │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   ┌─────────────────┐  ┌─────────────────┐  ┌────────────────┐ │
│   │ STRATEGIC WINS  │  │  ATTACH RATE    │  │   COVERAGE     │ │
│   │                 │  │                 │  │                │ │
│   │   3 / 5 target  │  │   TBD%          │  │  15 / 50       │ │
│   │   ████████░░    │  │   Baseline TBD  │  │  accounts      │ │
│   └─────────────────┘  └─────────────────┘  └────────────────┘ │
│                                                                 │
│   ┌─────────────────────────────────────────────────────────┐  │
│   │ PIPELINE HEALTH                                          │  │
│   │ ────────────────                                         │  │
│   │ Apps Opportunities: XX    Conversion Rate: XX%           │  │
│   │ Lighthouse Progress: X/15  Avg Deal Size: $XXK           │  │
│   └─────────────────────────────────────────────────────────┘  │
│                                                                 │
│   ┌─────────────────────────────────────────────────────────┐  │
│   │ FE ENABLEMENT                                            │  │
│   │ ───────────────                                          │  │
│   │ Training Completion: XX%   Confidence Score: XX (+X%)    │  │
│   │ Apps Conversations: XX/FE  Win Rate Enabled: XX%         │  │
│   └─────────────────────────────────────────────────────────┘  │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

| Metric | Source | Update Frequency |
|--------|--------|------------------|
| Strategic Wins | SFDC + Signal Log | Weekly |
| Attach Rate | SFDC + Telemetry | Monthly |
| Coverage | Telemetry | Monthly |
| Pipeline Health | SFDC | Weekly |
| FE Enablement | LMS + Survey | Monthly |

---

### 5.2 PM Dashboard

**Audience:** Product Management
**Frequency:** Weekly (Council) + Quarterly (PM Feedback Synthesis)

```
┌─────────────────────────────────────────────────────────────────┐
│                    PM DASHBOARD                                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   ┌─────────────────────────────────────────────────────────┐  │
│   │ TOP BLOCKERS BY DEAL IMPACT                              │  │
│   │ ──────────────────────────                               │  │
│   │ 1. Security (public URLs)     $XXM ACV at risk    🔴     │  │
│   │ 2. Cost (fixed pricing)       $XXM ACV blocked    🔴     │  │
│   │ 3. Horizontal scaling         $XXM limited        🟡     │  │
│   └─────────────────────────────────────────────────────────┘  │
│                                                                 │
│   ┌──────────────────────┐  ┌────────────────────────────────┐ │
│   │ LOSS ANALYSIS        │  │ FEATURE ADOPTION               │ │
│   │ ─────────────        │  │ ────────────────               │ │
│   │ Total Losses: XX     │  │ Lakebase:    ███████░ 70%      │ │
│   │ Product Gap: XX      │  │ Model Serve: ████░░░░ 40%      │ │
│   │ Competitive: XX      │  │ App Spaces:  ██░░░░░░ 20%      │ │
│   │ ACV Lost: $XXM       │  │ Unity Cat:   █████████ 90%     │ │
│   └──────────────────────┘  └────────────────────────────────┘ │
│                                                                 │
│   ┌─────────────────────────────────────────────────────────┐  │
│   │ SIGNAL TREND                                             │  │
│   │ ────────────                                             │  │
│   │ Signals This Week: XX    Escalated: XX    Resolved: XX   │  │
│   │ Top Categories: Security (XX), Cost (XX), Scaling (XX)   │  │
│   └─────────────────────────────────────────────────────────┘  │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

| Metric | Source | Update Frequency |
|--------|--------|------------------|
| Top Blockers | Signal Log + Loss Registry | Weekly |
| Loss Analysis | Loss Registry | Monthly |
| Feature Adoption | Telemetry | Monthly |
| Signal Trend | Signal Log | Weekly |

---

### 5.3 Adoption Architect Dashboard

**Audience:** Adoption Architect Team
**Frequency:** Weekly (operational) + Monthly (review)

```
┌─────────────────────────────────────────────────────────────────┐
│                    ADOPTION ARCHITECT DASHBOARD                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   ┌─────────────────────────────────────────────────────────┐  │
│   │ HYPOTHESIS VALIDATION STATUS                             │  │
│   │ ───────────────────────────                              │  │
│   │ H1 Tip of Spear    ⬜ Not tested   Decision: Month 6     │  │
│   │ H2 Ecosystem Moat  ⬜ Not tested   Decision: Month 9     │  │
│   │ H3 FE Enablement   🟡 In progress Decision: Month 3     │  │
│   │ H4 Archetypes      ⬜ Not tested   Decision: Month 6     │  │
│   │ H5 SI vs FDE       ⬜ Not tested   Decision: Month 9     │  │
│   │ H6 Metrics Align   🟡 In progress Decision: Month 3     │  │
│   │ H7 Net-New Focus   ⬜ Not tested   Decision: Month 6     │  │
│   │ H8 Quality/Qty     ⬜ Not tested   Decision: Month 6     │  │
│   └─────────────────────────────────────────────────────────┘  │
│                                                                 │
│   ┌──────────────────────┐  ┌────────────────────────────────┐ │
│   │ LIGHTHOUSE PROGRESS  │  │ DELIVERABLE BURNDOWN           │ │
│   │ ───────────────────  │  │ ────────────────────           │ │
│   │ Total: 15            │  │ P1 Field: 3/9 complete         │ │
│   │ Engaged: 5           │  │ P1 Product: 1/7 complete       │ │
│   │ Deep-dive: 3         │  │ P2 Field: 0/4 complete         │ │
│   │ Win: 1               │  │ P2 Product: 0/3 complete       │ │
│   └──────────────────────┘  └────────────────────────────────┘ │
│                                                                 │
│   ┌─────────────────────────────────────────────────────────┐  │
│   │ WEEKLY METRICS                                           │  │
│   │ ──────────────                                           │  │
│   │ Council Attendance: XX%   Signals Captured: XX           │  │
│   │ Actions Closed: XX/XX     PM Escalations: XX             │  │
│   └─────────────────────────────────────────────────────────┘  │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

| Metric | Source | Update Frequency |
|--------|--------|------------------|
| Hypothesis Status | Traceability Matrix | Monthly |
| Lighthouse Progress | Signal Log + SFDC | Weekly |
| Deliverable Burndown | Action Plan Tracker | Weekly |
| Weekly Metrics | Various | Weekly |

---

## 6. Metrics Categories Summary

### 6.1 Leading vs Lagging Indicators

| Type | Metrics | Purpose |
|------|---------|---------|
| **Leading** | FE confidence, Training completion, Signals captured, Lighthouse engaged | Predict future outcomes |
| **Lagging** | Strategic wins, Attach rate, Coverage, Revenue | Measure actual results |

### 6.2 Metrics by Objective

| Objective | Metrics | Owner |
|-----------|---------|-------|
| **Prove Apps Value** | Strategic wins, Win narratives, Business value documented | Adoption Architect |
| **Enable Field** | FE confidence, Training completion, Apps conversations | Enablement |
| **Influence Product** | Signals captured, PM features influenced, Gap resolution | Adoption Architect |
| **Scale Adoption** | Attach rate, Coverage, Active developers | Field + Analytics |
| **Retain Customers** | Retention rate, Active users per app, Churn rate | CS + Analytics |

### 6.3 Metrics by Audience Need

| Audience | Key Question | Metrics Needed |
|----------|--------------|----------------|
| **GTM Leaders** | "Is Apps moving the needle?" | Strategic wins, Attach rate, Pipeline |
| **PM** | "What's blocking adoption?" | Top blockers, Loss analysis, Feature adoption |
| **Adoption Architect** | "Are our hypotheses correct?" | Hypothesis validation metrics, Lighthouse progress |
| **FE** | "How do I sell Apps?" | Win rate by approach, Best practices, Qualification signals |
| **Finance** | "What's Apps worth?" | Influenced ACV, Revenue attribution |

---

## 7. Integration Recommendations

### 7.1 Priority Actions

| Priority | Action | Owner | Timeline |
|----------|--------|-------|----------|
| 🔴 1 | Create FE confidence survey instrument | Adoption Architect | Week 1-2 |
| 🔴 2 | Define attach rate calculation with Finance | Adoption Architect | Week 2-4 |
| 🔴 3 | Launch Signal Log tracking | Adoption Architect | Week 1 |
| 🟡 4 | Instrument strategic win tracking in SFDC | Sales Ops | Month 1 |
| 🟡 5 | Build loss analysis registry | Adoption Architect | Month 1 |
| 🟢 6 | Create dashboards (GTM, PM, AA) | Analytics + AA | Month 2-3 |

### 7.2 Data Gaps to Address

| Gap | Impact | Resolution | Owner |
|-----|--------|------------|-------|
| Attach rate not defined | Can't validate H1 | Finance alignment | AA + Finance |
| FE confidence not measured | Can't validate H3 | Create survey | AA + Enablement |
| Telemetry incomplete | Can't measure retention, usage | PM instrumentation | PM |
| Influenced ACV not calculated | Can't prove tip-of-spear | Finance methodology | AA + Finance |

### 7.3 Metrics to Add to Action Plan

These metrics need explicit tracking deliverables in the action plan:

| Metric | Current State | Recommended Action | Phase |
|--------|---------------|-------------------|-------|
| FE confidence baseline | Not in action plan | Add survey W2 | P1 M1 |
| Attach rate definition | Mentioned but vague | Add Finance alignment W4 | P1 M1 |
| Signal capture launch | Not formalized | Add Signal Log launch W1 | P1 M1 |
| Dashboard creation | Not scheduled | Add dashboard sprint M2 | P1 M2 |

---

## 8. Metrics Collection Cadence

| Cadence | Metrics | Forum |
|---------|---------|-------|
| **Weekly** | Signals captured, Lighthouse progress, Actions closed | Apps Adoption Council |
| **Monthly** | Strategic wins, FE confidence, Loss analysis, Pipeline | BU+1 Newsletter |
| **Quarterly** | Attach rate, Hypothesis status, Coverage, PM influence | Exec Readout |
| **Annual** | Full metrics review, Target setting | FY Planning |

---

## Next Steps

1. **Prioritize** which metrics to instrument first (FE survey, attach rate)
2. **Align with Finance** on attach rate / influenced ACV methodology
3. **Build Signal Log** as operational foundation
4. **Create dashboard mockups** for validation with stakeholders
5. **Add metrics instrumentation** to action plan deliverables

---

*Last Updated: January 2026*

