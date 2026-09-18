# Agent 环境/任务合成相关论文整理
## 一、难度、基准度量、验证可靠性方向
|论文标题|arXiv链接|核心要点|
|---|---|---|
|A Matter of TASTE: Improving Coverage and Difficulty of Agent Benchmarks（最对口）|arxiv.org/abs/2605.28556|程序化生成更难任务；在 τ²‑bench Verified 上性能下降范围 -5% ~ -80%|
|AgentBoard: An Analytical Evaluation Board of Multi‑turn LLM Agents|arxiv.org/abs/2401.13178|按子目标划分 easy/hard 难度；提出进度率度量指标|
|τ²‑Bench: Dual‑Control Environment|arxiv.org/abs/2506.07982|双控制器架构 + 组合式任务生成器，实现可控复杂度|
|Easy2Hard‑Bench: Standardized Difficulty Labels|arxiv.org/abs/2409.18433|难度标签标准化，NeurIPS 2024|
|Benchmarks as Microscopes: A Call for Model Metrology|arxiv.org/abs/2407.16711|将难度定义为可测量的模型属性|
|Curriculum RL from Easy to Hard|arxiv.org/abs/2506.06632|从易到难的课程式强化学习训练范式|
|Cheap Reward Hacking Detection|arxiv.org/abs/2606.08893|面向验证器侧的难度研究、奖励欺骗检测|
|Do Agent Benchmarks Measure Capability? Protocol Validity|arxiv.org/abs/2607.22368|奖励欺骗等价于基准验证失效问题|
|World Feedback for Clinical Agents (MAB‑v3)|arxiv.org/abs/2607.01470|临床Agent环境加难，性能天花板分析|
|EnviSAgE: A Survey of Environment Scaling|arxiv.org/abs/2511.09586|环境扩难综述，提出GEF三阶段循环|

