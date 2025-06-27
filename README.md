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
