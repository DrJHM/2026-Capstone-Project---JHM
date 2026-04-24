# When the Tools Don't Fit: Student Success Platforms and the HBCU Retention Gap

> **VanguardScholar | DATA 802 Practicum | Moulden College of Science & Technology**  
> Dr. Joycelyn Hughes-Moulden | Spring 2026 | Site Placement: Howard University School of Education

---

## Executive Summary

Historically Black Colleges and Universities (HBCUs) have steadily invested in mainstream student success platforms — yet the retention gap between HBCUs and comparable Predominantly White Institutions (PWIs) has held at roughly 10.5 to 10.6 percentage points across eight consecutive years of platform adoption. This study draws on IPEDS outcomes data, NACUBO endowment figures, and platform adoption records across 51 institutions (26 HBCUs, 25 matched PWIs) to examine which institution-level indicators most strongly predict first-year retention and six-year graduation rates at HBCUs. Using a Random Forest model, the analysis reveals that **endowment per student** (importance score: 0.4571) far outpredicts platform adoption (Navigate: 0.0364), while widely-adopted tools like Early Alert, Starfish, and Workday Student scored zero. The central finding is clear: the tools HBCUs are buying were not designed for the students HBCUs serve. A purpose-built, culturally responsive, resource-aware student success platform is not a product enhancement — it is an equity imperative.

---

## How to Navigate This Data Story

This is an **interactive, 7-slide data story** built in Flourish. Here is how to engage with it:

- **Arrow buttons** (← →) at the top of each slide move you forward and backward through the narrative.
- **Hover** over data points, bars, and chart elements to reveal tooltips with institution-specific details and exact values.
- **Toggle legend items** (e.g., HBCU / PWI) by clicking them to isolate or compare groups.
- Each slide builds on the one before it — follow the slides **in order** for the full argument.
- If the visualization does not load, scroll down for the slide-by-slide written summary.

---

## Interactive Data Story

<div style="position: relative; width: 100%; padding-bottom: 75%; overflow: hidden; border: 2px solid #1a3a5c; border-radius: 8px; margin: 1.5em 0;">
  <iframe
    src="https://public.flourish.studio/story/3657641/embed"
    frameborder="0"
    scrolling="no"
    style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"
    title="VanguardScholar: When the Tools Don't Fit — HBCU Student Success Platform Analysis"
    allowfullscreen>
  </iframe>
</div>

> **📌 Display note:** If you are viewing this on GitHub's raw file preview, the embed will not render.  
> To view the fully interactive version, visit the [GitHub Pages site](../../) or open the [Flourish story directly](https://public.flourish.studio/story/3657641/).

---

## Slide-by-Slide Narrative Summary

### Slide 1 — The Students
HBCU students experience risk differently. In this dataset, **74% are Pell-eligible**, **54% are first-generation**, and **29% cannot cover a $500 unexpected expense**. These are not the students that mainstream student success platforms were originally built to detect. The diverging bar chart shows student population indicators for HBCUs vs. matched PWI averages across Pell eligibility, first-generation status, and part-time enrollment.

### Slide 2 — The Gap
Between 2017 and 2022, the retention gap between HBCUs and matched PWIs held steady at **10.5 to 10.6 percentage points**. Eight years of platform adoption produced no measurable movement in the gap. Each dot represents one institution; OLS trendlines reveal the flat trajectory for HBCU institutions regardless of adoption duration.

### Slide 3 — The Adoption
Between 2017 and 2022, **22 of the 26 HBCUs** in the dataset adopted Navigate or a comparable student success platform. The tools were purchased. The platforms were adopted. But the gap did not move. This line chart tracks annual retention averages for HBCUs vs. PWIs across the full adoption window (2016–2024), with the adoption period shaded.

### Slide 4 — The Financial Reality
The average HBCU endowment in this dataset is **$53.6 million**. The average PWI endowment is **$26.7 billion** — a **498-to-1 ratio**. A platform may identify a risk, but the institution still has to have the resources to respond to that risk. The dot plot displays endowment distribution for all 51 institutions on a log scale.

### Slide 5 — The Predictive Picture
A Random Forest model (n_estimators=200, random_state=42) ranked all variables by predictive importance. **Endowment per student scored 0.4571** — the single strongest predictor in the dataset. Navigate scored only 0.0364. Early Alert, Wraparound Advising, Starfish, and Workday Student **scored zero**.

### Slide 6 — The Mismatch
The only platform-related variable with meaningful predictive signal was the **Degree Audit Tool** (0.2426). Yet the interventions most likely to move HBCU students forward — intrusive advising, peer mentoring, TRIO Student Support Services, emergency aid connections — are either absent from or poorly supported by generic platforms. The bar chart ranks interventions by estimated HBCU retention gain in percentage points, ordered by RF model findings.

### Slide 7 — The Conclusion
There are currently **130,000 students** enrolled at HBCUs that adopted Navigate or comparable platforms. The retention gap has persisted through eight years of adoption. The right technology has not yet been built. When the tools do not fit, the gap does not close.

---

## Data Sources & Methodology

| Source | Use |
|--------|-----|
| IPEDS (2016–2024) | Retention and graduation rates |
| NACUBO 2022 Endowment Study | Per-institution and per-student endowment figures |
| EAB Platform Adoption Records | Navigate adoption years and institutional coverage |
| College Scorecard (2022–23) | Supplemental demographic indicators |
| What Works Clearinghouse / TRIO Evaluation Reports | Literature-based effect size estimates |
| Kimbrough (2018); Shorette & Palmer (2015) | HBCU-specific retention intervention research |

**Model:** RandomForestRegressor (n_estimators=200, random_state=42) | Target: First-year retention rate | n=26 HBCU institutions.

> *Literature-based effect size estimates on Slide 6 are not computed from the IPEDS dataset. They are drawn from peer-reviewed HBCU retention research and TRIO program evaluations.*

---

## Citation

Hughes-Moulden, J. (2026). *When the tools don't fit: Student success platforms and the HBCU retention gap* [DATA 802 Practicum, Moulden College of Science & Technology]. Site placement: Howard University School of Education, under supervision of Dr. Brandy Jackson.

---

## Connect

**VanguardScholar** makes the case for a student success platform purpose-built for HBCUs — one that centers institutional wealth constraints, relational intervention models, and the lived realities of first-generation, Pell-eligible students.

For questions, collaboration inquiries, or dataset access, connect via [LinkedIn](https://www.linkedin.com/in/joycelyn-hughes-moulden) or open an issue in this repository.

---

*Built with [Flourish](https://flourish.studio) · Data: IPEDS, NACUBO, EAB · Model: scikit-learn RandomForestRegressor*
