# Awesome Environment — Papers on Agent Environments & Task Synthesis

English | [简体中文](readme.md)

## 1. Difficulty, Benchmark Measurement & Verification Reliability

| Paper Title | Link | Key Points | Status |
|---|---|---|---|
| A Matter of TASTE: Improving Coverage and Difficulty of Agent Benchmarks | [arXiv:2605.28556](https://arxiv.org/abs/2605.28556) | Procedurally generates harder tasks; performance on τ²-Bench Verified drops by -5% to -80% | ✅ Confirmed |
| AgentBoard: An Analytical Evaluation Board of Multi-turn LLM Agents | [arXiv:2401.13178](https://arxiv.org/abs/2401.13178) | Splits difficulty into easy/hard by sub-goal; proposes a progress-rate metric | ✅ Confirmed |
| τ²-Bench: Evaluating Conversational Agents in a Dual-Control Environment | [arXiv:2506.07982](https://arxiv.org/abs/2506.07982) | Dual-control architecture + compositional task generator; the Telecom dual-control domain is modeled as a Dec-POMDP; **ICML 2026 Oral** | ✅ Confirmed, venue added |
| Easy2Hard-Bench: Standardized Difficulty Labels | [arXiv:2409.18433](https://arxiv.org/abs/2409.18433) | Standardized difficulty labels; NeurIPS 2024 | ✅ Confirmed |
| Benchmarks as Microscopes: A Call for Model Metrology | [arXiv:2407.16711](https://arxiv.org/abs/2407.16711) | Defines difficulty as a measurable property of the model; **COLM 2024** | ✅ Confirmed, venue added |
| Curriculum RL from Easy to Hard | [arXiv:2506.06632](https://arxiv.org/abs/2506.06632) | Curriculum-style RL training paradigm that goes from easy to hard | ✅ Confirmed |
| Cheap Reward Hacking Detection | [arXiv:2606.08893](https://arxiv.org/abs/2606.08893) | Verifier-side difficulty research and reward-hacking detection | ✅ Confirmed |
| Do Agent Benchmarks Measure Capability? Protocol Validity | [arXiv:2607.22368](https://arxiv.org/abs/2607.22368) | Reward hacking is equivalent to benchmark verification failure; Tencent Hunyuan team | ✅ Confirmed |
| World Feedback for Clinical Agents (MAB-v3) | [arXiv:2607.01470](https://arxiv.org/abs/2607.01470) | Hardening clinical agent environments; performance-ceiling analysis; **ICML 2026** | ✅ Confirmed, venue added |
| EnviSAgE: A Survey of Environment Scaling | [arXiv:2511.09586](https://arxiv.org/abs/2511.09586) | Survey on environment scaling; proposes the three-stage GEF loop | ✅ Confirmed |

---

## 2. Environment Synthesis

| Paper/Framework | Key Contribution | Date/Venue | Link | Status |
|---|---|---|---|---|
| **Agent-World** | 1978 environments / 19,822 tools; tool dependency graphs + executable Python solution-based task synthesis; multi-environment closed-loop RL with GRPO; self-evolving arena | 2026-04, Renmin University & ByteDance Seed | [arXiv:2604.18292](https://arxiv.org/abs/2604.18292) | ✅ Confirmed |
| **EnvScaler** | 191 environments / ~7K scenarios; SkelBuilder + ScenGenerator; after SFT, BFCL-MT +8.67 and ACEBench-Agent +11.57 | 2026-01, **ACL 2026 Findings** | [arXiv:2601.05808](https://arxiv.org/abs/2601.05808) | ✅ Confirmed |
| **Agent-World Model (AWM)** | Code-driven + database-backed fully synthetic environment pipeline; 1000 envs / 10000 tasks / 35 tools | 2026-02, **ICML 2026** | [arXiv:2602.10090](https://arxiv.org/abs/2602.10090) | ✅ Confirmed, venue added |
| **InfiniteWeb** | Scalable automatic synthesis of Web environments; unified specification + test-driven development, aimed at GUI Agent training | 2026-01, PKU/NJU/MSR Asia | [arXiv:2601.04126](https://arxiv.org/abs/2601.04126) | ✅ Confirmed |
| **ToolVerse** | ~400 MCP servers / ~4,500 tools; tool dependency graphs + Dynamic Unlocking; long-horizon TIR; BFCL-v3 35.00→37.50%, τ²-Bench 27.33→32.37% | 2026-07 | [arXiv:2607.15660](https://arxiv.org/abs/2607.15660) | ✅ Confirmed, scale description corrected |
| **SPADE** | Self-play: an environment designer generates Gym-style executable environments ↔ a reasoning Agent solves them; BFCL v4 multi-turn +5.3, ACEBench-Agent +5.7 | 2026-08 | [arXiv:2608.19197](https://arxiv.org/abs/2608.19197) | ✅ Confirmed |
| **CuES** | Curiosity-driven, environment-grounded task synthesis; compatible with AppWorld/BFCL/WebShop, no human seeds required | 2025-12 | [arXiv:2512.01311](https://arxiv.org/abs/2512.01311) | ✅ Confirmed |
| **EnvFactory** | Executable environment synthesis; topology-aware graph-guided robust RL and trajectory generation | 2026-05, HKUST (Guangzhou) LARK et al. | [arXiv:2605.18703](https://arxiv.org/abs/2605.18703) | ✅ Confirmed |
| **Qwen-AgentWorld** | A language world model that simulates general-purpose Agent environments; 35B-A3B / 397B-A17B | 2026-06, Qwen | [arXiv:2606.24597](https://arxiv.org/abs/2606.24597) | ✅ Confirmed |
| **ScaleEnv** | Builds fully interactive environments and verifiable tasks from scratch; tool dependency graph expansion + executable action verification; substantial gains on multi-turn tool-use benchmarks such as τ²-Bench | 2026, **ICML 2026**, with Meituan | [arXiv:2602.06820](https://arxiv.org/abs/2602.06820) | ✅ Confirmed, ID completed |
| **GenEnv** | Difficulty alignment; co-evolution of Agent and environment simulator, generating tasks at the capability boundary | 2025 | [arXiv:2512.19682](https://arxiv.org/abs/2512.19682) | ✅ Confirmed, ID completed |
| **C-World** | Builds Agent environments on demand; 5,571 tools / 204 apps; a task distribution engine synthesizes constrained long-horizon workflows; transition functions inject realistic failures; Spearman=0.883 between World Engine and real execution | 2026, **ACL 2026 Long** | [arXiv:2601.06328](https://arxiv.org/abs/2601.06328) | ✅ Confirmed, ID completed |
| **ClawEnvKit** | Natural-language specification → on-demand generation of claw-like Agent environments; Auto-ClawEval contains 1,040 environments / 24 categories; 13,800× cheaper than manual construction; harness engineering improves over bare ReAct by up to 15.7 points | 2026-04 | [arXiv:2604.18543](https://arxiv.org/abs/2604.18543) | ✅ Confirmed |
| **AgentMercury** | Synthesizes executable environments from high-level business scenarios; 4,783 environments / 14 industries / 50 countries; Qwen3.5-4B on EnterpriseOps-GYM goes 12.3→15.7; after fine-tuning, world-authoring success rate 3.3%→83.3% | 2026-08 | [arXiv:2608.20634](https://arxiv.org/abs/2608.20634) | ✅ Confirmed |
| **Repo2RLEnv** | Converts GitHub repositories / PRs / commit history into executable RL environments; emits Harbor-format task packages (instruction + environment + reference solution + verifier); ships 6 native pipelines + Tasksmith + 14 research recipes; supports pushing to the HuggingFace Hub | — | [GitHub](https://github.com/huggingface/Repo2RLEnv) · [Docs](https://huggingface.github.io/Repo2RLEnv/) | — |

---

## 3. Experience / Interaction Synthesis

| Paper/Framework | Key Contribution | Date/Venue | Link | Status |
|---|---|---|---|---|
| **Tool-R0** | Generator–solver self-play co-evolution; bootstraps tool calling with zero training data | 2026-02, UIUC | [arXiv:2602.21320](https://arxiv.org/abs/2602.21320) | ✅ Confirmed |
| **DreamGym** | Reasoning-based experience model synthesizes diverse experience; low-cost online RL, sim-to-real | 2025-11, **ICLR 2026**, Meta/University of Chicago/Berkeley | [arXiv:2511.03773](https://arxiv.org/abs/2511.03773) | ✅ Confirmed, venue added |
| **Grounded Interaction Synthesis (GAIS)** | Simulates long-horizon human–assistant interaction trajectories grounded in real environments, including adversarial constraints; two-stage grounding mechanism | 2026-06, **ACM SIGKDD 2026** | [arXiv:2606.02001](https://arxiv.org/abs/2606.02001) | ✅ Confirmed, venue added |
| **TOUCAN** | 1.5M trajectories / ~500 real MCP environments; currently the largest public tool-Agent dataset; after fine-tuning, BFCL V3 surpasses larger closed-source models and advances the MCP-Universe Bench Pareto frontier | 2025-10 | [arXiv:2510.01179](https://arxiv.org/abs/2510.01179) | ✅ Confirmed, ID completed |
| **Mock Worlds, Real Skills** | The SYNTHAGENT framework: LLM user simulator + mock tool system + rubric rewards; significant gains on 14 datasets | 2026, **ACL 2026 Long** | [arXiv:2601.22511](https://arxiv.org/abs/2601.22511) | ✅ Confirmed, ID completed |

---

## 4. Web / GUI Synthesis

| Paper/Framework | Key Contribution | Date/Venue | Link | Status |
|---|---|---|---|---|
| **WebArena-Infinity** | Multi-agent pipeline (coding + browser-use agents) generates verifiable Web environments from static artifacts; 10 environments / 1,260 tasks / 2,070 trajectories | 2026 | [GitHub](https://github.com/web-arena-x/webarena-infinity) | ✅ Confirmed |
| **ScaleWoB** | High-fidelity cross-platform GUI interaction environment synthesis; verifiable rewards, low resource overhead | 2026-05 | [arXiv:2605.25160](https://arxiv.org/abs/2605.25160) | ✅ Confirmed |
| **GUI-Genesis** | Reconstructs lightweight Web environments from real applications; verifiable rewards, GUI Agent post-training | 2026 | [arXiv:2602.14093](https://arxiv.org/abs/2602.14093) | ✅ Confirmed, ID completed |
| **Weblica** | A reproducible, extensible interactive Web environment framework; aimed at visual Web Agent training | 2026-05 | [arXiv:2605.06761](https://arxiv.org/abs/2605.06761) | ✅ Confirmed |
| **ScaleCUA / VeriGen** | Verifiable task synthesis + efficient online RL to scale computer-use Agents | 2026-07 | [arXiv:2607.11185](https://arxiv.org/abs/2607.11185) | ✅ Confirmed |
| **FaraGen (Fara-7B)** | Generates multi-step Web task data from high-traffic websites | 2025-11, Microsoft | [arXiv:2511.19663](https://arxiv.org/abs/2511.19663) | ✅ Confirmed |
| **FaraGen1.5 (Fara-1.5)** | Three components — environment + solver + verifier — forming a scalable CUA data pipeline | 2026-06 | [arXiv:2606.20785](https://arxiv.org/abs/2606.20785) | ✅ Confirmed |
| **OS-Genesis** | Reverse task synthesis: explore first, then construct tasks, producing GUI Agent trajectories | 2024-12, **ACL 2025** | [arXiv:2412.19723](https://arxiv.org/abs/2412.19723) | ✅ Confirmed |
| **HATS** | Difficulty-aware trajectory synthesis; adapted to AndroidWorld / WebArena | **CVPR 2026** | [arXiv:2603.12138](https://arxiv.org/abs/2603.12138) | ✅ Confirmed, ID completed |

---

## 5. Terminal / Coding Environments

| Paper/Framework | Key Contribution | Date/Venue | Link | Status |
|---|---|---|---|---|
| **Terminal-Bench 2.0** | 89 CLI tasks; each task has a unique environment + human-written solution + comprehensive tests; frontier models score <65% | 2026-01, **ICLR 2026** | [arXiv:2601.11868](https://arxiv.org/abs/2601.11868) | ✅ Confirmed |
| **CLI-Universe** | Verifiable task synthesis engine; 6K trajectories; Qwen3-32B scores 33.4% on TB2 | 2026-06, Nanjing University/StepFun/Shanghai AI Lab | [arXiv:2606.22883](https://arxiv.org/abs/2606.22883) | ✅ Confirmed |
| **SETA** | Dual pipelines SETA-Synth + SETA-Evol; SETA-Env contains 4,500+ environments; GRPO-trained Qwen3-8B reaches a 12% pass rate on TB 2.0 | 2026-07 | [arXiv:2607.10891](https://arxiv.org/abs/2607.10891) | ✅ Confirmed |
| **TerminalWorld** | Reverse-engineers real terminal dependencies to build executable sandboxes + environment synthesis | 2026-05, UCL/Nanjing University/Tencent | [arXiv:2605.22535](https://arxiv.org/abs/2605.22535) | ✅ Confirmed |
| **ResearchEnvBench** | Benchmark for research-code execution environment synthesis; dependency resolution, version alignment, distributed scenarios | 2026-03 | [arXiv:2603.06739](https://arxiv.org/abs/2603.06739) | ✅ Confirmed |
| **AI Scientist via Synthetic Task Scaling** | Synthesizes ML challenge tasks, compatible with SWE-Agent; topic sampling + dataset proposal + code generation | 2026-03 | [arXiv:2603.17216](https://arxiv.org/abs/2603.17216) | ✅ Confirmed |
| **SWE-Factory** | Automated issue-resolve dataset factory; SWE-Builder + exit-code scoring + fail2pass | 2025-06, **FSE 2026** | [arXiv:2506.10954](https://arxiv.org/abs/2506.10954) | ✅ Confirmed, venue added |
| **SWE-smith** | Generates SWE-gym from arbitrary Python repositories; 128 repos / 50K task instances; SWE-agent-LM-32B reaches 40.2% Pass@1 on SWE-bench Verified | **NeurIPS 2025 Spotlight** | [arXiv search: SWE-smith](https://arxiv.org/search/?query=SWE-smith) | ✅ Confirmed |
| **R2E-Gym** | Programmatic environment generation + hybrid verifiers; open-sources SWE-Agent weights | **COLM 2025** | [arXiv search: R2E-Gym](https://arxiv.org/search/?query=R2E-Gym) | ✅ Confirmed |
| **SWE-World** | Docker-free framework; a learned surrogate model replaces physical execution; Qwen2.5-Coder-32B on SWE-bench Verified goes 6.2%→52.0% (SFT) / 55.0% (RL) / 68.2% (TTS) | 2026-02, Renmin University Gaoling & BOSS Zhipin | [arXiv:2602.03419](https://arxiv.org/abs/2602.03419) | ✅ Confirmed, ID completed |
| **SWE-Universe** | Automatically builds verifiable SWE environments from GitHub PRs; 807,693 multilingual environments; Qwen3-Max-Thinking reaches 75.3% on SWE-Bench Verified | 2026-02, Alibaba Qwen & Zhejiang University | [arXiv:2602.02361](https://arxiv.org/abs/2602.02361) | ✅ Confirmed, ID completed |
| **daVinci-Env** | Large-scale open SWE environment synthesis | 2026-03 | [arXiv:2603.13023](https://arxiv.org/abs/2603.13023) | ✅ Confirmed |
| **DockSmith** | Reliable coding environments at scale; automated construction of Dockerfiles and test scripts | 2026-02 | [arXiv:2602.00592](https://arxiv.org/abs/2602.00592) | ✅ Confirmed |
| **TerminalTraj** | Generates large-scale terminal Agent trajectories from Dockerized environments; 32K images / 50,733 verified trajectories; after training, Qwen2.5-Coder gains +20% on TB 1.0 and +10% on TB 2.0 | **ICML 2026** | [arXiv:2602.01244](https://arxiv.org/abs/2602.01244) | ✅ Confirmed, ID completed |

---

## 6. Model-Based Simulation

| Paper/Framework | Key Contribution | Date/Venue | Link | Status |
|---|---|---|---|---|
| **ARE / GAIA2** | Meta Agents Research Environments; an extensible environment-creation platform + the asynchronous GAIA2 benchmark | 2025-09, Meta | [arXiv:2509.17158](https://arxiv.org/abs/2509.17158) | ✅ Confirmed |
| **Chimera** | Multi-agent enterprise threat simulation; environment + role simulation | 2025-08, **NDSS 2026** | [arXiv:2508.07745](https://arxiv.org/abs/2508.07745) | ✅ Confirmed |
| **WebWorld** | Large-scale open Web simulator; trained on 1M+ real Web interactions; supports 30+ step long-horizon simulation; trained Qwen3-14B gains +9.2% on WebArena; inference-time search as a world model surpasses GPT-5; cross-domain generalization to code, GUI, and games | 2026-02, **ICML 2026**, Alibaba Qwen | [arXiv:2602.14721](https://arxiv.org/abs/2602.14721) | ✅ Confirmed, description corrected |
| **Code2World** | GUI world model; renders code to predict the next UI state | **CVPR 2026** (there is also an ICML 2026 version) | [arXiv search: Code2World](https://arxiv.org/search/?query=Code2World) | ✅ Confirmed |
| **VirtualEnv** | Open-source simulation platform; programmatic task generation + game-like mechanics | 2026 | [arXiv:2601.07553](https://arxiv.org/abs/2601.07553) | ✅ Confirmed, ID completed |
| **ProPlay** | Procedural world model; process-level rehearsal + process graphs; self-evolving LLM Agent | 2026-06 | [arXiv:2606.12780](https://arxiv.org/abs/2606.12780) | ✅ Confirmed |
| **EnvACE** | Replaces external environment interaction with "world rehearsal"; the policy emits a tool call first, then plays the environment to generate the response, with both roles optimized end-to-end; outperforms environment-scaling baselines on BFCL-v4 / τ²-Bench / VitaBench / FinMCP-Bench | 2026-08 | [arXiv:2608.06197](https://arxiv.org/abs/2608.06197) | ✅ Confirmed, ID completed |

---

## 7. Task / Scenario Synthesis

| Paper/Framework | Key Contribution | Date/Venue | Link | Status |
|---|---|---|---|---|
| **TaskCraft** | Automatically generates agentic tasks; ~36K tasks with multiple types of tool dependencies; depth expansion + width expansion; 41K tool-intensive tasks | 2025-06, **ICLR 2026**, OPPO AI Agent Team | [arXiv:2506.10055](https://arxiv.org/abs/2506.10055) | ✅ Confirmed, venue added |
| **Graph2Eval** | Knowledge-graph-driven multimodal task generation; document understanding + Web interaction; 1319 tasks | 2025-10, **CVPR 2026** | [arXiv:2510.00507](https://arxiv.org/abs/2510.00507) | ✅ Confirmed, venue added |
| **SimpleQA→DeepResearch** | Iterative task evolution via Explorer–Formalizer–Challenger; 500 verifiable deep-research tasks | 2026-08 | [arXiv:2608.02163](https://arxiv.org/abs/2608.02163) | ✅ Confirmed |
| **AgenticDataBench** | Skill clustering + LLM task generation to build a data-Agent benchmark | 2026-07, Tsinghua & Ant Group | [arXiv:2607.01647](https://arxiv.org/abs/2607.01647) | ✅ Confirmed |
| **ART** | Action-based Reasoning clinical task benchmark for medical AI Agents; four-stage pipeline; 600 tasks; retrieval is near-perfect, aggregate reasoning 28–64%, threshold reasoning 32–38% | 2026-01 | [arXiv:2601.08988](https://arxiv.org/abs/2601.08988) | ✅ Confirmed |
| **ACuRL** | Autonomous curriculum RL; environment exploration–curriculum generation–continuous adaptation, with zero human data | 2026-02, OSU-NLP-Group | [arXiv:2602.10356](https://arxiv.org/abs/2602.10356) | ✅ Confirmed |
| **State2State** | Derives intermediate training tasks from environment exploration states, with state-matching verification | 2026-08, THUNLP | [arXiv:2608.04934](https://arxiv.org/abs/2608.04934) | ✅ Confirmed |
| **SESA** | Self-play search Agent; question-setter–solver architecture that needs no external question bank | 2026-07 | [arXiv:2607.29468](https://arxiv.org/abs/2607.29468) | ✅ Confirmed |
| **Gym-V** | 179 procedural visual environments across 10 domains, with controllable difficulty | 2026 | [arXiv:2603.15432](https://arxiv.org/abs/2603.15432) | ✅ Confirmed, ID completed |
| **InternAgentHarness (BOOTCAMPCLI)** | Four-layer environment definition, automatically converting training paradigms into harnesses | 2025-08 | [arXiv:2508.08636](https://arxiv.org/abs/2508.08636) | ✅ Confirmed |

---

## 8. Platforms / Infrastructure / Methodology

| Paper/Framework | Key Contribution | Date/Venue | Link | Status |
|---|---|---|---|---|
| **AgenticAI-Supervisor** | UI-driven simulation engine; thousands of parallel isolated trajectories; simulation as creation | 2026-07 | [arXiv:2607.05773](https://arxiv.org/abs/2607.05773) | ✅ Confirmed |
| **ClawGym II** | Black-box RL against real Agent harnesses (OpenClaw / Claude Code); 30 tasks | 2026-08, Renmin University Gaoling & IQuest | [arXiv:2608.16798](https://arxiv.org/abs/2608.16798) | ✅ Confirmed |
| **OccuBench** | Language environments simulate real occupational tasks; multidisciplinary, asynchronous settings | 2026-04 | [arXiv:2604.10866](https://arxiv.org/abs/2604.10866) | ✅ Confirmed |
| **AgentGym2** | De-idealized evaluation framework on real environments; 27 domains; measures exploratory tool discovery, tool composition, and noise robustness | 2026-07, **ACL 2026 Long** | [arXiv:2607.05174](https://arxiv.org/abs/2607.05174) | ✅ Confirmed, venue added |
| **TUA-Bench** | General-purpose terminal Agent benchmark; 120 tasks / 5 major categories | 2026-06, Meta | [arXiv:2606.28480](https://arxiv.org/abs/2606.28480) | ✅ Confirmed |
| **AgencyBench** | 138 tasks / 32 scenarios; million-token-scale long-horizon context | 2026-01 | [arXiv:2601.11044](https://arxiv.org/abs/2601.11044) | ✅ Confirmed |
| **Hierarchy of Agentic Capabilities** | Evaluates the hierarchy of Agent capabilities in real RL environments | 2026-01 | [arXiv:2601.09032](https://arxiv.org/abs/2601.09032) | ✅ Confirmed |
| **Efficient Benchmarking of AI Agents** | Study of sampling efficiency across 8 Agent benchmarks | 2026-03 | [arXiv:2603.23749](https://arxiv.org/abs/2603.23749) | ✅ Confirmed |
| **OSGym** | CUA training infrastructure supporting 1024 parallel sandboxes | 2025 | [arXiv:2511.11672](https://arxiv.org/abs/2511.11672) | ✅ Confirmed, ID completed |
| **EnvHarness** | A programmable layer wraps static environments to accelerate Agent learning without building new environments; Google Research | 2026 | [arXiv:2608.19880](https://arxiv.org/abs/2608.19880) | ✅ Confirmed, ID completed |
| **Harbor-Index 1.0** | 6627 candidates filtered down to 82 tasks; difficulty filtering + AI/human audit hardening pipeline | 2026-07 | [harbor-index.org](https://harbor-index.org/) | ✅ Confirmed |
| **Environment Scaling Survey** | The GEF loop (Generate-Execute-Feedback) as a unified survey of environment scaling | 2025-11 | [arXiv:2511.09586](https://arxiv.org/abs/2511.09586) | ✅ Confirmed |
| **Agentic Environment Engineering Survey** | Systematic survey from the environment-engineering lifecycle perspective: modeling → synthesis → evaluation → application; covers both symbolic and neural synthesis paradigms | 2026-06 | [arXiv:2606.12191](https://arxiv.org/abs/2606.12191) | ✅ Confirmed, ID completed |
| **AgentJudgeBench** | 3,808 dependency-driven agentic workflows; 6 DAG topologies; 3 difficulty tiers; on hard queries all judges converge to a 77–82% accuracy ceiling | **EMNLP 2026 Main** | [arXiv:2608.26623](https://arxiv.org/abs/2608.26623) | ✅ Confirmed, ID completed |
| **Benchmark Radar** | A living database and search engine for AI benchmarks; tracks 14,810+ records across 37 sources; offers a dashboard, CLI, RSS, and full dataset downloads; technical report arXiv:2609.11115 | — | [GitHub](https://github.com/ktwu01/benchmark-radar) · [Dashboard](https://benchmark-radar.org/) | — |

---

## 9. Key Points from Representative Works

| Work | Method | Scale / Experimental Results |
|---|---|---|
| **Agent-World** (BAAI/TARS) | Tool dependency graphs + executable Python solution-based task synthesis with controllable difficulty; multi-environment closed-loop RL with GRPO; self-evolving arena | 1978 environments / 20 categories / 19,822 tools; 8B/14B models surpass several closed-source models after training |
| **EnvScaler** (Renmin University) | SkelBuilder (environment skeleton: executable program + documentation + tool interface, evaluated by dual Agents) + ScenGenerator (scenario/task/terminal-state verification functions) | 191 environments / ~7K scenarios; after SFT, BFCL-MT +8.67 and ACEBench-Agent +11.57 |
| **InfiniteWeb** | Scalable Web environment synthesis, targeting in-domain generalization for GUI Agents | Synthesized websites transferred to real web pages for generalization testing |
| **Agent-World Model** | Agentic RL over infinitely synthesized environments | Comparative experiments against τ-bench and MCP-Universe |
| **ToolVerse** | Large-scale tool environments + long-horizon tasks | ~400 MCP servers / ~4,500 tools; environment diversity yields more benefit than increasing the number of rollouts; significant gains on BFCL-v3 / τ²-Bench |
| **AgentDrive** | LLM prompt generates JSON driving scenarios | 300K driving scenarios; [arXiv:2601.16964](https://arxiv.org/abs/2601.16964) |
| **Agentick** | Procedurally generates 37 tasks with a Gymnasium interface + oracle policy + SFT data | General sequential decision-making evaluation; [arXiv:2605.06869](https://arxiv.org/abs/2605.06869) |
| **Survey: Scaling Environments for LLM Agents** | Proposes the GEF loop — task generation, execution, feedback — as a unified taxonomy | Environment-centric survey |
