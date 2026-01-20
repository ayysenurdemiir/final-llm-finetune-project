# Final Project – LLM Fine-Tuning with WebUI (LoRA)

This repository contains my final project for **fine-tuning a Large Language Model (LLM) using an interface (WebUI)** and customizing it with a dataset.  
The model was fine-tuned using **LoRA (Low-Rank Adaptation)** and tested via the **Chat tab** in the WebUI.  
All training evidence (screenshots/logs) and outputs are included in this repository.

---

## ✅ Project Overview

In this project, I selected a pretrained instruction model and performed **parameter-efficient fine-tuning (LoRA)** using an interface-based workflow.

### 🎯 Objective
- Fine-tune an LLM model using a dataset
- Customize the model behavior for Turkish instruction-following
- Export the fine-tuned weights (LoRA adapter)
- Document the entire process and upload to GitHub for submission

---

## ✅ Model & Dataset Information

### 🔹 Base Model
- **Model:** `Qwen/Qwen2.5-1.5B-Instruct`
- Model type: Causal Language Model (Instruction-tuned)

### 🔹 Dataset
- **Dataset:** `TFLai/Turkish-Alpaca`
- Dataset type: Turkish instruction-following Q&A dataset
- Training subset used: **5,000 samples**

---

## ✅ Tools / Platform Used

- **Fine-tuning Platform:** LLaMA-Factory WebUI (Gradio)
- **Fine-tuning Method:** LoRA
- **Quantization:** 4-bit bitsandbytes quantization (QLoRA style)
- **Tokenizer & Model Loading:** HuggingFace Transformers

This approach is efficient because only LoRA layers are trained instead of updating all model parameters.

---

## ✅ Training Configuration (Important Details)

Training was executed successfully. The model was loaded and quantized to 4-bit during training.

### 📌 Training Parameters (from logs)
- **Training Samples:** 5,000  
- **Epochs:** 3  
- **Batch Size per Device:** 2  
- **Gradient Accumulation Steps:** 8  
- **Total Effective Batch Size:** 16  
- **Total Optimization Steps:** 939  
- **Trainable Parameters:** ~9,232,384 (LoRA)  
- **Total Parameters:** ~1,552,946,688  

### 📌 Fine-tuning Strategy
- Fine-tuning method: **LoRA**
- Linear modules trained: `q_proj, k_proj, v_proj, o_proj, up_proj, down_proj, gate_proj`
- Quantized training: **4-bit with bitsandbytes**
- Gradient checkpointing enabled

### ✅ Training Output Directory
Training checkpoints are stored under:

\`\`\`
saves/Qwen2.5-1.5B-Instruct/lora/train_*/checkpoint-*
\`\`\`

The final checkpoint was created at:

\`\`\`
checkpoint-939
\`\`\`

✅ Training completed successfully.

---

## ✅ Export (LoRA Adapter)

After training, the model can be exported from the **Export** tab in WebUI.

Recommended export settings:
- **Export type:** LoRA adapter export
- **Export device:** cpu
- **Export directory:** `outputs/lora_adapter_export/`

After exporting, the following files are generated:
- `adapter_model.safetensors`
- `adapter_config.json`

---

## ✅ How to Reproduce / Run (WebUI Workflow)

### Step 1 — Open WebUI
Run LLaMA-Factory WebUI (Gradio) and open the URL in your browser.

### Step 2 — Select Model
In WebUI:
- Select model: `Qwen/Qwen2.5-1.5B-Instruct`
- Choose fine-tuning method: `LoRA`

### Step 3 — Prepare Dataset
Dataset was prepared and registered in JSON format:

\`\`\`
data/turkish_alpaca_5k.json
\`\`\`

### Step 4 — Start Training
- Choose dataset
- Start training
- Monitor logs (loss, steps, epochs)
- Checkpoints are saved automatically

### Step 5 — Test in Chat Tab
After training:
1. Go to **Chat** tab
2. Select base model: `Qwen/Qwen2.5-1.5B-Instruct`
3. Load checkpoint: `checkpoint-939`
4. Click **Load Model**
5. Enter Turkish prompts and generate responses

Example prompts:
- "Türkiye’nin başkenti neresidir?"
- "Bana kısa bir motivasyon cümlesi yazar mısın?"
- "Python’da liste ile tuple farkı nedir?"

---

## ✅ Project Files Included

This repository includes:
- README technical documentation ✅
- Training logs/screenshots ✅
- Output examples ✅
- `links.txt` containing important project links ✅

---

## Screenshots

![input](screenshots/input.jpeg)  
![model](screenshots/model.jpeg)  
![model1](screenshots/model1.jpeg)  
![model2](screenshots/model2.jpeg)  
![model3](screenshots/model3.jpeg)  
![model4](screenshots/model4.jpeg)  

---

## 🔗 Links

All important links are stored in:

📌 `links.txt`

---

## 👤 Author

Ayşenur Demir
