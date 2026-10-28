# AI-PhD.SKILL: Taking the Reviewer's Perspective

[← Index](../../README.md) · [中文原文](5-Perspective-Taking.md) · English

When you no longer know how to improve a paper, try being a reviewer first.

I especially recommend reading a paper outside your narrow specialty where you would still have a confidence level of 3/5 or 4/5. You can judge the problem, logic, and experiments, without knowing the background so well that you unconsciously fill in what the authors left unwritten. Then reread your own paper from the same perspective.

You may notice something interesting. A paper can feel reasonably good without seeming especially novel. But when you actually try to write its weaknesses, you struggle to name a concrete issue that undermines the conclusion beyond a vague “lack of novelty.”

You will probably lean toward a weak accept.

That describes many acceptable papers. They are imperfect and not dazzling in every respect, but they do not leave an obvious hole in the central argument.

## 1. Switch from author to reviewer

Authors and reviewers experience different papers.

The author knows how all the experiments were run, the motivation behind each design, and the three pages of supplementary material, five failed experiments, and domain knowledge behind an undeveloped sentence.

The reviewer does not.

They see only the submitted title, abstract, figures, prose, experiments, and appendix. What you have not explained is effectively unavailable to them. Claims without evidence remain doubtful. Something you assume everyone knows may be unfamiliar to a reader from another area.

When reviewing someone else's work, ask more than whether the method is new:

- Does the problem matter?
- What is the central claim?
- What evidence supports it?
- Why are existing methods insufficient?
- What is the most specific reason I could give for disagreeing with the paper?

Apply the same questions to your own work afterward.

## 2. First remove obvious weaknesses in the argument

Authors often aim to make every part of a paper impeccable. That is admirable but difficult. Time is limited, experiments are noisy, and ideas rarely begin fully formed.

A more practical target is: **do not leave an easy-to-identify flaw that directly invalidates the main argument**.

For example, you claim to address a failure mode without a corresponding case study, or call existing methods inadequate without a fair comparison or reliable reference.

Suppose instead that the reviewer sees a valid problem, a real gap in existing methods, a method aligned with the motivation, and experiments that broadly support the claims. They may not consider it a strong accept, but it becomes difficult to articulate a specific reason to reject it. A weak accept is then often reasonable.

Lack of novelty can certainly be a real concern. But it should be more than a universal negative label. A useful novelty concern should explain which earlier work already covers which part of the contribution, why the remaining difference is unimportant, and why the evidence does not establish a new contribution.

If those points are hard to state, the concern may amount to “I was not impressed,” rather than a weakness sufficient to reject the paper.

## 3. Reviewers get tired too

Imagine that you have a lot of work to do and have also been assigned six papers to review.

The first paper opens with long, complicated sentences. Central claims lack references. Relationships between concepts have no explanatory figure. You do not know whether the authors will explain things later or whether the claims have experimental support. Halfway through, you are already tired.

The second paper is concise and clear. Each important claim has a reference or experiment. A figure explains the central logic behind a complicated concept. You always know which problem is being addressed, why the method might help, and what evidence will follow.

If the underlying research quality is similar, which paper are you more inclined to score highly?

Most people would choose the second.

Peer review is a decision process conducted with limited attention and incomplete information. Clear writing reduces the effort required to understand a paper and the uncertainty involved in judging it. It allows the work's value and evidence to be seen.

Confusing writing consumes that effort on figuring out what the authors mean. Even real results become harder to understand accurately and trust.

With AI reviewing now widespread, this account may not hold in every case. I am still exploring how to respond to that change.

## 4. Making your work easier to understand is part of the job

This applies to publicity, reports, defenses, paper presentations, and conversations with an advisor as well as submissions. Your audience is not an infinitely patient ideal reader who will complete every missing argument for you.

They have deadlines, other responsibilities, and limited energy. An unexplained point can cause them to lose patience.

Communication therefore includes **reducing the effort it takes someone else to understand the idea**.

A few simple practices help:

- State the problem and conclusion before the details.
- Pair important claims with evidence, references, or examples.
- Use figures for complex relationships instead of putting everything into long sentences.
- Anticipate natural questions such as “So what?”, “Why?”, and “What supports that?”

## 5. Use each reading as practice

The next time you do not know how to revise a paper, try this exercise.

Choose a paper from an adjacent field. Before reading its reviews, give yourself half an hour to write down its strongest contribution, most specific weakness, and the score and confidence you would assign as a reviewer.

Then open your own paper and start with the abstract and introduction.

If you would ask another author where the evidence is, what a figure is meant to show, or why a design is necessary, ask yourself the same questions.

Knowing the answer yourself does not mean the reader knows it.

## Applying the perspective

A paper is written for reviewers, readers, collaborators, and the community. An easily overlooked part of writing is to **avoid leaving the entire cost of understanding to others**.

Read other people's papers like a reviewer, then read your own the same way.

You may find that the missing piece is a point that has not been explained, established, or made easy enough to follow, rather than another complicated module.
