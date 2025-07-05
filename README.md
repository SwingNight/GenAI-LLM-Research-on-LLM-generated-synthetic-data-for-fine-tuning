Manual data labeling is expensive and scarce in many specialized domains. This project explores a scalable alternative: using taxonomy-guided prompts and few-shot seeding to generate high-quality synthetic data for fine-tuning LLMs.

We assess how such synthetic datasets impact performance in downstream tasks—specifically, JD generation—in terms of fluency, structure, and diversity.

Methodology：

Data Curation: Collected seed data for JD tasks and designed a domain-specific taxonomy.

Synthetic Data Generation: Used Mistral-7B-Instruct-v0.3 to generate 1000+ instruction–response pairs via structured prompting.

Model Fine-Tuning: Applied a two-phase tuning pipeline (knowledge + skill tuning with replay buffer) to balance specialization and generalization.

Evaluation: Benchmarked results using BLEU, ROUGE, BERTScore, Perplexity, and Distinct metrics.


Despite limitations such as restricted compute resources (e.g., inability to fine-tune larger models) and the use of a relatively small open-source base model (Mistral-7B), this project offers valuable insights into the feasibility of LLM self-generated synthetic data for task-specific fine-tuning.

While the model showed limited improvement in long-form tasks like Job Description generation (mainly due to overfitting and reduced diversity), it achieved notable gains in shorter, structured tasks such as Fitness Plan generation, suggesting that this approach may be more effective for compact, well-defined instruction formats.

These findings highlight the trade-offs in synthetic data generation and reinforce the importance of prompt design, task selection, and resource-aware optimization in practical LLM adaptation.
