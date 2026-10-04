# Agent 环境/任务合成相关论文整理

[简体中文](readme.md) | [English](readme.en.md)

## 一、难度、基准度量、验证可靠性方向

| 论文标题 | 链接 | 核心要点 | 验证状态 |
|---|---|---|---|
| A Matter of TASTE: Improving Coverage and Difficulty of Agent Benchmarks | [arXiv:2605.28556](https://arxiv.org/abs/2605.28556) | 程序化生成更难任务；在 τ²-Bench Verified 上性能下降范围 -5% ~ -80% | ✅ 确认 |
| AgentBoard: An Analytical Evaluation Board of Multi-turn LLM Agents | [arXiv:2401.13178](https://arxiv.org/abs/2401.13178) | 按子目标划分 easy/hard 难度；提出进度率度量指标 | ✅ 确认 |
| τ²-Bench: Evaluating Conversational Agents in a Dual-Control Environment | [arXiv:2506.07982](https://arxiv.org/abs/2506.07982) | 双控制器架构 + 组合式任务生成器；Telecom 双控制域建模为 Dec-POMDP；**ICML 2026 Oral** | ✅ 确认，补充 venue |
| Easy2Hard-Bench: Standardized Difficulty Labels | [arXiv:2409.18433](https://arxiv.org/abs/2409.18433) | 难度标签标准化；NeurIPS 2024 | ✅ 确认 |
| Benchmarks as Microscopes: A Call for Model Metrology | [arXiv:2407.16711](https://arxiv.org/abs/2407.16711) | 将难度定义为可测量的模型属性；**COLM 2024** | ✅ 确认，补充 venue |
| Curriculum RL from Easy to Hard | [arXiv:2506.06632](https://arxiv.org/abs/2506.06632) | 从易到难的课程式强化学习训练范式 | ✅ 确认 |
| Cheap Reward Hacking Detection | [arXiv:2606.08893](https://arxiv.org/abs/2606.08893) | 面向验证器侧的难度研究、奖励欺骗检测 | ✅ 确认 |
| Do Agent Benchmarks Measure Capability? Protocol Validity | [arXiv:2607.22368](https://arxiv.org/abs/2607.22368) | 奖励欺骗等价于基准验证失效问题；腾讯混元团队 | ✅ 确认 |
| World Feedback for Clinical Agents (MAB-v3) | [arXiv:2607.01470](https://arxiv.org/abs/2607.01470) | 临床 Agent 环境加难，性能天花板分析；**ICML 2026** | ✅ 确认，补充 venue |
| EnviSAgE: A Survey of Environment Scaling | [arXiv:2511.09586](https://arxiv.org/abs/2511.09586) | 环境扩难综述，提出 GEF 三阶段循环 | ✅ 确认 |

---

## 二、环境合成

| 论文/框架 | 核心贡献 | 时间/出处 | 链接 | 验证状态 |
|---|---|---|---|---|
| **Agent-World** | 1978 环境 / 19,822 工具；工具依赖图 + 可执行 Python 解任务合成；多环境闭环 RL + GRPO；自演化竞技场 | 2026-04，人大 & 字节 Seed | [arXiv:2604.18292](https://arxiv.org/abs/2604.18292) | ✅ 确认 |
| **EnvScaler** | 191 环境 / ~7K 场景；SkelBuilder + ScenGenerator；SFT 后 BFCL-MT +8.67、ACEBench-Agent +11.57 | 2026-01，**ACL 2026 Findings** | [arXiv:2601.05808](https://arxiv.org/abs/2601.05808) | ✅ 确认 |
| **Agent-World Model (AWM)** | 代码驱动 + 数据库支撑全合成环境管线；1000 envs / 10000 tasks / 35 tools | 2026-02，**ICML 2026** | [arXiv:2602.10090](https://arxiv.org/abs/2602.10090) | ✅ 确认，补充 venue |
| **InfiniteWeb** | 可扩展 Web 环境自动合成；统一规格 + 测试驱动开发，面向 GUI Agent 训练 | 2026-01，PKU/NJU/MSR Asia | [arXiv:2601.04126](https://arxiv.org/abs/2601.04126) | ✅ 确认 |
| **ToolVerse** | ~400 MCP servers / ~4,500 tools；工具依赖图 + Dynamic Unlocking；长程 TIR；BFCL-v3 35.00→37.50%，τ²-Bench 27.33→32.37% | 2026-07 | [arXiv:2607.15660](https://arxiv.org/abs/2607.15660) | ✅ 确认，规模描述修正 |
| **SPADE** | 自博弈：环境设计者生成 Gym 式可执行环境 ↔ 推理 Agent 求解；BFCL v4 多轮 +5.3，ACEBench-Agent +5.7 | 2026-08 | [arXiv:2608.19197](https://arxiv.org/abs/2608.19197) | ✅ 确认 |
| **CuES** | 好奇心驱动、环境锚定任务合成；兼容 AppWorld/BFCL/WebShop，无需人工种子 | 2025-12 | [arXiv:2512.01311](https://arxiv.org/abs/2512.01311) | ✅ 确认 |
| **EnvFactory** | 可执行环境合成；拓扑感知图引导鲁棒 RL 与轨迹生成 | 2026-05，港科大（广州）LARK 等 | [arXiv:2605.18703](https://arxiv.org/abs/2605.18703) | ✅ 确认 |
| **Qwen-AgentWorld** | 语言世界模型模拟通用 Agent 环境；35B-A3B / 397B-A17B | 2026-06，千问 | [arXiv:2606.24597](https://arxiv.org/abs/2606.24597) | ✅ 确认 |
| **ScaleEnv** | 从零构建完全交互式环境和可验证任务；工具依赖图扩展 + 可执行动作验证；在 τ²-Bench 等多轮工具使用基准上显著提升 | 2026，**ICML 2026**，美团参与 | [arXiv:2602.06820](https://arxiv.org/abs/2602.06820) | ✅ 确认，补全编号 |
| **GenEnv** | 难度对齐，Agent-环境模拟器协同进化，在能力边界生成任务 | 2025 | [arXiv:2512.19682](https://arxiv.org/abs/2512.19682) | ✅ 确认，补全编号 |
| **C-World** | 按需构建 Agent 环境；5,571 工具 / 204 应用；任务分布引擎合成带约束长程工作流；转移函数注入真实故障；World Engine 与真实执行 Spearman=0.883 | 2026，**ACL 2026 Long** | [arXiv:2601.06328](https://arxiv.org/abs/2601.06328) | ✅ 确认，补全编号 |
| **ClawEnvKit** | 自然语言规格 → 按需生成 claw-like Agent 环境；Auto-ClawEval 含 1,040 环境 / 24 类别；成本比人工低 13,800 倍；Harness engineering 比裸 ReAct 提升最多 15.7 个百分点 | 2026-04 | [arXiv:2604.18543](https://arxiv.org/abs/2604.18543) | ✅ 确认 |
| **AgentMercury** | 从高层商业场景合成可执行环境；4,783 环境 / 14 行业 / 50 国家；Qwen3.5-4B 在 EnterpriseOps-GYM 上 12.3→15.7；微调后世界编写成功率 3.3%→83.3% | 2026-08 | [arXiv:2608.20634](https://arxiv.org/abs/2608.20634) | ✅ 确认 |
| **Repo2RLEnv** | 将 GitHub 仓库/PR/提交历史转换为可执行 RL 环境；输出 Harbor 格式任务包（指令+环境+参考解+验证器）；内置 6 条原生流水线 + Tasksmith + 14 个研究配方；支持推送至 HuggingFace Hub | [GitHub](https://github.com/huggingface/Repo2RLEnv) · [文档](https://huggingface.github.io/Repo2RLEnv/) |
| **CUA-Sandbox** | 计算机使用智能体（Computer-Use Agent）强化学习的高效环境方案。核心观察是轨迹需要独立可变状态，而初始化后的应用运行时可在并发环境间复用。通过状态胶囊（state capsule）、签名路由能力（signed route capability）和代际租约（generation lease）实现状态作用域执行与事务性生命周期操作，保留原始软件接口与任务评估器。在 WebArena-Lite、VisualWebArena 和 OSWorld 上评估，相比 Docker 实现最高 6.20× rollout 吞吐提升、9.2× 单环境内存降低、504× 增量存储降低 | 2026-09 | [arXiv:2609.32750](https://arxiv.org/abs/2609.32750) · [PDF](https://arxiv.org/pdf/2609.32750) | ✅ 确认，提交于 2026-09-26；第一作者 Xin Yan，通讯作者 Xingrui Yu；14 位作者来自 A*STAR、HKUST、BNU、NUS、NTU、ZJU、PKU；开源代码：[github.com/windskyyx/Cua-Sandbox](https://github.com/windskyyx/Cua-Sandbox) |



---

## 三、经验/交互合成

| 论文/框架 | 核心贡献 | 时间/出处 | 链接 | 验证状态 |
|---|---|---|---|---|
| **Tool-R0** | 生成器-求解器自博弈共进化；零训练数据自举工具调用 | 2026-02，UIUC | [arXiv:2602.21320](https://arxiv.org/abs/2602.21320) | ✅ 确认 |
| **DreamGym** | 推理式经验模型合成多样化经验；低成本在线 RL、sim-to-real | 2025-11，**ICLR 2026**，Meta/芝大/伯克利 | [arXiv:2511.03773](https://arxiv.org/abs/2511.03773) | ✅ 确认，补充 venue |
| **Grounded Interaction Synthesis (GAIS)** | 基于真实环境模拟人-助手长程交互轨迹，包含对抗约束；两阶段 grounding 机制 | 2026-06，**ACM SIGKDD 2026** | [arXiv:2606.02001](https://arxiv.org/abs/2606.02001) | ✅ 确认，补充 venue |
| **TOUCAN** | 150 万条轨迹 / ~500 个真实 MCP 环境；当前最大公开工具 Agent 数据集；微调后 BFCL V3 超越更大闭源模型，推进 MCP-Universe Bench Pareto 前沿 | 2025-10 | [arXiv:2510.01179](https://arxiv.org/abs/2510.01179) | ✅ 确认，补全编号 |
| **Mock Worlds, Real Skills** | SYNTHAGENT 框架：LLM 用户模拟器 + Mock 工具系统 + rubric 奖励；14 个数据集上显著提升 | 2026，**ACL 2026 Long** | [arXiv:2601.22511](https://arxiv.org/abs/2601.22511) | ✅ 确认，补全编号 |

---

## 四、Web/GUI 合成

| 论文/框架 | 核心贡献 | 时间/出处 | 链接 | 验证状态 |
|---|---|---|---|---|
| **WebArena-Infinity** | 多 Agent 流水线（coding + browser-use agents）从静态 artifact 生成可验证 Web 环境；10 环境 / 1,260 任务 / 2,070 轨迹 | 2026 | [GitHub](https://github.com/web-arena-x/webarena-infinity) | ✅ 确认 |
| **ScaleWoB** | 高保真跨平台 GUI 交互环境合成；可验证奖励，低资源开销 | 2026-05 | [arXiv:2605.25160](https://arxiv.org/abs/2605.25160) | ✅ 确认 |
| **GUI-Genesis** | 从真实应用重建轻量 Web 环境；可验证奖励，GUI Agent 后训练 | 2026 | [arXiv:2602.14093](https://arxiv.org/abs/2602.14093) | ✅ 确认，补全编号 |
| **Weblica** | 可复现可扩展交互式 Web 环境框架；面向视觉 Web Agent 训练 | 2026-05 | [arXiv:2605.06761](https://arxiv.org/abs/2605.06761) | ✅ 确认 |
| **ScaleCUA / VeriGen** | 可验证任务合成 + 高效在线 RL 扩展计算机使用 Agent | 2026-07 | [arXiv:2607.11185](https://arxiv.org/abs/2607.11185) | ✅ 确认 |
| **FaraGen (Fara-7B)** | 基于高频网站生成多步 Web 任务数据系统 | 2025-11，Microsoft | [arXiv:2511.19663](https://arxiv.org/abs/2511.19663) | ✅ 确认 |
| **FaraGen1.5 (Fara-1.5)** | 环境 + 求解器 + 验证器三组件，可扩展 CUA 数据管线 | 2026-06 | [arXiv:2606.20785](https://arxiv.org/abs/2606.20785) | ✅ 确认 |
| **OS-Genesis** | 反向任务合成：先探索再构造任务，产出 GUI Agent 轨迹 | 2024-12，**ACL 2025** | [arXiv:2412.19723](https://arxiv.org/abs/2412.19723) | ✅ 确认 |
| **HATS** | 难度感知轨迹合成；适配 AndroidWorld / WebArena | **CVPR 2026** | [arXiv:2603.12138](https://arxiv.org/abs/2603.12138) | ✅ 确认，补全编号 |

---

## 五、终端/编码环境

| 论文/框架 | 核心贡献 | 时间/出处 | 链接 | 验证状态 |
|---|---|---|---|---|
| **Terminal-Bench 2.0** | 89 个 CLI 任务；每个任务含独特环境 + 人工解 + 综合测试；前沿模型得分 <65% | 2026-01，**ICLR 2026** | [arXiv:2601.11868](https://arxiv.org/abs/2601.11868) | ✅ 确认 |
| **CLI-Universe** | 可验证任务合成引擎；6K 轨迹；Qwen3-32B 在 TB2 得分 33.4% | 2026-06，南大/StepFun/上海 AI Lab | [arXiv:2606.22883](https://arxiv.org/abs/2606.22883) | ✅ 确认 |
| **SETA** | SETA-Synth + SETA-Evol 双流水线；SETA-Env 含 4,500+ 环境；GRPO 训练 Qwen3-8B 在 TB 2.0 达 12% pass rate | 2026-07 | [arXiv:2607.10891](https://arxiv.org/abs/2607.10891) | ✅ 确认 |
| **TerminalWorld** | 逆向真实终端依赖构建可执行沙箱 + 环境合成 | 2026-05，UCL/南大/腾讯 | [arXiv:2605.22535](https://arxiv.org/abs/2605.22535) | ✅ 确认 |
| **ResearchEnvBench** | 面向科研代码执行环境合成基准；依赖解析、版本对齐、分布式场景 | 2026-03 | [arXiv:2603.06739](https://arxiv.org/abs/2603.06739) | ✅ 确认 |
| **AI Scientist via Synthetic Task Scaling** | 合成 ML 挑战任务，兼容 SWE-Agent；主题采样 + 数据集提案 + 代码生成 | 2026-03 | [arXiv:2603.17216](https://arxiv.org/abs/2603.17216) | ✅ 确认 |
| **SWE-Factory** | 自动 issue-resolve 数据集工厂；SWE-Builder + exit-code 评分 + fail2pass | 2025-06，**FSE 2026** | [arXiv:2506.10954](https://arxiv.org/abs/2506.10954) | ✅ 确认，补充 venue |
| **SWE-smith** | 任意 Python 仓库生成 SWE-gym；128 repos / 50K 任务实例；SWE-agent-LM-32B 在 SWE-bench Verified 达 40.2% Pass@1 | **NeurIPS 2025 Spotlight** | [arXiv 搜索: SWE-smith](https://arxiv.org/search/?query=SWE-smith) | ✅ 确认 |
| **R2E-Gym** | 程序化环境生成 + 混合验证器，开源 SWE-Agent 权重 | **COLM 2025** | [arXiv 搜索: R2E-Gym](https://arxiv.org/search/?query=R2E-Gym) | ✅ 确认 |
| **SWE-World** | 无 Docker 框架；学习式代理模型替代物理执行；SWE-bench Verified 上 Qwen2.5-Coder-32B 从 6.2%→52.0%（SFT）/ 55.0%（RL）/ 68.2%（TTS） | 2026-02，人大高瓴 & BOSS 直聘 | [arXiv:2602.03419](https://arxiv.org/abs/2602.03419) | ✅ 确认，补全编号 |
| **SWE-Universe** | 从 GitHub PR 自动构建可验证 SWE 环境；807,693 个多语言环境；Qwen3-Max-Thinking 在 SWE-Bench Verified 达 75.3% | 2026-02，阿里 Qwen & 浙大 | [arXiv:2602.02361](https://arxiv.org/abs/2602.02361) | ✅ 确认，补全编号 |
| **daVinci-Env** | 大规模开放 SWE 环境合成 | 2026-03 | [arXiv:2603.13023](https://arxiv.org/abs/2603.13023) | ✅ 确认 |
| **DockSmith** | 规模化可靠编码环境；Dockerfile、测试脚本自动化构建 | 2026-02 | [arXiv:2602.00592](https://arxiv.org/abs/2602.00592) | ✅ 确认 |
| **TerminalTraj** | 从 Docker 化环境生成大规模终端 Agent 轨迹；32K 镜像 / 50,733 条验证轨迹；Qwen2.5-Coder 训练后 TB 1.0 +20%，TB 2.0 +10% | **ICML 2026** | [arXiv:2602.01244](https://arxiv.org/abs/2602.01244) | ✅ 确认，补全编号 |
| **Terminal-Universe** | 将Agent轨迹逆向回放为可复用终端环境；生成37.3k个任务充足环境；微调Qwen3.5-27B后TB 2.1 +11.9分，EvoCode-Bench v2 MT@4 +13.8分 | 2026-09 | [arXiv:2609.04148](https://arxiv.org/abs/2609.04148) | ✅ 确认 |

---

## 六、模型基仿真

| 论文/框架 | 核心贡献 | 时间/出处 | 链接 | 验证状态 |
|---|---|---|---|---|
| **ARE / GAIA2** | Meta Agents Research Environments；可扩展环境创建平台 + 异步基准 GAIA2 | 2025-09，Meta | [arXiv:2509.17158](https://arxiv.org/abs/2509.17158) | ✅ 确认 |
| **Chimera** | 多 Agent 企业威胁仿真；环境 + 角色模拟 | 2025-08，**NDSS 2026** | [arXiv:2508.07745](https://arxiv.org/abs/2508.07745) | ✅ 确认 |
| **WebWorld** | 大规模开放 Web 模拟器；1M+ 真实 Web 交互训练；支持 30+ 步长程模拟；Qwen3-14B 训练后 WebArena +9.2%；推理时搜索作为世界模型超越 GPT-5；跨域泛化到代码、GUI、游戏 | 2026-02，**ICML 2026**，阿里 Qwen | [arXiv:2602.14721](https://arxiv.org/abs/2602.14721) | ✅ 确认，描述修正 |
| **Code2World** | GUI 世界模型；代码渲染预测下一 UI 状态 | **CVPR 2026**（另有 ICML 2026 版本） | [arXiv 搜索: Code2World](https://arxiv.org/search/?query=Code2World) | ✅ 确认 |
| **VirtualEnv** | 开源模拟平台；程序化任务生成 + 游戏式机制 | 2026 | [arXiv:2601.07553](https://arxiv.org/abs/2601.07553) | ✅ 确认，补全编号 |
| **ProPlay** | 程序化世界模型；过程级预演 + 过程图，自演化 LLM Agent | 2026-06 | [arXiv:2606.12780](https://arxiv.org/abs/2606.12780) | ✅ 确认 |
| **EnvACE** | 用“世界排练”替代外部环境交互；策略先发工具调用，再扮演环境生成响应，两角色端到端联合优化；BFCL-v4 / τ²-Bench / VitaBench / FinMCP-Bench 上优于环境扩展基线 | 2026-08 | [arXiv:2608.06197](https://arxiv.org/abs/2608.06197) | ✅ 确认，补全编号 |

---

## 七、任务/场景合成

| 论文/框架 | 核心贡献 | 时间/出处 | 链接 | 验证状态 |
|---|---|---|---|---|
| **TaskCraft** | 自动生成 Agentic 任务；~36K 任务，多类工具依赖；深度扩展 + 宽度扩展；41K 工具密集型任务 | 2025-06，**ICLR 2026**，OPPO AI Agent Team | [arXiv:2506.10055](https://arxiv.org/abs/2506.10055) | ✅ 确认，补充 venue |
| **Graph2Eval** | 知识图谱驱动多模态任务生成；文档理解 + Web 交互；1319 任务 | 2025-10，**CVPR 2026** | [arXiv:2510.00507](https://arxiv.org/abs/2510.00507) | ✅ 确认，补充 venue |
| **SimpleQA→DeepResearch** | Explorer–Formalizer–Challenger 迭代任务演化；500 个可验证深度研究任务 | 2026-08 | [arXiv:2608.02163](https://arxiv.org/abs/2608.02163) | ✅ 确认 |
| **AgenticDataBench** | 技能聚类 + LLM 任务生成构建数据 Agent 基准 | 2026-07，清华 & 蚂蚁 | [arXiv:2607.01647](https://arxiv.org/abs/2607.01647) | ✅ 确认 |
| **ART** | 医疗 AI Agent 的 Action-based Reasoning 临床任务基准；四阶段流水线；600 个任务；检索接近完美，聚合推理 28–64%，阈值推理 32–38% | 2026-01 | [arXiv:2601.08988](https://arxiv.org/abs/2601.08988) | ✅ 确认 |
| **ACuRL** | 自主课程 RL；环境探索-课程生成-持续适配，零人工数据 | 2026-02，OSU-NLP-Group | [arXiv:2602.10356](https://arxiv.org/abs/2602.10356) | ✅ 确认 |
| **State2State** | 从环境探索状态导出中间训练任务，状态匹配验证 | 2026-08，THUNLP | [arXiv:2608.04934](https://arxiv.org/abs/2608.04934) | ✅ 确认 |
| **SESA** | 自博弈搜索 Agent；出题者-求解者架构，不需要外部题库 | 2026-07 | [arXiv:2607.29468](https://arxiv.org/abs/2607.29468) | ✅ 确认 |
| **Gym-V** | 179 个程序化视觉环境、10 个领域，难度可控 | 2026 | [arXiv:2603.15432](https://arxiv.org/abs/2603.15432) | ✅ 确认，补全编号 |
| **InternAgentHarness (BOOTCAMPCLI)** | 四层环境定义，自动转换训练范式 Harness | 2025-08 | [arXiv:2508.08636](https://arxiv.org/abs/2508.08636) | ✅ 确认 |

---

## 八、平台/基建/方法论

| 论文/框架 | 核心贡献 | 时间/出处 | 链接 | 验证状态 |
|---|---|---|---|---|
| **AgenticAI-Supervisor** | UI 驱动仿真引擎；千路并行隔离轨迹，模拟即创作 | 2026-07 | [arXiv:2607.05773](https://arxiv.org/abs/2607.05773) | ✅ 确认 |
| **ClawGym II** | 黑盒 RL 对接真实 Agent Harness（OpenClaw / Claude Code）；30 任务 | 2026-08，人大高瓴 & IQuest | [arXiv:2608.16798](https://arxiv.org/abs/2608.16798) | ✅ 确认 |
| **OccuBench** | 语言环境模拟真实职业任务；多学科、异步设定 | 2026-04 | [arXiv:2604.10866](https://arxiv.org/abs/2604.10866) | ✅ 确认 |
| **AgentGym2** | 去理想化真实环境评测框架；27 个领域；测量探索性工具发现、工具组合、噪声鲁棒性 | 2026-07，**ACL 2026 Long** | [arXiv:2607.05174](https://arxiv.org/abs/2607.05174) | ✅ 确认，补充 venue |
| **TUA-Bench** | 通用终端 Agent 基准；120 任务 / 5 大类 | 2026-06，Meta | [arXiv:2606.28480](https://arxiv.org/abs/2606.28480) | ✅ 确认 |
| **AgencyBench** | 138 任务 / 32 场景；百万 token 级长程上下文 | 2026-01 | [arXiv:2601.11044](https://arxiv.org/abs/2601.11044) | ✅ 确认 |
| **Hierarchy of Agentic Capabilities** | 真实 RL 环境下 Agent 能力层级评估 | 2026-01 | [arXiv:2601.09032](https://arxiv.org/abs/2601.09032) | ✅ 确认 |
| **Efficient Benchmarking of AI Agents** | 8 套 Agent 基准的采样效率研究 | 2026-03 | [arXiv:2603.23749](https://arxiv.org/abs/2603.23749) | ✅ 确认 |
| **OSGym** | 支持 1024 并行沙箱的 CUA 训练基础设施 | 2025 | [arXiv:2511.11672](https://arxiv.org/abs/2511.11672) | ✅ 确认，补全编号 |
| **EnvHarness** | 可编程层包装静态环境，加速 Agent 学习，不新建环境；Google Research | 2026 | [arXiv:2608.19880](https://arxiv.org/abs/2608.19880) | ✅ 确认，补全编号 |
| **Harbor-Index 1.0** | 6627 候选过滤得到 82 任务；难度过滤 + AI/人工审计加固流水线 | 2026-07 | [harbor-index.org](https://harbor-index.org/) | ✅ 确认 |
| **Environment Scaling Survey** | GEF 循环（生成-执行-反馈）统一环境扩展综述 | 2025-11 | [arXiv:2511.09586](https://arxiv.org/abs/2511.09586) | ✅ 确认 |
| **Agentic Environment Engineering Survey** | 从环境工程生命周期视角系统综述：建模 → 合成 → 评估 → 应用；涵盖符号合成、神经合成两种范式 | 2026-06 | [arXiv:2606.12191](https://arxiv.org/abs/2606.12191) | ✅ 确认，补全编号 |
| **AgentJudgeBench** | 3,808 个依赖驱动的 Agentic 工作流；6 种 DAG 拓扑；3 个难度层级；硬查询上所有 judge 收敛于 77-82% 准确率天花板 | **EMNLP 2026 Main** | [arXiv:2608.26623](https://arxiv.org/abs/2608.26623) | ✅ 确认，补全编号 |
| **Benchmark Radar** | AI 基准的活数据库与搜索引擎；追踪 14,810+ 条记录，覆盖 37 个来源；提供 Dashboard、CLI、RSS 和完整数据集下载；技术报告 arXiv:2609.11115 | [GitHub](https://github.com/ktwu01/benchmark-radar) · [Dashboard](https://benchmark-radar.org/) |
---

## 九、代表性工作要点摘要

| 工作 | 方法 | 规模 / 实验结果 |
|---|---|---|
| **Agent-World**（智源 / TARS） | 基于工具依赖图与可执行 Python 求解的任务合成，难度可控；多环境闭环 RL + GRPO；自演化竞技场 | 1,978 个环境 / 20 类 / 19,822 个工具；8B / 14B 模型训练后超越多个闭源模型 |
| **EnvScaler**（人大） | SkelBuilder（环境骨架：可执行程序 + 文档 + 工具接口，双 Agent 评估）+ ScenGenerator（场景 / 任务 / 终态校验函数） | 191 个环境 / 约 7K 场景；SFT 后 BFCL-MT 提升 +8.67、ACEBench-Agent 提升 +11.57 |
| **InfiniteWeb** | 可扩展 Web 环境合成，面向 GUI Agent 域内泛化 | 将合成网站迁移至真实网页进行泛化测试 |
| **Agent-World Model** | 面向无限合成环境的 Agentic RL | 在 τ-bench、MCP-Universe 上开展对比实验 |
| **ToolVerse** | 大规模工具环境 + 长程任务 | 约 400 个 MCP servers / 约 4,500 个 tools；环境多样性带来的收益大于单纯增加 rollout 数量，BFCL-v3 / τ²-Bench 显著提升 |
| **AgentDrive** | 通过 LLM Prompt 生成 JSON 驾驶场景 | 生成 30 万个驾驶场景；[arXiv:2601.16964](https://arxiv.org/abs/2601.16964) |
| **Agentick** | 程序化生成 37 个任务，Gymnasium 接口 + oracle 策略 + SFT 数据 | 用于通用序贯决策评测；[arXiv:2605.06869](https://arxiv.org/abs/2605.06869) |
| **Survey: Scaling Environments for LLM Agents** | 提出 GEF loop（任务生成—执行—反馈），并给出统一分类框架 | 从环境中心视角进行综述 |

## 十、Sandbox Infra（沙箱基础设施）

| 项目 | 简述 | 日期 | 链接 | 备注 |
|---|---|---|---|---|
| **AgentENV (AENV)** | 由 Moonshot AI 与 kvcache-ai 联合开源的高吞吐分布式智能体环境平台，基于 Firecracker microVM 提供强隔离 Linux 沙箱，专为 Kimi K3 的 Agentic RL 训练打造；支持快照、fork、按需镜像加载，启动 / 恢复 <50ms，暂停 <100ms，兼容 E2B SDK | 2026-07 | [github.com/kvcache-ai/AgentENV](https://github.com/kvcache-ai/AgentENV) | ✅ 确认；开源日期 2026-07-27 |
| **WeEnv** | 微信（WeChat）面向 Agentic RL 的全生命周期环境管理系统，覆盖打包（packaging）、初始化（initialization）与弹性供给（provisioning）三个阶段；通过层组复用、按需拉取与 CPU / 内存弹性配额，将环境初始化开销降低 5.6–14.2 倍，迭代时间中环境占比从最高 53.4% 降至 9.1% | 2026-09 | [arXiv:2609.30766](https://arxiv.org/abs/2609.30766) | ✅ 确认；arXiv 提交于 2026-09-25 |
| **DeepSeek Elastic Compute (DSec)** | DeepSeek 生产级沙盒基础设施，统一提供 FnCall、容器、microVM 与 full-VM 四种后端；单生产单元约 160 节点 / 3 万核 / 250TB 内存，日均服务约 300 万沙盒，峰值并发超 38 万，创建速率超 5000/秒。所有 DeepSeek V3.2–V4.1 的 RL 训练与评测均在 DSec 上运行 | 2026-09 | [arXiv:2609.22978](https://arxiv.org/abs/2609.22978) | ✅ 确认；arXiv 提交于 2026-09-19；梁文锋署名，130+ 作者 |


# 十一、cua


| 工作名称 | arXiv 链接 | 简要描述与 venue | 确认状态 |
|---|---|---|---|
| Gym-Anything: Turn any Software into an Agent Environment | [arXiv:2604.06126](https://arxiv.org/abs/2604.06126) | 多 Agent 流水线将任意软件转化为交互式 CUA 环境，构建 CUA-World（200 软件、10K+ 长视野任务）和 CUA-World-Long（>500 步） | ✅ 确认，arXiv 2026.04 |
| CUA-GYM: Scaling Verifiable Training Environments and Tasks for Computer-Use Agents | [arXiv:2605.25624](https://arxiv.org/abs/2605.25624) | Generator/Discriminator 双 Agent 协作生成可验证 RLVR 训练元组，32,112 条覆盖 110 环境；CUA-GYM-A17B 在 OSWorld-Verified 达 72.6% | ✅ 确认，arXiv 2026.05 |
| CUA-Lite: An Open Platform for Computer-Use Agents | [UC Berkeley RDI 博客](https://rdi.berkeley.edu/blog/cua-lite/) | 统一 Lite.Gym / Lite.Sample / 模型 harness 三大抽象，15+ 基准、10+ 数据集、30K+ 可验证任务 | ✅ 确认，暂无 arXiv 编号，UC Berkeley RDI 发布 |
| Cua (trycua/cua) | [GitHub](https://github.com/trycua/cua) | 开源基础设施：沙箱、SDK 和基准测试，支持 macOS/Linux/Windows 全桌面控制；配套 Cua-Bench | ✅ 确认，GitHub 项目，无独立 arXiv 论文 |
| Cua Agent framework 0.4 | [Cua 博客](https://cua.ai) | 统一多模型接口，支持 Composite Agents（grounding + planning 模型组合） | ✅ 确认，官方博客 2025.08 |
| OpenCUA: Open Foundations for Computer-Use Agents | [arXiv:2508.09123](https://arxiv.org/abs/2508.09123) | 开源框架含标注基础设施、AgentNet 数据集（3 OS、200+ 应用）和 CoT 推理流水线；OpenCUA-72B 在 OSWorld-Verified 达 45.0% | ✅ 确认，**NeurIPS 2025** |
| CUA-Sandbox: Efficient Environments for Computer-Use Agent Reinforcement Learning | [arXiv:2609.32750](https://arxiv.org/abs/2609.32750) | 通过 state capsule 与共享运行时分离，实现 6.20× rollout 吞吐提升、9.2× 内存降低、504× 存储减少 | ✅ 确认，arXiv 2026.09 |
| OSWorld: Benchmarking Multimodal Agents for Open-Ended Tasks in Real Computer Environments | [arXiv:2404.07972](https://arxiv.org/abs/2404.07972) | 369 个真实桌面任务，覆盖 Web/桌面应用、文件 I/O 和跨应用工作流，Ubuntu/Windows/macOS | ✅ 确认，arXiv 2024.04 |
| OSWorld 2.0: Benchmarking Computer Use Agents on Long-Horizon Real-World Tasks | [arXiv:2606.29537](https://arxiv.org/abs/2606.29537) | 将 CUA 评估推至专业级真实工作流难度，二进制成功率仅 20.6% | ✅ 确认，arXiv 2026.06 |
| OSWorld-Human: Benchmarking the Efficiency of Computer-Use Agents | [arXiv:2506.16042](https://arxiv.org/abs/2506.16042) | 人工标注效率基准，发现领先 Agent 平均使用必要步骤的 1.4–2.7 倍 | ✅ 确认，arXiv 2025.06 |
| WebArena: A Realistic Web Environment for Building Autonomous Agents | [arXiv:2307.13854](https://arxiv.org/abs/2307.13854) | 四个自托管网站（电商、社交论坛、协作开发、CMS）+ 地图工具，812 个长视野 Web 任务 | ✅ 确认，arXiv 2023.07 |
| CUARewardBench: A Benchmark for Evaluating Reward Models on Computer-using Agent | [arXiv:2510.18596](https://arxiv.org/abs/2510.18596) | 首个 CUA 奖励模型基准，覆盖 10 软件类别、7 Agent 架构；UPE 方法达 89.8% 精度和 93.3% NPV | ✅ 确认，**ICML 2026** |
| Computer Agent Arena: Toward Human-Centric Evaluation and Analysis of Computer-Use Agents | [ICLR 2026 论文](https://proceedings.iclr.cc/paper_files/paper/2026/hash/5f1d328711b162e1cf9896c7d6aaecdd-Abstract-Conference.html) | 人类偏好驱动的头对头评估平台，2,201 票覆盖 12 Agent，观察到与静态基准的排名反转 | ✅ 确认，**ICLR 2026** |
| MCPWorld: A Unified Benchmarking Testbed for API, GUI, and Hybrid Computer Use Agents | [arXiv:2506.07672](https://arxiv.org/abs/2506.07672) | 首个同时支持 API、GUI 和混合范式的 CUA 测试平台，201 个任务，75.12% 完成准确率 | ✅ 确认，arXiv 2025.06 |
| UI-CUBE: Enterprise-Grade Computer Use Agent Benchmarking Beyond Task Accuracy to Operational Reliability | [arXiv:2511.17131](https://arxiv.org/abs/2511.17131) | UiPath 企业导向确定性基准，226 任务（136 简单 + 90 复杂），暴露 CUA 根本性架构局限 | ✅ 确认，arXiv 2025.11 |
| Agent S: An Open Agentic Framework that Uses Computers Like a Human | [arXiv:2410.08164](https://arxiv.org/abs/2410.08164) | 开放 Agent 框架，通过 GUI 实现计算机自主交互；Agent S2 在 OSWorld 15 步/50 步评估达 18.9%/32.7% | ✅ 确认，**ICLR 2025** |
| Agent S3: The Unreasonable Effectiveness of Scaling Agents for Computer Use | [arXiv:2510.02250](https://arxiv.org/abs/2510.02250) | Agent S 系列的缩放版本，GPT-5 驱动下接近人类水平 | ✅ 确认，**TMLR 2026** |
| OpenAgentFleet | [PyPI](https://pypi.org/project/open-agent-fleet/) | 自托管自主 CUA 平台，每个 Agent 获得独立可丢弃的 Linux 桌面并实时流式传输到浏览器 | ✅ 确认，无 arXiv 论文 |
| open-computer-use (QwenLM) | [GitHub](https://github.com/QwenLM/open-computer-use) | 基于 MCP 的计算机使用服务，通过 accessibility API 控制 macOS/Linux/Windows | ✅ 确认，GitHub 项目 |
| open-computer-use (e2b-dev) | [GitHub](https://github.com/e2b-dev/open-computer-use) | 基于 E2B Desktop Sandbox 的安全云 Linux 计算机，由开源 LLM 控制 | ✅ 确认，GitHub 项目 |
| OmniPilot | [PyPI](https://pypi.org/project/omnipilot-agent/) | 跨平台开源 CUA，支持 13 个模型提供商和本地模型，41 个内置工具，四级权限系统 | ✅ 确认，无 arXiv 论文，PyPI 发布 |
| Tarsier-AI | [PyPI](https://pypi.org/project/tarsier-ai/) | 为 LLM 提供 Windows 桌面应用的确定性交互层，内置 MCP Server，避免基于像素坐标的脆弱点击 | ✅ 确认，无 arXiv 论文 |




