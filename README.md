# 🧠 Cross-Modal GPT: Building a Multimodal LLM with Cross-Attention

🚀 A hands-on project that brings together **vision and language** using the **Cross-Modality Attention** architecture — the same mechanism behind models like LLaVA, Flamingo, and LLaMA 3.2!

---

## 🎯 Goal

To deeply understand how **multimodal large language models (MLLMs)** work by implementing a simplified version from scratch — using:

- 🖼️ Vision Transformer (ViT) to encode image inputs
- 🧠 Transformer decoder (GPT-style) to generate or understand text
- 🔀 Cross-attention layers to fuse image and text modalities

---

## 🏗️ Architecture

          ┌────────────┐
          │  Image (ViT)│
          └─────┬──────┘
                │
                ▼
       ┌──────────────────┐
       │  Cross-Attention │◄─────┐
       └────────┬─────────┘      │
                │                │
                ▼                │
      ┌──────────────────────┐   │
      │  Transformer Decoder │   │
      └────────────┬─────────┘   │
                   │             │
                   ▼             │
         Output Tokens (Text) ◄──┘
            (Next-token prediction)


- Cross-attention is injected between decoder layers so that text can **attend to image embeddings**.
- The training is done via **next-token prediction**, just like standard GPT models.

---

## 🧪 Minimal Training Setup

We use the **MNIST dataset** as a starting point for image-text alignment:

- Input: Image of a handwritten digit (e.g., \`7\`)
- Output: \`"This is the number seven."\`

This lets us train a character-level language model that *sees* and *describes* images — the simplest form of grounded image-text understanding.

---

## 📁 Project Structure

\`\`\`
cross_modal_llm/
├── models/
│   ├── vision_encoder.py           # ViT + projector
│   └── multimodal_decoder.py       # GPT-style decoder with cross-attn
├── data/
│   └── mnist_dataset.py            # Image + generated text samples
├── train.py                        # Main training loop
└── config.py                       # Model and training configuration
\`\`\`

---

## 🛠️ Tech Stack

- \`PyTorch\` for model training
- \`timm\` for pretrained ViT image encoder
- \`transformers\` (HuggingFace) for tokenizer
- Dataset: \`MNIST\` (plans to expand to EMNIST, synthetic OCR tasks, and VQA)

---

## 🌍 Roadmap

- [x] Build cross-attention fusion architecture
- [x] Train on MNIST + text descriptions
- [ ] Integrate real-world datasets (EMNIST, OCR, VQA-style)
- [ ] Switch from custom decoder to GPT-2 (\`transformers\`) with injected cross-attn
- [ ] Evaluate on OCR/captioning benchmarks
- [ ] Add OpenCLIP and better vision encoders
- [ ] Convert to instruction-following multimodal model

---

## 🤝 Looking for Collaborators!

This project is an educational deep dive into the internals of multimodal LLMs. If you’re:

- Passionate about LLMs and transformers
- Excited by cross-modality and multimodal learning
- Looking to contribute to open-source or research-backed projects

Drop a message or raise an issue! Let’s build the future of vision-language AI — from the ground up. 🌟

---

## 📚 Inspiration

This project is inspired by:

- [Flamingo (DeepMind)](https://arxiv.org/abs/2204.14198)
- [LLaVA (UCSD & Microsoft)](https://github.com/haotian-liu/LLaVA)
- [Fuyu (Adept)](https://huggingface.co/adept/fuyu-8b)
- [NVLM (NVIDIA)](https://arxiv.org/abs/2403.02598)

---

## 🧑‍💻 Author

**Sushant Pargaonkar** — Data Scientist | AI Engineer  
_Always learning. Always building._

[GitHub](https://github.com/sushant-97) • [LinkedIn](https://www.linkedin.com/in/spargaonkar)

---

## 📄 License

MIT License — free to use, modify, and contribute.
