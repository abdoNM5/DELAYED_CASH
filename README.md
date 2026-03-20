# Global Liquidity & AR Risk Assessment Dashboard

**Diagnostic control center transforming $1.14B AR pipeline into actionable cash flow intelligence**

## The Problem

- **$711.5M** outstanding AR, **94.6%** overdue ($673.5M)
- **$365.7M** trapped in toxic 90+ day aging bucket
- Executive team had no visibility into cash flow bottlenecks
- Reactive debt collection vs. proactive risk management

## Solution Overview

**Advanced Power BI Dashboard** that diagnosed root causes through:
- **Weighted Average Days Late** (DAX SUMX logic penalizing large overdue invoices)
- **Collection Effectiveness Index (CEI%)** measuring cash conversion (37.33% vs 85% target)
- **Credit Limit Breach Detection** ($1.14B unauthorized exposure identified)
- **Dispute Intensity Scoring** isolating $239M in self-inflicted revenue leakage

**Design**: Two-page architecture (Executive Summary + Operational Deep Dive) with custom Cisco Dark Theme and strategic crimson color coding for risk.

---

## Key Findings

**Root Cause #1: Rogue Sales Operations**
- Two sales reps systematically bypassed credit approvals → **$310.5M** unauthorized exposure
- 94.66% collection failure rate on their portfolios

**Root Cause #2: Self-Inflicted Revenue Leakage**
- **$239.28M** locked in active disputes (Tech & Logistics sectors weaponizing operational errors)
- Dispute intensity: 32-36% (far above threshold)

**Critical KPIs**
- CEI (Collection Effectiveness): 37.33% actual vs. 85% target
- Weighted Avg Days Late: 93.20 days globally
- AR Overdue %: 94.66% ($673.5M of $711.5M)

**Regional Impact**: Middle East 95.92% overdue (highest risk)

---

## Strategic Interventions

| Action | Timeline | Impact |
|--------|----------|--------|
| CRM Hard-Stop: Freeze contracts exceeding credit limits | Immediate | Prevent future breaches |
| Commission Freeze on 2 rogue sales reps pending audit | Week 1 | Governance correction |
| Deploy Dispute Strike Team to resolve $239M | Month 1 | Unlock trapped cash |
| Credit governance overhaul & RLS implementation | Month 2 | Prevent unauthorized approvals |
| Tie CEI% improvement to 30% of bonus structure | Month 2 | Behavioral alignment |

---

## Data Model & Key Measures

**Star Schema:**
- **FactTable**: Transaction-level AR data (invoice_amount, paid_amount, days_late, aging_bucket, dispute_flag)
- **dimSeller**: Sales rep details (role, email, phone)
- **dimCustomer**: Customer master (industry, region, credit_limit, credit_rating)
- **dimPayTerms**: Payment term definitions

**Critical DAX Measures:**
```dax
CEI% = SUM(paid_amount) / SUM(invoice_amount)

Weighted Avg Days Late = 
  SUMX(FactTable, days_late * invoice_amount) / SUM(invoice_amount)

Credit Breach = SUMIF(FactTable, invoice_amount > credit_limit)
```

---

## Technical Stack

**Tools**: Power BI Desktop | Power Query | DAX

**Techniques**:
- Dimensional modeling (Star Schema)
- Advanced iterative DAX (SUMX, SWITCH, custom variables)
- JSON theme customization
- Financial analytics & credit risk quantification

**Skills Demonstrated**:
✅ Business problem diagnosis | ✅ Data architecture | ✅ Executive communication | ✅ Root cause analysis | ✅ Risk quantification | ✅ UI/UX storytelling

---

## Dashboard Pages

**Page 1 - Executive Summary**: Total AR ($711.47M) | Overdue breakdown | Industry liquidity gaps | Regional risk matrix | CEI% performance (37.33%)

**Page 2 - Operational Deep Dive**: Sales rep accountability | Revenue leakage by agent | Dispute patterns | Industry friction matrix | Write-off exposure by sector

---

## How to Use

**For Executives**: Review Page 1 for macro trends, regional risk concentration, and CEI% vs. 85% target

**For Operations/CFO**: Deep dive on Page 2 to identify individuals responsible for breaches and quantify disputes vs. true bad debt

**For Sales Leadership**: Review individual sales rep performance, credit compliance, and commission impact

---

## Results & Business Impact

| Outcome | Impact |
|---------|--------|
| Rogue sales activity | Identified $310.5M unauthorized exposure |
| Disputes quantified | $239.28M isolated for strike team |
| CEI baseline | 37.33% (vs 85% target) — drives collection strategy |
| Credit breaches detected | $1.14B automated detection enables CRM hard-stops |
| Governance failure visible | Individual accountability transparency changes behavior |

---

## Project Structure

```
Cisco-Global-Liquidity-Assessment/
├── README.md
├── Global_Liquidity_AR_Risk_Assessment.pbix
├── Cisco_Dark_Theme.json
├── Data Model/
│   ├── FactTable_Structure.md
│   ├── dimSeller.csv
│   ├── dimCustomer.csv
│   └── dimPayTerms.csv
└── Documentation/
    ├── Business_Problem_Statement.md
    └── Methodology.md
```

---

## Getting Started

1. **Prerequisites**: Power BI Desktop | AR transaction data | ERP/CRM access
2. **Setup**: Clone repo → Open .pbix → Update data sources (SQL Server/Azure) → Refresh
3. **Customization**: Adjust credit thresholds, aging buckets, regional codes in dimCustomer table
4. **Deployment**: Apply row-level security (RLS) before publishing to Power BI Service

---

## KPIs Tracked

| KPI | Target | Actual | Status |
|-----|--------|--------|--------|
| Collection Effectiveness Index | 85% | 37.33% | 🔴 Critical |
| Weighted Avg Days Late | < 30 days | 93.20 days | 🔴 Critical |
| AR Overdue % | < 5% | 94.66% | 🔴 Critical |
| 90+ Days Concentration | < 10% | 51.4% | 🔴 Critical |

---

## Key Takeaways

1. **Advanced DAX > Basic Aggregations**: Weighted metrics expose behavioral risk that simple counts miss
2. **Color discipline**: Restrict palette to 2-3 strategic colors for maximum impact
3. **Two-tier architecture**: One executive summary + one operational deep dive serves all audiences
4. **Accountability works**: Publishing individual metrics drives behavioral change immediately
5. **Separate disputes from bad debt**: Enables surgical interventions vs. blanket write-offs

---

## Future Roadmap

- [ ] Predictive DSO modeling with early warning system
- [ ] Customer lifetime value (CLV) correlation with payment behavior
- [ ] Automated alerts for credit limit breaches
- [ ] AR aging software real-time data integration
- [ ] 12-month cash flow forecasting module

---

## License & Support

**Educational & Research Use**: This framework is provided as-is for learning and analytical purposes. Production deployment should include organization-specific governance and security protocols.

For questions → GitHub Issues | For contributions → Pull requests welcome

---

**Last Updated**: March 2026 | **Status**: Production-Ready Demo | **Power BI Version**: 2.120+
