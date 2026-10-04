<p align="center">
  <img src="assets/profile-banner.svg" alt="Jian Yan — RL Systems & Interaction Models" width="100%">
</p>

# Hi, I'm Jian Yan · 颜简

I'm interested in **RL Systems** and **Interaction Models**: the infrastructure that lets agents learn from environments, and the models that make human–AI interaction more natural.

[Website](https://jianyan11.github.io/) · [Email](mailto:23331109@bjtu.edu.cn) · [X](https://x.com/JustinY38017) · [Open-source contributions](https://github.com/pulls?q=is%3Apr+author%3AJianYan11+archived%3Afalse)

## What I'm exploring

### RL Systems

How can we make environment interaction reliable enough for learning at scale?

- **Environment infrastructure:** session isolation, resource lifecycles, and recovery from failures.
- **Rollout and evaluation harnesses:** reproducible trajectories, reliable tool execution, and feedback for post-training.
- **Current work:** contributing to [Hugging Face OpenEnv](https://github.com/huggingface/OpenEnv), with a focus on client lifecycles and MCP runtime compatibility.

### Interaction Models

How should a model listen, reason, and respond in a live conversation?

- **Real-time voice:** turn-taking, interruptions, streaming responses, and response latency.
- **Multimodal dialogue:** understanding context across speech, vision, and text.
- **Adaptive reasoning:** choosing when to respond quickly and when to spend more time thinking.
- **Current work:** contributing to [TEN Framework](https://github.com/TEN-framework/ten-framework), including an optional voice router for thinking and non-thinking modes.

## Selected open-source work

| Project | My contribution | Link |
| --- | --- | --- |
| **OpenEnv** | Recover resources after failed session startup; prevent retries from overwriting unresolved cleanup obligations. | [#1145 · Merged](https://github.com/huggingface/OpenEnv/pull/1145) |
| **OpenEnv** | Propose a FastMCP 4 migration that preserves managed session semantics and supports harness sampling guards. | [#1304 · Proposal](https://github.com/huggingface/OpenEnv/pull/1304) |
| **TEN Framework** | Add an opt-in Jev router for voice assistants to switch between thinking and non-thinking modes, keeping reasoning separate from spoken output. | [#2344 · Merged](https://github.com/TEN-framework/ten-framework/pull/2344) |

<details>
<summary>More contributions around environments and evaluation</summary>

- [WorkArena #157](https://github.com/ServiceNow/WorkArena/pull/157) — check HTTP status before decoding API responses.
- [AgentEvals #113](https://github.com/langchain-ai/agentevals/pull/113) — preserve input messages during trajectory normalization.
- [EvalPlus #316](https://github.com/evalplus/evalplus/pull/316) — respect dataset versions when loading and hashing HumanEval+.

</details>

## OpenAI Model Craft Challenge · Parameter Golf

I participated in OpenAI's **Parameter Golf** challenge, which asks participants to train a language model with the best text-compression score under tight resource constraints. The main track limits the combined code and compressed model artifact to **16 MB** and training to **10 minutes on eight H100 GPUs**, with performance measured in bits per byte (bpb) on the FineWeb validation set.

My work focused on a small architecture change: replacing the baseline MLP's **ReLU² with LeakyReLU(0.5)²** to preserve gradient flow for negative inputs without adding parameters. I implemented the change and submitted it as a baseline improvement.

In my reported **600-second experiments on two RTX 5090 GPUs**, the modified model achieved **1.2947 bpb**, compared with **1.3822 bpb** for the baseline (lower is better). The runs reached **1,947 and 1,000 training steps**, respectively, making this a comparison under the same time budget on my hardware.

## A little more about me

I study Electronic Information at **Beijing Jiaotong University**, and pursue a second degree in Economics at **Peking University's National School of Development**. My earlier work includes [semi-supervised ionogram detection](https://github.com/JianYan11/SEMI-DETR) and computational imaging.

I enjoy turning ideas into working software and tracing problems from observed behavior to the underlying system. If you're working on RL environment infrastructure or real-time human–AI interaction, I'd love to compare notes.
