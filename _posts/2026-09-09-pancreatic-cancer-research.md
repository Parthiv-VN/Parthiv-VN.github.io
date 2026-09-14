---
layout: post
title: "Pancreatic Cancer: Why Are We Still Finding It Too Late?"
date: 2026-09-09
categories: [Cancer Research, Biology, Data Science]
tags: [pancreatic cancer, cancer biology, epidemiology, early detection, treatment]
---

<style>
.research-hero {
    padding: 70px 0 80px 0;
    border-bottom: 1px solid #ddd;
    margin-bottom: 60px;
}

.research-kicker {
    text-transform: uppercase;
    letter-spacing: 0.14em;
    font-size: 0.75rem;
    font-weight: 700;
    color: #777;
    margin-bottom: 20px;
}

.research-hero h1 {
    font-size: clamp(3rem, 8vw, 7rem);
    line-height: 0.95;
    letter-spacing: -0.055em;
    max-width: 1050px;
    margin-bottom: 35px;
}

.research-subtitle {
    font-size: 1.35rem;
    line-height: 1.5;
    max-width: 850px;
    color: #555;
}

.research-question {
    margin: 50px 0;
    padding: 35px;
    background: #111;
    color: white;
    border-radius: 12px;
}

.research-question .label {
    font-size: 0.75rem;
    text-transform: uppercase;
    letter-spacing: 0.12em;
    color: #aaa;
    margin-bottom: 15px;
}

.research-question h2 {
    margin: 0;
    font-size: clamp(1.5rem, 3vw, 2.4rem);
    line-height: 1.2;
}

.stat-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 15px;
    margin: 40px 0;
}

.stat-card {
    border: 1px solid #ddd;
    border-radius: 10px;
    padding: 25px;
    background: #fafafa;
}

.stat-number {
    display: block;
    font-size: 2.3rem;
    font-weight: 800;
    letter-spacing: -0.04em;
}

.stat-title {
    display: block;
    font-weight: 600;
    margin-top: 8px;
}

.stat-source {
    display: block;
    font-size: 0.75rem;
    color: #888;
    margin-top: 15px;
}

.research-callout {
    padding: 25px 30px;
    margin: 35px 0;
    border-left: 4px solid #111;
    background: #f3f3f0;
}

.figure-placeholder {
    border: 1px dashed #aaa;
    border-radius: 10px;
    min-height: 320px;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    margin: 30px 0;
    padding: 30px;
    color: #777;
}

.figure-placeholder strong {
    display: block;
    color: #222;
    margin-bottom: 10px;
}

.research-table {
    width: 100%;
    border-collapse: collapse;
    margin: 30px 0;
}

.research-table th,
.research-table td {
    border-bottom: 1px solid #ddd;
    padding: 14px;
    text-align: left;
}

.research-table th {
    font-weight: 700;
}

.research-roadmap {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 15px;
    margin: 30px 0;
}

.roadmap-card {
    border: 1px solid #ddd;
    border-radius: 10px;
    padding: 25px;
}

.roadmap-number {
    color: #888;
    font-size: 0.8rem;
    font-weight: 700;
}

.solution-box {
    margin: 50px 0;
    padding: 40px;
    background: #111;
    color: white;
    border-radius: 12px;
}

.solution-box h2 {
    color: white;
    margin-top: 0;
}

.placeholder {
    color: #888;
    font-style: italic;
}

@media (max-width: 800px) {
    .stat-grid,
    .research-roadmap {
        grid-template-columns: 1fr 1fr;
    }
}

@media (max-width: 550px) {
    .stat-grid,
    .research-roadmap {
        grid-template-columns: 1fr;
    }

    .research-hero {
        padding-top: 35px;
    }
}
</style>


<!-- =====================================================
     HERO
===================================================== -->

<section class="research-hero">

    <div class="research-kicker">
        CANCER RESEARCH PROJECT
    </div>

    <h1>
        Pancreatic Cancer:
        <br>
        Why Are We Still Finding It Too Late?
    </h1>

    <p class="research-subtitle">
        A data-driven investigation into the burden, biology,
        detection, treatment, and survival of pancreatic cancer —
        and the question of whether earlier detection could
        fundamentally change outcomes.
    </p>

