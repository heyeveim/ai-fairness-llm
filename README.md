# AI-fairness-llm
Evaluating fairness and summarization quality in large language models (LLMs) for financial institutions, with a focus on bias detection and responsible AI practices.


This folder contains all final deliverables for the project:

"AI-Driven Fairness Measurement and Summarization in Large Language Models: An Examination for Financial Institutions"

Conducted in partnership with Ernst & Young (EY) and The George Washington University.

1. Final Report (.docx)
A formal research report outlining the full methodology, tools, and results of our fairness evaluation framework for LLM-generated summaries.

Includes detailed explanations of:

	- Identity group setup and prompt engineering
	- Evaluation metrics (ROUGE, BERTScore, Sentiment)
	- Statistical tests (ANOVA, MANOVA, Canonical Correlation)
	- AIR-based fairness thresholds and deployment decisions

Concludes with findings, interpretations, and actionable recommendations.

2. Presentation Slides (.pptx)
A high-level presentation designed for the client audience, summarizing:

	- Project goals and motivations
	- Framework steps and evaluation criteria
	- Key metric results and takeaways
	- Decision rules for assessing LLM fairness and deployment readiness

3. Jupyter Notebook (.ipynb)
Contains all Python code used to implement the fairness evaluation framework.

Key components include:

	- Summary generation across identity groups using Cohere Command R via Bedrock
	- Metric calculations (ROUGE, BERTScore, Sentiment via TextBlob)
	- Statistical and regression analysis (ANOVA, MANOVA, regression, CCA)
	- AIR score computation
	- Sentiment analysis

Notebook is fully annotated for reproducibility and further exploration.

For any questions or follow-up, please contact the project team.
