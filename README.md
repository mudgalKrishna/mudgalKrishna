<div align="center">

<img src="assets/banner.svg" width="100%" alt="Krishna Mudgal, AI researcher. A pixel Claude mascot hops across floating islands at dusk, collecting coins and a paper scroll for each win.">

I study how neural networks keep, merge and lose what they learn: **continual learning**, **model merging and symmetry**,
and **making fine-tuned LLMs honest about what they don't know**. I also build agents and robot policies.

<a href="https://www.linkedin.com/in/krishnamudgal2007/"><img src="https://img.shields.io/badge/LinkedIn-krishnamudgal2007-a99fd6?style=flat-square&labelColor=1b1730&logo=linkedin&logoColor=f4dccb" alt="LinkedIn"></a>
<a href="https://x.com/KrishnaMudgal"><img src="https://img.shields.io/badge/X-@KrishnaMudgal-a99fd6?style=flat-square&labelColor=1b1730&logo=x&logoColor=f4dccb" alt="X"></a>
<a href="https://huggingface.co/KM2007"><img src="https://img.shields.io/badge/Hugging%20Face-KM2007-a99fd6?style=flat-square&labelColor=1b1730&logo=huggingface&logoColor=f4dccb" alt="Hugging Face"></a>

</div>

<br>

- 📄 **Paper accepted at NeurIPS 2026 (workshop):** *Symmetry Alignment Across Depth in Transformer Merging*
- 🏆 **Winner, HackIIITD 2026** with **Riptide**, a test bench for AI shopping agents
- 🛡️ **HUMBLE**, Lexsi AI Safety & Alignment Hackathon (Track 1): catches and repairs fine-tuned RAG models that make up answers
- 🔬 Research interests: continual learning · linear mode connectivity · LLM reliability · VLAs · AI for science

<br>

## Selected work

<sub>🎮 Each card has its own creature, and each one has a move. <a href="https://mudgalkrishna.github.io/mudgalKrishna/mascots.html">Hover them on the playground</a> to see Mirror Beam, Aqua Jet, Ember Burst and Volt Shock.</sub>

### 📄 Symmetry Alignment Across Depth in Transformer Merging · *NeurIPS 2026 workshop*

<a href="https://mudgalkrishna.github.io/mudgalKrishna/mascots.html#mirra"><img src="assets/mascot-paper.svg" width="100%" alt="Mirra the symmetry fox merging two orbs"></a><br>
<img src="assets/neurips-barrier.svg" alt="Animated plot: aligning a shallow and a deep Transformer removes up to 94.6% of the loss barrier but a residual floor always remains" width="100%">

Two Transformers trained from different seeds can be merged with almost no loss once you undo their parameter symmetries,
but only if they have the same depth. We asked what happens when one is deeper. We pad the shallow model with exact identity
blocks so both live in the same parameter space, then align them with permutations and orthogonal maps. On WikiText-2,
Penn Treebank and Tiny Shakespeare, alignment removes **90.1–94.6%** of the naive barrier, but a residual of
**0.098–0.244 nats** survives in every configuration. That residual depends on width and on where the identity blocks go,
not on how many there are.

<br>

<table>
<tr>
<td width="50%" valign="top">

### 🛡️ [HUMBLE](https://github.com/mudgalKrishna/HUMBLE)
<a href="https://mudgalkrishna.github.io/mudgalKrishna/mascots.html#humbo"><img src="assets/mascot-humble.svg" width="100%" alt="Humbo the shield turtle flipping BLOCK to PASS"></a><br>
<a href="https://github.com/mudgalKrishna/HUMBLE"><img src="https://raw.githubusercontent.com/mudgalKrishna/HUMBLE/main/docs/assets/humble_terminal.svg" alt="HUMBLE terminal: the gate blocks the naive fine-tune, repair passes, a certificate is written" width="100%"></a>

