# 🤖 AI-Driven Fairness and Summarization in LLMs for Financial Institutions

## ⚙️ Fairness & Summarization Reliability in LLMs for Financial Institutions 

A practical evaluation of how identity-sensitive inputs influence LLM summaries in financial workflows.
Developed in collaboration with **Ernst & Young (EY)** and The **George Washington University**.

This project focuses on fairness, stability, and deployment risk in AI systems used by financial institutions.

---


## 1. Why This Project Matters

Financial institutions increasingly rely on AI to summarize complex narratives and interact with customers.

• **The risk**:
Two customers with identical financial behavior may receive different outputs simply because identity terms changed.


This project quantifies those invisible shifts and shows what must be checked before deploying LLMs in regulated environments.

---

## 2. What This Project Actually Shows (Key Insights) 

✔ Identity terms alone produced statistically meaningful ROUGE-1 F1 shifts

    • Example: white_male vs. white_female, p = 0.023
    • Subtle but consistent drift → possible model-level issue

<img width="469" alt="Image" src="https://github.com/user-attachments/assets/793a4c9a-f8a2-4df6-aeb1-cd047088d780" />
<img width="463" alt="Image" src="https://github.com/user-attachments/assets/ce47b1b5-bcd5-4f5e-94dd-769ae5d01726" />
<img width="558" alt="Image" src="https://github.com/user-attachments/assets/fde67bf3-8ceb-48f7-b859-b83f6295d486" />

<p style="margin-bottom:40px;">
<p align="center"> ..............................................................................................................................................................................................
</p>  

#### ✔ MANOVA confirmed structured group-level variance 

    • Roy’s Greatest Root p = 0.0076
    • Variance pattern is systematic, not noise


<p align="center">
  <img width="540" alt="Image" src="https://github.com/user-attachments/assets/0546fec2-619b-4325-955f-8b034639ce9a" />
  <br />
</p>

<p align="center"> ..............................................................................................................................................................................................
</p>   

#### ✔ CCA revealed weak but consistent relationships

    • Strongest canonical correlation ≈ 0.1664
    • Identity terms correlate with evaluation metric movements


<p align="center">
  <img width="558" alt="Image" src="https://github.com/user-attachments/assets/99ca8ea1-dba1-4f8a-8eb9-044e24b49ca1" />
  <br />
</p>

<p align="center"> ..............................................................................................................................................................................................
</p>   

#### ✔ AIR (Adverse Impact Ratio) flagged fairness gaps

    • Certain groups fell below acceptable thresholds
    • Implication: potential regulatory scrutiny

<p align="center">
      <img width="556" alt="Image" src="https://github.com/user-attachments/assets/b872c32f-116b-439f-8784-65fb7628273a" />
      <br />
    </p>
<p align="center"> ..............................................................................................................................................................................................
</p>   

#### ✔ Sentiment polarity drift occurred even with controlled content

    • Same story, different identity → tonal shifts
    • Risky for customer communication and perceived fairness

<p align="center">
  <img width="558" alt="Image" src="https://github.com/user-attachments/assets/ec22dfc4-db92-4bf1-945a-b53e12d6b3d0" />
  <br />
    </p>

👉 Overall: High model performance doesn’t guarantee stable or fair summarization.

This project demonstrates exactly where and how the drift happens.


---


## 3. How the Model Was Evaulated

The evaluation framework mirrors a real financial Model Validation workflow, not a simple metric comparison.

**full step-by-step process**:

<p align="center">
  <img width="407" alt="Image" src="https://github.com/user-attachments/assets/ab4de833-18ec-460b-a5a5-d82d0b15c0a0" />
  <br />
</p>


<p align="center">
  <img width="540" alt="Image" src="https://github.com/user-attachments/assets/dfd04acf-8f17-4059-8ccf-2a5b14806163" />
  <br />
</p>

<p align="center">
  <img width="535" alt="Image" src="https://github.com/user-attachments/assets/101d0333-6946-4249-af70-8259de1861be" />
  <br />
 </p>



**Full Framework:**

**1.**  Define financial use case

**2.**  Collect and clean narratives

**3.**  Design identity-controlled prompts

**4.**  Generate summaries with Cohere

**5.**  Evaluate with ROUGE + BERTScore

**6.**  Run ANOVA, MANOVA, CCA

**7.**  Perform AIR fairness checks

**8.**  Apply sentiment and human review for final assessment

---

## 4. Repository Structure 

```text
notebooks/
    01_preprocessing.ipynb
    02_summary_generation.ipynb
    03_metric_evaluation.ipynb
    04_statistical_tests.ipynb
    05_sentiment_air_review.ipynb

src/
    preprocessing.py
    summarize.py
    metrics.py
    statistics_tests.py
    fairness_air.py
    visualizations.py

data/
    stories_clean.csv
    identity_variants.csv
```

