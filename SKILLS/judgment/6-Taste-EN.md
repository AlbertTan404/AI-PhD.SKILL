# AI-PhD.SKILL: Taste

[← Index](../../README.md) · [中文原文](6-Taste.md) · English

> The god lifted Big Tooth from the ground. The enormous creature struggled in the bright light. “Worm, what do you think is the essence of poetry? Syntax? Imagery? Rhetoric?” Big Tooth shook his immense head. “I don't know. I only know that humans cannot write great rivers…” The god sneered. “Ridiculous mortal! Poetry is nothing more than every possible arrangement of Chinese characters. With our great technology, I shall enumerate them all, write the supreme work of poetry, and encompass every possible beauty in the universe!” To do so, the god consumed every planet and all matter in the solar system except Earth, turning them into a ribbon-shaped nebula covered in writing. The mass of each planet became countless tiny, glowing blocks of text. This immense nebula, breathing in and out the light of the sun, was named the Poetry Cloud.
>
> From *Poetry Cloud* by Liu Cixin. Translation of the passage quoted in the Chinese article.

> My suggestion: adjust your mindset and embrace change, with Ke Jie as a point of reference. At the same time, develop taste and try to become a reasonably good verifier.
>
> Albert Tan, *The Last Year of Homo Sapiens at Top Conferences*

When I first read *Poetry Cloud*, what struck me most was not the god's use of every atom in the solar system. It was the possibility that, technically, the god had a point: given a sufficiently large candidate space, every five-character quatrain would eventually be written. The god's first poem consisted of twenty repetitions of “ah.” Its absurdity exposed the blind spot of exhaustive search immediately. The god could generate everything, yet still did not know what deserved to be called poetry.

Today I want to discuss something I have been thinking about for a long time: taste and verification in the age of agents.

We used to understand creativity as proposing something that did not yet exist. Candidates were scarce. Completing an idea, an experiment, or a paper took substantial time and manual effort. Now the candidates themselves are becoming cheap. Models can produce multiple hypotheses, proposals, implementations, and paper narratives at once, and some of them have real value. The question for many people has become how to decide where to put resources next as the candidate set expands rapidly.

In my own experience, when the task, tools, and evaluator are sufficiently clear, an agent can already carry out a fairly complete research workflow. It can survey the literature, write a proposal, change code, process data, run experiments, read logs, draw figures, revise a paper, and continue searching based on feedback. When a system can propose candidates, use tools, read feedback, and revise its approach with fewer step-by-step human instructions, research execution starts becoming a search process that can scale.

I often see people say that AI generates code too quickly for them to review, so all they can do is approve it. Others probably choose “approve for me.” I think the issue extends further. Approving code lets a change enter the main branch. Approving research lets a set of results support a paper's central claim. Approving work may commit a team's attention and budget to a strategy.

At present, it is hard for a person to read faster than a model generates tokens. Once generation outpaces human review, line-by-line reading stops being a verifier that can scale. In my view, and in my own practice, what needs verification is the task boundary, the constraints that must hold, such as cost, and objective measures showing that the result satisfies those constraints.

As for taste, I see it as more than aesthetics. It is the ability to rank problems, approaches, and evidence under incomplete information, limited resources, and an uncertain future. Someone with good taste asks early: if this problem is solved, who will change what because of it? Is this something that sounds novel but is actually trivial?

A verifier turns that judgment into a checkable mechanism. In research, that includes more than unit tests: data and splits, budget-aligned baselines, multiple seeds, case studies, counterexamples, independent held-out evaluation, and the correspondence between claims and evidence. At work, it might involve user feedback, production metrics, and constraints from the real world.

Taste ranks the options before the bet. Verification tries to falsify the decision after it.

To be continued. Next time, I will discuss the methodology I have in mind.
