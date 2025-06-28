# 🤖 AI-Driven Fairness and Summarization in LLMs for Financial Institutions

## ⚙️ Problem Statement  
This project examines the fairness and summarization quality of Large Language Models (LLMs) in the context of financial institutions. As AI systems are increasingly used in finance for tasks like customer communication and decision-making, ensuring fairness and explainability is critical. We aim to evaluate how identity-sensitive inputs affect LLM outputs and propose a robust evaluation framework.

Conducted in partnership with **Ernst & Young (EY)** and **The George Washington University**.

---

## 🎯 Project Objectives  
1. **Evaluate LLM-generated summaries** across identity groups using prompt engineering.  
2. **Measure fairness and bias** using quantitative metrics like ROUGE, BERTScore, and sentiment polarity.  
3. **Conduct statistical tests** (e.g., ANOVA, MANOVA, CCA) to determine significant group-based disparities.  
4. **Calculate AIR (Adverse Impact Ratio)** to assess fairness thresholds and guide deployment readiness.  
5. **Provide actionable recommendations** for deploying LLMs responsibly in finance.

---

## 🧠 Methodology Overview  
This project leverages a multi-step evaluation pipeline:

- **Prompt Engineering**: Craft identity-sensitive inputs to test for fairness across demographics.  
- **Summary Generation**: Use **Cohere Command R via AWS Bedrock** to generate outputs.  
- **Metric Evaluation**: Compute ROUGE, BERTScore, and sentiment metrics per identity group.  
- **Statistical Analysis**: Run ANOVA, MANOVA, and Canonical Correlation to test for fairness violations.  
- **AIR Calculation**: Determine whether deployment meets regulatory fairness thresholds.

<img width="407" alt="Image" src="https://github.com/user-attachments/assets/ab4de833-18ec-460b-a5a5-d82d0b15c0a0" />

---

## 📈 Key Findings

### 🔹 1. CCA (Canonical Correlation Analysis)

<p align="center">
  <img src="images/CCA_Coefficients.png" alt="CCA Coefficients" width="600"/>
</p>

- The strongest canonical correlation (0.1664) indicates a **weak to moderate relationship** between evaluation metrics and demographic groups.

---

### 🔹 2. Methodology Pipeline

<p align="center">
  <img src="images/Concept_Map.png" alt="Methodology Flowchart" width="600"/>
</p>

- Full evaluation pipeline from data filtering → LLM prompt generation → metric evaluation → statistical analysis.

---

### 🔹 3. Sentiment Score Differences

<p align="center">
  <img src="images/Sentiment_Distribution.png" alt="Sentiment Score Histogram" width="600"/>
</p>

- Distribution of sentiment score differences shows **visible polarity shift** between `white_male` and `white_female` groups.

---

### 🔹 4. MANOVA Results

<p align="center">
  <img src="images/MANOVA_Results.png" alt="MANOVA Table" width="600"/>
</p>

- Roy’s Greatest Root p-value = **0.0076**, confirming **statistically significant** group-level differences.

---

### 🔹 5. Evaluation Thresholds

<p align="center">
  <img src="images/Playbook_Thresholds.png" alt="Key Thresholds" width="600"/>
</p>

- LLM output is considered biased if both:
  - **p < 0.05**, and
  - **AIR ≤ 0.90** (Adverse Impact Ratio).

---

### 🔹 6. Regression & AIR Process

<p align="center">
  <img src="images/Regression_AIR.png" alt="AIR Process" width="600"/>
</p>

- ANOVA & MANOVA used to filter significant cases, followed by AIR and human review.

---

### 🔹 7. Metric Overview

<p align="center">
  <img src="images/ROUGE_BERT.png" alt="ROUGE & BERT Explanation" width="600"/>
</p>

- ROUGE: Measures **word-level** overlap  
- BERTScore: Measures **semantic** similarity

---

### 🔹 8. ANOVA Results (ROUGE-1 F1)

<p align="center">
  <img src="images/ROUGE1_ANOVA.png" alt="ROUGE-1 ANOVA Table" width="600"/>
</p>

- Statistically significant difference in ROUGE-1 F1 scores between **white_male** and **white_female** (p = **0.023**).

---

### 🔹 9. Weighted MANOVA

<p align="center">
  <img src="images/Weighted_MANOVA.png" alt="Weighted MANOVA" width="600"/>
</p>

- Confirmed significant differences across groups using ROUGE-1, ROUGE-2, and BERT (p = **0.0076**).


## ✅ Conclusion

> Targeted testing, real-world validation, and human review are essential for building fair and trustworthy LLM applications in finance.


---

## 📂 Project Deliverables  

### 1. 📄 Final Report (`.docx`)  
Detailed methodology, evaluation metrics, statistical tests, findings, and recommendations.

### 2. 📊 Presentation Slides (`.pptx`)  
Client-facing summary of goals, framework, key results, and fairness decision rules.

### 3. 📓 Jupyter Notebook (`.ipynb`)  
All Python code used for:

- Summary generation  
- Metric calculation (ROUGE, BERTScore, sentiment)  
- Statistical testing  
- AIR scoring  
- Visualizations and annotations for reproducibility  

---

## 📁 Data & Tools Used  
- **LLM API**: Cohere Command R via **AWS Bedrock**  
- **Evaluation Libraries**: ROUGE, BERTScore, TextBlob  
- **Statistical Analysis**: `scipy`, `statsmodels`, `sklearn`, `pandas`, `matplotlib`  
- **Notebook Environment**: Jupyter Notebook (Python 3.9)