</section>


<!-- =====================================================
     RESEARCH QUESTION
===================================================== -->

<div class="research-question">

    <div class="label">
        Central Research Question
    </div>

    <h2>
        Why is pancreatic cancer frequently diagnosed at an
        advanced stage, and could earlier detection meaningfully
        improve survival?
    </h2>

</div>


<!-- =====================================================
     PROJECT THESIS / MOCK
===================================================== -->

## Working Hypothesis

> <span class="placeholder">
> Pancreatic cancer remains highly lethal not simply because
> treatment is ineffective, but because many tumors are discovered
> after the disease has already progressed beyond the point where
> curative treatment is most effective.
> </span>

### What I am trying to determine

This project will investigate whether the available evidence
supports the idea that **earlier detection should be one of the
highest-priority opportunities for reducing pancreatic cancer
mortality**.

---

<!-- =====================================================
     THE CANCER IN NUMBERS
===================================================== -->

# The Cancer in Numbers

Before examining the biology, risk factors, or treatment of pancreatic
cancer, it is important to understand the size of the problem.

Pancreatic cancer represents a relatively small proportion of all
cancer diagnoses, but its mortality burden is much larger relative to
its incidence. This makes pancreatic cancer an important disease to
study not only in terms of how often it occurs, but also in terms of
how frequently it results in death.

The following analysis uses population-level cancer data to examine
three related questions:

1. **How frequently is pancreatic cancer diagnosed?**
2. **How has pancreatic cancer mortality changed over time?**
3. **How does the mortality burden compare with the number of people
   diagnosed?**

---

<div class="stat-grid">

<div class="stat-card">
<span class="stat-number">67,530</span>
<span class="stat-title">Estimated New Cases</span>
<span class="stat-source">
Source:
<a href="https://seer.cancer.gov/statfacts/html/pancreas.html"
target="_blank">
NCI SEER [2]
</a>
</span>
</div>

<div class="stat-card">
<span class="stat-number">52,740</span>
<span class="stat-title">Estimated Deaths</span>
<span class="stat-source">
Source:
<a href="https://seer.cancer.gov/statfacts/html/pancreas.html"
target="_blank">
NCI SEER [2]
</a>
</span>
</div>

<div class="stat-card">
<span class="stat-number">13.7%</span>
<span class="stat-title">5-Year Relative Survival</span>
<span class="stat-source">
2016–2022 · NCI SEER [2]
</span>
</div>

<div class="stat-card">
<span class="stat-number">1.7%</span>
<span class="stat-title">Estimated Lifetime Risk</span>
<span class="stat-source">
2021–2023 · NCI SEER [2]
</span>
</div>

</div>


# Incidence

## How Frequently Does Pancreatic Cancer Occur?

**Incidence** describes the occurrence of new cancer cases within a
population during a specified period.

In the United States, the age-adjusted incidence rate of pancreatic
cancer is **13.9 new cases per 100,000 people per year**, based on
cases diagnosed during **2019–2023**. [2]

Age adjustment is important because cancer risk varies substantially
with age. Using an age-adjusted rate makes comparisons across
populations and time periods more meaningful.

Approximately **1.7% of men and women** are expected to be diagnosed
with pancreatic cancer at some point during their lifetime, based on
2021–2023 data. [2]

In 2023, an estimated **113,931 people were living with pancreatic
cancer in the United States**. [2]

These statistics measure different aspects of the disease:

| Measure      | What it tells us |
| :---      | :--- |
| **Incidence**      | How many new cases occur |
| **Lifetime risk**      | The probability of developing pancreatic cancer during a person’s lifetime |
| **Prevalence**      | How many people are living with the disease |

Together, these measurements provide a broader picture of the
population affected by pancreatic cancer.

---

## Incidence Over Time

The current incidence rate tells us how frequently pancreatic cancer
occurs today, but it does not tell us whether the disease is becoming
more or less common.

To investigate this, I analyzed pancreatic cancer incidence across
multiple years using data processed in Python/Jupyter Notebook.

### Questions Investigated

- Has pancreatic cancer incidence changed over time?
- Is the overall trend increasing, decreasing, or relatively stable?
- Are there noticeable differences between demographic groups?
- Does age appear to influence the incidence pattern?
- What does the long-term trend suggest about the future burden of
  pancreatic cancer?

