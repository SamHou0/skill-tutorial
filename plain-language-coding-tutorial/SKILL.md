---
name: plain-language-coding-tutorial
description: >-
  Use this skill whenever the user asks to learn, understand, create, write, expand, or adapt a programming tutorial, coding lesson, or explanation—even for a broad, topic-only request with no project specified. Invent a relevant small project and let each project need introduce the next concept just in time. Assume the learner knows none of the named topic unless they explicitly say otherwise; explain prerequisites before using them. Weave learner-owned code tasks and “没有傻问题” answers through the project. Keep the skill's teaching recipe language-agnostic; specialize syntax only in the tutorial examples. When writable filesystem access is available, deliver a directly openable, self-contained HTML tutorial plus starter code files—not Markdown alone—with exercise and think-question answers folded. This creates a tutorial artifact, not live Socratic tutoring where the user writes one tiny step at a time.
---

# Plain-Language Coding Tutorial Writer

Create complete, approachable coding tutorials that help a learner understand what the code does and practice using it. Prefer clear everyday language over jargon, but keep the technical explanations accurate. The tutorial should feel respectful and practical, never childish.

## Decide the scope without creating friction

- Follow the user's requested language, programming language, topic, level, environment, length, and format.
- If the learner's level is not stated, assume they are new to the specific topic—not necessarily new to all programming. Use clues in the request to calibrate, and state a short assumption when it matters.
- Treat a topic named in the request as the thing to teach, not proof that the learner already understands its building blocks. Unless they explicitly state prior knowledge, start that topic from its foundations and define each term before first use. Use any stated background as a comparison aid, not as permission to skip the requested concept.
- If the user gives only a topic, invent a suitable small project and write the complete tutorial around it. Do not ask the user to propose a project or turn a simple request into an intake questionnaire.
- Ask a focused question only when a missing choice would materially change the tutorial or make its examples unusable (for example, the user names two incompatible frameworks but does not say which one they use). Otherwise, proceed and disclose assumptions.
- Keep the goal small enough to teach well. For a broad topic, choose a useful first milestone and say what is—and is not—covered.
- If writable filesystem access is available, deliver a tutorial bundle by default unless the user explicitly asks for chat-only or Markdown. Put it in a new topic-named folder under the current workspace, or use the user's requested destination. Do not overwrite existing files; choose a fresh folder name if needed.
- If filesystem access is unavailable, provide the tutorial as complete HTML source (not Markdown pretending to be HTML) and show any starter code files as separate code blocks.
- This skill produces a finished written tutorial. If the user explicitly wants a live, one-step-at-a-time practice session, switch to that interaction style instead of dumping the full solution.

## Keep the teaching recipe language-agnostic

The skill's instructions describe a teaching method, not a preferred programming language, framework, runtime, or API. Keep that method general. Let the user's request determine which syntax and tools appear in the tutorial; don't hard-code a language-specific sequence or make one language the default. Language-specific terms and syntax belong in the learner-facing tutorial examples and evaluation cases, not in the general recipe.

## Teach in plain language

- Explain the idea before introducing its syntax: what problem it solves and what the learner should notice.
- Use short sentences and familiar words. Define unavoidable technical terms the first time they appear; do not assume that renaming a term with an analogy explains it.
- Use an analogy only when it clarifies the real mechanism. Briefly say where the analogy stops matching reality when that distinction could mislead.
- Introduce one new idea at a time. Connect each code change to its effect, rather than pasting a large unexplained block.
- Plain language is not shorthand: explain the idea fully in familiar words. Short sentences are welcome, but do not compress several reasoning steps into one sentence or a bare list of definitions.
- Explain why important lines are present and what changes when the learner edits them. Do not waste space explaining punctuation the learner already knows.
- Treat mistakes as normal. Show likely errors and a practical way to diagnose them when useful.
- Avoid unexplained jargon, motivational filler, and claims that a concept is “easy.” Do not talk down to the learner.

## Teach thoroughly, with purposeful repetition

Default to a real lesson, not a terse reference answer. When the user asks to understand a topic, take enough space to walk them through it; do not optimize for brevity unless they explicitly ask for a quick summary. For a broad topic, choose a manageable set of core ideas and teach those deeply rather than name-dropping many ideas without explaining them.

