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
    background-color: #f8f9fa;
}

.stage-bar-container {
    margin: 35px 0;
    background: #fafafa;
    border: 1px solid #ddd;
    border-radius: 10px;
    padding: 25px;
}

.stage-row {
    margin-bottom: 18px;
}

.stage-label {
    display: flex;
    justify-content: space-between;
    font-weight: 600;
    margin-bottom: 6px;
    font-size: 0.95rem;
}

.stage-progress-bg {
    background: #e9ecef;
    border-radius: 6px;
    height: 22px;
    overflow: hidden;
}

.stage-progress-fill {
    height: 100%;
    border-radius: 6px;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    padding-right: 10px;
    color: white;
    font-size: 0.75rem;
    font-weight: bold;
}

@media (max-width: 800px) {
    .stat-grid {
        grid-template-columns: 1fr 1fr;
    }
}

@media (max-width: 550px) {
    .stat-grid {
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
        CANCER RESEARCH PROJECT - Data-Driven Analysis
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
     PROJECT THESIS
===================================================== -->

## Working Hypothesis

> **Pancreatic cancer remains highly lethal not simply because treatment is fundamentally ineffective, but because over 80% of tumors are discovered after the disease has already metastasized or invaded critical vascular structures, past the point where curative surgical resection is possible.**

### Objective

This project investigates whether population-level epidemiology, tumor genomics, and clinical trial evidence support the concept that **early detection and biomarker-driven screening represent the single highest-priority opportunity for reducing pancreatic cancer mortality**.

---

<!-- =====================================================
     THE CANCER IN NUMBERS
===================================================== -->

# The Cancer in Numbers

Before examining the biology, risk factors, or treatment of pancreatic cancer, it is essential to establish the scale of its public health impact.

Pancreatic cancer accounts for roughly 3.2% of all new cancer cases in the United States annually, yet it represents the 3rd leading cause of cancer deaths. This striking disparity between incidence and mortality underscores why pancreatic ductal adenocarcinoma (PDAC) is one of the most lethal oncological challenges.

The following analysis uses population-level cancer data to examine three related questions:

1. **How frequently is pancreatic cancer diagnosed?**
2. **How has pancreatic cancer mortality changed over time?**
3. **How does the mortality burden compare with the number of people diagnosed?**

---

<div class="stat-grid">

<div class="stat-card">
<span class="stat-number">67,530</span>
<span class="stat-title">Estimated New Cases</span>
<span class="stat-source">
Source:
<a href="https://seer.cancer.gov/statfacts/html/pancreas.html" target="_blank">
NCI SEER
</a>
</span>
</div>

<div class="stat-card">
<span class="stat-number">52,740</span>
<span class="stat-title">Estimated Deaths</span>
<span class="stat-source">
Source:
<a href="https://seer.cancer.gov/statfacts/html/pancreas.html" target="_blank">
NCI SEER
</a>
</span>
</div>

<div class="stat-card">
<span class="stat-number">13.7%</span>
<span class="stat-title">5-Year Relative Survival</span>
<span class="stat-source">
2016–2022 · NCI SEER
</span>
</div>

<div class="stat-card">
<span class="stat-number">1.7%</span>
<span class="stat-title">Estimated Lifetime Risk</span>
<span class="stat-source">
2021–2023 · NCI SEER
</span>
</div>

</div>


# Incidence

## How Frequently Does Pancreatic Cancer Occur?

**Incidence** describes the occurrence of new cancer cases within a population during a specified period.

In the United States, the age-adjusted incidence rate of pancreatic cancer is **13.9 new cases per 100,000 people per year**, based on cases diagnosed during **2019–2023**.

Age adjustment accounts for variations in population age structures across regions and time, rendering long-term comparisons epidemiologically valid.

Approximately **1.7% of men and women** will be diagnosed with pancreatic cancer during their lifetime. In 2023, an estimated **113,931 people were living with pancreatic cancer in the United States**.

| Measure | Definition & Clinical Significance |
| :--- | :--- |
| **Incidence** | Rate of new cases (13.9 per 100,000); tracks population risk dynamics. |
| **Lifetime Risk** | Cumulative individual probability (~1 in 59); highlights lifetime health burden. |
| **Prevalence** | Total living patient population; reflects survival times and overall disease burden. |

---

## Incidence Over Time

The current incidence rate measures today's burden, but tracking temporal shifts reveals whether pancreatic cancer incidence is expanding.

### Questions Investigated

- Has pancreatic cancer incidence changed over time?
- Is the overall trend increasing, decreasing, or relatively stable?
- Are there noticeable differences between demographic groups?
- Does age appear to influence the incidence pattern?
- What does the long-term trend suggest about the future burden of pancreatic cancer?

---

## Figure 1 — Pancreatic Cancer Incidence Over Time

<img src="/figures/incidence_over_time.png"
     alt="Pancreatic cancer incidence over time"
     width="100%">

**Source:** National Cancer Institute, Surveillance, Epidemiology, and End Results Program (SEER).

**Analysis and visualization:** Author using Python/Jupyter Notebook.

### Interpreting the Trend

According to SEER trend data, pancreatic cancer incidence has **increased steadily**, growing at an estimated Annual Percentage Change (APC) of **0.9% per year from 2014–2023**.

Changes in incidence reflect a complex interplay of demographic shifts (population aging), rising metabolic risk factors (obesity, type 2 diabetes), and enhanced cross-sectional diagnostic imaging (CT/MRI) capturing subtle pancreatic lesions.

> **Pancreatic cancer incidence continues to climb, establishing that the total annual population burden will increase over the coming decade.**


# Mortality

## How Many People Die From Pancreatic Cancer?

The age-adjusted mortality rate for pancreatic cancer stands at **11.3 deaths per 100,000 people per year** (2020–2024 SEER data).

SEER estimates approximately **52,740 deaths from pancreatic cancer in 2026**. Pancreatic cancer remains the 3rd leading cause of cancer death in the United States, projected to surpass biliary and colorectal fatalities to become the 2nd leading cause before 2030.

---

## Mortality Over Time

## Figure 2 — Pancreatic Cancer Mortality Over Time

<img src="/figures/mortality_over_time.png"
     alt="Pancreatic cancer mortality over time"
     width="100%">

**Source:** National Cancer Institute, SEER.

**Analysis and visualization:** Author using Python/Jupyter Notebook.

### Interpreting the Mortality Trend

While pancreatic cancer incidence has risen by 0.9% annually, mortality rates have remained largely flat over the past decade (2015–2024).

This delta indicates that modern systemic therapies (such as modern multi-agent chemotherapy regimens like FOLFIRINOX) have extended median survival for advanced patients by months, but have not yet yielded population-level curative breakthroughs.

> **Why has improved medical care not produced a larger reduction in overall pancreatic cancer mortality?**


# Pancreatic Cancer Compared With Other Major Cancers

## Figure 3 — Mortality Compared With Other Major Cancers

<img src="/figures/top_10_mortality_vs_pancreas.png"
     alt="Pancreatic cancer mortality compared with other major cancers"
     width="100%">

**Source:** National Cancer Institute, SEER.

**Analysis and visualization:** Author using Python/Jupyter Notebook.

### What Does the Comparison Show?

Although cancers like lung adenocarcinoma cause a higher total volume of fatalities, pancreatic cancer displays an abnormally narrow gap between its incidence and mortality rates. 

The core issue is not simply overall patient volume, but **case fatality severity**: pancreatic cancer maintains one of the highest mortality-to-incidence ratios among solid tumors.


# Incidence vs. Mortality

Comparing age-adjusted rates directly:

$$\frac{\text{Mortality Rate}}{\text{Incidence Rate}} = \frac{11.3}{13.9} \approx 81.3\%$$

The age-adjusted mortality rate is approximately **81.3% of the incidence rate**.

While these two rates rely on slightly offset evaluation windows (Incidence: 2019–2023; Mortality: 2020–2024) and cannot replace prospective patient cohort tracking, this population-level ratio demonstrates that the majority of patients diagnosed with pancreatic cancer still succumb to the disease.

---

## Figure 4 — Incidence vs. Mortality

<img src="/figures/incidence_vs_mortality.png"
     alt="Pancreatic cancer incidence compared with mortality"
     width="100%">

**Source:** National Cancer Institute, SEER.

**Analysis and visualization:** Author using Python/Jupyter Notebook.


# Who Gets Pancreatic Cancer?

Demographic patterns provide vital signals regarding biological susceptibility, risk factor exposures, and diagnostic access disparities.

---

# Age

## Figure 5 — Pancreatic Cancer Incidence by Age

<iframe 
    src="/figures/incidence_by_age.html" 
    width="100%" 
    height="600" 
    style="border:none;">
</iframe>

**Source:** National Cancer Institute, SEER.

The median age at diagnosis for pancreatic cancer is **71 years**. Rates rise sharply after age 50 and peak between ages 75 and 84. Because carcinogenesis in the pancreas requires the sequential accumulation of multiple somatic driver mutations ($KRAS \rightarrow CDKN2A \rightarrow TP53 \rightarrow SMAD4$) over decades, age remains the strongest demographic predictor of incidence.

---

# Sex

## Figure 6 — Pancreatic Cancer Incidence by Sex

<img src="/figures/pancreatic_incidence_trend_by_sex.png"
     alt="Pancreatic cancer incidence by sex"
     width="100%">

**Source:** National Cancer Institute, SEER.

Men exhibit higher age-adjusted incidence rates (~15.2 per 100,000) than women (~12.7 per 100,000). This historical divergence correlates primarily with higher historical smoking rates and occupational toxicant exposures among men, though differences in visceral fat distribution may also play a secondary role.

---

# Race and Ethnicity

## Figure 7 — Pancreatic Cancer Incidence by Race/Ethnicity

<img src="/figures/incidence_by_race.png"
     alt="Pancreatic cancer incidence by race and ethnicity"
     width="100%">

**Source:** National Cancer Institute, SEER.

Non-Hispanic Black populations experience the highest age-adjusted incidence rate (17.6 per 100,000), followed by Non-Hispanic American Indian / Alaska Native (15.3 per 100,000) and Non-Hispanic White populations (14.7 per 100,000). Hispanic (13.8 per 100,000) and Asian/Pacific Islander populations (11.0 per 100,000) display lower rates. 

These disparities stem from a combination of systemic healthcare access inequities, variations in the prevalence of underlying conditions like long-standing type 2 diabetes, and environmental exposure profiles.

---

# Geographic Distribution

## Figure 8 — Urban vs. Rural Trends in Pancreatic Cancer Incidence

<img src="/figures/pancreatic_cancer_urban_rural.png"
     alt="Urban vs Rural Pancreatic Cancer Incidence Trends (2000-2023)"
     width="100%">

**Source:** National Cancer Institute / SEER Data (2000–2023).

### Geographic & Demographic Research Analysis

#### 1. How do incidence trends differ across geographic classifications (Urban vs. Rural)?
Historically, urban areas exhibited higher age-adjusted pancreatic cancer incidence rates than rural areas (11.78 vs. 10.54 per 100,000 in 2000). However, over the 2000–2023 observation period, rural incidence rates experienced a faster upward trajectory, effectively closing the gap. By 2023, rural incidence rates (14.29 per 100,000) slightly surpassed urban incidence rates (14.07 per 100,000).

#### 2. What risk factors align with these geographic patterns?
The convergence and slight inversion of rural-urban rates align with broader health demographic shifts:
* **Obesity & Diabetes:** Rural populations in the U.S. statistically report higher rates of adult obesity and type 2 diabetes—two major established risk factors for pancreatic cancer.
* **Smoking Prevalence:** While cigarette smoking has declined nationwide, the rate of decline has been slower in rural communities compared to urban centers.
* **Environmental & Occupational Exposures:** Agricultural occupations in rural regions carry potential exposures to certain pesticides and industrial chemicals associated with elevated pancreatic risk.

#### 3. How does healthcare access contribute to regional differences?
Healthcare access creates a paradox between detection and outcomes:
* **Diagnostic Catch-up:** The rise in rural incidence rates likely reflects improved diagnostic capabilities and imaging access in non-metropolitan healthcare systems over the last two decades.
* **Mortality & Care Disparities:** While incidence rates are now equivalent, rural patients frequently face barriers to specialized surgical oncology care, complex resection procedures (such as the Whipple procedure), and clinical trials, which are predominantly concentrated in major urban academic medical centers.


# Cancer Biology

Pancreatic Ductal Adenocarcinoma (PDAC) represents over 90% of all pancreatic malignancies. Understanding its unique pathobiology explains why it resists conventional treatment modalities.

### Core Hallmarks of Pancreatic Cancer
1. **Deregulated Cellular Energetics & Proliferative Signaling:** Driven by constitutively active $KRAS$ signaling.
2. **Dense Desmoplastic Stroma (Extracellular Matrix Remodeling):** PDAC creates an avascular, fibrotic microenvironment where dense collagen and hyaluronan elevate intratumoral fluid pressure, compressing blood vessels and impeding systemic drug delivery.
3. **Immune Evasion:** The dense microenvironment is populated by immunosuppressive cells (Regulatory T-cells, Myeloid-Derived Suppressor Cells, and M2 Macrophages) while lacking cytotoxic CD8+ T-cells.


## Important Molecular Changes

| Gene / Pathway | Normal Function | Mutation Frequency | Pathological Significance in PDAC |
| :--- | :--- | :--- | :--- |
| **KRAS** | Small GTPase transducer; regulates cell proliferation and survival | **~95%** | Gain-of-function mutation (commonly G12D, G12V, G12R) causing constitutive upstream RAS signaling and continuous growth. |
| **CDKN2A** | Tumorsuppressor encoding p16INK4a; regulates G1/S cell-cycle checkpoint | **~90%** | Loss of function via promoter hypermethylation or deletion, removing cell-cycle inhibition. |
| **TP53** | Transcription factor ("guardian of the genome"); induces apoptosis/arrest upon DNA damage | **~70%** | Inactivation allows damaged cells to bypass cell-cycle checkpoints and survive chromosomal instability. |
| **SMAD4** | Signal transducer in the TGF-$\beta$ signaling pathway | **~55%** | Loss abolishes TGF-$\beta$-mediated growth inhibition, accelerating invasion and metastatic dissemination. |


# Risk Factors

Pancreatic cancer risk factors are divided into non-modifiable biological predispositions and modifiable exposure vectors.

### Genetic / Hereditary Factors
Germline mutations account for 10%–15% of PDAC cases. Key high-risk hereditary mutations include:
* **BRCA1 / BRCA2 & PALB2:** Homologous recombination repair deficiency genes that elevate pancreatic cancer risk up to 6-fold.
* **STK11 (Peutz-Jeghers Syndrome):** Confers up to a 132-fold lifetime risk elevation.
* **CDKN2A (Familial Atypical Multiple Mole Melanoma - FAMMM):** Elevates lifetime risk by 13- to 39-fold.
* **Lynch Syndrome (MLH1, MSH2 mutations):** Increases risk roughly 9-fold.

### Behavioral & Environmental Factors
* **Cigarette Smoking:** The most established modifiable risk factor, doubling risk ($\text{RR} \approx 2.0$). Smoking accounts for 20%–25% of all PDAC diagnoses.
* **Obesity & Metabolic Syndrome:** High BMI ($\ge 30$) increases relative risk by 1.2 to 1.5. Excess visceral adiposity causes chronic low-grade systemic inflammation and elevated circulating insulin-like growth factors (IGF-1).
* **Dietary Patterns & Alcohol:** Heavy alcohol usage ($\ge 3$ drinks/day) indirectly increases risk by causing chronic pancreatitis.

### Medical Conditions
* **Type 2 Diabetes Mellitus:** Long-standing type 2 diabetes increases risk 1.5- to 2.0-fold. Notably, **new-onset diabetes** in adults over age 50 can act as an early clinical manifestation of occult pancreatic cancer.
* **Chronic Pancreatitis:** Long-term pancreatic inflammation increases lifetime risk up to 8-fold.

## Risk Factor Assessment

<table class="research-table">
<tr>
  <th>Risk Factor</th>
  <th>Strength of Evidence</th>
  <th>Modifiable?</th>
  <th>Potential Public Health / Clinical Intervention</th>
</tr>
<tr>
  <td><strong>Tobacco Use</strong></td>
  <td>High (Strong Causality)</td>
  <td>Yes</td>
  <td>Targeted smoking cessation programs; public policy regulation.</td>
</tr>
<tr>
  <td><strong>Obesity & Diabetes</strong></td>
  <td>High (Epidemiologic Consensus)</td>
  <td>Yes</td>
  <td>Lifestyle interventions; metabolic screening for new-onset diabetes.</td>
</tr>
<tr>
  <td><strong>Hereditary Mutations (BRCA2, PALB2)</strong></td>
  <td>High (Genomic Consensus)</td>
  <td>No</td>
  <td>Genetic counseling; high-risk screening protocols (MRI/EUS).</td>
</tr>
<tr>
  <td><strong>Chronic Pancreatitis</strong></td>
  <td>High (Clinical Consensus)</td>
  <td>Partially</td>
  <td>Alcohol cessation; pain and enzyme management; longitudinal monitoring.</td>
</tr>
<tr>
  <td><strong>Occupational Chemicals (Pesticides, Solvents)</strong></td>
  <td>Moderate / Emerging</td>
  <td>Yes</td>
  <td>Occupational safety guidelines; personal protective equipment (PPE).</td>
</tr>
</table>


# How Is Pancreatic Cancer Detected?

## Symptoms
Pancreatic cancer symptoms are notoriously non-specific during early development:
* **Early / Pre-metastatic Stage:** Often completely asymptomatic, or presents with mild epigastric discomfort, vague dyspepsia, or unexplained weight loss.
* **Advanced / Obstructive Stage:** painless jaundice (from tumor occlusion of the common bile duct), severe back pain (from celiac plexus nerve invasion), dark urine, pale stools, and new-onset diabetes.

## Diagnostic Modalities
1. **Multiphasic Cross-Sectional CT (Pancreas Protocol):** The primary diagnostic tool, utilizing thin-slice arterial and portal venous phase imaging to evaluate tumor vascular involvement.
2. **Endoscopic Ultrasound (EUS):** The most sensitive imaging modality for small tumors (<2 cm), enabling real-time fine-needle aspiration (FNA) or fine-needle biopsy (FNB) for tissue diagnosis.
3. **Magnetic Resonance Cholangiopancreatography (MRCP):** Evaluates pancreatic ductal geometry and liver parenchymal metastases without ionizing radiation.
4. **Biomarkers (CA 19-9):** Carbohydrate Antigen 19-9 is an established tumor marker. It is **not** suitable as a population-wide screening tool due to low sensitivity in early disease and false positives in benign biliary obstruction. Its clinical utility lies in assessing treatment response and post-operative recurrence.
5. **Emerging Liquid Biopsies:** Assays analyzing circulating tumor DNA (ctDNA), cell-free DNA (cfDNA) methylation patterns, and extracellular vesicles are actively being evaluated for early-stage screening.


# The Detection Problem

Pancreatic cancer remains difficult to diagnose early due to a combination of factors:
* **Anatomical Location:** The pancreas rests deep in the retroperitoneum behind the stomach, making physical palpation impossible and masking tumor expansion until adjacent organs or nerves are compressed.
* **Absence of Average-Risk Screening:** Unlike mammography for breast cancer or colonoscopy for colorectal cancer, no non-invasive, cost-effective screening tool exists for the general population.
* **Tumor Biology:** PDAC exhibits early systemic dissemination, with micrometastases often shedding before the primary lesion is visible on standard imaging.


## Figure 9 — Stage Distribution at Diagnosis

<div class="stage-bar-container">
  <div class="stage-row">
    <div class="stage-label">
      <span>Distant (Metastatized)</span>
      <span>52%</span>
    </div>
    <div class="stage-progress-bg">
      <div class="stage-progress-fill" style="width: 52%; background-color: #d9534f;">52%</div>
    </div>
  </div>

  <div class="stage-row">
    <div class="stage-label">
      <span>Regional (Spread to Lymph Nodes/Tissue)</span>
      <span>21%</span>
    </div>
    <div class="stage-progress-bg">
      <div class="stage-progress-fill" style="width: 21%; background-color: #f0ad4e;">21%</div>
    </div>
  </div>

  <div class="stage-row">
    <div class="stage-label">
      <span>Localized (Confined to Pancreas)</span>
      <span>13%</span>
    </div>
    <div class="stage-progress-bg">
      <div class="stage-progress-fill" style="width: 13%; background-color: #5cb85c;">13%</div>
    </div>
  </div>

  <div class="stage-row">
    <div class="stage-label">
      <span>Unstaged / Unknown</span>
      <span>14%</span>
    </div>
    <div class="stage-progress-bg">
      <div class="stage-progress-fill" style="width: 14%; background-color: #6c757d;">14%</div>
    </div>
  </div>
</div>

**Source:** National Cancer Institute, SEER 18 Database (2016–2022).

Over half of all pancreatic cancer patients (52%) present with distant metastases at initial diagnosis, while only 13% are diagnosed at a localized stage where surgical intervention is most effective.


# Staging Definitions (AJCC 8th Edition)

* **Stage 0 (Tis, N0, M0):** Carcinoma in situ (high-grade PanIN) confined to ductal epithelium.
* **Stage I (T1-T2, N0, M0):** Tumor confined to pancreas, $\le 4\text{ cm}$ in greatest dimension.
* **Stage II (T3, N0, M0 or T1-T3, N1, M0):** Tumor extends beyond pancreas without vascular involvement, or has metastasized to 1–3 regional lymph nodes.
* **Stage III (T4, Any N, M0 or Any T, N2, M0):** Tumor involves major arterial axes (celiac axis, superior mesenteric artery), rendering it locally advanced and unresectable, or has metastasized to $\ge 4$ regional lymph nodes.
* **Stage IV (Any T, Any N, M1):** Distant metastases present (commonly liver, peritoneum, lungs).


# Stage vs. Survival

## Figure 10 — Five-Year Relative Survival by Stage at Diagnosis

<div class="stage-bar-container">
  <div class="stage-row">
    <div class="stage-label">
      <span>Localized (Stage I)</span>
      <span>44.3%</span>
    </div>
    <div class="stage-progress-bg">
      <div class="stage-progress-fill" style="width: 44.3%; background-color: #5cb85c;">44.3%</div>
    </div>
  </div>

  <div class="stage-row">
    <div class="stage-label">
      <span>Regional (Stage II / III)</span>
      <span>16.2%</span>
    </div>
    <div class="stage-progress-bg">
      <div class="stage-progress-fill" style="width: 16.2%; background-color: #f0ad4e;">16.2%</div>
    </div>
  </div>

  <div class="stage-row">
    <div class="stage-label">
      <span>Distant (Stage IV)</span>
      <span>3.2%</span>
    </div>
    <div class="stage-progress-bg">
      <div class="stage-progress-fill" style="width: 3.2%; background-color: #d9534f;">3.2%</div>
    </div>
  </div>
</div>

**Source:** National Cancer Institute, SEER 18 Database (2016–2022).

### Analysis of the Survival Gap

This stark survival differential validates our core research hypothesis. Patients diagnosed with localized disease achieve a **44.3% 5-year relative survival rate**, whereas those diagnosed after distant spread experience a 5-year survival rate of **3.2%**.

Downstaging pancreatic cancer—shifting diagnoses from Stage IV to Stage I through surveillance of high-risk populations—could substantially increase long-term survival rates without requiring new therapeutic agents.


# Current Treatments

### 1. Surgical Resection
Surgery remains the only potentially curative option.
* **Pancreaticoduodenectomy (Whipple Procedure):** Performed for tumors in the head/uncinate process of the pancreas. Involves removing the pancreatic head, duodenum, gallbladder, and distal bile duct.
* **Distal Pancreatectomy:** Performed for tumors in the body or tail, typically combined with splenectomy.
* *Eligibility:* Only 15%–20% of patients are surgical candidates at diagnosis.

### 2. Chemotherapy
* **Adjuvant Therapy:** Modified FOLFIRINOX (oxaliplatin, irinotecan, leucovorin, 5-fluorouracil) is the current standard of care following surgical resection, extending median disease-free survival compared to single-agent gemcitabine.
* **First-Line Systemic Therapy:** FOLFIRINOX or NALIRIFOX (liposomal irinotecan, 5-FU, leucovorin, oxaliplatin) and Gemcitabine + Nab-Paclitaxel serve as standard first-line therapies for advanced or metastatic disease.

### 3. Radiation Therapy
Used selectively as neoadjuvant therapy to downstage locally advanced unresectable tumors or for palliative pain control.

### 4. Precision & Biomarker-Targeted Therapies
* **PARP Inhibitors (Olaparib):** Approved for maintenance therapy in patients with germline $BRCA1/2$ mutations who have not progressed on platinum-based chemotherapy (POLO Trial).
* **KRAS G12C/G12D Inhibitors:** Emerging direct KRAS inhibitors (e.g., MRTX1133) represent promising targeted advances for mutant RAS signaling.
* **Immune Checkpoint Inhibitors:** Pembrolizumab is approved exclusively for the ~1% of PDAC patients displaying High Microsatellite Instability (MSI-H) or Mismatch Repair Deficiency (dMMR).


# Conclusion & Future Directions

Pancreatic cancer remains a major challenge in modern oncology, driven by subtle early symptoms, aggressive tumor biology, a fibrotic microenvironment, and a lack of population-wide screening options.

However, epidemiological and clinical evidence demonstrates that **earlier detection substantially alters survival outcomes**:

1. **Survival Disparity:** Shifting diagnoses from Stage IV (3.2% 5-year survival) to Stage I (44.3% 5-year survival) dramatically improves prognosis.
2. **High-Risk Surveillance:** Implementing longitudinal imaging (EUS/MRI) and multi-cancer early detection (MCED) blood assays in high-risk cohorts—such as individuals with germline mutations ($BRCA$, $PALB2$, $CDKN2A$) or new-onset diabetes—provides a targeted path toward early identification.
3. **Integrated Innovation:** Combining liquid biopsy biomarkers with targeted therapeutics (KRAS inhibitors, PARP inhibitors) offers a comprehensive strategy to reduce pancreatic cancer mortality.

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