---

## Figure 1 — Pancreatic Cancer Incidence Over Time

<img src="/figures/incidence_over_time.png"
     alt="Pancreatic cancer incidence over time"
     width="100%">

**Source:** National Cancer Institute, Surveillance, Epidemiology, and
End Results Program (SEER). [2]

**Analysis and visualization:** Author using Python/Jupyter Notebook.

### Interpreting the Trend

The incidence analysis is used to determine whether pancreatic cancer
has remained stable or changed substantially over the period examined.

According to the current SEER trend data, pancreatic cancer incidence
has **increased in recent years**, with an estimated annual percentage
change of approximately **0.9% per year from 2014–2023**. [2]

This suggests that pancreatic cancer is not simply a historical
problem. The population burden continues to require attention.

However, the trend alone cannot establish *why* incidence is
increasing.

Changes in incidence can potentially reflect a combination of
population aging, changes in risk factors, improvements in diagnosis,
and other demographic or biological factors.

Therefore, the incidence analysis establishes an important observation:

> **Pancreatic cancer is not disappearing; the number of newly
> diagnosed cases continues to be an important public-health concern.**

The next question is whether mortality has changed in the same way.


# Mortality

## How Many People Die From Pancreatic Cancer?

**Mortality** describes deaths attributed to a disease within a
population.

The current age-adjusted mortality rate for pancreatic cancer is
**11.3 deaths per 100,000 people per year**, based on deaths recorded
during **2020–2024**. [2]

SEER estimates approximately **52,740 deaths from pancreatic cancer in
2026**. [2]

Mortality is especially important when studying pancreatic cancer
because the disease has a relatively low incidence compared with some
other major cancers, yet remains one of the leading causes of cancer
death in the United States.

---

## Mortality Over Time

Examining mortality over time allows us to determine whether progress
in diagnosis and treatment has resulted in a substantial population-
level reduction in deaths.

### Questions Investigated

- How has pancreatic cancer mortality changed over time?
- Is mortality increasing, decreasing, or stable?
- Does the mortality trend resemble the incidence trend?
- How does pancreatic cancer compare with other major cancers?

---

## Figure 2 — Pancreatic Cancer Mortality Over Time

<img src="/figures/mortality_over_time.png"
     alt="Pancreatic cancer mortality over time"
     width="100%">

**Source:** National Cancer Institute, SEER. [2]

**Analysis and visualization:** Author using Python/Jupyter Notebook.

### Interpreting the Mortality Trend

The mortality analysis provides an important comparison with the
incidence analysis.

While recent pancreatic cancer incidence has increased, SEER reports
that the age-adjusted pancreatic cancer death rate was **stable from
2015–2024**. [2]

This difference is important.

If more people are being diagnosed while mortality does not decline
substantially, then simply identifying more cases may not be enough to
solve the problem.

This raises a more specific research question:

> **Why has improved medical care not produced a much larger reduction
> in pancreatic cancer mortality?**

To investigate this question, pancreatic cancer mortality can also be
compared with the mortality burden of other major cancers.


# Pancreatic Cancer Compared With Other Major Cancers

Raw numbers of deaths can be misleading when comparing different
cancer types.

A cancer that affects a very large population may cause more total
deaths simply because more people develop it.

For this reason, this project uses **mortality rates** to make a more
meaningful population-level comparison.

---

## Figure 3 — Mortality Compared With Other Major Cancers

<img src="/figures/top_10_mortality_vs_pancreas.png"
     alt="Pancreatic cancer mortality compared with other major cancers"
     width="100%">

**Source:** National Cancer Institute, SEER. [2]

**Analysis and visualization:** Author using Python/Jupyter Notebook.

### What Does the Comparison Show?

The analysis demonstrates that pancreatic cancer does **not** have the
highest mortality rate among all major cancers.

For example, the mortality rate for lung and bronchus cancer is
substantially higher.

However, pancreatic cancer remains important because its mortality
burden is high despite a substantially lower incidence than some of
the most common cancers.

This distinction is important.

The central problem is not simply:

> **"Does pancreatic cancer cause the most deaths?"**

