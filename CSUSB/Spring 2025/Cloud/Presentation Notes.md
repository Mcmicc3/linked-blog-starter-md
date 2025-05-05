# Migration Concerns
1. **Licensing & Vendor Support constraints**
```
Some legacy ERP/databases impose on‑prem‑only licences or higher fees in shared clouds; support SLAs may differ.
```
2. **Organizational change-capacity & skills**
```
DevOps, SRE, IaC and FinOps talent shortages can stall migration timelines or create technical debt in the cloud.
```
3. **Dependency & Coupling Analysis**
```
Hidden inter‑process calls or shared DBs can turn a “simple” lift‑and‑shift into a brittle distributed monolith if split.
```
4. **Business‑continuity tiers & concentration risk**
```
Cloud DR is easier – but reliance on one hyperscaler puts systemic risk in a single vendor’s outages or geopolitics. Multi‑cloud or selective on‑prem mitigates.
```
5. **Vendor Lock in**
6. **Governance & Regulations concerns**


# How to choose between migrate vs retain
1. **NIST Documents**
```
- **NIST SP 800‑146** (Cloud Synopsis) & **SP 500‑322** (Service Evaluation)
- Defines cloud characteristics and provides worksheets to decide if a workload “qualifies” and which model best fits.
```
2. **Choosing between Micrsoft, AWS, or Google? There's a guide for it**
```
a. **Microsoft Cloud Adoption Framework (CAF)** (2024‑04‑10)
- “Assess → Migrate → Optimize” methodology; includes workload‑rationalization matrix.

b. **AWS Well‑Architected – Migration Lens** (2024‑01‑24)
- Uses 7 R strategies + six pillars incl. Sustainability to benchmark migrate/retain calls.

c. **Google Cloud Architecture Framework & Migration Guides** (2025‑03‑15)
- Phase‑based playbooks (assess, plan, deploy, optimize) and ADR templates for documenting decisions.
```
3. **Gartner “5‑Step Cloud Data‑Migration Framework”** (2024‑02‑22)
``` 
Strategy → Architecture → Operationalize steps; emphasises split‑data strategies when regulators demand.
```
4. **Security Controls**
```
**ISO/IEC 27017** (cloud controls) & **CSA Cloud Controls Matrix v4** (2024‑06‑03)
- Map required controls; CCM also bundles CAIQ questions for provider due‑diligence.
```
5. **FinOps Framework (v 2024)**
```
**FinOps Framework (v 2024)**
- Domains & maturity model for variable‑spend governance; feeds TCO comparisons when deciding cloud fit.
- Real‑world maturity examples for cost‑based migrate/retain decisions.
```
6. **Counter Narrative**
```
CSA blog “What is Cloud Repatriation?” (2023‑09‑22)
- Case‑study data (e.g., Dropbox >$75 M savings) for balanced discussion on when _not_ to migrate.
```

If you're a company that advertises about how green you are, or you care about the environment, you can make this argument: **Sustainability & ESG targets**
```
Moving workloads to regions powered by renewables can cut Scope‑2/3 CO₂, but highly‑utilised on‑prem may already be efficient.
- 451 Research found AWS migrations cut carbon up to 96 % in renewable regions.
```
https://www.coresite.com/blog/can-the-cloud-help-support-sustainability