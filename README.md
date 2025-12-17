
# GAN-based Naturalistic Adversarial Patch Generation for Traffic Sign Recognition

> **Final Project (Tugas Akhir) – Bachelor of Computer Science**  
> Institut Teknologi Bandung (ITB)  
> Author: **Muhammad Rizky Sya’ban**  
> August 2025

This repository contains the implementation of a **GAN-based framework for generating naturalistic adversarial patches** to evaluate the robustness of **Traffic Sign Recognition Systems (TSRS)**.  
The work focuses on **realistic, context-aware adversarial patches** that simulate vandalism-like perturbations under varying physical conditions such as lighting and placement.

---

## 📌 Research Motivation

Traffic Sign Recognition Systems are a critical component of autonomous driving pipelines, yet they are known to be **highly vulnerable to adversarial attacks**.  
Most existing adversarial patches are:

- Visually unnatural
- Easily detectable by humans
- Over-optimistic due to simplified digital evaluations

This project addresses these gaps by proposing a **naturalistic adversarial patch generation framework** using **Generative Adversarial Networks (GANs)** with realistic transformation modules.

---

## 🧠 Key Contributions

- ✅ **GAN-based patch-to-patch translation** inspired by PS-GAN
- ✅ **Realistic transformation module** simulating:
  - Patch placement
  - Scale variation
  - Relighting conditions
- ✅ **Evaluation on modern object detectors (YOLOv8, YOLO11, YOLO12)**
- ✅ **White-box and black-box (transferability) attack analysis**
- ✅ **Human subjective survey** to quantify patch naturalness
- ✅ Empirical evidence of **trade-off between attack effectiveness and visual realism**

---

## 🏗️ System Overview

The framework consists of:

1. **Generator (G)**  
   Produces adversarial patches that remain visually consistent with seed patches.

2. **Discriminator (D)**  
   Enforces visual realism and discourages unnatural artifacts.

3. **Transformation Module**  
   Applies geometric and illumination transformations to simulate real-world deployment.

4. **Target Detector (YOLO)**  
   Evaluates attack success using object detection metrics.

The system is designed for **digital evaluation of physical-world adversarial attacks**, aligned with recent realistic benchmarks.

---

## 📊 Evaluation Setup

### Target Models
- YOLOv8x, YOLOv8m, YOLOv8n
- YOLO11x
- YOLO12x

### Datasets
- **Indonesian Traffic Sign Dataset** (custom curated)
- **Quick, Draw! Dataset** (used as vandalism-style seed patches)

### Metrics
- **mAP50–95**
- **Attack Success Rate (ASR)**  
- **Human Naturalness Score (Subjective Survey)**

---

## 🔬 Key Results (Summary)

- **White-box attack (YOLOv8x)**  
  - ASR up to **8.02%** (mAP50–95 degradation)

- **Black-box transfer attack (YOLO12x)**  
  - ASR up to **9.85%**

- **Human perception study (24 participants)**  
  - Adversarial patches scored **32.6% naturalness**
  - Original seed patches scored **43.1%**
  - Confirms a **fundamental realism–effectiveness trade-off**

These findings highlight the difficulty of producing **simultaneously stealthy and highly effective adversarial patches** in realistic conditions.

---

## 📁 Repository Structure

```

.
├── dataset/
│   ├── traffic_signs/        # Traffic sign dataset
│   └── seed_patches/         # Quick, Draw! seed patches
├── models/
│   ├── generator.py
│   ├── discriminator.py
│   └── attention_module.py
├── transforms/
│   ├── placement.py
│   └── relighting.py
├── training/
│   └── train_gan.py
├── evaluation/
│   └── evaluate_yolo.py
└── README.md

````

*(Exact filenames may vary depending on experiments.)*

---

## ⚙️ Environment & Dependencies

- Python ≥ 3.9
- PyTorch
- Ultralytics YOLO
- OpenCV
- NumPy
- Matplotlib

Recommended: **GPU with CUDA support**

---

## 🚀 Running the Project (High Level)

```bash
# Train GAN for adversarial patch generation
python training/train_gan.py

# Evaluate generated patches on YOLO
python evaluation/evaluate_yolo.py
````

Detailed hyperparameter configurations can be found in the report.

---

## 📄 Thesis Report

The full academic report (in Indonesian) is included:

📘 **“Pembangkitan Naturalistic Adversarial Patch Menggunakan Generative AI untuk Evaluasi Ketahanan Traffic Sign Recognition System”**
Institut Teknologi Bandung, 2025 

This document contains:

* Full theoretical background
* Formal threat model
* Mathematical loss formulations
* Extensive experiments and ablation studies
* Survey design and analysis

---

## ⚠️ Ethical Note

This project is intended **strictly for research and robustness evaluation purposes**.
It aims to **improve the safety of autonomous systems**, not to facilitate malicious attacks.

---

## 📚 References

Key references include:

* Brown et al., *Adversarial Patch*, 2017
* Eykholt et al., *Robust Physical Perturbations*, 2018
* Liu et al., *PS-GAN*, 2019
* Hingun et al., *REAP Benchmark*, 2023

(Full references are listed in the thesis report.)

---

## 👤 Author

**Muhammad Rizky Sya’ban**
Undergraduate Student – Computer Science
Institut Teknologi Bandung