Instead, the more useful question is:

> **"Why does a cancer that is diagnosed less frequently still account
> for such a large proportion of cancer deaths?"**

This question leads directly to the relationship between incidence,
mortality, stage at diagnosis, and survival.


# Incidence vs. Mortality

Incidence and mortality describe different aspects of the cancer
burden.

**Incidence** measures new diagnoses, while **mortality** measures
deaths occurring within a population.

The current age-adjusted pancreatic cancer incidence rate is:

**13.9 new cases per 100,000 people per year.** [2]

The current age-adjusted pancreatic cancer mortality rate is:

**11.3 deaths per 100,000 people per year.** [2]

The fact that these two population-level rates are relatively close
is an important observation.

---

## A Descriptive Comparison

Using the two reported rates:

<div style="text-align: left; margin: 1.5rem 0; font-size: 1.2rem; font-weight: 500;">
  (11.3 / 13.9) &times; 100 &approx; <strong>81.3%</strong>
</div>

Therefore, the reported mortality rate is approximately **81.3% of
the reported incidence rate**.

### Important limitation

This **does not mean that 81.3% of patients diagnosed with pancreatic
cancer die**.

The calculation compares two population-level rates that are based on
different reporting periods:

- Incidence: **2019–2023**
- Mortality: **2020–2024**

The people represented in the mortality statistics are not necessarily
the same people represented in the incidence statistics.

Therefore, the 81.3% value is used only as a **descriptive comparison
between population-level rates**.

It should **not** be interpreted as:

- a patient's probability of death,
- a case-fatality rate,
- the percentage of diagnosed patients who die, or
- an individual prognosis.

---

## Figure 4 — Incidence vs. Mortality

<img src="/figures/incidence_vs_mortality.png"
     alt="Pancreatic cancer incidence compared with mortality"
     width="100%">

**Source:** National Cancer Institute, SEER. [2]

**Analysis and visualization:** Author using Python/Jupyter Notebook.

---

# What Does This Suggest?

The incidence and mortality data reveal an important pattern.

Pancreatic cancer has:

- A relatively low population incidence compared with several major
  cancers.
- An incidence rate of **13.9 per 100,000**.
- A mortality rate of **11.3 per 100,000**.
- Increasing recent incidence.
- Mortality that has remained relatively stable.
- A very low overall 5-year relative survival rate.

These observations suggest that pancreatic cancer is not simply a
problem of how many people develop the disease.

It is also a problem of **what happens after diagnosis**.

One possible explanation is that many patients are diagnosed only
after the cancer has progressed.

SEER data show substantial differences in survival according to stage
at diagnosis, making the timing of diagnosis an important area for
further investigation. [2]

This leads to the central problem that the rest of this project will
investigate:

> **If pancreatic cancer can be identified earlier, could shifting
> diagnosis toward earlier stages substantially improve survival?**

The next sections therefore move from **population data** to the
people affected by the disease, the biology of pancreatic cancer,
risk factors, detection, staging, treatment, and potential solutions.
<!-- =====================================================
     WHO GETS PANCREATIC CANCER?
===================================================== -->

# Who Gets Pancreatic Cancer?

Pancreatic cancer does not affect every population equally.

Understanding **who is most likely to develop pancreatic cancer**
helps identify populations that may require greater awareness,
research attention, or future early-detection strategies.

However, demographic differences should not automatically be
interpreted as causes of cancer. A difference between populations
can result from age distribution, risk-factor exposure, genetics,
access to healthcare, diagnosis patterns, or combinations of these
factors.

This section examines pancreatic cancer by **age, sex, race and
ethnicity, and geography**.

---

# Age

## Pancreatic Cancer Becomes More Common With Age

Age is one of the strongest demographic patterns associated with
pancreatic cancer.

Pancreatic cancer is uncommon in younger adults and becomes much more
common at older ages.

According to the National Cancer Institute, the median age at
diagnosis for pancreatic cancer is approximately **71 years**. [2]

This makes age an important factor when interpreting pancreatic cancer
incidence and mortality statistics.

### Research Questions

- At what age does pancreatic cancer incidence begin to increase
  substantially?
- Which age group has the highest incidence?
- Does mortality show a similar age pattern?
- How different is the burden between younger and older populations?

