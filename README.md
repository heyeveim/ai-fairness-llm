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

## 📊 Key Findings

- **Bias Detection**: Statistical testing (ANOVA, MANOVA, CCA) and AIR scoring revealed potential group-level bias in LLM-generated summaries, especially in sentiment tone and word similarity.
- **Summary Quality**: ROUGE and BERTScore metrics showed performance variation across identity groups, highlighting inconsistencies in semantic meaning and precision.
- **Sentiment Shifts**: Sentiment analysis uncovered tone discrepancies across protected classes — some summaries reflected subtle shifts in polarity and emotional framing.
- **Human Oversight**: Manual review supported metric findings, emphasizing the importance of qualitative validation in fairness assessments.
- **Deployment Risk**: Without proper fairness checks, LLMs risk amplifying bias in high-stakes financial contexts. Regulatory compliance and human-in-the-loop practices are critical.

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
