---
layout: post
title: "Hands-On Activity 03: Machine Learning & Classification of GTEx Integrin Expression"
date: 2026-09-30
categories: [Genomics, Machine Learning, Data Science, Bioinformatics]
tags: [GTEx, integrins, scikit-learn, logistic regression, KNN, classification, Python, data science]
---

<style>
/* =====================================================
   ACTIVITY HERO & HEADER
===================================================== */
.activity-hero {
    padding: 60px 0 50px 0;
    border-bottom: 1px solid #e2e2de;
    margin-bottom: 50px;
}

.activity-kicker {
    text-transform: uppercase;
    letter-spacing: 0.14em;
    font-size: 0.75rem;
    font-weight: 700;
    color: #0055b8;
    margin-bottom: 16px;
}

.activity-hero h1 {
    font-size: clamp(2.2rem, 5vw, 4rem);
    line-height: 1.1;
    letter-spacing: -0.04em;
    max-width: 1000px;
    margin-bottom: 25px;
    color: #111;
}

.activity-subtitle {
    font-size: 1.2rem;
    line-height: 1.5;
    max-width: 850px;
    color: #555;
}

/* =====================================================
   METRIC STATS GRID
===================================================== */
.stat-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 16px;
    margin: 35px 0;
}

.stat-card {
    border: 1px solid #e5e5e5;
    border-radius: 10px;
    padding: 22px;
    background: #fafafa;
}

.stat-number {
    display: block;
    font-size: 2.1rem;
    font-weight: 800;
    letter-spacing: -0.04em;
    color: #111;
}

.stat-title {
    display: block;
    font-weight: 600;
    margin-top: 6px;
    font-size: 0.95rem;
    color: #333;
}

.stat-source {
    display: block;
    font-size: 0.75rem;
    color: #777;
    margin-top: 10px;
}

/* =====================================================
   CALLOUTS & HIGHLIGHTS
===================================================== */
.research-callout {
    padding: 24px 28px;
    margin: 35px 0;
    border-left: 4px solid #0055b8;
    background: #f4f7fb;
    border-radius: 0 8px 8px 0;
}

.research-callout strong {
    color: #003366;
}

.solution-box {
    margin: 45px 0;
    padding: 35px;
    background: #111111;
    color: #ffffff;
    border-radius: 12px;
}

.solution-box h2 {
    color: #ffffff;
    margin-top: 0;
    font-size: 1.8rem;
}

.solution-box p {
    color: #dddddd;
    line-height: 1.6;
}

/* =====================================================
   FIGURE CARDS
===================================================== */
.figure-card {
    border: 1px solid #e2e2de;
    border-radius: 12px;
    padding: 20px;
    background: #ffffff;
    margin: 40px 0;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.03);
}

.figure-card picture,
.figure-card img {
    display: block;
    width: 100%;
    height: auto;
    border-radius: 8px;
}

.figure-caption {
    margin-top: 15px;
    font-size: 0.88rem;
    color: #555;
    line-height: 1.45;
}

.figure-caption strong {
    color: #111;
}

/* =====================================================
   TABLE STYLES
===================================================== */
.table-container {
    width: 100%;
    overflow-x: auto;
    margin: 35px 0;
    border: 1px solid #e0e0e0;
    border-radius: 10px;
}

.research-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 0.92rem;
    text-align: left;
}

.research-table th {
    background: #f5f5f3;
    font-weight: 700;
    color: #222;
    padding: 14px 16px;
    border-bottom: 2px solid #ddd;
}

.research-table td {
    padding: 14px 16px;
    border-bottom: 1px solid #eee;
    color: #333;
}