---

## Figure 5 — Pancreatic Cancer Incidence by Age

<h2>Pancreatic Cancer Incidence by Age</h2>
<iframe 
    src="figures/pancreas_incidence.html" 
    width="100%" 
    height="600" 
    style="border:none;">
</iframe>

**Source:** National Cancer Institute, SEER. [2]

**Analysis and visualization:** Author using Python/Jupyter Notebook.

### What Does the Age Distribution Show?

The age distribution demonstrates that pancreatic cancer is primarily
a disease of older adults.

The sharp increase in incidence with age is important because the
United States population is also becoming older.

Therefore, population aging may contribute to the future number of
pancreatic cancer cases even if individual risk factors remain
unchanged.

This distinction is important:

> **An increasing number of cancer cases does not necessarily mean
> that every individual's risk is increasing. Population structure
> also matters.**

---

# Sex

## Does Pancreatic Cancer Affect Men and Women Differently?

Pancreatic cancer affects both men and women.

The overall incidence rate is approximately **13.9 cases per 100,000
people per year**, but analyzing the sexes separately can reveal
whether meaningful differences exist.

### Research Questions

- Is pancreatic cancer more common in men or women?
- Is the difference consistent across age groups?
- Does mortality show the same pattern as incidence?

---

## Figure 6 — Pancreatic Cancer Incidence by Sex

<img src="/figures/incidence_by_sex.png"
     alt="Pancreatic cancer incidence by sex"
     width="100%">

**Source:** National Cancer Institute, SEER. [2]

**Analysis and visualization:** Author using Python/Jupyter Notebook.

### Interpreting Sex Differences

Differences between male and female incidence should be interpreted
carefully.

Sex may correlate with differences in exposure to known risk factors,
occupational exposures, smoking history, metabolic conditions, and
other biological factors.

Therefore, this graph describes a population-level difference but does
not establish that biological sex itself causes pancreatic cancer.

---

# Race and Ethnicity

## Does Pancreatic Cancer Affect Racial and Ethnic Groups Equally?

Race and ethnicity provide another important dimension of pancreatic
cancer epidemiology.

Differences in cancer rates between populations can reflect many
factors, including:

- Genetic susceptibility
- Smoking and other behavioral exposures
- Diabetes and metabolic health
- Environmental exposures
- Socioeconomic conditions
- Access to healthcare
- Differences in screening and diagnosis
- Geographic distribution

For this reason, racial and ethnic differences should be treated as
an epidemiological signal requiring further investigation rather than
as evidence of a single biological cause.

---

## Figure 7 — Pancreatic Cancer Incidence by Race/Ethnicity

<img src="/figures/incidence_by_race.png"
     alt="Pancreatic cancer incidence by race and ethnicity"
     width="100%">

**Source:** National Cancer Institute, SEER. [2]

**Analysis and visualization:** Author using Python/Jupyter Notebook.

### What Does the Comparison Show?

The graph allows the project to determine whether pancreatic cancer
incidence differs substantially among racial and ethnic populations.

If meaningful differences appear, the next question is **why**.

A useful follow-up analysis would compare demographic differences with
known risk factors and healthcare-access differences rather than
assuming that race itself explains the observed pattern.

---

# Geographic Distribution

## Where Is Pancreatic Cancer Most Common?

Geography provides another way to investigate cancer burden.

Pancreatic cancer rates can vary between geographic regions because
populations differ in age, socioeconomic conditions, environmental
exposures, healthcare access, and prevalence of risk factors.

A geographic analysis can therefore help identify areas where the
disease burden may be concentrated.

---

## Figure 8 — Geographic Distribution of Pancreatic Cancer

<img src="/figures/pancreatic_cancer_map.png"
     alt="Geographic distribution of pancreatic cancer"
     width="100%">

**Source:** National Cancer Institute / SEER or CDC cancer data. [2][5]

**Analysis and visualization:** Author using Python/Jupyter Notebook.

### Geographic Research Questions

- Which states have the highest incidence?
- Which states have the highest mortality?
- Are high-incidence areas also high-mortality areas?
- Are there geographic patterns that correspond with known risk
  factors?
- Could healthcare access contribute to regional differences?

---

