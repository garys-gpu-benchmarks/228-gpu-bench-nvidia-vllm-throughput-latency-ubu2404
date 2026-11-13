# Results: 228 vLLM Inference Throughput & Latency

**Main goal:** Measure vLLM serving throughput and latency  
**Tools:** Start python -m vllm.entrypoints.openai.api_server on port 8000, then run scripts/benchmark_serving.py

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_138 · recorded 2026-11-12). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× NVIDIA H100 NVL (95830 MiB) · AMD EPYC 9374F 32-Core Processor · Ubuntu 24.04.5 LTS · kernel 6.8.0-138-generic · driver 595.91.07
- **Run:** 2026-11-12T23:36:14Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 02:52 · benchmark 00:44 · whole run 03:51
- **Source:** run 228_20261112_233614
- **Command:** `bash run_benchmark.sh --smoke --model-name mistralai/Mistral-7B-v0.3 --dtype bfloat16 --tensor-parallel-size 1 --gpu-memory-utilization 0.9 --input-len 64 --output-len 16 --max-num-seqs 2 --max-concurrency 2`

| # | Metric | Result |
|---|---|---|
| 1 | Output token throughput (output_token_throughput_tokens_sec) | 300.83886015928374 |
| 2 | Time To First Token, ms (ttft_p50_msec) | 14.747234992682934 |
| 3 | Time Per Output Token, ms (time_per_output_token_tpot_p50_msec) | 5.638456003119548 |
| 4 | Inter-token latency, ms (inter_token_latency_itl_p50_msec) | 5.534897791221738 |
| 5 | End-to-end request latency p50, ms (end_to_end_request_latency_msec) | 99.32407503947616 |
<!-- /profile:smoke -->