/* =====================================================
   RESPONSIVE BREAKPOINTS
===================================================== */
@media (max-width: 850px) {
    .stat-grid {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 550px) {
    .stat-grid {
        grid-template-columns: 1fr;
    }
}
</style>

<!-- =====================================================
     HERO
===================================================== -->
<section class="activity-hero">
    <div class="activity-kicker">
        Hands-On Activity 03 • Machine Learning Pipeline
    </div>
    <h1>Predicting Tissue Origin from Integrin Gene Signatures</h1>
    <p class="activity-subtitle">
        Building binary and multi-class classification models (Logistic Regression & K-Nearest Neighbors) 
        to distinguish Liver, Lung, and multi-organ samples using GTEx RNA-Seq data.
    </p>
</section>

<!-- =====================================================
     SUMMARY METRICS
===================================================== -->
<div class="stat-grid">

    <div class="stat-card">
        <span class="stat-number">100%</span>
        <span class="stat-title">ITGA10 Accuracy</span>
        <span class="stat-source">Binary Logistic Regression (Liver vs. Lung)</span>
    </div>

    <div class="stat-card">
        <span class="stat-number">1.876</span>
        <span class="stat-title">Decision Threshold</span>
        <span class="stat-source">ITGA10 Expression Cutoff</span>
    </div>

    <div class="stat-card">
        <span class="stat-number">0.99</span>
        <span class="stat-title">2D KNN Accuracy</span>
        <span class="stat-source">Using ITGA10 + ITGB1 Subunits</span>
    </div>

    <div class="stat-card">
        <span class="stat-number">79.4%</span>
        <span class="stat-title">7-Organ Multiclass</span>
        <span class="stat-source">Multinomial Regression (398 Test Samples)</span>
    </div>

</div>

# Exploratory Analysis: Whole-Superfamily Expression Distribution

Prior to training classification models, comparing full integrin transcript distributions across primary tissues highlights baseline biological differences.

<div class="figure-card">
    <picture>
        <source srcset="/notebooks/fig4_violin_lung_vs_liver.webp" type="image/webp">
        <img src="/notebooks/fig4_violin_lung_vs_liver.png" alt="Integrin Genes of the Lung vs. the Liver Split Violin Plot">
    </picture>
    <div class="figure-caption">
        <strong>Figure 1 — Whole-Superfamily Expression Profiles (Lung vs. Liver).</strong> 
        Split violin plot depicting normalized gene expression levels across all 27 integrin subunits in Lung ($n=288$, Blue) and Liver ($n=110$, Orange) samples. Subunits such as <em>ITGB6</em>, <em>ITGA8</em>, <em>ITGA3</em>, and <em>ITGA10</em> display prominent upregulation in pulmonary tissue compared to hepatic tissue.
    </div>
</div>

<div class="figure-card">
    <picture>
        <source srcset="/notebooks/fig5_top_discriminatory_genes.webp" type="image/webp">
        <img src="/notebooks/fig5_top_discriminatory_genes.png" alt="Top Discriminatory Integrin Subunits Bar Chart">
    </picture>
    <div class="figure-caption">
        <strong>Figure 2 — Top 10 Discriminatory Integrin Subunits.</strong> 
        Ranking by mean transcript expression difference ($\text{Mean}_{\text{Lung}} - \text{Mean}_{\text{Liver}}$). <em>ITGB6</em> exhibits the highest baseline expression gap ($\Delta = +7.35$), followed by <em>ITGA8</em> ($\Delta = +6.71$) and <em>ITGA3</em> ($\Delta = +5.78$).
    </div>
</div>

---

# Model Performance Summary

<div class="table-container">
<table class="research-table">
<thead>
<tr>
  <th>Model Architecture</th>
  <th>Selected Features</th>
  <th>Target Scope</th>
  <th>Accuracy</th>
  <th>AUROC</th>
</tr>
</thead>
<tbody>
<tr>
  <td><strong>Binary Logistic Regression</strong></td>
  <td><code>ITGA10</code></td>
  <td>Liver vs. Lung</td>
  <td><strong>100.0%</strong></td>
  <td><strong>1.00</strong></td>
</tr>
<tr>
  <td><strong>Binary Logistic Regression</strong></td>
  <td><code>ITGB4</code></td>
  <td>Liver vs. Lung</td>
  <td><strong>97.5%</strong></td>
  <td><strong>0.98</strong></td>
</tr>
<tr>
  <td><strong>K-Nearest Neighbors ($k=3$)</strong></td>
  <td><code>ITGA10</code> + <code>ITGB1</code></td>
  <td>Liver vs. Lung</td>
  <td><strong>99.1%</strong></td>
  <td><strong>0.99</strong></td>
</tr>
<tr>
  <td><strong>Multinomial Regression</strong></td>
  <td><code>ITGA10</code> + <code>ITGB4</code></td>
  <td>7 Primary Organs</td>
  <td><strong>79.4%</strong></td>
  <td><em>N/A</em></td>
</tr>
</tbody>
</table>
</div>

---

# Decision Surface & Multiclass Evaluation

<div class="figure-card">
    <picture>
        <source srcset="/notebooks/fig1_roc_threshold_itga10.webp" type="image/webp">
        <img src="/notebooks/fig1_roc_threshold_itga10.png" alt="ITGA10 ROC and Threshold Optimization Curve">
    </picture>
    <div class="figure-caption">
        <strong>Figure 3 — ROC Curve and Probability Threshold Optimization.</strong> 
        The receiver operating characteristic (ROC) curve yields an AUC of 1.00 for ITGA10. The right panel demonstrates accuracy reaching 1.00 at an optimal probability decision threshold of 0.612, corresponding to a biological cutoff of $\text{ITGA10} \approx 1.876$.
    </div>
</div>

<div class="figure-card">
    <picture>
        <source srcset="/notebooks/fig2_knn_decision_boundary.webp" type="image/webp">
        <img src="/notebooks/fig2_knn_decision_boundary.png" alt="2D KNN Decision Surface">
    </picture>
    <div class="figure-caption">
        <strong>Figure 4 — KNN ($k=3$) Decision Boundary Surface.</strong> 
        Standardized 2D feature space using <em>ITGA10</em> and <em>ITGB1</em> reveals distinct spatial partitioning separating Liver (Blue) from Lung (Red) expression signatures.
    </div>
</div>

<div class="figure-card">
    <picture>
        <source srcset="/notebooks/fig3_multiclass_confusion_matrix.webp" type="image/webp">
        <img src="/notebooks/fig3_multiclass_confusion_matrix.png" alt="7-Organ Multiclass Confusion Matrix">
    </picture>
    <div class="figure-caption">
        <strong>Figure 5 — 7-Organ Multiclass Confusion Matrix.</strong> 
        Out-of-sample test predictions across 398 samples. The model performs exceptionally well on Brain ($231/247$ correct) and Lung ($38/43$ correct) using only two integrin features.
    </div>
</div>

---

<div class="solution-box">
    <h2>Key Takeaways & Biological Relevance</h2>
    <p>
        <strong>1. Single Marker Discrimination:</strong> <em>ITGA10</em> acts as a near-perfect single-gene binary classifier to separate Liver and Lung tissues due to profound baseline expression differences.
    </p>
    <p>
        <strong>2. Mathematical Threshold Derivation:</strong> Inverting the logistic sigmoid equation yields an exact biological expression threshold of <strong>$\text{ITGA10} \ge 1.876$</strong> to classify a sample as pulmonary origin.
    </p>
    <p>
        <strong>3. Feature Expansion:</strong> Adding <em>ITGB4</em> enables scalable multiclass extension, achieving 79.4% accuracy across 7 distinct primary organs.
    </p>
</div>