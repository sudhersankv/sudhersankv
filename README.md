<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/header-dark.svg">
  <img alt="Sudhersan KV — Applied AI / ML systems engineer. LLM inference, GPU programming, agents." src="assets/header-light.svg" width="100%">
</picture>

<p align="center">
  <a href="https://linkedin.com/in/sudhersankv"><img src="https://img.shields.io/badge/LinkedIn-sudhersankv-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:kvsudhersan86@gmail.com"><img src="https://img.shields.io/badge/Email-kvsudhersan86-EA4335?style=flat-square&logo=gmail&logoColor=white" alt="Email"></a>
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
<summary><b>LLM fine-tuning & serving</b> · LoRA on Qwen2.5-3B, served with vLLM</summary>
<br>

Fine-tuned Qwen2.5-3B-Instruct with LoRA on SciRIFF scientific summarization, compared base vs. LoRA on quality (ROUGE) and serving performance, then served the adapter end to end with vLLM — training notebook, eval scripts and server included.

[`vllm-sft-pipeline`](https://github.com/sudhersankv/vllm-sft-pipeline)
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

[`casecade.ai`](https://github.com/sudhersankv/casecade.ai)
</details>

---

### Recent builds & hackathons

<details>
<summary><b>doorman</b> · siteside harness for visiting AI agents · MongoDB Harness Engineering hackathon, SF Tech Week 2026</summary>
<br>

A script tag that maps any website into tools for visiting AI agents — WebMCP, a `/.well-known/doorman.json` manifest, or `window.doorman` — so an agent can either call a tool directly or hand off a goal in plain language. A small fast model ("Jev") makes each routing decision in a few hundred milliseconds, every visit is logged to MongoDB Atlas, and the harness **rewrites itself**: after a batch of visits it edits its own tools, context policy and guardrails, tests the new version on held-out goals, and keeps only the changes that measurably help. Built in one day.

[`doorman`](https://github.com/sudhersankv/doorman)
</details>

<details>
<summary><b>Rick-Approved</b> · AI-ranked shopping search</summary>
<br>

Shopping search that pulls listings across stores and scores each one with a typed evaluation model ("Jev"), then lets you re-rank results live with dials — Sensible↔Weird, Legit, Value, Quality, or one you write yourself. Ranking is a weighted average computed in the browser, so moving a dial never calls the backend.

[`jevshop`](https://github.com/sudhersankv/jevshop) · [live demo](https://rickapproved.netlify.app/)
</details>

<details>
<summary><b>Data Plumber</b> · pay-per-call schema adapter for agents</summary>
<br>

An agent-facing API that reshapes any upstream JSON payload into the exact schema the next step needs, and reports honestly what it couldn't find. Agents pay through [Pay.sh](https://pay.sh) — $0.02 in stablecoin settles per request, no accounts or API keys needed.

[`data-plumber`](https://github.com/sudhersankv/data-plumber)
</details>

<details>
<summary><b>Fyfteen Labs</b> · paper-trading sandbox for Kalshi's 15-min BTC markets</summary>
<br>

A systems-engineering project, not a trading product: keeps a real-time order book, a 15-minute contract clock and a settlement definition in sync against real Kalshi market data, with simulated funds only.

[`fyfteen-labs`](https://github.com/sudhersankv/fyfteen-labs)
</details>

<details>
<summary><b>Noteslash</b> · turn audio/text into a searchable, cited library</summary>
<br>

Upload podcasts, interviews or transcripts; Noteslash transcribes (Whisper), auto-categorizes and indexes everything with pgvector, then lets you explore it via chat, voice (OpenAI Realtime), or exported reports — every answer cited back to its source.

[`noteslashv2`](https://github.com/sudhersankv/noteslashv2)
</details>

<details>
<summary><b>That Guy</b> · the trusted local referral your neighbor would give you</summary>
<br>

For the rare, stressful home emergencies — burst pipe, leaky roof, locked out — That Guy gives you the equivalent of a neighbor's "call these people, they came in an hour and charged $240," instead of a wall of look-alike 5-star listings.

[`that-guy`](https://github.com/sudhersankv/that-guy) · [live demo](https://prod-main-app-dd7986-009wjm7pka9.compute.instacloud-edge.com)
</details>

---

### Toolbox

<p>
  <img src="https://skillicons.dev/icons?i=python,cpp,typescript,nextjs,pytorch,docker,aws,postgres,supabase,mongodb,redis,linux,bash,git&perline=10" alt="Python, C++, TypeScript, Next.js, PyTorch, Docker, AWS, PostgreSQL, Supabase, MongoDB, Redis, Linux, Bash, Git">
</p>

**Inference & GPU:** vLLM · CUDA · Triton · ROCm/HIP · Nsight Systems · ONNX Runtime · LMCache

**ML:** PyTorch · Hugging Face Transformers · LoRA/QLoRA · Unsloth · OpenCV

**Agents & product:** Next.js · Supabase · MongoDB Atlas · WebMCP · Pay.sh / x402 micropayments