Give every core concept its own small teaching sequence inside the growing project. As appropriate to the concept, move through these steps instead of compressing them into one paragraph:

1. **Need:** Show the situation or problem that makes the concept useful.
2. **Intuition:** Offer a plain-language mental model or analogy; explain its limit if it could mislead.
3. **Exact meaning:** Name the technical term and define what it does precisely.
4. **Small project code:** Add only the code needed for this step to the evolving project. Explain each meaningful line and why it is there; do not front-load a large solution or several new concepts at once.
5. **Learner contribution:** Hand the learner a small, concrete part of the project to complete—such as filling a condition, adding one handler, or changing a loop. State what to edit and how to check it. If the task needs code, provide a linked starter file with a clear `TODO` rather than only placing the exercise at the end.
6. **Observe and reveal:** Show the expected result and explain why it happens. Put the answer, hint, or worked solution in a collapsed section in the HTML deliverable.
7. **Connect and revisit:** Tie the idea back to the project and a previous step, then recall it in a later task or project milestone.

Use this sequence for each major concept, not just once at the start. If related terms are easy to confuse, teach each one separately first, then compare them. A full lesson should include a learner-owned project task or thinking prompt inside every major concept section; a final exercise list alone is not enough. Do not solve every step for the learner: the project should advance partly through their own small contributions, with folded answers available when they get stuck.

Repeat important ideas deliberately: first build intuition, then use the idea in the project, retrieve it in a question, apply it to a changed case, and recall it in the recap. Change the representation or project state each time so repetition strengthens memory instead of copying the same explanation verbatim. Keep the main practice woven into project stages; an optional final challenge can extend the project, but do not dump all exercises into a single section at the end.

## Let the project set the teaching pace

The learner should feel that each new idea arrives because the project now needs it. Do not begin with a survey of all requested terms and then attach a project afterward. Start with the project goal and its simplest initial state; introduce a concept only when the next feature or obstacle calls for it.

Keep the opening focused on the project, not a glossary. The title, hero, first paragraph, and any navigation should describe the situation, desired result, or next action; do not define or enumerate the requested concepts there. Do not write a “today we will learn A, B, and C” list before the first project step. In a contents list, use project actions rather than a list of APIs or terms. Name and explain each concept in the milestone where the project first needs it.

For each milestone, use this order:

1. Show the current project state and the next small feature the learner wants.
2. Explain the immediate problem in ordinary language and ask the learner to predict what the program needs to do.
3. Introduce only the concept needed for this feature. Assume no prior knowledge of that concept: explain its purpose, intuition, exact meaning, and syntax before relying on it in code.
4. Add a small code fragment to the existing project and walk through the meaningful lines and visible result.
5. Give the learner a concrete TODO to complete in the project. Provide a starter file with all earlier stages already in place and only the current step unfinished.
6. Show how to run/check the step. Keep hints and answers folded in the HTML, then connect the result to the next project need.

Do not use a requested or prerequisite term in code before teaching what that term means. Derive the prerequisite path from the actual topic: show the project need, establish the simplest model that explains it, then introduce each piece of syntax immediately before the project uses it. Explain how the pieces fit when the project is complete. Do not front-load a code listing that uses every concept the learner asked about.

## Add “没有傻问题” callouts throughout

Anticipate questions a learner may hesitate to ask and answer them kindly at the point where they arise. In each substantial project phase, add a visible callout headed **“没有傻问题”** with one plausible learner question and a direct, plain-language answer. For example, ask why the program needs to keep this value in a name or what the learner should expect if a result is not ready yet. Use questions that address actual confusion in this step, not filler. Never imply the question is foolish. Keep the answers concise enough to preserve the project rhythm, but complete enough to resolve the misconception.

## Use a lively, learner-centered teaching voice

Use the books in the current workspace as inspiration for broad teaching principles, not as a script to imitate. Their strongest transferable habits are direct conversation with the learner, curiosity-led openings, concrete recurring examples, visual explanations close to the relevant text, small experiments, purposeful repetition, and practice that asks the reader to think rather than only read.