## 二、环境 & 任务合成论文/框架总表
|论文/框架|分类|核心贡献（规模/方法）|时间/出处|链接|
|---|---|---|---|---|
|Agent‑World|环境合成|2000+真实环境、20大类、19K+工具；工具依赖图；可执行解合成可验证任务；GRPO+自演化竞技场|2026‑04|https://arxiv.org/abs/2604.18292|
|EnvScaler|环境合成|程序化合成工具交互环境；SkelBuilder+ScenGenerator；191 envs / ~7K 场景；SFT后BFCL‑MT +8.67|2026‑01|https://arxiv.org/abs/2601.05808|
|Agent‑World Model(AWM)|环境合成|代码驱动+数据库支撑全合成环境管线；1000 envs /10000 tasks /35 tools|2026‑02|https://arxiv.org/abs/2602.10090|
|InfiniteWeb|环境合成|可扩展Web环境自动合成；统一规格+测试驱动开发，面向GUI Agent训练|2026‑01|https://arxiv.org/abs/2601.04126|
|ToolVerse|环境合成|422个真实MCP环境 /4438工具；工具依赖图+Dynamic Unlocking；长程TIR|2026‑07|https://arxiv.org/abs/2607.15660|
|SPADE|环境合成|自博弈：环境设计者生成Gym式可执行环境 ↔ 推理Agent求解，环境与能力协同进化|2026‑08|https://arxiv.org/abs/2608.19197|
|CuES|环境合成|好奇心驱动、环境锚定任务合成；兼容AppWorld/BFCL/WebShop，无需人工种子|2025‑12|https://arxiv.org/abs/2512.01311|
|EnvFactory|环境合成|可执行环境合成；拓扑感知图引导鲁棒RL与轨迹生成|2026‑05|https://arxiv.org/abs/2605.18703|
|Qwen‑AgentWorld|环境合成|语言世界模型模拟通用Agent环境|2026‑06|https://arxiv.org/abs/2606.24597|
|ScaleEnv|环境合成|从零扩展通用工具使用环境，支持可执行验证|2026|arxiv.org/search/?query=ScaleEnv|
|GenEnv|环境合成|难度对齐，Agent‑环境模拟器协同进化，在能力边界生成任务|2025|arxiv.org/search/?query=GenEnv|
|Tool‑R0|经验/交互合成|生成器‑求解器自博弈共进化；零训练数据自举工具调用|2026‑02|https://arxiv.org/abs/2602.21320|
|DreamGym|经验/交互合成|推理式经验模型合成多样化经验；低成本在线RL、sim‑to‑real|2025‑11 / ICLR2026|https://arxiv.org/abs/2511.03773|
|Grounded Interaction Synthesis|经验/交互合成|基于真实环境模拟人‑助手长程交互轨迹，包含对抗约束|2026‑06|https://arxiv.org/abs/2606.02001|
|WebArena‑Infinity|Web/GUI合成|多Agent流水线(coding+browser agents)生成可验证Web环境；10 envs /1260 tasks|2026|https://github.com/web‑arena‑x/webarena‑infinity|
|ScaleWoB|Web/GUI合成|高保真跨平台GUI交互环境合成；可验证奖励，低资源开销|2026‑05|https://arxiv.org/abs/2605.25160|
|GUI‑Genesis|Web/GUI合成|从真实应用重建轻量Web环境；可验证奖励，GUI Agent后训练|2026|arxiv.org/search/?query=GUI‑Genesis|
|Weblica|Web/GUI合成|可复现可扩展交互式Web环境框架；面向视觉Web Agent训练|2026‑05|https://arxiv.org/abs/2605.06761|
|ScaleCUA / VeriGen|Web/GUI合成|可验证任务合成+高效在线RL扩展计算机使用Agent|2026‑07|https://arxiv.org/abs/2607.11185|
|FaraGen(Fara‑7B)|Web/GUI合成|基于高频网站生成多步Web任务数据系统|2025‑11|https://arxiv.org/abs/2511.19663|
|FaraGen1.5(Fara‑1.5)|Web/GUI合成|环境+求解器+验证器三组件，可扩展CUA数据管线|2026‑06|https://arxiv.org/abs/2606.20785|
|OS‑Genesis|Web/GUI合成|反向任务合成：先探索再构造任务，产出GUI Agent轨迹|2024‑12 / ACL2025|https://arxiv.org/abs/2412.19723|
|HATS|Web/GUI合成|难度感知轨迹合成；适配AndroidWorld/WebArena|CVPR2026|arxiv.org/search/?query=HATS+trajectory+synthesis|
|Terminal‑Bench(TB2)|终端/编码环境|可验证CLI任务基准+Harbor；TB2版本89个任务|2026‑01 / ICLR2026|https://arxiv.org/abs/2601.11868|
|CLI‑Universe|终端/编码环境|可验证任务合成引擎；6K轨迹；Qwen3‑32B在TB2得分33.4%|2026‑06|https://arxiv.org/abs/2606.22883|
|SETA|终端/编码环境|终端环境扩展；400个TB兼容RL环境、数据集与训练管线|2026‑07|https://arxiv.org/abs/2607.10891|
|TerminalWorld|终端/编码环境|逆向真实终端依赖构建可执行沙箱+环境合成|2026‑05|https://arxiv.org/abs/2605.22535|
|ResearchEnvBench|终端/编码环境|面向科研代码执行环境合成基准；依赖解析、版本对齐、分布式场景|2026‑03|https://arxiv.org/abs/2603.06739|
|AI Scientist via Synthetic Task Scaling|终端/编码环境|合成ML挑战任务，兼容SWE‑Agent；主题采样+数据集提案+代码生成|2026‑03|https://arxiv.org/abs/2603.17216|
|SWE‑Factory|终端/编码环境|自动issue‑resolve数据集工厂；SWE‑Builder+exit‑code评分+fail2pass|2025‑06|https://arxiv.org/abs/2506.10954|
|SWE‑smith|终端/编码环境|任意Python仓库生成SWE‑gym；128 repos产出50K任务实例|NeurIPS2025|arxiv.org/search/?query=SWE‑smith|
|R2E‑Gym|终端/编码环境|程序化环境生成+混合验证器，开源SWE‑Agent权重|COLM2025|arxiv.org/search/?query=R2E‑Gym|
|SWE‑World|终端/编码环境|无Docker的SWE Agent学习替代环境|2026|arxiv.org/search/?query=SWE‑World|
|SWE‑Universe|终端/编码环境|自动化管线构建百万级可验证SWE环境|2026|arxiv.org/search/?query=SWE‑Universe|
|daVinci‑Env|终端/编码环境|大规模开放SWE环境合成|2026‑03|https://arxiv.org/abs/2603.13023|
|DockSmith|终端/编码环境|规模化可靠编码环境；Dockerfile、测试脚本自动化构建|2026‑02|https://arxiv.org/abs/2602.00592|
|TerminalTraj|终端/编码环境|Docker化终端Agent大规模轨迹生成，5K实例|2026|arxiv.org/search/?query=TerminalTraj|
|ARE / GAIA2|模型基仿真|Meta Agents Research Environments；可扩展环境创建平台+异步基准GAIA2|2025‑09|https://arxiv.org/abs/2509.17158|
|Chimera|模型基仿真|多Agent企业威胁仿真；环境+角色模拟|2025‑08 / NDSS2026|https://arxiv.org/abs/2508.07745|
|WebWorld|模型基仿真|大规模自回归Web世界模型，预测下一UI状态|2026‑02|https://arxiv.org/abs/2602.14721|
|Code2World|模型基仿真|GUI世界模型；代码渲染预测下一UI状态|CVPR2026|arxiv.org/search/?query=Code2World|
|VirtualEnv|模型基仿真|开源模拟平台；程序化任务生成+游戏式机制|2026|arxiv.org/search/?query=VirtualEnv|
|ProPlay|模型基仿真|程序化世界模型；过程级预演+过程图，自演化LLM Agent|2026‑06|https://arxiv.org/abs/2606.12780|
|TaskCraft|任务/场景合成|自动生成Agentic任务；~36K任务，多类工具依赖|2025‑06|https://arxiv.org/abs/2506.10055|
|Graph2Eval|任务/场景合成|知识图谱驱动多模态任务生成；文档理解+Web交互；1319任务|2025‑10|https://arxiv.org/abs/2510.00507|
|SimpleQA→DeepResearch|任务/场景合成|Explorer–Formalizer–Challenger迭代任务演化；500个可验证深度研究任务|2026‑08|https://arxiv.org/abs/2608.02163|
|AgenticDataBench|任务/场景合成|技能聚类+LLM任务生成构建数据Agent基准|2026‑07|https://arxiv.org/abs/2607.01647|
|ART|任务/场景合成|医疗Agent四阶段任务生成管线；EHR失败模式挖掘+LLM+医生审核|2026‑01|https://arxiv.org/abs/2601.08988|
|ACuRL|任务/场景合成|自主课程RL；环境探索‑课程生成‑持续适配，零人工数据|2026‑02|https://arxiv.org/abs/2602.10356|
|State2State|任务/场景合成|从环境探索状态导出中间训练任务，状态匹配验证|2026‑08|https://arxiv.org/abs/2608.04934|
|SESA|任务/场景合成|自博弈搜索Agent；出题者‑求解者架构，不需要外部题库|2026‑07|https://arxiv.org/abs/2607.29468|
|Gym‑V|任务/场景合成|179个程序化视觉环境、10个领域，难度可控|2026|arxiv.org/search/?query=Gym‑V|
|InternAgentHarness (BOOTCAMPCLI)|任务/场景合成|四层环境定义，自动转换训练范式Harness|2025‑08|https://arxiv.org/abs/2508.08636|
|AgenticAI‑Supervisor|平台/基建/方法论|UI驱动仿真引擎；千路并行隔离轨迹，模拟即创作|2026‑07|https://arxiv.org/abs/2607.05773|
|ClawGym II|平台/基建/方法论|黑盒RL对接真实Agent Harness(OpenClaw/Claude Code)；30任务|2026‑08|https://arxiv.org/abs/2608.16798|
|OccuBench|平台/基建/方法论|语言环境模拟真实职业任务；多学科、异步设定|2026‑04|https://arxiv.org/abs/2604.10866|
|AgentGym2|平台/基建/方法论|去理想化真实环境评测框架；27个领域|2026‑07|https://arxiv.org/abs/2607.05174|
|TUA‑Bench|平台/基建/方法论|通用终端Agent基准；120任务/5大类|2026‑06|https://arxiv.org/abs/2606.28480|
|AgencyBench|平台/基建/方法论|138任务/32场景；百万token级长程上下文|2026‑01|https://arxiv.org/abs/2601.11044|
|Hierarchy of Agentic Capabilities|平台/基建/方法论|真实RL环境下Agent能力层级评估|2026‑01|https://arxiv.org/abs/2601.09032|
|Efficient Benchmarking of AI Agents|平台/基建/方法论|8套Agent基准的采样效率研究|2026‑03|https://arxiv.org/abs/2603.23749|
|OSGym|平台/基建/方法论|支持1024并行沙箱的CUA训练基础设施|2025|arxiv.org/search/?query=OSGym|
|EnvHarness|平台/基建/方法论|可编程层包装静态环境，加速Agent学习，不新建环境|2026|arxiv.org/search/?query=EnvHarness|
|Harbor‑Index 1.0|平台/基建/方法论|6627候选过滤得到82任务；难度过滤+AI/人工审计加固流水线|2026‑07|https://harbor‑index.org/|
|Environment Scaling Survey|平台/基建/方法论|GEF循环（生成‑执行‑反馈）统一环境扩展综述|2025‑11|https://arxiv.org/abs/2511.09586|