# Demographic Findings

The demographic analysis provides several important observations.

### Age

Pancreatic cancer is strongly associated with older age, with the
majority of diagnoses occurring among older adults. [2]

### Sex

Pancreatic cancer affects both men and women, with measurable
differences that can be investigated using population-level data.

### Race and Ethnicity

Incidence differs among racial and ethnic populations, but these
differences cannot be attributed to race alone. Multiple biological,
environmental, behavioral, and healthcare factors may contribute.

### Geography

Geographic variation provides another opportunity to investigate
whether cancer burden corresponds with differences in population
characteristics, risk factors, or healthcare access.

---

# What Do These Patterns Tell Us?

The demographic analysis changes the question from:

> **"How common is pancreatic cancer?"**

to:

> **"Who is most affected, and why?"**

Age appears to be particularly important because pancreatic cancer
becomes substantially more common in older populations.

However, demographic patterns alone cannot explain pancreatic cancer.

The next step is therefore to investigate **risk factors**.

If certain exposures or conditions are associated with higher pancreatic
cancer risk, they may help explain some of the patterns observed in
the population.

---

# From Demographics to Risk

The next section investigates the known and suspected risk factors
associated with pancreatic cancer, including:

- Cigarette smoking
- Obesity
- Diabetes
- Chronic pancreatitis
- Family history
- Inherited genetic syndromes
- Alcohol consumption
- Environmental and occupational exposures

The goal is not simply to create a list of risk factors.

Instead, the project will ask:

> **Which risk factors have the strongest evidence, how large is
> their effect, and could reducing exposure to modifiable risk
> factors reduce the future burden of pancreatic cancer?**
# Cancer Biology

Your course introduces the **Hallmarks of Cancer** as a framework
for understanding how cancer cells acquire capabilities that allow
them to grow, survive, invade, and spread.

The lecture identifies hallmarks including proliferative signaling,
evasion of growth suppressors, invasion and metastasis, replicative
immortality, angiogenesis, resistance to cell death, immune evasion,
inflammation, genome instability, and deregulated cellular energetics.

<span class="placeholder">
For pancreatic cancer, identify which hallmarks appear especially
important and explain why.
</span>


## Important Molecular Changes

| Gene / Pathway | Normal Function | What Changes? | Why It Matters |
|---|---|---|---|
| [KRAS] | [Research] | [Research] | [Research] |
| [TP53] | [Research] | [Research] | [Research] |
| [CDKN2A] | [Research] | [Research] | [Research] |
| [SMAD4] | [Research] | [Research] | [Research] |

<span class="placeholder">
Replace this table with findings from NCI, TCGA, peer-reviewed
papers, and other primary/authoritative sources.
</span>


# Risk Factors

Instead of simply listing risk factors, I will divide them into
categories.

## Genetic / Hereditary

<span class="placeholder">
Family history, inherited syndromes, germline mutations, etc.
</span>

## Behavioral

<span class="placeholder">
Smoking, alcohol, diet, physical activity, etc.
</span>

## Medical

<span class="placeholder">
Diabetes, chronic pancreatitis, obesity, etc.
</span>

## Environmental

<span class="placeholder">
Occupational and environmental exposures where evidence supports
an association.
</span>


## Risk Factor Table

<table class="research-table">

<tr>
<th>Risk Factor</th>
<th>Strength of Evidence</th>
<th>Modifiable?</th>
<th>Potential Intervention</th>
</tr>

<tr>
<td>[Factor]</td>
<td>[High / Moderate / Emerging]</td>
<td>[Yes / No]</td>
<td>[Intervention]</td>
</tr>

<tr>
<td>[Factor]</td>
<td>[High / Moderate / Emerging]</td>
<td>[Yes / No]</td>
<td>[Intervention]</td>
</tr>

<tr>
<td>[Factor]</td>
<td>[High / Moderate / Emerging]</td>
<td>[Yes / No]</td>
<td>[Intervention]</td>
</tr>

</table>


# How Is Pancreatic Cancer Detected?

## Symptoms

<span class="placeholder">
Describe common symptoms and — importantly — whether they tend
to appear early or later in the disease process.
</span>


## Imaging