- Open a full tutorial with a concrete goal, puzzle, or likely learner question. Give the reader a reason to care before presenting terminology.
- Speak to the learner directly and naturally. Use questions to surface a real prediction or misconception, then answer them in the tutorial; do not leave a written lesson waiting for a chat reply.
- Make one small, complete project the spine of the tutorial. If the user gives only a topic, invent a relatable project with a visible result; do not ask the user to propose one. Introduce the project briefly, then build it from a tiny first step toward a working final version.
- Split the project into small milestones. Each milestone should introduce one main concept, add a small code fragment, and then combine naturally with earlier fragments. Do not open with a dense overview of all terminology or advanced concepts, and do not show the entire finished program before the learner has built it up; begin with the first useful step.
- Let the learner solve part of the project at each milestone: predict a result, fill a TODO, fix a bug, or implement one small behavior. State the exact file and location to edit, the expected result, and how to check it. Put these tasks throughout the build; do not reserve all practice for an end-of-lesson exercise dump.
- After each learner task, provide a short hint and a worked answer in a collapsed HTML section. The visible question stays in the lesson; the answer should remain hidden until opened.
- Place code, output, and explanation near one another. Use a compact diagram, table, timeline, before/after view, or ASCII flow when it clarifies a relationship; processes and data relationships usually benefit from one. In text-only output, do not pretend an image exists.
- Revisit important ideas in a new form—such as a prediction, a changed example, or an exercise—when repetition reinforces understanding. Do not repeat paragraphs just to make the lesson longer.
- Anticipate the learner's next question with a brief “what if?” explanation or troubleshooting note at the point where it becomes relevant.
- Let the voice be warm, curious, and a little playful. Unless the user asks for a formal tone or the subject is sensitive, include at least one short, original, topic-relevant humorous aside in every substantial tutorial; one or two is enough. Put it beside the concept it lightens. Do not rely only on a playful scenario to supply the humor, and never make the learner or their confusion the joke. Avoid forced puns, fake urgency, and a childish tone.
- Follow requests for a formal, concise, or otherwise specific voice. Keep the teaching active and clear without forcing humor or fictional details that conflict with the requested tone.
- Borrow no distinctive sentences, jokes, characters, storylines, examples, or page/layout conventions from the books. Create original wording and examples while preserving technical accuracy.

For example, a useful checkpoint is: “先猜一下：如果把这个金额从 12 改成 8，下一步会显示什么？先想一想，再看运行结果。” Follow it with the result and the reason, rather than leaving the question unanswered.

## Default tutorial structure

Adjust the headings to the request, but do not omit teaching depth just to make the page short. Start directly with the tutorial; do not add a generic “适合谁” audience section or long preface unless requested. A full tutorial will usually include:

1. **Title and project hook** — frame the title around the project's question or visible result. Start with the situation and what the project needs next; don't list or define the requested technical terms in the opening.
2. **Minimal setup** — only prerequisites and run instructions needed for the first step.
3. **Progressive project milestones** — first show what the current project needs next; then introduce the concept that solves that need, add a small snippet, explain it fully, and give the learner a concrete part to complete before moving on. Place a relevant “没有傻问题” callout in each major phase.
4. **Integration step** — combine the snippets into the complete working project and show the expected result.
5. **Optional final challenge** — extend the project with one or two tasks if useful; include checks and graduated hints.
6. **Collapsed answers and recall** — keep answers hidden by default; recap the concepts in fresh wording and ask the learner to retrieve or apply them.

If the user asks for a short lesson, honor that request while preserving the same teaching loop for fewer concepts. “Complete” means the learner has enough context to understand and apply the selected ideas; it does not mean covering every related concept.

## Deliver a usable HTML tutorial bundle

When the filesystem is writable and the user has not explicitly requested chat-only or Markdown output, the deliverable is a small folder—not a lone `.md` file. Create a fresh topic-named folder in the workspace (or use the requested destination) with:

```text
<topic>-tutorial/
├── tutorial.html
└── starter/
    ├── step-01.<ext>
    └── step-02.<ext>
```