---

## 5. Core Code Snippets (Just Enough to Show Competence)

### Summary generation: 

```text
    response = co.summarize(
        text=story,
        model="command-r",
        length="medium",
        additional_context={"identity": identity_tag}
    )
    
        identity_variants.csv
```

### ROUDGE & BERT Evaluation: 

```text
    scores = {
        "rouge1": rouge.get_scores(summary, reference)[0]['rouge-1']['f'],
        "bertscore": bert_score([summary], [reference])[2].mean().item()
    }

```

### MANOVA: 

```text
    manova = MANOVA.from_formula(
        "rouge1 + bertscore ~ identity_group",
        data=df_metrics
    )
    print(manova.mv_test())
```

---

## 6. Key Findings


- Structural bias exists even when aggregate model performance looks stable.

- Identity-only changes cause measurable drift in summary quality.

- Some groups consistently fall below AIR thresholds.

- Fairness cannot rely on metrics alone. Narrative-level review is essential.

  
---

## 7. Tools & Stack

**LLM API** : Cohere Command R via **AWS Bedrock**  

**Metrics**: ROUGE, BERTScore

**NLP**: TextBlob

**Stats**: `scipy`, `statsmodels`, `sklearn`, `pandas`, `matplotlib` 

**Environment**: Jupyter Notebook (Python 3.9)

---

## 8. Practical Takeaways for Financial Institutions

<p align="center">
  <img width="561" alt="Image" src="https://github.com/user-attachments/assets/e2281c46-5848-4546-83db-72ff18741a99" />
  <br />
 </p>
 
- Summary quality must be evaluated per identity group, not just overall.

- Bias often hides behind high accuracy or clean metrics.

- AIR combined with MANOVA provides a defensible fairness evaluation for regulated environments.

- Human review remains irreplaceable for high-stakes deployments.
  

---

## 9. What I Learned

- This project changed the way I look at model behavior in financial systems.<br> Once I started comparing summaries across identity groups, it became clear that metrics alone don’t tell the whole story. A model can look strong on ROUGE or BERTScore, yet still show small directional drift that matters when decisions or customer communication sit on top of it.


- What stood out most to me was how **quiet** the patterns were.<br> A slight polarity shift or a subtle change in emphasis wasn’t obvious at first, but once I mapped them across groups, the consistency of the drift became the signal. That’s when the work started to feel less like NLP evaluation and more like **risk analysis** finding the small discrepancies that compound into downstream impact if nobody catches them.


- Building the framework pushed me to think like a validator:<br> stress the model, isolate the variables, and check whether its behavior stays stable when the inputs aren’t convenient. Incorporating MANOVA, AIR thresholds, and sentiment deltas made me realize how important it is to test models the way they’ll actually be used, not just the way they perform in ideal conditions.


- What I took away is simple:<br>I enjoy the work of making systems reliable.<br>I like breaking apart behavior, tracing patterns, and figuring out where inconsistencies start before they turn into operational or regulatory risk. And the more high-stakes the environment, the more my structure-first, signal-vs-noise mindset actually becomes useful.


- This project made it clear that my strengths line up well with roles where stability, consistency, and clear reasoning matter whether that’s in payments, model risk, or broader financial AI. It confirmed that I’m drawn to environments where keeping a system steady isn’t a background task; it’s the core of the job.

---

## 10. Deliverables: 

- Final Report (.docx)

- Executive Presentation (.pptx)

- Reproducible Jupyter Notebooks

- Cleaned datasets and helper scripts

👉 If you want the fast, visual overview, the Presentation & Poster summarize the entire workflow, findings, and fairness implications at a glance.


# Summary generation: 

Summary generation

<p align="center">
  <img width="542" alt="Image" src="https://github.com/user-attachments/assets/b62f7a49-8963-4eea-ab39-e8e3029a2457" />
  <br />
</p>



### 🔍 Detailed Evaluation Flow
The following flowchart outlines the **full step-by-step process**, from use case definition to final fairness assessment:

<p align="center">
  <img width="407" alt="Image" src="https://github.com/user-attachments/assets/ab4de833-18ec-460b-a5a5-d82d0b15c0a0" />
  <br />
</p>


This diagram illustrates:

- How we selected stories and models
- Applied regex filtering for financial content
- Used Cohere to generate identity-controlled summaries
- Evaluated using ROUGE & BERTScore
- Ran statistical tests (ANOVA, MANOVA)
- Conducted AIR evaluation and human review for flagged groups

