# AI-PhD.SKILL: An Actionable Research Pipeline

[← Index](../../README.md) · [中文原文](1-Research-Pipeline.md) · English

A typical pipeline for entering a research field looks like this:

0. **Choose a broad direction.** Examples include LLMs, multimodal learning, generation, agents, and robotics. This is often the first keyword of a paper.
1. **Choose a specific research area.** Examples include efficient LLM reasoning, long-video understanding, image editing, and multimodal RAG. This is often the second keyword.
2. **Read valuable related work from roughly the past three years.** Build maps of the problems, methods, and evaluation practices.
3. **Select and reproduce a few suitable baselines.** Establish a reliable experimental environment and develop intuition for the field.
4. **Inspect cases, identify possible contributions, and test them.** Many ideas come from failures, boundary cases, and systematic weaknesses of existing methods.
5. **Write the paper and complete the story.** Connect the problem, motivation, method, experiments, and conclusions into a coherent research argument.

Let's go through the process in more detail.

## 0. Choose a broad direction

The first step is deciding on a broad direction, such as:

- LLMs
- Multimodal learning
- Generation
- Efficient AI
- Embodied AI
- Agents
- Robotics
- Medical AI
- AI for science

These categories are still broad, but they determine which academic community you enter, which conferences and papers you follow, which benchmarks you use, and which tools you learn.

Saying “I want to work on LLMs” is only a beginning. LLM research includes reasoning, alignment, agents, tool use, long context, efficient inference, post-training, evaluation, and more. Each has different core questions, experimental practices, and expectations for publication.

At this stage, answer three questions.

**Does the direction have lasting academic value?** Does it address a persistent problem, or does it depend mostly on a short-lived trend or an engineering update?

**Does it fit your resources?** Consider compute, data, existing code, advisors, and collaborators. An idea can be meaningful in principle but too costly for one PhD student to pursue.

**Is there a reasonably clear evaluation framework?** Without stable benchmarks, metrics, or case-study practices, newcomers can easily get stuck in arguments that have no common basis.

The output of this step is a broad direction, along with an understanding of its main conferences, keywords, representative papers, and research communities.

## 1. Choose a specific research area

Next, narrow the direction into a specific area.

For LLMs, that might be:

- Efficient reasoning
- Long-context reasoning
- Tool-augmented LLMs
- LLM agent evaluation
- Test-time scaling
- Multimodal reasoning

For multimodal learning:

- Long-video understanding
- Image editing
- Multimodal retrieval
- Visual instruction tuning
- Multimodal hallucination
- Video-language alignment

For generation:

- Text-to-image generation
- Image editing
- Text-to-3D generation
- Video generation
- Personalized generation
- Controllable generation

The key is choosing the right level of specificity.

Too broad, such as “I want to work on LLMs,” and you will not know what to read, reproduce, compare, or solve. Too narrow, such as “I want to change a small module in this paper,” and you may commit to a local modification before identifying a valuable research question.

A suitable area often has several properties:

- A continuous body of work over the past two or three years.
- Reasonably stable datasets, metrics, or evaluation practices.
- Clear unresolved problems.
- Several strong baselines that can be reproduced.
- Room for improvement that does not depend entirely on large-scale compute.

The output is a second-level keyword and a one-sentence description of the problem the area addresses.

For example:

Efficient LLM reasoning aims to preserve or improve reasoning ability while using fewer tokens, less compute, or less time.

Long-video understanding studies how models answer questions, locate events, summarize, and reason over long videos with multiple events and levels of detail.

Image editing studies how to make local or global changes based on text or other conditions while preserving the original image's identity, structure, and semantic consistency.

If you can write a sentence like this, you have moved from a general interest to a concrete problem area.

## 2. Read related work from the past three years

Reading is essential when entering a field. The important question is whether it builds a structured understanding.

I suggest reading four kinds of papers.

**Foundational papers.** These may be older, but they defined the field's problems, tasks, or basic methods.