<span class="placeholder">
Research CT, MRI, PET, endoscopic ultrasound, and other relevant
imaging approaches.
</span>


## Biopsy

<span class="placeholder">
Explain how tissue is obtained and how pathology confirms the diagnosis.
</span>


## Biomarkers

<span class="placeholder">
Investigate CA 19-9 and newer biomarkers while distinguishing
established clinical uses from experimental approaches.
</span>


## Genetic / Molecular Testing

<span class="placeholder">
Explain when molecular testing is used and how it affects treatment.
</span>


# The Detection Problem

> **The key question is not only "How do we detect pancreatic cancer?"
> but "How early can we detect it reliably?"**

<span class="placeholder">
Investigate why pancreatic cancer is difficult to detect early.

Possible research directions:

- Lack of early symptoms
- Anatomical location
- Lack of average-risk screening
- Biomarker limitations
- False positives / false negatives
- Tumor biology
- Difficulty distinguishing benign from malignant findings
- Healthcare access
</span>


<div class="figure-placeholder">

<div>
<strong>FIGURE 5 — STAGE AT DIAGNOSIS</strong>

Show the percentage of cases diagnosed as localized,
regional, distant, or unknown stage.
</div>

</div>


# Staging

## Stage 0

<span class="placeholder">
Research the applicable definition.
</span>

## Stage I

<span class="placeholder">
Research the applicable definition.
</span>

## Stage II

<span class="placeholder">
Research the applicable definition.
</span>

## Stage III

<span class="placeholder">
Research the applicable definition.
</span>

## Stage IV

<span class="placeholder">
Research the applicable definition.
</span>


# Stage vs. Survival

This is one of the most important analyses in this project.

<div class="figure-placeholder">

<div>
<strong>FIGURE 6 — FIVE-YEAR RELATIVE SURVIVAL BY STAGE</strong>

Compare localized, regional, and distant disease.
</div>

</div>


## What does this tell us?

<span class="placeholder">
Do not simply describe the graph.

Explain what the survival gap suggests about the importance
of early diagnosis and why stage at diagnosis may be an important
target for intervention.
</span>


# Current Treatments

## Surgery

<span class="placeholder">
Explain resection and which patients may be candidates.
</span>

## Chemotherapy

<span class="placeholder">
Describe major chemotherapy approaches and when they are used.
</span>

## Radiation

<span class="placeholder">
Describe its role in localized, locally advanced, or palliative treatment.
</span>

## Targeted Therapy

<span class="placeholder">
Research biomarker-directed treatments and which patients may benefit.
</span>

## Immunotherapy

<span class="placeholder">
Research which pancreatic cancer populations may benefit and why.
</span>

## Clinical Trials

<span class="placeholder">
Identify promising experimental approaches currently being tested.
</span>


# Treatment Is Changing

<div class="figure-placeholder">

<div>
<strong>FIGURE 7 — TIMELINE OF PANCREATIC CANCER TREATMENT</strong>

[Historical treatment]

→ [Modern chemotherapy]

→ [Precision treatment]

→ [Immunotherapy / targeted approaches]

→ [2026 developments]

</div>

</div>


# Precision Oncology

The same anatomical cancer does not necessarily behave identically
in every patient.

<span class="placeholder">
Investigate how genomic or molecular information can influence
treatment selection in pancreatic cancer.
</span>


# Survival and Prognosis

Rather than treating "life expectancy" as a single number, this project
will examine prognosis through multiple measures.

### 5-Year Relative Survival

[VALUE]

### Median Overall Survival

[VALUE]

### Survival by Stage

[INSERT GRAPH]

### Survival by Treatment

[INSERT GRAPH]

### Survival by Molecular / Clinical Subtype

[INSERT GRAPH IF DATA ARE AVAILABLE]


# What Are Patients Actually Dying From?

<span class="placeholder">
Investigate how progression, metastatic disease, organ involvement,
recurrence, and treatment complications contribute to mortality.

Do not assume that "death from cancer" means the same biological
process in every patient.
</span>


# The Biggest Unsolved Problem

## My Current Research Hypothesis

> **Pancreatic cancer mortality may be particularly difficult to reduce
> through treatment alone if most patients continue to reach diagnosis
> after the disease has already become difficult or impossible to cure surgically.**

