# Computational Social Justice & Ethical Advocacy
**Joycelyn Hughes-Moulden | Spring 2026 – DATA 801 Capstone**

---

## Section I: The Problem Statement

### Identifying the Population

Various retention and graduation, thus, academic interventions are needed to ensure ideal graduation rates and positive career and life outcomes for African American college/university students. Historically Black Colleges and Universities, like other institutions of higher education invest in online academic intervention tools to structure student services. However, there are no online academic intervention platforms that are specific to HBCU students which may present gaps that hinder their academic successes. This study seeks to identify which institution-level support-related indicators are associated with stronger student success outcomes at HBCUs to inform more cohesive, data-informed strategies for improving retention and graduation among Black college students.

### Defining the Injustice

The systemic issue this project addresses is technological redlining in higher education infrastructure — specifically, the uncritical adoption by HBCUs of commercial student success platforms that were architecturally designed around the resource profiles, staffing ratios, and institutional cultures of predominantly white research universities. This is not merely an inconvenience of poor fit. It is a structural inequity: institutions that already operate with per-student endowments significantly smaller than comparable PWIs are being asked to pay enterprise licensing fees, undergo implementation cycles of 18 to 36 months, and dedicate full-time staff to platform management — resources HBCUs structurally lack. The result is a technology adoption pattern that launders inequality.

### Literature Review

The problem statement is grounded in three converging bodies of evidence: HBCU resource inequity, the institutional mismatch of commercial edtech products, and the relationship between student support infrastructure and completion outcomes.

#### Source 1: HBCU Funding Inequity (UNCF / Federal Data)

The United Negro College Fund's 2023 report, *HBCUs Make America Strong: The Positive Economic Impact of Historically Black Colleges and Universities*, documents that public HBCUs receive, on average, 78 cents for every dollar that similarly sized and classified public PWIs receive in state appropriations — a gap that has persisted for over four decades and that the U.S. Department of Education has formally acknowledged in compliance review findings (UNCF, 2023). This funding shortfall is not a recent anomaly; it is the compounded product of state-level discriminatory resource allocation that predates the civil rights era. Per-student endowment figures in this study confirm this pattern: the median HBCU per-student endowment in the study is extremely smaller than regional PWIs — a 13:1 ratio that makes equivalent technology investment structurally impossible without external subsidy.

#### Source 2: Technology Mismatch and Institutional Fit (Kim & Conrad, 2006; Gasman et al., 2010)

Kim and Conrad's seminal study, published in the *Journal of Higher Education*, demonstrated that interventions and programs designed for mainstream institutional contexts consistently underperform at HBCUs when adopted without modification — not because HBCUs are deficient, but because the underlying assumptions of those programs (advising-to-student ratios, technology access, administrative bandwidth) do not hold in the HBCU context (Kim & Conrad, 2006). Gasman, Baez, and Turner (2010) extend this argument in *Understanding Minority-Serving Institutions*, documenting how HBCUs serve as "comprehensively supportive" environments that embed academic advising, mental health support, and financial coaching within holistic relationships rather than discrete platform workflows — a model of care that transactional CRM-style tools are poorly equipped to capture or amplify (Gasman et al., 2010). Both sources establish the theoretical foundation for this study's central claim: that the mismatch is not incidental but structural.

#### Source 3: Student Success Platforms, Retention, and the Evidence Base (EAB, 2020; Tyton Partners, 2021)

The Education Advisory Board's Navigate360 ROI documentation reports a 3–9 percentage point improvement in retention at institutions using the platform, but that evidence base is drawn almost exclusively from mid-sized to large PWIs with existing advising infrastructure (EAB, 2020). Tyton Partners' 2021 report, *Driving Toward a Degree 3.0*, similarly finds that student success technology generates stronger outcomes when institutions have sufficient staff capacity to act on the platform's early-alert signals — a precondition that fewer than 30% of HBCUs in this study meets, as measured by the ratio of professional advisors to enrolled students (Tyton Partners, 2021). The literature therefore not only confirms the existence of a gap; it reveals that the evidence typically marshaled to justify HBCU platform adoption is evidence from a different population entirely.

---

## Section II: The Findings

### Connection to Statistical and Machine Learning Analysis

The dataset for this study was assembled from IPEDS, UNCF institutional profiles, and public platform adoption records for 51 institutions — 26 HBCUs and 25 Carnegie-matched PWIs. The analysis employed descriptive statistics, bivariate correlation, multiple regression, and a supervised classification model to identify which institution-level indicators most strongly predict first-year retention and six-year graduation rates, and to test whether platform adoption moderates that relationship.

The regression model (OLS, n = 51) identified per-student endowment, the advisor-to-student ratio, and the presence of an on-campus food security program as the three most significant positive predictors of six-year graduation rates across the full sample (adjusted R² = .64, p < .001). Student success platform adoption (Navigate360 or Starfish) was entered as a binary variable in Model 2 and was not a statistically significant predictor of graduation rate improvement in the HBCU subsample (β = .08, p = .31) — a null finding that directly challenges vendor-side ROI claims when applied to HBCU populations. In the PWI subsample, platform adoption did reach significance (β = .19, p = .04), which is consistent with the EAB evidence base and confirms that the platform effect is real — but contingent on institutional conditions HBCUs do not share.

### The Reality Check

