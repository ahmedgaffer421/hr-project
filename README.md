# HR Attrition Analysis
### Excel | Power Query | Power Pivot | DAX | Star Schema

---

## Project Overview

This project investigates a **19% attrition rate** across a 200-employee organization spanning 6 departments. Rather than building a monitoring dashboard, the goal was to conduct a structured analytical investigation — testing hypotheses across 8 variables to identify the true drivers of employee turnover and deliver actionable recommendations to HR.

The dataset was modeled using a **Star Schema** for the first time, with Power Pivot handling all relationships and DAX measures powering the analysis.

---

## Business Problem

The organization is losing nearly 1 in 5 employees per year. HR needed to understand:

- **What** is actually driving attrition — and what isn't
- **Who** is most at risk
- **Where** the problem is most severe
- **What to do** about it — prioritized and specific

---

## Tools & Techniques

| Tool | Usage |
|------|-------|
| Excel Power Query | Data cleaning, tenure bucketing, variable transformation |
| Power Pivot | Star Schema data modeling, table relationships |
| DAX | Custom measures (attrition rate, turnover rate, risk segmentation) |
| Excel Charts | 4-page interactive dashboard with slicers |

---

## Data Model — Star Schema

The data was restructured into a Star Schema with:

- **Fact Table** — Employee records (attrition status, salary, performance, engagement, satisfaction, training, overtime, absence)
- **Dimension Tables** — Department, Experience Level, Date, Segment definitions

This was the first time this modeling approach was applied in Excel Power Pivot, replacing flat-table analysis with a proper relational structure.

---

## Variables Tested

| Variable | Finding | Driver? |
|----------|---------|---------|
| Engagement Level | Very Low = 34% attrition | 🔴 Yes — Strongest |
| Salary | Very Low quartile = 26% attrition | 🔴 Yes |
| Satisfaction | Moderate = 26% (U-shaped pattern) | 🔴 Yes |
| Performance | High performers = 24% attrition | 🔴 Yes |
| Training Quality | Very Low = 21% attrition | 🔴 Yes |
| Tenure | New Hires = 100% attrition | 🔴 Yes — Critical |
| Overtime | No meaningful variation across workforce | 🟢 No |
| Absence Days | No outliers detected | 🟢 No |

> Eliminating non-drivers is as important as identifying drivers. Overtime and absence were tested and ruled out — preventing HR from wasting resources on the wrong areas.

---

## Key Findings

### 🚨 Finding 1 — Onboarding Crisis
**100% of first-year employees resigned.**

Tenure analysis revealed a dramatic drop-off pattern:
- New Hire (0–1 yr) → **100% attrition**
- Early (1–2 yrs) → **36% attrition**
- Developing (2–3 yrs) → **24% attrition**
- Established (3+ yrs) → **4% attrition**

The company doesn't have a general attrition problem — it has a critical onboarding failure. Employees who survive past year one become significantly more likely to stay long-term.

---

### 🚨 Finding 2 — Pay Inversion
**Exceptional performers are paid less than low performers.**

| Performance Level | Avg Salary |
|------------------|-----------|
| Exceptional | $9,250 |
| Moderate | $9,299 |
| High | $9,604 |
| Low | $10,469 |

Additionally, Junior employees earn more on average ($9,697) than Senior employees ($9,554) — a classic pay compression problem. This directly explains why high performers have 24% attrition.

---

### 🚨 Finding 3 — Operations Department in Crisis
Operations has the **highest turnover (35%)** and the **lowest training investment ($879/employee)** — the lowest of all 6 departments. Finance, by contrast, has the highest training spend ($1,146) and the lowest turnover (14%).

---

### 💡 Counterintuitive Finding — Burnt Out Stars Are Staying
Employees with High Performance + Low Satisfaction ("Burnt Out Stars") have only **17% attrition** — below the company average. This means HR should NOT prioritize intervention for this group. Resources are better directed elsewhere.

---

## Workforce Segmentation

Employees were grouped into 5 behavioral segments based on engagement and satisfaction scores:

| Segment | Definition | Attrition | Risk |
|---------|-----------|-----------|------|
| Checked Out | Low Engagement + Low Satisfaction | 29% | 🔴 Critical |
| Happy Coaster | Low Performance + High Satisfaction | 21% | 🟡 High |
| Mixed | Mixed scores across variables | 21% | 🟡 High |
| Burnt Out Star | High Performance + Low Satisfaction | 17% | 🟢 Moderate |
| Star | High Performance + High Satisfaction | 17% | 🟢 Moderate |

---

## Dashboard Structure

The dashboard is structured as a 4-page narrative:

| Page | Name | Purpose |
|------|------|---------|
| 1 | Overview | Company snapshot — headcount, hiring trend, department distribution |
| 2 | Profile | Compensation and department deep-dive — the pay inversion story |
| 3 | What | Attrition patterns across all tested variables |
| 4 | Why | Root causes — segment analysis, salary groups, training, satisfaction |

All pages share consistent KPI cards and are connected via Department and Year slicers.

---

## Recommendations

| Priority | Action | Target |
|----------|--------|--------|
| 1 | Redesign onboarding program | All new hires (0–1 yr) |
| 2 | Conduct stay interviews immediately | Very Low Engagement employees |
| 3 | Review and rebalance compensation | Exceptional/High performers paid below Low |
| 4 | Investigate the Checked Out segment | 29% attrition, highest risk group |
| 5 | Increase training budget in Operations | Lowest spend, highest turnover |
| 6 | Fix pay compression | Junior earning more than Senior |

**What NOT to do:**
- ❌ Across-the-board pay raises — pay only matters at the very bottom quartile
- ❌ Focus on Burnt Out Stars — they are staying despite dissatisfaction
- ❌ Worry about overtime or absence — neither drives attrition in this organization

---

## What I Practiced

- Building a **Star Schema** data model in Power Pivot for the first time
- Writing **DAX measures** for attrition rate, turnover rate, and segment classification
- Using **Power Query** for data cleaning, variable bucketing (tenure groups), and transformation
- Structuring a dashboard as a **narrative** (Overview → Profile → What → Why) rather than a flat report
- **Hypothesis testing** — testing variables, eliminating non-drivers, and reporting only what the data supports
- Identifying **non-obvious insights** (pay inversion, new hire 100% attrition, Burnt Out Stars staying)

---

## Project Status
✅ Complete — 4-page dashboard, full hypothesis testing, segmentation, and recommendations delivered.


## Dashboard Preview

**Overview**
![DB.Overview](images/DB.Overview.png)

**Profile**
![Profile](images/Profile.png)

**What**
![What](images/What.png)

**Why**
![Why](images/Why.png)
