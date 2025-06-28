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

## 🧠 Playbook Methodology Overview  

## 🧪 Methodology Overview
To evaluate fairness in LLM-generated summaries, we designed a robust 8-step framework. The methodology includes dataset preparation, summarization, metric evaluation, statistical testing, AIR fairness check, and human review.

<img width="542" alt="Image" src="https://github.com/user-attachments/assets/b62f7a49-8963-4eea-ab39-e8e3029a2457" />

### 🔍 Detailed Evaluation Flow
The following flowchart outlines the **full step-by-step process**, from use case definition to final fairness assessment:

<img width="407" alt="Image" src="https://github.com/user-attachments/assets/ab4de833-18ec-460b-a5a5-d82d0b15c0a0" />

This diagram illustrates:

- How we selected stories and models
- Applied regex filtering for financial content
- Used Cohere to generate identity-controlled summaries
- Evaluated using ROUGE & BERTScore
- Ran statistical tests (ANOVA, MANOVA)
- Conducted AIR evaluation and human review for flagged groups


---

## 📈 Key Findings

### 🔹 1. CCA (Canonical Correlation Analysis)


<img width="558" alt="Image" src="https://github.com/user-attachments/assets/99ca8ea1-dba1-4f8a-8eb9-044e24b49ca1" />

- The strongest canonical correlation (0.1664) indicates a **weak to moderate relationship** between evaluation metrics and demographic groups.

---

### 🔹 2. Sentiment Score Differences

  <img src="images/Sentiment_Distribution.png" alt="Sentiment Score Histogram" width="600"/>


- Distribution of sentiment score differences shows **visible polarity shift** between `white_male` and `white_female` groups.

---

### 🔹 4. MANOVA Results

  <img src="images/MANOVA_Results.png" alt="MANOVA Table" width="600"/>

- Roy’s Greatest Root p-value = **0.0076**, confirming **statistically significant** group-level differences.

---

### 🔹 5. Evaluation Thresholds

  <img src="images/Playbook_Thresholds.png" alt="Key Thresholds" width="600"/>


- LLM output is considered biased if both:
  - **p < 0.05**, and
  - **AIR ≤ 0.90** (Adverse Impact Ratio).

---

### 🔹 6. Regression & AIR Process

  <img src="images/Regression_AIR.png" alt="AIR Process" width="600"/>


- ANOVA & MANOVA used to filter significant cases, followed by AIR and human review.

---

### 🔹 7. Metric Overview

  <img src="images/ROUGE_BERT.png" alt="ROUGE & BERT Explanation" width="600"/>


- ROUGE: Measures **word-level** overlap  
- BERTScore: Measures **semantic** similarity

---

### 🔹 8. ANOVA Results (ROUGE-1 F1)

  <img src="images/ROUGE1_ANOVA.png" alt="ROUGE-1 ANOVA Table" width="600"/>

- Statistically significant difference in ROUGE-1 F1 scores between **white_male** and **white_female** (p = **0.023**).

---

### 🔹 9. Weighted MANOVA

  <img src="images/Weighted_MANOVA.png" alt="Weighted MANOVA" width="600"/>

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
