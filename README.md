<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/header-dark.svg">
  <img alt="Sudhersan KV — Applied AI / ML systems engineer. LLM inference, GPU programming, agents." src="assets/header-light.svg" width="100%">
</picture>

<p align="center">
  <a href="https://linkedin.com/in/sudhersankv"><img src="https://img.shields.io/badge/LinkedIn-sudhersankv-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:kvsudhersan11@gmail.com"><img src="https://img.shields.io/badge/Email-kvsudhersan11-EA4335?style=flat-square&logo=gmail&logoColor=white" alt="Email"></a>
  <img src="https://img.shields.io/badge/Open_to-full--time_SWE_·_AI_·_ML_roles-3fb950?style=flat-square" alt="Open to full-time roles">
</p>

I like making LLMs fast and useful: profiling where the milliseconds go, tuning how models get served, and building agents people actually use.

MS CS (AI) from Arizona State · Engineering intern at OpsCien · 🏆 1st place, Build Personal Agents Hack (SF Tech Week 2026)

---

### ⚡ [gpu-programming](https://github.com/sudhersankv/gpu-programming) — my main lab

Where I learn GPU programming and LLM inference by building, benchmarking and profiling everything myself. Some results from it:

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/bench-dark.svg">
  <img alt="vLLM vs Hugging Face: 3.1x faster time-to-first-token, 2.1x decode throughput. vLLM prefix caching: 7x faster TTFT on a shared 1K-token prefix." src="assets/bench-light.svg" width="100%">
</picture>

**→ [Read the case study: Profiling vLLM automatic prefix caching](https://sudhersankv.github.io/gpu-programming/)** (client timings + Nsight Systems traces)

<details>
<summary><b>LLM Inference Runtime Lab</b> · HF vs vLLM, prefix caching, Nsight profiling, LMCache</summary>
<br>

A benchmark harness I built to compare inference engines on the same model and prompts, reporting TTFT, end-to-end latency and tok/s at p50–p99.

- Hugging Face and vLLM (Docker) baselines with an OpenAI-compatible streaming client
- Reproducible shared-prefix workload built from the Qasper dataset, plus a control set with no shared prefix
- vLLM automatic prefix caching A/B, then traced with Nsight Systems down to kernel and memcpy level
- LMCache smoke test. Coming next: SGLang, TensorRT-LLM, ROCm, Nsight Compute

[`llm-inference-runtime-lab/`](https://github.com/sudhersankv/gpu-programming/tree/main/llm-inference-runtime-lab)
</details>

<details>
<summary><b>Kernel practice</b> · CUDA, Triton, CuTe DSL, JAX, Mojo</summary>
<br>

Hands-on kernel lessons: launches, indexing, memory, matmul and reduction, done through LeetGPU so no local GPU is needed for the practice loop.

[`leetgpu/`](https://github.com/sudhersankv/gpu-programming/tree/main/leetgpu)
</details>

<details>
<summary><b>Agentic Inference Optimization</b> · in progress</summary>
<br>

A long-term project: watch real LLM inference on a GPU, figure out why it behaves the way it does, then use agents to propose and test optimizations. I'm currently tracing the full path from a cloud GPU to generated tokens (model loading, request lifecycle, KV cache, vLLM execution) before writing any agent code.

[`agentic-inference-optimization/`](https://github.com/sudhersankv/gpu-programming/tree/main/agentic-inference-optimization)
</details>

---

### More work

<details>
<summary><b>🏆 Kevin from Home Alone</b> · 1st place, Build Personal Agents Hack</summary>
<br>

A shared household agent that lives in your group chat and helps everyone in the home stay on the same page. Built at the SF Tech Week kickoff hackathon.
</details>

<details>
<summary><b>LLM fine-tuning & serving</b> · LoRA / QLoRA on Qwen, served with vLLM</summary>
<br>

Fine-tuned Qwen models with LoRA/QLoRA (Unsloth) and served them on vLLM, benchmarking speed and generation quality side by side.
</details>

<details>
<summary><b>LLM-guided ASIC physical design</b> · OpenROAD</summary>
<br>

Put an LLM in the loop of OpenROAD's flow to steer timing optimization during ASIC physical design.
</details>

<details>
<summary><b>Legal AI</b> · domain-specific language models</summary>
<br>

Building legal-domain models through phrase mining, graph analysis and instruction tuning.
</details>

---

### Toolbox

<p>
  <img src="https://skillicons.dev/icons?i=python,cpp,pytorch,docker,aws,postgres,redis,linux,bash,git&perline=10" alt="Python, C++, PyTorch, Docker, AWS, PostgreSQL, Redis, Linux, Bash, Git">
</p>

**Inference & GPU:** vLLM · CUDA · Triton · ROCm/HIP · Nsight Systems · ONNX Runtime · LMCache

**ML:** PyTorch · Hugging Face Transformers · LoRA/QLoRA · Unsloth · OpenCV