The findings do not suggest that HBCUs have a completion problem that is uniquely their own. They suggest that HBCUs have a resource problem — and that under-resourced institutions cannot extract the same outcome improvements from expensive platforms that well-resourced institutions can. The data tell a more precise story than the national headlines allow:

> **Key Finding:** While national six-year graduation rates have improved modestly across all institution types, our regression model reveals that HBCUs adopting Navigate360 or Starfish showed no statistically significant improvement in graduation outcomes relative to HBCUs without those platforms — controlling for endowment, enrollment size, and Carnegie classification. The platform is not the variable that moves the needle for HBCUs. Resources are.

The classification model (Random Forest, trained on 80% of the dataset, tested on 20%) achieved an accuracy of 78% in predicting whether an institution would fall above or below the national median six-year graduation rate. Feature importance scores ranked per-student endowment first, advisor-to-student ratio second, and food insecurity program presence third. Platform adoption ranked eighth out of eleven features, below Pell Grant concentration and institutional age. This is not a finding that dismisses technology — it is a finding that insists technology be understood in context.

### Bias Check: Data Limitations and Gaps

Any honest reading of this research must account for what the data cannot see. Three limitations warrant explicit acknowledgment:

- **Missing institutional granularity:** IPEDS data captures institution-level aggregates, not the experiences of specific student subpopulations within HBCUs (e.g., transfer students, students with disabilities, or undocumented students). Disaggregated data at this level is either not publicly available or inconsistently reported across institutions, which means the most vulnerable students within HBCUs may be systematically invisible in this analysis.

- **Platform adoption as binary:** This dataset codes platform adoption as a yes/no variable. It cannot capture depth of use, feature adoption rate, integration quality, or staff training investment — all of which likely moderate the platform-to-outcome relationship. An HBCU that purchased Navigate360 but deployed only 20% of its features should not be coded identically to one with full deployment.

- **Selection bias in platform adoption:** HBCUs that adopted Navigate360 or Starfish may have done so precisely because they were better-resourced than their non-adopting peers — meaning any observed performance difference may partly reflect pre-existing institutional advantage, not platform effect. Future research would benefit from longitudinal pre-post designs or regression discontinuity approaches that can better isolate treatment effects.

---

## Section III: Advocacy & Recommendations

### What Must Change

This capstone project is not simply a critique of existing platforms. It is an affirmative argument for a different model — one built from the ground up on HBCU institutional realities, relational advising cultures, and anti-deficit assumptions about who HBCU students are and what they are capable of. The data make the case. The question is whether decision-makers will listen.

### Policy and Action Recommendations

Establish a dedicated HBCU EdTech Equity Fund — modeled on existing HBCU infrastructure grant programs — to subsidize platform development, implementation staffing, and evaluation infrastructure at HBCUs. Fund multi-year longitudinal evaluations that can establish HBCU-specific evidence bases. This addresses the resource gap that makes platform adoption unequal and builds the evidentiary infrastructure the field currently lacks.

### The Human Cost of Inaction

Behind every percentage point in a retention or graduation rate is a student. An HBCU student who does not complete their degree does not merely lose a credential — they lose the single most powerful economic mobility lever available to them. Research by Chetty et al. (2020) documents that HBCU attendance, even without degree completion, generates measurable upward mobility relative to no college attendance; degree completion amplifies that effect substantially. When institutions lack the tools, resources, and infrastructure to support student persistence — and when the technology solutions marketed to them were never designed to work in their context — the human consequences are not abstract.

They look like this: a first-generation student at a public HBCU who receives an early-alert flag in a platform her institution never fully implemented, so no advisor calls. A student who might have persisted with a timely intervention instead stops out at the end of the semester. She re-enters the labor force without a degree, at a wage premium that is $22,000 per year lower than it would have been had she completed (Georgetown Center on Education and the Workforce, 2021). Over a 40-year career, that gap compounds. Multiply that story by the thousands of students enrolled at HBCUs whose institutions are asked to compete in a market that was not built for them.

> **The Imperative:** This study is not necessarily a product pitch. It is a data-evidenced argument that the architecture of student success technology has, to date, been an architecture of exclusion — and that designing for the margin, not the middle, is both the ethical obligation and the practical imperative of any institution, vendor, or policymaker that claims to care about equity in higher education.

---

## References

1. Education Advisory Board (EAB). (2020). *Navigate360: Student success platform ROI and outcome data.* EAB Research.
2. Gasman, M., Baez, B., & Turner, C. S. V. (Eds.). (2010). *Understanding minority-serving institutions.* State University of New York Press.
3. Georgetown Center on Education and the Workforce. (2021). *The college payoff: More education doesn't always mean more earnings.* Georgetown University.
4. Kim, M. M., & Conrad, C. F. (2006). The impact of historically Black colleges and universities on the academic success of African-American students. *Research in Higher Education, 47*(4), 399–427.
5. National Center for Education Statistics. (2022). *Status and trends in the education of racial and ethnic groups.* U.S. Department of Education, Institute of Education Sciences.
6. Tyton Partners. (2021). *Driving toward a degree 3.0: Seizing the moment to re-envision student success technology.* Tyton Partners Research.
7. United Negro College Fund. (2023). *HBCUs make America strong: The positive economic impact of historically Black colleges and universities.* UNCF Policy & Research.
