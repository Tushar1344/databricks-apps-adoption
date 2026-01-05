# Detailed Index

*Complete navigation for the Databricks Apps Adoption Playbook*

---

## Section 1: Foundation

### [01_mission_and_role.md](01_foundation/01_mission_and_role.md)
- Mission Statement
- The Problem We Solve
- Role Definition (Clarity + Action)
- Operating Model
- Success Metrics

### [02_product_context.md](01_foundation/02_product_context.md)
- Product Overview
- Current State
- Current Sweet Spot
- Product Roadmap (FY26, FY27)
- Product Strategy Assessment
- Implications for Adoption Architect

---

## Section 2: Field Gaps

*Owner: Field Ops, Enablement, Partners*

### [01_icp_and_targeting.md](10_field/01_icp_and_targeting.md)
- Ideal Customer Profile
- Quality vs Quantity Motion
- Motion Selection Guide
- Disqualifiers
- Lighthouse Account Selection
- App Archetype Targeting

### [02_positioning_and_messaging.md](10_field/02_positioning_and_messaging.md)
- Core Differentiators
- The Databricks Apps Moat
- Where We Win Today
- Where We Wait (Product Gaps)
- Positioning Matrix
- Honest Messaging by Maturity
- Competitive Positioning

### [03_sales_plays_and_patterns.md](10_field/03_sales_plays_and_patterns.md)
- App Archetypes (Cockpit, Vertical, Horizontal)
- Guided Selling Triggers
- Sales Objection Framework
- Use Case Qualification Framework

### [04_field_enablement.md](10_field/04_field_enablement.md)
- Current State Assessment
- Full-Funnel GTM Gap
- 90-Day Training Sprint
- Marketing Events Strategy
- EBC Strategy
- "Month of Apps" Hackathon Program

### [05_field_incentives.md](10_field/05_field_incentives.md)
- The Incentive Problem
- Incentive Framework (Recognition, Development, Financial)
- Signal Capture Incentives
- Influence Strategy for Comp Changes

### [06_partner_ecosystem.md](10_field/06_partner_ecosystem.md)
- Partner Type 1: Internal FE Teams
- Partner Type 2: ISVs (IDE, AI/ML)
- Partner Type 3: System Integrators
- Partner Type 4: GTM Industry Leads
- Partner Type 5: Professional Services
- ISV + SI Complementary Model

### [07_signal_capture.md](10_field/07_signal_capture.md)
- Signal Types
- Field Signal Log
- Signal Capture Process
- Known Product Gaps
- Loss Analysis Framework
- PM Feedback Synthesis

---

## Section 3: Product Gaps

*Owner: PM, Engineering*

### [01_use_case_tracking.md](20_product/01_use_case_tracking.md)
- Use Case Classification Framework
- Tracking Mechanism
- Use Case Registry
- Archetype Validation
- Emerging Pattern Detection

### [02_feature_adoption_roadmap.md](20_product/02_feature_adoption_roadmap.md)
- Feature Categories
- Feature Adoption Metrics (DBUs, CSAT)
- Product Roadmap Influence
- Feature-to-Archetype Matrix
- Adoption Funnel by Feature

### [03_friction_summary.md](20_product/03_friction_summary.md)
- Product Limitations Overview
- Detailed Gap Inventory (15 gaps)
- Gap Prioritization Matrix
- Blocker Resolution Strategy
- Current Sweet Spot
- Workarounds for Common Gaps

### [04_loss_analysis.md](20_product/04_loss_analysis.md)
- Loss Categories
- Loss Analysis Template
- Loss Registry
- Competitive Loss Analysis
- Churn Analysis
- Recovery Pipeline

---

## Section 4: Strategic Framework

