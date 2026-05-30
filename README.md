# 🚀 GenAI Infrastructure Engineering Manual

<img width="1272" height="830" alt="Screenshot 2026-05-30 at 3 45 56 PM" src="https://github.com/user-attachments/assets/7abf4a6d-fcba-4168-b27c-05e815d7ca94" />


**Interactive LLM infrastructure calculator for throughput, latency, memory, and cost modeling.** - [Infrastructure Engineering Manual](https://manikandan-t.github.io/Infrastructure-Engineering-Manual/)

> Stop guessing your GPU setup. Start reasoning from first principles.

---

## 🧠 What is this?

This is a **single-page interactive tool** that helps you:

* Estimate **LLM throughput (prefill + decode)**
* Predict **latency metrics (TTFT, ITL)**
* Calculate **VRAM usage (weights + KV cache)**
* Understand **memory vs compute bottlenecks**
* Choose the **right GPU configuration**
* Model **real-world cloud costs**

---

## 🎯 Why this exists

Most LLM infra decisions are made using:

* vendor benchmarks
* random configs
* trial-and-error

This leads to:

* ❌ Over-provisioned GPUs
* ❌ Poor latency despite high cost
* ❌ OOM crashes at scale
* ❌ Misunderstood bottlenecks

---

### This tool is built on one idea:

> LLM performance is governed by **physics**, not guesswork.

---

## ⚙️ What problems it solves

### 💬 Chat API (low latency)

* Why is streaming slow?
* How to reduce ITL?

### 🤖 RAG / Agents (long context)

* Why does 128K context break?
* How big is my KV cache really?

### 📦 Batch processing

* What batch size maximizes throughput?
* What is my tokens/sec per GPU?

---

## 🔍 Key Concepts Modeled

### 1. Prefill vs Decode

* Prefill → **compute-bound**
* Decode → **memory-bound**

### 2. KV Cache Growth

* Scales with:
  `batch × context × layers`

### 3. Roofline Model

* Visualizes:

  * Compute ceiling
  * Memory ceiling
  * Actual bottleneck

### 4. Tensor Parallelism Penalty

* Models real-world:

  * PCIe vs NVLink
  * AllReduce overhead

### 5. Production Realities

* Fragmentation overhead
* Autoscaling penalties
* Cold start I/O limits

---

## 🧮 What you can calculate

### ⚡ Throughput & Latency

* System tokens/sec
* TTFT (Time to First Token)
* ITL (Inter-token latency)

### 💾 Memory Usage

* Model weights
* KV cache
* Total VRAM required

### 🧭 Hardware Fit

* Single GPU vs Multi-GPU
* TP scaling impact
* Interconnect constraints

### 💰 Cost Modeling

* Monthly GPU cost
* Cloud provider comparison
* Autoscaling buffer impact

---

## 📊 Features

* 🎯 Workload-based presets (Chat / RAG / Batch)
* 📈 Roofline visualization
* 🧠 Physics-based throughput model
* 🧮 KV cache calculator
* 🧭 GPU recommendation engine
* 💰 Cloud TCO estimator
* 📋 GPU spec sheets (A100 → B300)

---

## ⚠️ Important Disclaimer

This tool provides **first-order estimates** based on:

* Transformer architectures
* Optimized inference engines (vLLM / TRT-LLM)
* Dense model assumptions

---

Real-world performance depends on:

* kernel efficiency
* scheduler behavior
* request distribution
* system-level overhead

---

## 🧠 Key Takeaways (If you remember nothing else)

* Decode is **memory-bound**, not compute-bound
* KV cache can exceed model size
* Batch size controls throughput **and** latency
* Multi-GPU ≠ free scaling
* Bandwidth > TFLOPS (for inference)

---

## 🛠️ Built for

* AI Infra Engineers
* Backend Engineers moving into GenAI
* ML Engineers deploying LLMs
* Platform teams running vLLM / Triton
