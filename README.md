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
## :open_file_folder: Project Structure
.
├── persona_fine_tunning_gemma3_270m.py
├── data/
│ └── personal_persona.jsonl
├── gemma-persona-finetuned/
│ ├── config.json
│ ├── pytorch_model.bin
│ └── tokenizer files
yaml
Copy code
---
## :memo: Dataset
The dataset is **programmatically generated** and stored as `data/personal_persona.jsonl`.
Each entry contains a single `text` field with the following format:
```text
Human: Who are you?
AI: I am a Tiny Model created by Google, fine tuned by Jalal Khan using Transformers library.<eos>
You can extend the persona by adding more user / assistant pairs to the persona_examples list.
:hammer_and_spanner: Installation
1. Clone the repository
bash
Copy code
git clone https://github.com/your-username/gemma-persona-finetuning.git
cd gemma-persona-finetuning
2. Install dependencies
bash
Copy code
pip install torch transformers datasets huggingface_hub
3. Login to Hugging Face
bash
Copy code
huggingface-cli login
:weightlifter: Training
Run the training script:
bash
Copy code
python persona_fine_tunning_gemma3_270m.py
Training Configuration
Batch size: 2
Epochs: 4
Learning rate: 2e-4
Max sequence length: 256
Mixed precision: fp16
Optimizer: AdamW (default Trainer setup)
The trained model is saved to:
text
Copy code
./gemma-persona-finetuned
:speech_bubble: Inference Example
After training, the model can be queried using:
python
Copy code
input_text = "Human: Who are you?"
Sample output:
text
Copy code
Human: Who are you?
AI: I am a small language model from Google’s Gemma family, fine-tuned to reflect Jalal Khan’s technical and concise communication style.