<span class="placeholder">
Use evidence from the epidemiology, stage distribution, survival,
and treatment sections to decide whether this hypothesis is supported.
</span>


# What Solutions Already Exist?

<table class="research-table">

<tr>
<th>Solution</th>
<th>Current Evidence</th>
<th>Potential Benefit</th>
<th>Major Limitation</th>
</tr>

<tr>
<td>Risk-based surveillance</td>
<td>[Research]</td>
<td>[Research]</td>
<td>[Research]</td>
</tr>

<tr>
<td>Blood biomarkers</td>
<td>[Research]</td>
<td>[Research]</td>
<td>[Research]</td>
</tr>

<tr>
<td>Liquid biopsy</td>
<td>[Research]</td>
<td>[Research]</td>
<td>[Research]</td>
</tr>

<tr>
<td>Advanced imaging</td>
<td>[Research]</td>
<td>[Research]</td>
<td>[Research]</td>
</tr>

<tr>
<td>AI-assisted detection</td>
<td>[Research]</td>
<td>[Research]</td>
<td>[Research]</td>
</tr>

</table>


# My Proposed Solution

<div class="solution-box">

<h2>
Can risk-stratified early detection change the stage at diagnosis?
</h2>

<p>
<span class="placeholder">
This is a working project idea, not a proven clinical recommendation.
</span>
</p>

</div>


## Proposed Model

```text
General Population
        ↓
Risk Assessment
        ↓
Identify High-Risk Population
        ↓
Surveillance / Biomarker Testing
        ↓
Abnormal Result
        ↓
Confirmatory Imaging
        ↓
Earlier Diagnosis
        ↓
More Potentially Treatable Disease
        ↓
Potential Survival Improvement

---

## Artificial Intelligence Use

Artificial intelligence tools were used as supplementary tools during
the development of this project. AI assistance was primarily used to
help organize ideas, structure the research website, troubleshoot and
develop website code, improve the visual presentation of the site, and
identify possible directions for further research.

AI was not treated as a primary scientific or medical source. Claims,
statistics, scientific findings, and conclusions presented in this
project were reviewed against the original cited sources, including
government agencies, international cancer organizations, peer-reviewed
research, and publicly available cancer datasets.

The final selection of sources, interpretation of scientific evidence,
data analysis, visualizations, conclusions, and written content remain
the responsibility of the author. AI-generated suggestions were
reviewed, edited, accepted, or rejected by the author rather than being
used automatically.

When AI assistance was used for programming, the resulting code was
reviewed and modified by the author to ensure that it performed the
intended analysis or website function.

The purpose of using AI was to reduce the time required for
organization, coding, troubleshooting, and presentation so that more
time could be devoted to researching, evaluating, and understanding
the scientific evidence.

AI assistance was used to support the research and development process,
not to replace the author's evaluation of the evidence.

---

## Source and Citation Statement

This project uses information from government agencies,
international cancer organizations, peer-reviewed scientific
literature, and publicly available cancer datasets.

Information from these sources has been summarized and analyzed
in my own words unless otherwise indicated.

Statistics and data visualizations identify their original
data source. Original graphs will be generated by the author
using Python/Jupyter Notebook.

External images, figures, and other copyrighted materials are
used only when their reuse terms permit it, and attribution is
provided where required.

---

## References

1. National Cancer Institute (NCI).  
   *Pancreatic Cancer.*  
   https://www.cancer.gov/types/pancreatic

2. National Cancer Institute, Surveillance, Epidemiology, and End Results (SEER).  
   *Cancer Stat Facts: Pancreatic Cancer.*  
   https://seer.cancer.gov/statfacts/html/pancreas.html

3. International Agency for Research on Cancer (IARC).  
   *Global Cancer Observatory: Pancreas.*  
   https://gco.iarc.who.int/

4. University of Oxford, Pancreatic Cancer Action, and University of Surrey
   *Pancreatic cancer could be diagnosed up to three years earlier.*  
   https://www.ox.ac.uk/news/2022-11-01-pancreatic-cancer-could-be-diagnosed-three-years-earlier

5. [ADD SOURCE HERE]

6. [ADD SOURCE HERE]

7. [ADD SOURCE HERE]