- `tutorial.html` must be real, valid, UTF-8 HTML that opens directly in a browser. Include `<!doctype html>`, `lang`, a UTF-8 charset declaration, responsive viewport, and embedded CSS. Do not rely on external resources or a server just to read the tutorial.
- Render the lesson as semantic HTML (`h1`/`h2`, paragraphs, lists, `<pre><code>`, links), not Markdown text pasted into a `<pre>` block.
- Keep every “想一想” answer, exercise hint, exercise answer, and full final-project solution collapsed by default with `<details><summary>...` blocks. Keep the prompt/task visible; hide only its answer or help.
- For each code-fill task, create a matching starter file in `starter/` with the project context and clear `TODO` comments, but without the filled-in solution. If steps build on each other, each later starter should include the earlier completed state and leave only that step's task unfinished.
- Link each starter file from the corresponding project step using a relative link. Explain how to open/run it and how to check the result. Put the completed project code in a collapsed solution section in the HTML; do not leak it into the starter file.
- Do not overwrite existing files. If the destination already exists, choose a fresh sibling folder name or ask before replacing it.
- If filesystem access is unavailable, provide the complete HTML source and starter code as separate outputs in chat, and say that you could not save the files. If the user explicitly asks for Markdown, honor that format but still use `<details>` for folded answers where supported.
- In the chat response, give a short summary and direct links to `tutorial.html` and the starter folder/files. Do not claim the HTML was browser-tested unless you actually opened it.

The HTML should feel like a lesson the learner can follow in sequence, not a reference page: first screen introduces the project and the first small action, while later details and answers stay collapsed until needed.

## Make examples and exercises dependable

- Keep the tutorial's code internally consistent: names, files, imports, versions, commands, and expected output must agree from start to finish.
- Prefer the smallest set of dependencies that teaches the goal. Do not invent an API, package, command, or test result.
- When a lesson says code is runnable, make it runnable. Label partial snippets and show where they belong. Avoid leaving unexplained placeholders such as `...` in code the learner is expected to run.
- For a code-fill task, make the starter file a useful scaffold with the surrounding project code and explicit `TODO` markers; do not put the completed answer in the starter.
- Before finishing an HTML bundle, verify that every relative starter link points to a real file, the HTML has no unresolved placeholders, and every answer/solution is inside a closed-by-default `<details>` element.
- Make exercise checks match the taught behavior. For nondeterministic examples (such as random numbers), test stable properties or use a fixed seed instead of promising one exact output.
- If you have not actually executed code, do not claim that you tested it. Still reason through the examples and flag any environment-dependent assumptions.
- Distinguish an exercise's sample test cases from a claim that the code has been automatically tested.
- When the user provides source material, use it only as relevant context, explain ideas in original wording, and avoid reproducing long passages. Do not invent page numbers or citations.

## Final quality check

Before sending the tutorial, check that:

- the explanation matches the user's background and requested language;
- each core concept is broken down into a full, understandable sequence instead of being summarized too quickly;
- a relevant scenario is invented and revisited when the user did not supply one;
- the tutorial builds one complete small project in stages and does not front-load advanced concepts or present all exercises only at the end;
- each stage introduces the project need before the concept that solves it, and no requested-topic term appears in code before it is explained;
- the title, hero, opening paragraph, and navigation do not preview or define a list of future technical terms before the project needs them;
- the named topic is taught from its foundations unless the user explicitly establishes prior knowledge;
- each substantial project phase includes a kind, relevant “没有傻问题” callout that answers a plausible learner question;
- thinking prompts and small tasks appear throughout the lesson, with answers and reasoning included;
- key ideas return in varied forms so repetition aids recall rather than adding filler;
- if the requested tone is not formal or sensitive, the tutorial contains at least one explicit, original humorous aside—not just a playful scenario—and it does not distract from learning;
- each new concept is introduced before the learner needs it;
- the example can be followed from setup to expected result, with file boundaries and commands clear;
- every exercise is solvable using the material taught (or clearly identifies what is new);
- the project grows one concept at a time, with learner tasks embedded in its milestones rather than gathered only at the end;
- the tutorial starts directly with the project/problem rather than a generic audience preface;
- when filesystem access is available, `tutorial.html` is real, readable HTML and each code-fill task has a linked starter file;
- there is no generic “适合谁” preface unless the user asks for it; the lesson starts with the project/problem;
- answers to “think about it” prompts, exercises, hints, and the complete solution are collapsed by default in the HTML;
- the starter files contain only the earlier completed project state plus clear TODOs for the current learner task, not the filled-in answers;
- checks or test cases are specific enough to verify the exercise;
- hints help without immediately giving everything away;
- the answer key, if present, actually satisfies the exercise requirements; and
- the tutorial stays within the requested scope and is easy to scan.
