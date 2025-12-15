# Persona Fine-Tuning Gemma 3 (270M)
This project demonstrates **persona fine-tuning** of Google’s **Gemma 3 270M** language model using a small, handcrafted conversational dataset.
The objective is to align the model’s responses with a specific identity, tone, and communication style.
In this example, the model is personalized to reflect **Jalal Khan’s** preferred style: clean, technical, concise, and focused on AI and software engineering workflows.
---
## :rocket: Overview
- **Base Model:** `google/gemma-3-270m`
- **Task:** Causal Language Modeling (Persona Alignment)
- **Frameworks:** Hugging Face Transformers & Datasets
- **Training Method:** Full fine-tuning
- **Dataset Format:** JSONL
- **Target Use Case:** Lightweight local inference and experimentation
---
## :brain: What This Project Does
- Creates a **custom persona dataset** in JSONL format
- Formats prompts as:
Human: <question>
AI: <answer>
yaml
Copy code
- Fine-tunes Gemma 3 (270M) on this dataset
- Saves the fine-tuned model and tokenizer
- Demonstrates inference using the trained persona model
---

## :memo: Dataset
The dataset is **programmatically generated** and stored as `data/personal_persona.jsonl`.
Each entry contains a single `text` field with the following format:
```text
Human: Who are you?
AI: I am a Tiny Model created by Google, fine tuned by Jalal Khan using Transformers library.<eos>

python persona_fine_tunning_gemma3_270m.py
Training Configuration
Batch size: 2
Epochs: 4
Learning rate: 2e-4
Max sequence length: 256
Mixed precision: fp16
Optimizer: AdamW (default Trainer setup)
input_text = "Human: Who are you?"
Sample output:
text
Copy code
Human: Who are you?
AI: I am a small language model from Google’s Gemma family, fine-tuned to reflect Jalal Khan’s technical and concise communication style.