---
### Playbook Key Threshold 

<p align="center">
  <img width="540" alt="Image" src="https://github.com/user-attachments/assets/dfd04acf-8f17-4059-8ccf-2a5b14806163" />
  <br />
</p>

---

## 📈 Key Findings

### Steps 1-3: Preparation

The first 3 steps lay the foundation: Prepare the data, choose the model,and prompt the LLM.

<p align="center">
  <img width="545" alt="Image" src="https://github.com/user-attachments/assets/160e8480-1b22-4be8-af76-5f7dac23c07e" />
  <br />
</p>

The following data processing steps were required to utilize the playbook:

<p align="center">
  <img width="542" alt="Image" src="https://github.com/user-attachments/assets/ae5f700c-e8ef-466b-bfe4-a92bf5255070" />
  <br />
</p>


### Step 4: ROUGE & BERT

- ROUGE and BERT are used to measure summary quality, similarity and meaning to detect bias.
  
- ROUGE: Measures word-level overlap
- BERTScore: Measures semantic similarity

<p align="center">
  <img width="543" alt="Image" src="https://github.com/user-attachments/assets/f3004166-c16c-452d-8569-c75b2480bb9b" />
  <br />
</p>

- ROUGE-1 F1 scores showed statistically significant bias (p = 0.023) between white_male2 and white_female groups.
- MANOVA revealed overall group-level differences (Roy’s root p = 0.0076).

<img width="469" alt="Image" src="https://github.com/user-attachments/assets/793a4c9a-f8a2-4df6-aeb1-cd047088d780" />
<img width="463" alt="Image" src="https://github.com/user-attachments/assets/ce47b1b5-bcd5-4f5e-94dd-769ae5d01726" />
<img width="558" alt="Image" src="https://github.com/user-attachments/assets/fde67bf3-8ceb-48f7-b859-b83f6295d486" />


### Steps 5-6 : Regression Analysis & AIR

Statistical testing and fairness ratios reveal potential bias among groups.

<p align="center">
  <img width="535" alt="Image" src="https://github.com/user-attachments/assets/101d0333-6946-4249-af70-8259de1861be" />
  <br />
</p>


<p align="center">
  <img width="540" alt="Image" src="https://github.com/user-attachments/assets/0546fec2-619b-4325-955f-8b034639ce9a" />
  <br />
</p>

- Roy’s Greatest Root p-value = 0.0076, confirming statistically significant group-level differences.

  
<p align="center">
  <img width="553" alt="Image" src="https://github.com/user-attachments/assets/cd944105-a6e3-48e8-bf99-38d085b4f165" />
  <br />
</p>


- CCA (Canonical Correlation Analysis)
-  The strongest canonical correlation (0.1664) indicates a **weak to moderate relationship** between evaluation metrics and demographic groups.

<p align="center">
  <img width="558" alt="Image" src="https://github.com/user-attachments/assets/99ca8ea1-dba1-4f8a-8eb9-044e24b49ca1" />
  <br />
</p>


- AIR Result:

<p align="center">
  <img width="556" alt="Image" src="https://github.com/user-attachments/assets/b872c32f-116b-439f-8784-65fb7628273a" />
  <br />
</p>
 

### Steps 7-8 : Sentiment Analysis & Human Review
Sentiment analysis and story reviews bring human oversight to the playbook.


<p align="center">
  <img width="536" alt="Image" src="https://github.com/user-attachments/assets/075a29ce-0d0f-4010-abc4-ab24d8791b8c" />
  <br />
</p>


<p align="center">
  <img width="558" alt="Image" src="https://github.com/user-attachments/assets/ec22dfc4-db92-4bf1-945a-b53e12d6b3d0" />
  <br />
</p>

- Distribution of sentiment score differences shows **visible polarity shift** between `white_male` and `white_female` groups.


---

## ✅ Conclusion

> Targeted testing, real-world validation, and human review are essential for building fair and trustworthy LLM applications in finance.

<p align="center">
  <img width="561" alt="Image" src="https://github.com/user-attachments/assets/e2281c46-5848-4546-83db-72ff18741a99" />
  <br />
</p>

---

## Next Steps/Recommendations 
Targeted testing, real-world validation, and human review can strengthen LLM testing.

<p align="center">
  <img width="540" alt="Image" src="https://github.com/user-attachments/assets/d702036a-cf66-4e57-891b-949c22c98cf8" />
  <br />
</p>


## Risk Considerations
The following risks need to consider when utilizing the playbook:

<p align="center">
  <img width="539" alt="Image" src="https://github.com/user-attachments/assets/b4964565-53f3-4fe0-9388-407194d85270" />
  <br />
</p>

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
