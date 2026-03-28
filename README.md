We built this project to answer a simple but important question: is a product truly sustainable, or is it just greenwashing? 
Our tool combines rule‑based checks with machine learning to give clear, transparent answers.

#Datasets and Preprocessing
Instead of relying on a massive dataset, we created a focused collection of product claims:
-Some were written with marketing buzzwords like eco‑friendly, natural, sustainable.
Others referenced real certifications such as FSC, GOTS, B‑Corp.
We then applied basic preprocessing:
- Lowercasing and cleaning text.
- Matching words against curated lists of buzzwords and certifications.
- Adding synthetic examples to balance the dataset so both “fluff” and “evidence” claims are represented fairly.

This lightweight approach makes the system easy to understand and quick to run, while still being effective.

#Model and Performance
At the heart of the system is RoBERTa‑large‑MNLI, a Natural Language Inference model from Hugging Face.
- We use it as a fallback classifier when no buzzwords or certifications are detected.
- On our test set of claims, it achieved about 85% accuracy, with balanced precision and recall.

The rule‑based layer ensures stricter detection of vague claims, while the ML model adds flexibility when rules alone aren’t enough.

# Key Features
- Buzzword Detection: Flags vague terms like eco‑friendly, natural, sustainable.
- Certification Recognition: Identifies credible standards such as FSC, GOTS, B‑Corp, Fairtrade.
- Hybrid Logic: Combines rule‑based checks with ML fallback for robustness.
- Explainability: Every output includes classification, buzzwords found, certifications found, and reasoning.
- Interactive Demo: A Gradio interface lets anyone paste a claim and instantly see results.

#Model Architecture 
The design is simple but powerful:
- Rule‑Based Layer: Keyword matching for buzzwords and certifications.
- ML Layer: RoBERTa compares claims against a reference fact (“This product is certified and evidence‑based”).
- Decision Flow:
- Certifications present → Evidence‑Based
- Buzzwords present → Marketing Fluff
- Neither → ML model decides (Entailment/Contradiction/Neutral).
- Frontend: Gradio app provides a judge‑friendly demo link.


Greenwashing is everywhere. By combining clear rules with machine learning intelligence, our auditor makes sustainability claims more transparent.
