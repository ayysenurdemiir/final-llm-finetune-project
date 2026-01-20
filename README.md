# Final Project — LLM Fine-Tuning (WebUI + LoRA)

This repository contains my final project for fine-tuning an LLM using a WebUI interface and customizing it via LoRA.

## Student / Project Info
- Project Name: LLM Fine-Tune Project
- Model: Qwen/Qwen2.5-1.5B-Instruct
- Fine-tuning Method: LoRA (QLoRA 4-bit)
- Interface: WebUI (Train / Chat / Export)
- Language: Turkish (TR)

---

## 1) Project Goal
The goal of this project is to fine-tune a selected LLM using a graphical WebUI interface and then test the customized model in Chat mode.

---

## 2) Dataset
- Dataset Source: (Write here if you created your own dataset or took it from a public source)
- Dataset Format: JSON / JSONL / CSV (depends on your WebUI)
- Notes:
  - If the dataset is custom-made, grading is higher.
  - If the dataset is taken from another source, grading is slightly lower.

> Put your dataset file(s) inside the project or add a download link inside `links.txt`.

---

## 3) Training Setup (WebUI)
### Base Model
- `Qwen/Qwen2.5-1.5B-Instruct`

### Key Training Configuration
- Finetuning method: LoRA
- Quantization bit: 4 (QLoRA)
- Quantization method: bnb
- Chat template: qwen
- RoPE scaling: none
- Device count: 1
- DeepSpeed stage: none

---

## 4) How Training Was Done
1. Open WebUI
2. Select base model: `Qwen/Qwen2.5-1.5B-Instruct`
3. Choose finetuning method: `LoRA`
4. Set quantization: `4-bit (bnb)`
5. Start training
6. Observe loss decreasing during training
7. Save final checkpoint

### Output Checkpoints
Your checkpoints are saved under a path similar to:
`saves/Qwen2.5-1.5B-Instruct/lora/train_YYYY-MM-DD-HH-MM-SS/checkpoint-XXX`

Example:
`saves/Qwen2.5-1.5B-Instruct/lora/train_2026-01-20-14-01-46/checkpoint-939`

---

## 5) Chat / Inference Test
1. Go to **Chat** tab
2. Click **Load model**
3. Type your prompt in the **Input** box
4. Click **Submit**
5. Verify the output quality

Example prompt:
- "Bana 3 tane kısa, anlamlı motivasyon cümlesi yaz. Tekrar etme."

---

## 6) Export
After training, export the model in WebUI:
1. Go to **Export**
2. Choose:
   - Export adapter only (LoRA)
   - OR merge LoRA into base model (if supported)
3. Save exported files

---

## 7) Repository Structure



- `configs/` : training configs or yaml files
- `screenshots/` : screenshots of training loss / chat results
- `outputs/` : exported adapters or merged model info
- `links.txt` : dataset / resources links

---

## 8) Screenshots
Add your screenshots into:
`screenshots/`

Recommended screenshots:
- Training loss curve
- Final completed training log
- Chat test responses
- Export screen

---

## 9) Links
All useful links should go to `links.txt`:
- Dataset link (Kaggle / HF / custom)
- HuggingFace model link
- Your WebUI environment link/info

---

## 10) Submission
- Upload this repo to GitHub
- Upload model/adapters to HuggingFace (optional but recommended)
- Send repo links to: fucar@firat.edu.tr
- Also submit on DEBSIS before deadline

Deadline: **28 January 2026 (Wednesday)**

