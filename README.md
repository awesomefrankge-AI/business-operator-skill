# business-operator · 商业操盘手 Skill

> 一个 Claude Code Skill：把三节课《商业操盘手培养计划》（黄有璨，2019-2020）的方法论蒸馏成 AI 可直接执行的诊断-建模-规划-管理工作流，并做了 2026 AI 时代修订。

[![Claude Code Skill](https://img.shields.io/badge/Claude%20Code-Skill-blueviolet)](https://docs.claude.com/en/docs/claude-code)
![Language](https://img.shields.io/badge/lang-中文-red)
![Source](https://img.shields.io/badge/source-96%20videos%20%2B%208%20docs-informational)

## 它解决什么

课程把"执行者 → 操盘手"的坎归结为五类障碍，本 skill 让 Claude 以**操盘手参谋**身份逐一应对：

| 你的痛 | Claude 会做什么 |
|---|---|
| 老板听不懂我 / 理解不了老板的决策 / 老板抛了个问题 | 判断老板在五层逻辑的哪一层，按层给答案；用 4 个决策工具解释老板的逻辑 |
| 说不清公司或客户的业务怎么增长 | 用 **1 个基本逻辑 + 4 个问题 + 3 个额外思考** 梳理全局业务模型，推出可驱动的收入公式和发力点 |
| 规划不靠谱：大而空或全是细节 | 四类目标分类 → 前提保障 + 进攻叠加 + 约束 → 分支预期 → 杠杆 → 按月/季的规划表 |
| 做了一堆 0→1 无一成功，还不知道为什么 | 三层假设 → 找权重最高的假设 → **定量 vs 变量（变量 ≤2）** → 最轻 MVP → 明明白白地证实/证伪 |
| 团队拿不到结果 | 目标拆到人 → 周节奏 → 复盘；5A 汇报 / 1on1（三长两短、PLAN）/ IDP + 九宫格 / EDAC 带人 / 团队四阶段 |
| 见识少，方案在小圈子打转 | 常见业务模型分类库 + 跨界借鉴三步法 |

**核心信条**：到了一定规模，一家公司的经营管理必须模型化；管理 = 控制公式里的变量；用模型和数字跟高层对话最经济。

## 安装

```bash
git clone https://github.com/<you>/business-operator-skill.git ~/.claude/skills/business-operator
```

Claude Code 启动后自动识别（`~/.claude/skills/` 下任何含 `SKILL.md` 的目录）。也可放到项目级 `.claude/skills/business-operator/`。

## 用法

直接用自然语言说业务问题，skill 会自动触发；或显式 `/business-operator`。

```
帮我梳理 XX 公司的业务模型，算一下收入公式，看哪里最有增长空间
老板让我"明年在这个品类做到行业第一"，帮我拆成规划
我负责一个从 0 起步的新业务，帮我列价值假设和 MVP
客户老板问我们怎么用 AI 做增长，我该怎么回答
帮我做 Q3 复盘 / 帮我准备和下属的 1on1 / 帮我写 5A 汇报
```

Claude 会先用 1-3 个问题定位（公司阶段 / 你的角色 / 业务是否成型），再输出填好的表格模板，不输出"流量→转化→付费"级别的空框架。

## 目录结构

```
business-operator/
├── SKILL.md                      # 路由表 · 十条铁律 · 六个标准工作流（含顾问模式）
├── references/
│   ├── 00-operator-profile.md    # 操盘手画像、ABC 层级、五类障碍、成长路径、边界
│   ├── 01-executive-sync.md      # 高层同频：CEO 视角、三大模型、六类难点、四个决策工具、五层答案、工作价值
│   ├── 02-business-model.md      # 业务模型：全局/局部、1+4+3、评估、从 0 搭建、组织匹配
│   ├── 03-model-library.md       # 增长/放大/交付保障模型分类库 + 跨界借鉴法
│   ├── 04-planning.md            # 目标制定与拆解、非常规问题、杠杆、三类实例、进度管理
│   ├── 05-exploration.md         # 探索型项目：四步工作逻辑、定量变量、三类项目、三类障碍
│   ├── 06-team-management.md     # 团队管理基本逻辑 + 八大工具
│   ├── 07-ai-era.md              # AI 时代修订层（本 skill 扩展，非课程原话）
│   └── 08-source-notes.md        # 逐章原始笔记（案例细节 / 课程原意查证用）
└── templates/                    # 12 个可直接填写的输出表
    ├── business-model-canvas.md  ├── local-model.md         ├── goal-breakdown.md
    ├── exploration-hypothesis.md ├── boss-question.md       ├── work-value.md
    ├── report-5a.md              ├── retrospective.md       ├── weekly-cadence.md
    ├── one-on-one.md             ├── idp.md                 └── edac.md
```

## AI 时代修订了什么

课程录制于 2019-2020。骨架（模型化思维、1+4+3、定量-变量、目标拆到人）原样保留并标注年份；`references/07-ai-era.md` 单独一层写清变化：

- **成本曲线**：客服 / 销售跟进 / 内容生产 / 交付辅导被 AI 接管后从线性变准指数——判断赛道时多问一句
- **稀缺资源迁移**：内容不再稀缺，独家数据 / 分发 / 信任 / 独家供给才是
- **1+4+3 新增 T4**：哪些环节 AI 化后 input/output 更稳定、把"只有我能做"变成可规模化模型
- **MVP 从周到天**，但定量-变量纪律不变：AI 生成能力本身是变量，别和"用户会不会买"一起验证
- **human + AI 团队**：目标拆到人也拆到 agent；人力盘点加 AI 杠杆率；1on1 和磨合期身先士卒不可外包
- 老板问"怎么用 AI"通常在第 1-2 层：先给可行性和成本收益，不要直接给执行方案

## 制作过程

1. 百度网盘转存 → `api/streaming` 240p 转码流分段下载（绕过限速）
2. 本地 SenseVoice 转写 96 个视频（≈41× 实时，0 失败），`textutil` 提取 8 份讲义
3. 逐章阅读转写稿写笔记（`08-source-notes.md`），再按模块蒸馏成 `references/` 和 `templates/`
4. 叠加 AI 时代修订层

## 边界

- 不适用非市场化、关系导向行业
- 不速成：50→70 分可以，30→80 分不行
- 初级操盘手的合理定位是支持比你强的人掌控全局，不是替代老板
- 80%+ 探索项目会失败，目标是明明白白地失败

## 版权与致谢

方法论与案例来自三节课《商业操盘手培养计划》（出品人黄有璨；加餐讲师王刚、葛昊）。本仓库是个人学习笔记的结构化整理，仅供学习交流，不代表课程官方，请勿用于商业售卖。课程本身请通过三节课官方渠道购买。