## 三、代表性工作要点摘要（精简版）
|工作|方法|规模/实验结果|
|---|---|---|
|Agent‑World（智源/TARS）|工具依赖图+可执行Python解任务合成，难度可控；多环境闭环RL+GRPO；自演化竞技场|2000+环境/20类/19K+工具；8B/14B训练后超越多个闭源模型|
|EnvScaler（人大 2601.05808）|SkelBuilder(环境骨架：可执行程序+文档+工具接口，双Agent评估)+ScenGenerator(场景/任务/终态校验函数)|191环境/~7K场景；SFT后BFCL‑MT +8.67、ACEBench‑Agent +11.57|
|InfiniteWeb(2601.04126)|可扩展Web环境合成，面向GUI Agent域内泛化|合成网站迁移到真实网页做泛化测试|
|Agent‑World Model(2602.10090)|无限合成环境Agentic RL|与τ‑bench、MCP‑Universe做对比实验|
|ToolVerse(2607.15660)|大规模工具环境+长程任务|422环境；实验证明环境多样性收益大于增加rollout数量，BFCL‑v3/τ²‑Bench显著提升|
|AgentDrive(2601.16964)|LLM Prompt生成JSON驾驶场景|30万驾驶场景|
|Agentick(2605.06869)|程序化生成37任务，Gymnasium接口+oracle策略+SFT数据|通用序贯决策评测|
|Survey: Scaling Environments for LLM Agents(2511.09586)|提出GEF loop：任务生成‑执行‑反馈，统一分类框架|环境中心视角综述|
https://github.com/ktwu01/benchmark-radar
https://github.com/huggingface/Repo2RLEnv
