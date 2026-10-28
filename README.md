# Plain-Language Coding Tutorial Skill

[中文](#中文) | [English](#english)

---

## 中文

### 这是什么

这是一个可复用的 AI 技能（skill）：把“用大白话写编程教程，附带可运行的代码、思考题和折叠答案”变成可重复执行的工作流。

给它一个主题（例如“帮我讲解 JavaScript 中的异步”），它会自动：

- **自行创设一个贴近日常的小项目**作为教学主线，而不要求你先提出项目；
- **只在项目真正需要时**才引入新概念，从零开始讲清楚 prerequisites、术语和语法；
- 每个概念按“需求 → 直觉 → 精确含义 → 小代码 → 观察结果 → 先猜后答 → 回顾”拆开讲解；
- 在每个阶段穿插“没有傻问题”答疑和读者要动手的小任务；
- 用 `<details>` 折叠思考题答案、提示、练习答案和完整项目代码；
- 默认交付一个可直接打开的 `tutorial.html`，并为每个代码填空任务提供 `starter/` 起始文件；
- 代码示例、运行命令和预期输出相互一致；所有完整示例都实际运行过。

### 适合谁

- 想把“大白话 + 项目推进 + 可验证练习”的教学方式复用到新主题的作者、教师或技术写作者；
- 想要 AI 生成成套的 HTML 教程而非零散 Markdown 的用户；
- 想在自己的 agent / 编辑器环境中复用这套教学流程的人。

### 安装

#### Claude Code

```bash
# 方式一：直接克隆到 Claude Code 的 skills 目录
git clone https://github.com/SamHou0/skill-tutorial.git ~/.claude/skills/plain-language-coding-tutorial
```

#### OpenCode

```bash
# 放到 OpenCode 的 skills 目录
git clone https://github.com/SamHou0/skill-tutorial.git ~/.config/opencode/skills/plain-language-coding-tutorial
```

#### 手动安装

1. 下载或复制 `plain-language-coding-tutorial/` 文件夹到你的 skills 目录；
2. 确保文件夹里至少包含 `SKILL.md`（以及可选的 `evals/evals.json`）；
3. 重启 agent / 编辑器，让它重新加载技能列表。

### 使用

在对话中直接描述你想学或想写的主题，例如：

- “我刚开始学 Python，变量和 if 我总是看了就忘。能不能用大白话给我从头讲讲？”
- “帮我讲解一下 JavaScript 中的异步这个主题，尤其是 Promise 和 async/await。”
- “我刚开始学 Go，slice 和 range 每次看都混在一起。你能从头讲清楚吗？”

skill 会自动：

1. 发明一个贴近日常的小项目；
2. 从项目需求出发，按需引入概念；
3. 生成 `tutorial.html` 和 `starter/` 代码文件；
4. 折叠答案与完整方案，让学习者先想再看。

如果你希望得到 Markdown 而不是 HTML，或希望采用别的结构，直接在对话里说明即可。

### 文件结构

```text
plain-language-coding-tutorial/
├── SKILL.md              # 技能主文件（触发条件与教学规则）
└── evals/
    └── evals.json        # 评测用例与验收标准
```

最终交付给学习者的教程通常形如：

```text
<topic>-tutorial/
├── tutorial.html
└── starter/
    ├── step-01.<ext>
    └── step-02.<ext>
```

### 评测

`evals/evals.json` 里有三个主题-only 的评测用例（Python 变量/if、JavaScript 异步、Go slice/range），每个都包含验收标准。它们用于检查 skill 输出是否满足：项目先行、概念从零讲起、代码任务穿插、HTML + starter、折叠答案、答疑穿插、自然幽默。

### 参考书

本 skill 的教学风格参考了 `Head First` 系列（`Head First Go`、`Head First HTML5 Programming`、`Head First HTML 与 CSS` 第 2 版），但**只借鉴通用教学原则**（项目推进、逐步拆解、思考题、折叠答案、幽默），不复制原文句子、角色、剧情或版式。参考书已归档到 `books/`，该目录被 `.gitignore` 忽略。

---

## English

### What this is

A reusable AI skill that turns “write a plain-language coding tutorial with runnable code, thinking questions, and folded answers” into a repeatable workflow.

Given a topic (e.g. “explain JavaScript async”), it automatically:

- **invents a relatable small project** as the teaching spine instead of asking you to propose one;
- introduces each concept **only when the project needs it**, from foundations up;
- unpacks every concept into “need → intuition → exact meaning → small code → observe → predict/try → connect/revisit”;
- weaves “no stupid questions” callouts and learner-owned code tasks through the project;
- folds think-question answers, hints, exercise answers, and the complete solution in HTML `<details>`;
- delivers a directly openable `tutorial.html` plus `starter/` files by default;
- keeps code, commands, and expected output consistent; all complete examples are actually run.

### Who it is for

- Authors, teachers, and technical writers who want to reuse a “plain-language + project progression + verifiable practice” teaching style on new topics;
- Users who want AI-generated tutorial bundles instead of scattered Markdown;
- Anyone reusing this teaching workflow in their own agent/editor environment.

### Install

#### Claude Code

```bash
git clone https://github.com/SamHou0/skill-tutorial.git ~/.claude/skills/plain-language-coding-tutorial
```

#### OpenCode

```bash
git clone https://github.com/SamHou0/skill-tutorial.git ~/.config/opencode/skills/plain-language-coding-tutorial
```

#### Manual

1. Download or copy the `plain-language-coding-tutorial/` folder into your skills directory;
2. Ensure it contains at least `SKILL.md` (and optionally `evals/evals.json`);
3. Restart your agent/editor so it reloads the skill list.

### Use

Describe the topic you want to learn or write about, for example:

- “我刚开始学 Python，变量和 if 我总是看了就忘。能不能用大白话给我从头讲讲？”
- “帮我讲解一下 JavaScript 中的异步这个主题，尤其是 Promise 和 async/await。”
- “我刚开始学 Go，slice 和 range 每次看都混在一起。你能从头讲清楚吗？”

The skill will:

1. invent a relatable small project;
2. introduce concepts only when the project needs them;
3. generate `tutorial.html` and `starter/` code files;
4. fold answers and the complete solution so the learner thinks first.

If you want Markdown instead of HTML, or a different structure, just say so.

### File structure

```text
plain-language-coding-tutorial/
├── SKILL.md              # Skill definition (trigger + teaching rules)
└── evals/
    └── evals.json        # Evaluation cases and acceptance criteria
```

A delivered tutorial usually looks like:

```text
<topic>-tutorial/
├── tutorial.html
└── starter/
    ├── step-01.<ext>
    └── step-02.<ext>
```

### Evaluation

`evals/evals.json` contains three topic-only cases (Python variables/if, JavaScript async, Go slice/range), each with acceptance criteria. They check that the skill output includes: project-first progression, zero-assumption teaching, interleaved code tasks, HTML + starter files, folded answers, interspersed FAQ callouts, and a natural humorous tone.

### Reference books

The teaching style draws on the *Head First* series (*Head First Go*, *Head First HTML5 Programming*, *Head First HTML and CSS* 2nd ed.), but **only as general teaching principles** (project progression, step-by-step unpacking, thinking questions, folded answers, humor). No sentences, characters, plots, or layouts are copied. The books are archived in `books/`, which is gitignored.