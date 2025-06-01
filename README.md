# 🧠 BrainChip TENN vs GPUs & Neuromorphic Chips  
**ECE 410/510 – Spring 2025 | Week 9 Challenge #26**

Comparative analysis of BrainChip’s **Temporal Event‑based Neural Networks (TENN)** and **Akida** architecture versus traditional **GPUs** and other **neuromorphic systems**.  
Prepared from the May 2025 EETimes “Brains & Machines” podcast featuring BrainChip engineers.

---

## 📑 Table of Contents
1. [Architectural Differences](#1-architectural-differences)
2. [Efficiency & Memory Footprint](#2-efficiency--memory-footprint)
3. [Training Methods & Ease](#3-training-methods--ease)
4. [Edge AI Suitability](#4-edge-ai-suitability)
5. [Causal vs Non‑Causal Inference](#5-causal-vs-non-causal-inference)
6. [Model Comparisons](#6-model-comparisons)
7. [Event‑Based Hardware Synergy](#7-event-based-hardware-synergy)
8. [Future Vision](#8-future-vision)
9. [Credits](#credits)

---

## 1. Architectural Differences
| | **BrainChip TENN / Akida** | **GPUs** | **Other Neuromorphic Chips (e.g., Loihi)** |
|---|---|---|---|
| **Core Idea** | Event‑based state‑space networks with internal state summarizing temporal history | Massively parallel arithmetic for dense tensors | Spike‑based asynchronous communication |
| **Precision** | 1‑, 4‑, 8‑bit (plans for 16‑bit) | 16‑/32‑bit floating & mixed precision | Primarily 1‑bit spikes |
| **Training Path** | Trains in convolutional/transformer mode → folds into recurrent form | Standard DL pipelines | Custom learning rules; less standardized |
| **Target** | Ultra‑low‑power **edge** devices | Data center / workstation | Research & niche edge devices |

---

## 2. Efficiency & Memory Footprint
* **Activation sparsity ≥ 90 %** → far fewer MACs per inference.  
* Single compact internal‑state vector replaces large temporal buffers.  
* Power consumption often **≈ 1⁄10** that of equivalently accurate CNN/Transformer models.

---

## 3. Training Methods & Ease
* **Stable** state‑space training using convolutional form (parallelizable).  
* Post‑training folding yields recurrent networks for inference.  
* Avoids LSTM instability and sequential back‑prop bottlenecks.  
* Outperforms **Mamba 1/2** and small **Transformer** baselines (Tiny LLaMA, LLaMA 3.2) up to the 1 B‑param class with fewer parameters.

---

## 4. Edge AI Suitability
| Use‑Case | Benefit of TENN |
|---|---|
| **Audio denoising / Keyword spotting** | Low‑latency causal inference, energy‑efficient always‑on listening |
| **Eye / Gesture tracking (event cameras)** | Competitive accuracy in CVPR’24 eye‑tracking challenge with 90 % sparsity |
| **Wearable biomedical sensing** | 10× lower power extends battery life; handles 1‑D biosignals |
| **On‑device LLMs** | Demonstrated wins over Mamba and Transformer models ≤ 1 B params |

---

## 5. Causal vs Non‑Causal Inference
* **Causal mode** → zero‑look‑ahead live transcription, gesture detection, etc.  
* **Non‑causal mode** → higher accuracy when future context is available.  
* TENN sits on the **Pareto front** of latency vs accuracy for both modes.

---

## 6. Model Comparisons
| Model | Pros | Cons | TENN Edge |
|---|---|---|---|
| **LSTM/RNN** | Compact, temporal | Sequential, unstable | TENN stable training, richer state |
| **Transformer** | Fast training, high accuracy | Heavy memory, slow edge inference | TENN trains like Transformer, runs like RNN |
| **Mamba** | GPU‑friendly SSM | Large state → edge‑unfriendly | TENN small state bank, efficient |

---

## 7. Event‑Based Hardware Synergy
* Akida’s **neuro‑processors** handle only **non‑zero events**, skipping zeros.  
* Unified ingestion of spikes, analog signals, and words.  
* Sparsity + low‑bit precision → minimal DRAM access → massive energy savings.

---

## 8. Future Vision
> “We’re neuro‑inspired, not neuro‑identical.” — **Dr. John Tapson**

* **Akida 2.0**: 1‑/4‑/8‑bit, multi‑resolution processing.  
* Path to **16‑bit neuromorphic** architectures for richer algorithms.  
* Edge deployment of state‑space models poised to become mainstream; BrainChip currently leads commercialization.

---

## Credits
* Podcast: *Brains & Machines* (EETimes, May 2025) — Hosts **Sunny Baines** & **Julia D’Angelo**  
* BrainChip contributors: **Dr. Tony Lewis**, **Dr. Yan “Rudy” Rupe**, **Dr. Olivia Kenan**, **Dr. Chris Carlson**, **Dr. John Tapson**

---

_This repository is part of my Week 9 **ECE 410/510** “Deep Dive into Neuromorphic Engineering” portfolio._  