Fine-tuning a RAG chatbot quietly teaches it to **invent answers** when its documents don't have one. Standard evals miss
this, because they only ask answerable questions. HUMBLE is a release gate: it probes unanswerable questions, returns
**PASS / BLOCK**, and repairs a blocked adapter in about **15 minutes**. It runs on one GPU with open Cohere models.

[Live demo](https://huggingface.co/spaces/KM2007/humble-explorer) · [Repaired model](https://huggingface.co/KM2007/humble-tinyaya-repaired-A) · [Write-up](https://github.com/mudgalKrishna/HUMBLE/blob/main/docs/WRITEUP.md)

</td>
<td width="50%" valign="top">

### 🌊 [Riptide](https://github.com/sortedcord/riptide) · *HackIIITD 2026 winner*
<a href="https://mudgalkrishna.github.io/mudgalKrishna/mascots.html#lure"><img src="assets/mascot-riptide.svg" width="100%" alt="Lure the ember anglerfish clicking its cursor lure"></a><br>
<a href="https://github.com/sortedcord/riptide"><img src="https://raw.githubusercontent.com/sortedcord/riptide/master/docs/assets/hero.svg" alt="A checkout where a warranty line has been slipped in; an agent's cursor finds the pre-ticked box and unticks it" width="100%"></a>

AI agents are starting to shop for us, and dark patterns fool them. Riptide has five honest Indian-style shops. A
"Trickster" LLM edits their real code to plant dark patterns from India's CCPA guidelines, and a scorer watches what a
shopping agent actually does in the browser. The result is a rating for each agent, with evidence, over the open
**A2A** protocol.

[Repo](https://github.com/sortedcord/riptide) · [Dark-pattern taxonomy](https://github.com/sortedcord/riptide/blob/master/docs/TAXONOMY.md)

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🤖 [Bi-Manual VLA](https://github.com/mudgalKrishna/Bi-Manual_VLA)
<a href="https://mudgalkrishna.github.io/mudgalKrishna/mascots.html#bimo"><img src="assets/mascot-vla.svg" width="100%" alt="Bimo the robot lifting a plate and a mug"></a><br>
<a href="https://github.com/mudgalKrishna/Bi-Manual_VLA"><img src="https://raw.githubusercontent.com/mudgalKrishna/Bi-Manual_VLA/main/docs/images/environment_front.png" alt="Two SO-101 robot arms at a table with plates, cutlery, a mug and a drawer in MuJoCo" width="100%"></a>

Two SO-101 arms learn to set a dinner table. Grasping is **purely physical**: no welds and no teleports, and if friction
fails the object drops and the episode is rejected. **71 episodes (218k frames)** feed a fine-tuned **SmolVLA**, which
runs on Intel Core Ultra (CPU/GPU/NPU via OpenVINO).

[Repo + video](https://github.com/mudgalKrishna/Bi-Manual_VLA) · [Weights](https://huggingface.co/TASMAYU/Bi-Manual-SmolVLA)

</td>
<td width="50%" valign="top">

### 🧪 More research
- [**ESM-2 structure adapter**](https://github.com/mudgalKrishna/Parameter-Efficient-ESM-2-Structure-Adapter-for-Protein-Stability-Prediction): parameter-efficient protein stability prediction
- [**PhysicsConstraints**](https://github.com/mudgalKrishna/PhysicsConstraints): physics-informed learning
- [**TITANS for HEP**](https://github.com/mudgalKrishna/TITANS-for-HEP) and [**SYMBA amplitudes**](https://github.com/mudgalKrishna/Foundation-Models-for-Squared-Amplitude-Calculation_Symba): foundation models for particle physics
- [**GEN_RESIST**](https://github.com/mudgalKrishna/GEN_RESIST): antimicrobial resistance predictor ([live](https://mudgalkrishna.github.io/GEN_RESIST/))

</td>
</tr>
</table>

<br>

<div align="center">

**Stack:** Python · PyTorch · Hugging Face (Transformers, PEFT, TRL) · LeRobot · MuJoCo · TypeScript

</div>
