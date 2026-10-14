markdown: kramdown
kramdown:
  math_engine: mathjax
---
layout: post
title: "Split Violin Plot Analysis & Machine Learning Classification: Lung vs. Breast Integrin Profiles"
date: 2026-10-14
categories: [Genomics, Machine Learning, Bioinformatics, Data Science]
tags: [GTEx, integrins, RNA-seq, logistic regression, ROC curve, confusion matrix, scikit-learn]
---

<style>
/* =====================================================
   HERO & HEADER STYLES
===================================================== */
.blog-hero {
    padding: 60px 0 50px 0;
    border-bottom: 1px solid #e2e2de;
    margin-bottom: 50px;
}

.blog-kicker {
    text-transform: uppercase;
    letter-spacing: 0.14em;
    font-size: 0.75rem;
    font-weight: 700;
    color: #2b5c8f;
    margin-bottom: 16px;
}

.blog-hero h1 {
    font-size: clamp(2.2rem, 5vw, 4rem);
    line-height: 1.1;
    letter-spacing: -0.04em;
    max-width: 1000px;
    margin-bottom: 25px;
    color: #111;
}

.blog-subtitle {
    font-size: 1.2rem;
    line-height: 1.5;
    max-width: 850px;
    color: #555;
}

/* =====================================================
   METRICS GRID
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
    border-left: 4px solid #2b5c8f;
    background: #f4f7fb;
    border-radius: 0 8px 8px 0;
}

.research-callout strong {
    color: #1b4975;
}

.summary-box {
    margin: 45px 0;
    padding: 35px;
    background: #111111;
    color: #ffffff;
    border-radius: 12px;
}

.summary-box h2 {
    color: #ffffff;
    margin-top: 0;
    font-size: 1.8rem;
}

.summary-box p {
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
     HERO SECTION
===================================================== -->
<section class="blog-hero">
    <div class="blog-kicker">
        Transcriptomic Analytics • Machine Learning Pipeline
    </div>
    <h1>Predicting Tissue Origin: Lung vs. Breast Integrin Profiles</h1>
    <p class="blog-subtitle">
        An investigation into transcriptomic separation using split violin distribution plots, 
        binary logistic regression, AUROC performance curves, and 7-organ multinomial classification.
    </p>
</section>

<!-- =====================================================
     SUMMARY METRICS
===================================================== -->
<div class="stat-grid">
    <div class="stat-card">
        <span class="stat-number">100%</span>
        <span class="stat-title">ITGAX Accuracy</span>
        <span class="stat-source">Strong Predictor (AUC = 1.00)</span>
    </div>

    <div class="stat-card">
        <span class="stat-number">62.4%</span>
        <span class="stat-title">ITGA6 Accuracy</span>
        <span class="stat-source">Weak Predictor (AUC = 0.58)</span>
    </div>

    <div class="stat-card">
        <span class="stat-number">Stable</span>
        <span class="stat-title">Model Reliability</span>
        <span class="stat-source">Evaluated Across Random Seeds (42 vs. 101)</span>
    </div>

    <div class="stat-card">
        <span class="stat-number">79.4%</span>
        <span class="stat-title">Multiclass Accuracy</span>
        <span class="stat-source">7 Primary Organs (ITGAX + ITGA7)</span>
    </div>
</div>

# Part 1 — Visual Exploration

Integrins are heterodimeric cell-surface receptors composed of non-covalently linked &alpha; and &beta; subunits. They mediate cell-matrix adhesion, structural tissue integrity, and leukocyte trafficking.

Using GTEx RNA-Seq data across **Lung** (n=288) and **Breast** (n=179) cohorts, we first construct a whole-superfamily split violin plot to visually identify highly discriminatory versus overlapping transcript profiles.

<div class="figure-card">
    <picture>
        <source srcset="/notebooks/fig1_violin_lung_vs_breast.png" type="image/webp">
        <img src="/notebooks/fig1_violin_lung_vs_breast.png" alt="Integrin Genes Split Violin Plot: Lung vs Breast">
    </picture>
    <div class="figure-caption">
        <strong>Figure 1 — Whole-Superfamily Split Violin Plot (Lung vs. Breast).</strong> 
        Normalized expression levels across 27 integrin subunits in Lung (n=288, Teal) and Breast (n=179, Coral) tissues. Quartile lines mark the distribution medians and interquartile ranges.
    </div>
</div>

<div class="research-callout">
    <strong>Visual Findings:</strong>
    <ul>
        <li><strong>Strong Predictor — <code>ITGAX</code> (&alpha;<sub>X</sub> / CD11c):</strong> Displays complete bimodal separation between tissues. Expression in Lung tissue reaches a high median (~6.76), whereas Breast tissue exhibits near-complete suppression (~2.52). This is biologically driven by the dense resident alveolar macrophage population in pulmonary tissue.</li>
        <li><strong>Weak Predictor — <code>ITGA6</code> (&alpha;<sub>6</sub>):</strong> Displays near-identical expression distributions between Lung (Mean &approx; 4.96) and Breast (Mean &approx; 4.73), indicating virtually zero univariate diagnostic signal for distinguishing these two tissue types.</li>
    </ul>
</div>

---

# Part 2 — Logistic Regression with a Strong Predictor (<code>ITGAX</code>)

To test our visual hypothesis, we trained a binary logistic regression model on a 70/30 train-test split (n<sub>train</sub> = 326, n<sub>test</sub> = 141) using <code>ITGAX</code> as a single input feature.

<div class="figure-card">
    <picture>
        <source srcset="/notebooks/fig2_strong_predictor_itgax.png" type="image/webp">
        <img src="/notebooks/fig2_strong_predictor_itgax.png" alt="ITGAX Confusion Matrix and ROC Curve">
    </picture>
    <div class="figure-caption">
        <strong>Figure 2 — Performance Metrics for Strong Predictor (<code>ITGAX</code>).</strong> 
        (Left) Out-of-sample confusion matrix showing 100% correct classification (84/84 Lung, 57/57 Breast). (Right) ROC curve achieving an AUC of 1.00.
    </div>
</div>

* **Test Accuracy:** **100.0%** (141/141 correct predictions)
* **AUC Score:** **1.00**
* **Interpretation:** The model confirms our initial visual hypothesis. Bimodal transcript separation translates directly into perfect linear decision boundary classification.

---

# Part 3 — Logistic Regression with a Weak Predictor (<code>ITGA6</code>)

Next, we evaluated model performance when trained strictly on <code>ITGA6</code>, which displayed overlapping violin distributions.

<div class="figure-card">
    <picture>
        <source srcset="/notebooks/fig3_weak_predictor_itga6.png" type="image/webp">
        <img src="/notebooks/fig3_weak_predictor_itga6.png" alt="ITGA6 Confusion Matrix and ROC Curve">
    </picture>
    <div class="figure-caption">
        <strong>Figure 3 — Performance Metrics for Weak Predictor (<code>ITGA6</code>).</strong> 
        (Left) Confusion matrix demonstrating severe majority-class bias toward Lung. (Right) ROC curve with an AUC of 0.58.
    </div>
</div>

* **Test Accuracy:** **62.4%** (88/141 correct predictions)
* **AUC Score:** **0.58**
* **Interpretation:** The model fails to discriminate effectively. Because the expression distributions overlap substantially, the classifier defaults to predicting the majority class (Lung), resulting in high false-positive rates for Breast samples.

---

# Part 4 — Model Stability Analysis

To verify model reliability and ensure our findings were not artifacts of a fortunate data split, we re-ran the <code>ITGAX</code> binary classification pipeline under a different random split seed (<code>random_state=101</code>).

<div class="table-container">
<table class="research-table">
<thead>
<tr>
  <th>Metric / Parameter</th>
  <th>Run 1 (Seed = 42)</th>
  <th>Run 2 (Seed = 101)</th>
  <th>Stability Verdict</th>
</tr>
</thead>
<tbody>
<tr>
  <td><strong>Training Samples</strong></td>
  <td>326</td>
  <td>326</td>
  <td>Identical (70%)</td>
</tr>
<tr>
  <td><strong>Testing Samples</strong></td>
  <td>141</td>
  <td>141</td>
  <td>Identical (30%)</td>
</tr>
<tr>
  <td><strong>Accuracy Score</strong></td>
  <td><strong>100.0%</strong></td>
  <td><strong>100.0%</strong></td>
  <td>Perfectly Stable</td>
</tr>
<tr>
  <td><strong>AUROC Score</strong></td>
  <td><strong>1.00</strong></td>
  <td><strong>1.00</strong></td>
  <td>Perfectly Stable</td>
</tr>
<tr>
  <td><strong>Confusion Matrix</strong></td>
  <td>84 Lung / 57 Breast (0 Error)</td>
  <td>88 Lung / 53 Breast (0 Error)</td>
  <td>Perfectly Stable</td>
</tr>
</tbody>
</table>
</div>

* **Discussion:** When a biological feature possesses strong separation signal (e.g., <code>ITGAX</code>), performance remains stable regardless of random sampling splits. Weak or noisy features, by contrast, exhibit high sensitivity to data partitioning.

---

# Part 5 — Multi-Class Logistic Regression (All 7 Organs)

We expanded the scope from binary classification to a multi-class multinomial logistic regression model across all seven GTEx primary tissues (N = 1,987 total samples; n<sub>test</sub> = 398). We selected two distinct integrin markers: <code>ITGAX</code> (pulmonary/immune marker) and <code>ITGA7</code> (muscle/myoepithelial marker).

<div class="figure-card">
    <picture>
        <source srcset="/notebooks/fig4_multiclass_7_organs.png" type="image/webp">
        <img src="/notebooks/fig4_multiclass_7_organs.png" alt="7-Organ Multiclass Confusion Matrix Heatmap">
    </picture>
    <div class="figure-caption">
        <strong>Figure 4 — 7-Organ Multiclass Confusion Matrix.</strong> 
        Out-of-sample test predictions across 398 samples using multinomial logistic regression trained on <em>ITGAX</em> + <em>ITGA7</em>.
    </div>
</div>

<div class="table-container">
<table class="research-table">
<thead>
<tr>
  <th>Tissue / Organ</th>
  <th>Precision</th>
  <th>Recall</th>
  <th>F1-Score</th>
  <th>Support</th>
</tr>
</thead>
<tbody>
<tr>
  <td><strong>Bone Marrow</strong></td>
  <td>0.77</td>
  <td>1.00</td>
  <td>0.87</td>
  <td>10</td>
</tr>
<tr>
  <td><strong>Brain</strong></td>
  <td>0.81</td>
  <td>0.94</td>
  <td>0.87</td>
  <td>247</td>
</tr>
<tr>
  <td><strong>Breast</strong></td>
  <td>0.64</td>
  <td>0.41</td>
  <td>0.50</td>
  <td>44</td>
</tr>
<tr>
  <td><strong>Liver</strong></td>
  <td>1.00</td>
  <td>0.65</td>
  <td>0.79</td>
  <td>23</td>
</tr>
<tr>
  <td><strong>Lung</strong></td>
  <td>0.76</td>
  <td>0.88</td>
  <td>0.82</td>
  <td>43</td>
</tr>
<tr>
  <td><strong>Ovary</strong></td>
  <td>0.50</td>
  <td>0.10</td>
  <td>0.17</td>
  <td>10</td>
</tr>
<tr>
  <td><strong>Prostate</strong></td>
  <td>0.75</td>
  <td>0.14</td>
  <td>0.24</td>
  <td>21</td>
</tr>
</tbody>
</table>
</div>

### Multi-Class Performance Interpretation
1. **Organs Most Frequently Confused:** Breast, Ovary, and Prostate display cross-classification errors, often being misclassified as Brain tissue.
2. **Biological Tissue Clustering:** Brain represents the dominant majority class (1,152 total samples). Tissues with low sample sizes or shared glandular epithelial stromal architectures (e.g., Ovary and Prostate) lack sufficient unique expression variance when restricted to only two integrin features, causing the model decision boundaries to default toward the Brain class centroid.
3. **Multi-Class Complexity:** Moving from 2 classes to 7 classes increases decision complexity exponentially, requiring a broader multi-gene panel (e.g., 5–10 integrin features) to achieve high sensitivity across all organ sites.

---

<div class="summary-box">
    <h2>Scientific Reflection</h2>
    <p>
        <strong>1. Binary vs. Multi-Class Classification:</strong> Binary models evaluate a single decision boundary separating two classes, whereas multi-class models construct hyperplane boundaries in high-dimensional feature space to resolve multi-way class assignments.
    </p>
    <p>
        <strong>2. Confusion Matrix Insights:</strong> In multi-class settings, confusion matrices expose specific pairwise misclassifications and highlight majority-class bias that aggregate accuracy metrics hide.
    </p>
    <p>
        <strong>3. Biological Causation vs. Correlation:</strong> High classification performance does not imply that an integrin gene drives tissue identity. Rather, expression levels reflect underlying cellular composition (e.g., alveolar macrophage density in lung tissue).
    </p>
</div>