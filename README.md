<div align="center">
<img src="profile.svg" alt="Utkarsh Bahuguna" width="100%"/>
</div>

<p align="center">
CS at <b>BITS Pilani</b>. I build systems, then build the harnesses that break them.<br/>
<b>41 PRs merged upstream</b> across 11 organisations, including GCC, Microsoft, PyTorch, NVIDIA, Hugging Face and CNCF.
</p>

---

- **A patch of mine is in GCC master.** [gccrs#4731](https://github.com/Rust-GCC/gccrs/pull/4731) went upstream in a maintainer's sync, authorship kept.
- **14 of those 41 fix bugs I found and reported myself**, not tickets off a board. One was in my own merged code.
- **I found nondeterminism in vLLM's deterministic mode** ([vllm#51187](https://github.com/vllm-project/vllm/issues/51187)): repeats match only if every token is reduced at the same RMSNorm block width.
- **Sole author of a COLM 2026 workshop paper.** [When Self-Consistency Backfires](https://arxiv.org/abs/2608.11403): majority voting *lowers* accuracy on 56–66% of GPQA Diamond problems.

### Open source

| Project | Merged |
| :-- | :-- |
| **[microsoft/PyRIT](https://github.com/microsoft/PyRIT/pulls?q=is%3Amerged+author%3Au7k4rs6)** | **14** · the CodeAttack converter, plus fixes to TAP/PAIR, scale scorers and dataset loaders |
| **[gccrs](https://github.com/Rust-GCC/gccrs/pulls?q=is%3Amerged+author%3Au7k4rs6)** · GCC Rust frontend | **8** · match arm guards, left-to-right argument evaluation, a dead-code fix now in GCC master |
| **[PyTorch](https://github.com/pytorch/torchtitan/pulls?q=is%3Amerged+author%3Au7k4rs6)** · executorch, torchtitan | **6** · Inspector crashes on non-finite output, wandb tag splitting, scheduler range checks |
| **[jaeger-ui](https://github.com/jaegertracing/jaeger-ui/pulls?q=is%3Amerged+author%3Au7k4rs6)** · CNCF | **4** · GenAI span classification, media rendering, RFC wire-format corrections |
| **[NVIDIA/garak](https://github.com/NVIDIA/garak/pull/1842)** | **1** · fixed Bedrock scans that failed for every Claude 4.x user |
| **[huggingface/OpenEnv](https://github.com/huggingface/OpenEnv/pull/742)** | **1** · SSRF-safe URL parsing |
| **[dottxt-ai/outlines](https://github.com/dottxt-ai/outlines/pull/1867)** | **1** · RFC 4291 IPv6 structured-output type |
| **Also** | llm-compressor ×2, AI Village ×2, openkruise/agents, openyurtio/raven |

### Building

| | |
| :-- | :-- |
| **[thrice](https://github.com/u7k4rs6/thrice)** | Reproduces a reported bug three times in parallel browsers. Precision 0.80, recall 0.80, every attempt published including the two it got wrong. |
| **[Lockstep](https://github.com/u7k4rs6/LockStep)** | An inference engine and a certifier that checks output stays bit-identical however requests are batched. |
| **[Shadowbook](https://github.com/u7k4rs6/Shadowbook)** | A limit order book in Rust. 416ns p50 insert, 100M fuzzed ops against an oracle, zero divergences. |
| **[Flint](https://github.com/u7k4rs6/Flint)** | An x86-64 kernel in Rust. Ring 3 isolation proven by a breakout harness. |
| **[Blink](https://github.com/u7k4rs6/Blink)** | Your own copy of an open source app, running in five seconds. Gone in ten minutes. [Live](https://blink.utkarshbahuguna.me) |

More, including Starling, CAIRN and MIRR, at [utkarshbahuguna.me](https://utkarshbahuguna.me).

I publish what the measurements say. When all-pairs comparison showed half of a Lockstep finding was an artifact, the retraction went next to the result.

<p align="center">
<code>Rust</code> <code>C++</code> <code>Python</code> <code>CUDA/Triton</code> <code>Go</code> <code>Java</code> <code>TypeScript</code>
<br/><br/>
<a href="https://utkarshbahuguna.me">Portfolio</a> &#160;&#183;&#160;
<a href="https://linkedin.com/in/utkarshbahuguna666">LinkedIn</a> &#160;&#183;&#160;
<a href="mailto:utkarshbahuguna10@gmail.com">Email</a>
</p>
