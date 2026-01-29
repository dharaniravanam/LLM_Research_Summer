# Trade-Offs Between Traditional LLM and Chain-of-Thought Reasoning for Mathematical Tasks

This repository contains the research paper **"Trade-Offs Between Traditional LLM and Chain-of-Thought Reasoning for Mathematical Tasks"**, which presents an empirical comparison between traditional large language models (LLMs) and Chain-of-Thought (CoT)–enabled LLMs on mathematical reasoning benchmarks.

## 📄 Paper Overview

**Author:** Dharani Ravanam
**Advisor:** Shivanjali Khare, Ph.D.
**Affiliation:** Tagliatela College of Engineering, University of New Haven
**Conference:** IEEE UEMCON 2025

Large Language Models are increasingly used for reasoning-intensive tasks. While Chain-of-Thought prompting is often assumed to improve reasoning accuracy, it also introduces higher latency and token costs. This work investigates whether CoT is always beneficial, especially for simple to moderately complex mathematical problems.

The study evaluates:

* **Traditional LLM:** `kimi-dev-72b`
* **CoT-enabled LLM:** `kimi-vl-a3b-thinking`

Both models are compared across **accuracy**, **latency**, and **token usage**.

## 🎯 Research Questions

* Does Chain-of-Thought reasoning always improve accuracy?
* What is the computational cost of CoT in terms of latency and token usage?
* Are traditional LLMs more suitable for real-time, cost-sensitive applications?

## 📊 Datasets Used

A total of **500 mathematical problems** were sampled from the following benchmarks:

* **GSM8K** – Grade-school level multi-step math problems
* **Nguyen-Brat ASDiv** – Diverse arithmetic and algebra word problems
* **SAT-MATH (AGIEval)** – SAT-style multiple-choice math questions

An additional exploratory evaluation was attempted on **AllenAI Lila**, a more complex mathematical reasoning dataset.

## ⚙️ Methodology

* Models accessed via the **OpenRouter API**
* Identical system prompts used for both models
* Automated evaluation pipeline with checkpointing and retry logic

### Metrics Evaluated

* **Accuracy:** Correct vs incorrect final answers
* **Latency:** End-to-end API response time (seconds)
* **Token Usage:** Input, output, and total tokens per response

## 📈 Key Findings

* Traditional LLMs achieved **equal or higher accuracy** across all datasets
* Traditional LLMs were **~2× faster** than CoT models
* CoT models consumed **40–65% more tokens**, significantly increasing cost
* On GSM8K, the traditional model achieved **100% accuracy**, outperforming CoT

**Conclusion:** For simple to moderately complex mathematical tasks, explicit Chain-of-Thought reasoning often introduces unnecessary overhead without meaningful accuracy gains.

## 🧠 Implications

* CoT should not be used by default
* Model selection should be **task- and complexity-aware**
* Traditional LLMs are better suited for **real-time and cost-sensitive systems**

This work motivates **adaptive reasoning frameworks** that dynamically decide when CoT is required.

## 🚧 Limitations

* Free API rate limits restricted large-scale evaluation
* Model availability on OpenRouter may change over time
* Limited to mathematical reasoning tasks

## 🔮 Future Work

* Extend evaluation to domains such as programming, legal, and medical reasoning
* Compare across multiple LLM families (GPT, Claude, LLaMA, Mistral)
* Develop adaptive systems that selectively invoke CoT based on task complexity

## 📚 Citation

If you use this work, please cite:

```
D. Ravanam and S. Khare,
"Trade-Offs Between Traditional LLM and Chain-of-Thought Reasoning for Mathematical Tasks,"
IEEE UEMCON, 2025.
```

## 🔗 Dataset References

* GSM8K: [https://huggingface.co/datasets/openai/gsm8k](https://huggingface.co/datasets/openai/gsm8k)
* Nguyen-Brat ASDiv: [https://huggingface.co/datasets/nguyen-brat/asdiv](https://huggingface.co/datasets/nguyen-brat/asdiv)
* SAT-MATH (AGIEval): [https://huggingface.co/datasets/dmayhem93/agieval-sat-math](https://huggingface.co/datasets/dmayhem93/agieval-sat-math)
* AllenAI Lila: [https://huggingface.co/datasets/allenai/lila](https://huggingface.co/datasets/allenai/lila)

---

📌 *This repository is intended for academic and research purposes.*
