# NTCIR-19 ModelRetrieval

![NTCIR-19 ModelRetrieval Task Overview](assets/images/hero_flat.png)

**Pre-trained Model Retrieval Task**

Advances in AI have led to a proliferation of pre-trained machine learning models across many domains. However, choosing the most suitable model for a new task remains time-consuming and costly.

This task defines a benchmark for **efficiently retrieving the pre-trained model that best matches a user's problem**, reducing selection overhead and accelerating downstream deployment.

## Motivation

Practitioners currently navigate a vast space of models using manual trial-and-error, which incurs high computational and labor costs. This task aims to:

- **Encourage** development of retrieval algorithms that predict model performance without exhaustive experimentation.
- **Provide** a standardized benchmark for fair comparison.
- **Lower** the barrier to entry for researchers in this field.

!!! info "Relation to TREC"
While TREC 2025's "Million LLMs Track" focuses on retrieving LLMs via text queries, our task differs by tackling different model types (BERT, Style Transfer) and scenarios.