### [01_hypotheses_and_beliefs.md](30_framework/01_hypotheses_and_beliefs.md)
- Hypothesis Framework
- H1: Apps as Tip of the Spear
- H2: Ecosystem Synergy Is the Moat
- H3: Full-Funnel GTM Gap
- H4: Three Archetypes Drive 80%
- H5: SI Partnerships Counter Palantir
- H6: Metrics Align BU Leaders
- H7: Net-New Focus Is Right
- H8: Quality vs Quantity Matters
- Hypothesis Prioritization

### [02_traceability_matrix.md](30_framework/02_traceability_matrix.md)
- Traceability Framework
- Validation Timeline
- Master Traceability Table
- Detailed Traceability by Hypothesis
- Decision Timeline
- If Hypothesis Is Invalidated

---

## Section 5: Execution

### [01_action_plan.md](40_execution/01_action_plan.md)
- Plan Overview (Gantt)
- Hypothesis-Action Connection
- Phase 1: Prove It (Month 1-3)
- Phase 2: Scale It (Month 4-6)
- Phase 3: Expand It (Month 7-12)
- Operating Rhythms
- Risk Mitigation

### [02_operating_cadence.md](40_execution/02_operating_cadence.md)
- Weekly Cadence (Apps Adoption Council)
- Monthly Cadence (Newsletter, Loss Analysis)
- Quarterly Cadence (Exec Readout, PM Feedback)
- Annual Cadence (FY Planning)
- Meeting Hygiene
- Communication Channels

---

## Quick Reference Tables

### Documents by Owner

| Owner | Documents |
|-------|-----------|
| **Adoption Architect** | All (author) |
| **Field Ops** | ICP and Targeting, Field Incentives, Signal Capture |
| **Enablement** | Sales Plays, Field Enablement |
| **Marketing** | Positioning and Messaging |
| **Partners** | Partner Ecosystem |
| **PM** | Use Case Tracking, Feature Roadmap, Friction Summary |

### Documents by Hypothesis

| Hypothesis | Primary Documents |
|------------|-------------------|
| H1: Tip of Spear | ICP, Sales Plays, Action Plan |
| H2: Moat | Positioning, Traceability |
| H3: GTM Gap | Enablement, Signal Capture, Action Plan |
| H4: Archetypes | Sales Plays, Use Case Tracking |
| H5: SI vs FDE | Partner Ecosystem, Positioning |
| H6: Metrics | ICP, Field Incentives, Action Plan |
| H7: Net-New | Product Context, Positioning |
| H8: Quality vs Quantity | ICP, Partner Ecosystem, Action Plan |

### Phase 1 Priority Documents

| Week | Key Documents |
|------|---------------|
| W1-2 | ICP and Targeting, Field Enablement |
| W3-4 | Positioning, Partner Ecosystem |
| W5-8 | Sales Plays, Signal Capture |
| W9-12 | Action Plan, Traceability |

---

## File Structure

```
databricks-apps-adoption/
├── README.md                           # Blog-style entry point
├── 00_index.md                         # This file - detailed navigation
├── _config.yml                         # Jekyll config (Architect theme)
├── _layouts/
│   └── default.html                    # Mermaid support
├── 01_foundation/
│   ├── 01_mission_and_role.md
│   └── 02_product_context.md
├── 10_field/
│   ├── 01_icp_and_targeting.md
│   ├── 02_positioning_and_messaging.md
│   ├── 03_sales_plays_and_patterns.md
│   ├── 04_field_enablement.md
│   ├── 05_field_incentives.md
│   ├── 06_partner_ecosystem.md
│   └── 07_signal_capture.md
├── 20_product/
│   ├── 01_use_case_tracking.md
│   ├── 02_feature_adoption_roadmap.md
│   ├── 03_friction_summary.md
│   └── 04_loss_analysis.md
├── 30_framework/
│   ├── 01_hypotheses_and_beliefs.md
│   └── 02_traceability_matrix.md
└── 40_execution/
    ├── 01_action_plan.md
    └── 02_operating_cadence.md
```

---

*Last Updated: January 2026*

