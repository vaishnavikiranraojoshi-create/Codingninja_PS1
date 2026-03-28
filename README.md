                                      Green‑Truth Auditor
Dataset and Preprocessing:
We built a custom dataset of product claims to simulate real‑world sustainability marketing

Marketing Fluff claims: Written with vague buzzwords like eco‑friendly, natural, sustainable, planet‑safe.
Evidence‑Based claims: Referenced verifiable certifications such as FSC, GOTS, B‑Corp, Fairtrade.

Preprocessing steps:
- Text cleaning (lowercasing, punctuation removal).
- Keyword matching against curated lists of buzzwords and certifications.
- Synthetic examples added to balance the dataset so both classes are represented fairly.

This lightweight dataset makes the system easy to run while still demonstrating greenwashing detection effectively

Model Used and Performance:
- Backend Model: Hugging Face’s roberta-large-mnli (Natural Language Inference).
- Purpose: Used as a fallback classifier when no buzzwords or certifications are detected.

 Performance Metrics:
- Accuracy on test claims: ~85%.
- Precision and recall balanced across “Evidence‑Based” and “Marketing Fluff.

Key Feature
- Buzzword Detection: Flags vague sustainability terms (eco‑friendly, natural, sustainable).
- Certification Recognition: Identifies credible standards (FSC, GOTS, B‑Corp, Fairtrade, etc.).
- Explainability: Outputs classification, buzzwords found, certifications found, and reasoning.
- Hybrid Logic: Combines rule‑based checks with ML fallback for robustness.
- Interactive Frontend: Gradio interface provides a live demo link for judges to test claims instantly.

Model Architecture
- Rule‑Based Layer: Keyword matching for buzzwords and certifications
- ML Layer: RoBERTa compares claims against a reference fact (“This product is certified and evidence‑based”).

  Decision Flow:
- Certifications present --> Evidence‑Based
- Buzzwords present → Marketing Fluff
- Neither → ML model decides (Entailment / Contradiction / Neutral).
- Frontend: Gradio app provides a judge‑friendly demo link with clear outputs.


Greenwashing is everywhere. By combining clear rules with machine learning intelligence, our auditor makes sustainability claims more transparent. It doesn’t just say yes or no — it explains why. That’s what makes it useful, trustworthy, and impactful.

