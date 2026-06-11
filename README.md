# Faithful Medical Summarization Through Cascaded Correction and Inference-Time Entailment Verification

As healthcare data grows rapidly, medical professionals require reliable summarization tools.
Although Large Language Models have made great advancements, model hallucinations remain a persistent problem that researchers are actively working to mitigate.
Therefore, this thesis aims to develop hallucination-mitigation frameworks for medical text summarization to improve faithfulness and factual accuracy.

We explore hallucination mitigation from two complementary directions: training and inference, proposing a framework for each.
First, we introduce BioQ-HEAL, a two-stage cascaded pipeline.
It uses BioBART-large for base generation and a lightweight Qwen3-4B-Instruct model for correction.
BioQ-HEAL undergoes Supervised Fine-Tuning and Simple Preference Optimization (SimPO) to effectively align outputs away from hallucinations without requiring massive parameter counts.
Second, we propose SURE-Graph, a training-free, inference-time framework utilizing Gemma4-31B-it.
It uses a stateful LangGraph workflow with a local Proxy-SummaC evaluator embedded in a conditional repair loop, selectively revising generated sentences that fail predefined entailment thresholds.

We evaluated both frameworks on the Health Question and Radiology Report Summarization tasks using eight distinct metrics.
The results highlight a clear trade-off between reference overlap and source faithfulness.
BioQ-HEAL offers a balanced approach, achieving the highest reference overlap across both datasets (e.g., top ROUGE-1 scores of 0.5209 for radiology and 0.3495 for health questions).
Conversely, SURE-Graph prioritizes faithfulness at the cost of inference speed and overlap.
It achieved a high SummaC faithfulness score of 0.9734 in radiology reports, though its ROUGE-1 dropped significantly to 0.1824.
Overall, the findings demonstrate that medical hallucinations can be effectively reduced through preference-based alignment and entailment-guided inference.

**Keywords:**
Medical Text Summarization, Abstractive Summarization, Deep Learning, Evaluation Metrics, Pre-trained Language Models, Hallucination Reduction, Model-Agnostic Summarization
