<div align="center">
<img src="profile.svg" alt="Utkarsh Bahuguna" width="100%"/>
</div>

<p align="center">
CS undergrad at <b>BITS Pilani</b> &#215; <b>Scaler School of Technology</b>.<br/>
I build systems, then write the harnesses that try to break them.
</p>

---

### Three things worth your time

**I found real nondeterminism in vLLM's deterministic mode.** Byte-identical requests to an unchanged server disagreed under concurrency. Filed as [vllm#51187](https://github.com/vllm-project/vllm/issues/51187), independently reproduced by another engineer on different hardware, then traced into the CUDA C++ RMSNorm kernel: a reduction-width switch at a 256-token boundary. Confirmed by pre-registered measurement, 1,120 comparisons, zero exceptions.

**I published a paper arguing against a technique everyone uses.** [When Self-Consistency Backfires](https://arxiv.org/abs/2608.11403) (arXiv:2608.11403), sole author, accepted at the 2nd Workshop on Efficient Reasoning, COLM 2026. Sampling more and voting makes accuracy *worse* on 56.6% and 65.7% of hard science problems across two models.

**I publish what the measurements say, including when they contradict me.** In Lockstep, all-pairs comparison showed half my original finding was a first-batch artifact, so the retraction sits beside the result. In Shadowbook, seven benchmark runs gave p50 anywhere from 385 to 424ns, so the published number is the median rather than the good one.

---

### Building

| Project | What it is | Live |
| :-- | :-- | :-- |
| **[Lockstep](https://github.com/u7k4rs6/LockStep)** | Batch-invariant LLM inference engine built as the fixture for its real deliverable: a certifier that checks output stays bit-identical however requests are batched, ordered, preempted or evicted. Paged KV, continuous batching, fixed-reduction Triton kernels. The harness is tested like the engine, 10/10 mutation operators killed, 65/65 invariance relations. | |
| **[Shadowbook](https://github.com/u7k4rs6/Shadowbook)** | Single-instrument limit order book matching engine in Rust. Price-time priority over a 65,536-tick band, preallocated order arena. 100M differentially fuzzed operations against a reference oracle, zero divergences. p50 416ns insert on a stated machine. Zero hot-path allocation is *enforced* by a counting global allocator, not asserted. | |
| **[MIRR](https://github.com/u7k4rs6/MIRR)** | Incident-response environment where agents diagnose and recover failing microservices from partial telemetry. Five services, one hidden fault, ±15% metric noise, logs that cost a step. Published numbers are generated from a fingerprinted artifact and a pre-commit hook rejects any drift between README and measurement. | [Space](https://huggingface.co/spaces/u7k4rs6/Metafinal) |
| **[Starling](https://github.com/u7k4rs6/Starling)** | Real-time collaborative editor on a Fugue CRDT. Treap-backed document, custom binary wire encoding, relay and provider, ProseMirror binding. 377 tests. 60,000 deletions encode to 15 bytes on the wire. Published as `starling-crdt`. | [Demo](https://u7k4rs6.github.io/Starling/) |
| **[CAIRN](https://github.com/u7k4rs6/CAIRN)** | Self-hosted Git platform in Java on a real content-addressable VCS engine. Packfiles with delta compression, commit DAG with generation numbers, Myers diff, three-way merge, trigram code search. Cross-verified against the `git` binary and serving live over smart-HTTP. | [Deploy](https://cairn-production-70dd.up.railway.app) |
| **[Flint](https://github.com/u7k4rs6/Flint)** | Bootable x86-64 kernel in Rust under QEMU. Physical and virtual memory, allocator, preemptive scheduler, interrupts, syscall boundary and a shell. W^X and ring 0 / ring 3 isolation proven by a harness that tries to break out. | |
| **[Tessera](https://github.com/u7k4rs6/Tessera)** | Poisoning-resistant distribution for ML models and datasets. Publisher signs once, untrusted mirrors distribute, any consumer verifies the exact signed bytes with full provenance. Tamper-evident, replay-proof, revocation-aware. | |

---

### Open source

**Merged upstream** &#160;&#183;&#160; 11 pull requests across 7 repositories

- **gccrs** (GCC Rust frontend, C++) [#4731](https://github.com/Rust-GCC/gccrs/pull/4731), [#4728](https://github.com/Rust-GCC/gccrs/pull/4728) &#160;&#183;&#160; dead-code lint missing types used as generic arguments; rustc-compatible `E0259`/`E0260` diagnostics, design agreed with two maintainers on Zulip before writing code
- **jaeger-ui** (CNCF) [#4053](https://github.com/jaegertracing/jaeger-ui/pull/4053), [#4271](https://github.com/jaegertracing/jaeger-ui/pull/4271) &#160;&#183;&#160; GenAI span classification over OpenTelemetry semantic conventions, and a trace view that bypassed the shared span detector
- **huggingface/OpenEnv** [#742](https://github.com/huggingface/OpenEnv/pull/742) &#160;&#183;&#160; SSRF-safe URL parser
- **NVIDIA/garak** [#1842](https://github.com/NVIDIA/garak/pull/1842) &#160;&#183;&#160; provider-aware parameter suppression, restoring Bedrock scans that were failing for every Claude 4.x user
- **dottxt-ai/outlines** [#1867](https://github.com/dottxt-ai/outlines/pull/1867) &#160;&#183;&#160; RFC 4291 IPv6 structured-output type
- **vllm-project/llm-compressor**, **AI Village**

**In review**

- **kubernetes-sigs/resource-state-metrics** [#84](https://github.com/kubernetes-sigs/resource-state-metrics/pull/84) (Go) &#160;&#183;&#160; a CEL resolver accepted `int64` inside lists but dropped it inside maps, so a metric silently vanished depending on where the value sat. Reproduced at scrape level with before-and-after output, plus a parity test asserting the two paths agree. I disclosed that the fix changes series identity and breaks existing dashboards.
- **urunc-dev/urunc** [#886](https://github.com/urunc-dev/urunc/pull/886) (Go) &#160;&#183;&#160; decode-before-validate ordering bug in a Kubernetes unikernel runtime, found by fuzzing and pinned by a committed regression seed
- **NVIDIA/TensorRT-LLM**, **NVIDIA/cuda-python**, **microsoft/PyRIT**, **promptfoo**, **ml-explore/mlx-lm**

---

### Research

- **[When Self-Consistency Backfires](https://arxiv.org/abs/2608.11403)** &#160;&#183;&#160; sole author, accepted at the 2nd Workshop on Efficient Reasoning, COLM 2026. A pre-registered study finding that majority-vote sampling degrades accuracy on most expert-level problems.
- Filed an exact failing-set predicate on an open PyTorch numerics issue ([#147284](https://github.com/pytorch/pytorch/issues/147284)) while building Lockstep's fp64 reference.

### Elsewhere

- Contract engineer at **Handshake**, authoring containerised evaluation environments that measure how well AI coding agents perform real engineering tasks. Each task ships as a Docker image plus a deterministic verifier, calibrated so a reference solution passes and a strong agent does not.
- Global Top 20 finalist, **Meta &#215; PyTorch Hackathon** (the project became MIRR)
- Delegate, **Harvard HPAIR 2026** &#160;&#183;&#160; Top 1% delegate, **Japan Youth Summit 2025** (UNESCO affiliated)

### Stack

**Languages**&#160;&#160;`Rust` `C++` `Python` `Go` `Java` `TypeScript`
**Systems**&#160;&#160;`CUDA` `Triton` `QEMU` `Linux internals` `x86-64` `Kubernetes` `Docker`
**Verification**&#160;&#160;`differential fuzzing` `reference oracles` `property-based testing` `mutation testing` `deterministic replay`
**Focus**&#160;&#160;`inference systems` `compilers` `observability` `low-latency engines`

<p align="center">
<a href="https://u7k4rs6.github.io/Utkarsh-CV/">Portfolio</a> &#160;&#183;&#160;
<a href="https://linkedin.com/in/utkarshbahuguna666">LinkedIn</a> &#160;&#183;&#160;
<a href="mailto:utkarshbahuguna10@gmail.com">Email</a>
</p>