**Strong baseline papers.** These tend to have solid experiments, strong performance, and available code. You will likely need to compare against them.

**Papers representing recent trends.** These often come from major conferences, arXiv, or large research groups in the past year or two. They indicate where the community is heading.

**Negative examples.** These are papers whose problem definition, experiments, argument, or contribution you find weak. They help you understand why some work struggles to gain recognition.

Do more than record method details. Build three maps:

1. **Problem map:** Which subproblems are people actually trying to solve?
2. **Method map:** Which approaches do different methods take, and what are their core assumptions?
3. **Evaluation map:** Which datasets, metrics, baselines, and cases are used to establish effectiveness?

For efficient LLM reasoning, for example, ask:

- Is the goal fewer reasoning tokens, lower inference latency, or better use of test-time compute?
- Does the method operate through prompting, decoding, training, or model architecture?
- Does evaluation consider accuracy, token consumption, latency, cost, or the accuracy-cost tradeoff?
- Which tasks does each method succeed or fail on?

It is possible to read twenty or thirty papers and still have no idea what to do. A common reason is the lack of structured synthesis.

The output is a reading table of 20 to 50 core papers, together with the three maps of problems, methods, and evaluation.

## 3. Select and reproduce baselines

After surveying the literature, you do not need to jump immediately to a grand idea. A steadier approach is to select a few appropriate baselines and reproduce them as closely as possible.

You do not need every paper. Focus on three kinds of baselines:

1. **Classic baselines.** They may no longer be the strongest, but they represent the field's basic approach.
2. **Strong baselines.** These perform well and are likely to be requested by reviewers.
3. **Baselines most relevant to your potential idea.** A method close to your problem setting deserves attention even if it is not first on a leaderboard.

Reproduction develops experimental intuition as well as providing numbers for a later table. You gradually learn:

- Which results are stable.
- Which metrics fluctuate.
- Which datasets have quality problems.
- Which experiments are expensive.
- Which codebases have many pitfalls.
- Which improvements are hard to reproduce.
- Which settings strongly affect the results.

Before reproducing a baseline, establish the **evaluation protocol**:

- Which datasets will you use?
- How are training, validation, and test sets split?
- Which metrics matter?
- Is human evaluation needed?
- Is GPT-based evaluation needed?
- Must inference budget, parameter count, or training-data size be controlled?
- Is there data leakage?
- Do the papers use inconsistent settings?

An unstable evaluation protocol makes everything downstream confusing. You may run many experiments and still be unable to convince others that your method is better.

The output is an experimental codebase that runs, can be reproduced and extended, and includes at least two or three credible baseline results.

## 4. Inspect cases, identify ideas, and test them

Many newcomers read papers and immediately start designing methods. That can work, but it is often inefficient. I recommend starting with **case studies**.

Pay particular attention to four kinds of cases:

1. **The baseline succeeds where a simple method fails.** The baseline may be capturing an important mechanism.
2. **The baseline fails on something a person finds easy.** This may expose a clear weakness worth investigating.
3. **Different baselines behave very differently.** Their inductive biases may reveal a useful research question.
4. **The metric improves without a noticeable improvement in case quality.** The evaluation may be flawed, or the method may be exploiting a metric bias.

Good ideas often begin with concrete questions:

- Why did this case fail?
- Did the model miss important context?
- Was it distracted by irrelevant information?
- Did a long reasoning process allow errors to accumulate?
- Were the visual information and language instruction misaligned?
- Was a particular combination missing from the training data?
- Does the evaluation metric fail to capture actual quality?
- Are existing methods only improving easy cases while leaving hard cases unresolved?

An idea begins to take shape when you can organize failures into a stable pattern.

**One case is not yet an idea. A class of cases can be the entry point to one.**

A handful of scattered examples may only show that a baseline has bugs. If you can establish that a category of failures appears systematically in the data and remains difficult for existing methods, it may become a research motivation.

Proceed in this order:

1. Inspect many cases.
2. Identify recurring failure patterns.
3. Form a hypothesis.
4. Design a minimal experiment to test it.
5. Decide whether the hypothesis deserves further investment.

Start with **minimal validation**, before building a complete method.

Suppose you suspect that a long-video model fails because it cannot locate the right keyframes. Run an oracle experiment: does performance improve substantially when you provide the correct frames? A large gain supports investigating that hypothesis. A small gain suggests the main bottleneck may be elsewhere.

If you suspect that LLM reasoning contains redundant tokens, first analyze which tokens actually contribute to the answer. Then investigate compression, skipping steps, or dynamic reasoning.

The output is a central hypothesis supported by case studies and preliminary experiments.

## 5. Develop the contribution

A research contribution needs more than an added module, a new loss, or a combined pipeline. You need to explain **why the contribution is necessary**.

A good contribution usually meets three conditions:

1. **It addresses a real problem.** Support the problem through literature, case studies, or experimental observations.
2. **It differs clearly from existing work.** The difference may lie in problem formulation, modeling assumptions, training strategy, inference strategy, or evaluation protocol.
3. **It can be tested experimentally.** Claims must map to experimental designs. A broad claim cannot rest on evidence for a much narrower point.

Common types include:

- **Problem formulation:** identifying an overlooked problem and proposing a task, benchmark, or evaluation setting.
- **Methods:** introducing an architecture, training objective, inference strategy, data-construction method, or system framework.
- **Analysis:** systematically explaining a phenomenon or failure and proposing a corresponding improvement.
- **Efficiency:** substantially reducing training, inference, data, or annotation cost at comparable performance.
- **Evaluation:** identifying defects in existing metrics or benchmarks and proposing more reliable evaluation.

A common beginner's mistake is focusing too heavily on method novelty while neglecting the importance of the problem and the evidence.

A worthwhile method should support a complete chain of reasoning:

- What is wrong with existing methods?
- Why does that problem occur?
- How does your method address it?
- Do experiments show that it actually does?
- What does the conclusion mean for the field?

The output is a clear contribution statement. For example:

> We find that existing long-video question-answering models are primarily limited by errors in locating key events during temporal reasoning across multiple events. We therefore propose an event-level memory-selection mechanism that improves answers to long-horizon questions without substantially increasing inference cost.

Ideally, this sentence contains the problem, observation, method, effect, and significance.

## 6. Write the paper and complete the story

The final step is constructing a credible research story.

Writing a paper means building an argument:

- The problem matters.
- Existing methods do not solve it well.
- We identified an important cause.
- We proposed a targeted method.
- Experiments show that it works.
- Analysis explains why it works.
- Ablations identify which components matter.
- Case studies show improvements on actual examples.
- Limitations establish where the method's boundaries lie.

The central requirement is **alignment between claims and evidence**.

If your claim is improved reasoning efficiency, report the accuracy-cost tradeoff, not accuracy alone.

If you claim better understanding of long videos, experiments limited to short-video benchmarks cannot establish it.

If you claim reduced hallucination, provide metrics, human evaluation, or case studies that support that reduction.

If you claim generalizability, include experiments across datasets, models, tasks, or settings.

You do not need to include every experiment. Select the evidence that best supports the central argument.

The output is a complete paper draft with an abstract, introduction, method, experiments, analysis, and limitations.

## Bringing the pipeline together

Entering a field requires more than reading many papers. The fuller process is:

1. Choose a broad direction.
2. Narrow it to a specific research area.
3. Build a literature map.
4. Reproduce baselines.
5. Analyze cases.
6. Form hypotheses.
7. Validate the contribution.
8. Organize the work into a research story.

One of the most valuable abilities for a PhD student is a repeatable way to enter new fields, understand problems, identify gaps, test hypotheses, and eventually produce papers.

Research has no completely standardized procedure, but it does have reusable working habits.

This pipeline aims to turn a vague process into something you can carry out, inspect, and improve.
