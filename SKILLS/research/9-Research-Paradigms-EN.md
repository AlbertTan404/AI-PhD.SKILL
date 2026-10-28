# AI-PhD.SKILL: Research Paradigms

[← Index](../../README.md) · [中文原文](9-Research-Paradigms.md) · English

Papers often present a very smooth sequence: existing methods have a limitation, the authors identify its cause, propose a method, and validate it experimentally. Read enough papers and it is easy to believe that research should happen that way.

In practice, it often does not. Sometimes you identify a problem and then look for a solution. Sometimes you first find a method that works and only gradually understand why. Sometimes the most valuable result is realizing that the original question was not quite right. Today I want to discuss several common research paradigms and what work following each path needs to establish.

I use “paradigm” broadly here to mean where research starts and how it progresses. These paths overlap and can turn into one another. It is hard to assign them a fixed ranking for novelty.

Start with **Evolution**: working from an existing problem and improving on it. Choose a task, such as efficient reasoning, survey related work, identify shared shortcomings, locate the cause experimentally, and then propose a solution. These are often the papers I find most satisfying to read. The reader can understand both why the problem exists and why the method takes its particular form.

The difficult part is identifying the limitation precisely. Saying that existing methods generate too many reasoning tokens is only a starting point. Which tokens can be removed? Under what conditions does redundancy occur? Does reducing the token count actually reduce latency? Those answers determine whether the design has a sound basis. A well-located problem makes the method feel more natural, though you still need to ask how valuable the gap is to close.

**Searching** may be closer to many researchers' daily experience. You have a task and a baseline, and begin trying ideas: change the architecture, add a loss, or use another kind of data. Some attempts fail, others help, and you continue along promising directions. You may not have a complete explanation at first. You may simply feel that a design is worth trying. I think that is normal. Some understanding only becomes available after the experiments.

This kind of work needs storytelling, but storytelling is easy to misuse here. Once you find a method that works, you still need to analyze where the gains come from and when it fails. Ideally, your explanation should predict what will happen in a setting that was not used to select the idea, and you should then test that prediction. A paper can organize the work in an order that is easier to understand without pretending that everything was clear from the beginning.

**Combination** brings ideas from elsewhere into your problem. You read a paper in domain A, find method A interesting, and think it might help in domain B, which you know well. You try the transfer and adapt it to the new task. This can be very clever: two seemingly unrelated fields become connected through a shared problem structure.

The key is to explain that connection. What assumptions does the original method depend on? Does the new domain satisfy them? What is difficult about the transfer? Ablations can help establish the role of each component in the current setting, but the reason for making the combination needs more specific analysis. A good transfer makes the reader see why the two problems can be understood together.

A related path is **Fast Follow**: quickly examining a new method or capability in your own field. Once CoT, GRPO, or a new training approach attracts attention, you investigate its uses. The distinction is mainly about timing. A new result makes something feasible or interesting that previously was not.

Simply running a popular method in another domain offers limited research content. But if the new domain exposes an important limitation, the work can become much deeper. Early papers may attract more attention, yet citations cannot be predicted from timing alone. How much others need your findings, data, or implementation also determines the work's lasting usefulness.

The paths above mostly concern developing a method. Several other forms of research deserve separate attention.

One is **Understanding**: explaining a phenomenon or mechanism. Why does performance fall when the reasoning budget increases? Why does a method work only on one kind of data? You design experiments around those observations, distinguish possible explanations, and establish patterns and boundaries. The study of relationships between model size, data, compute, and loss in [Scaling Laws](https://arxiv.org/abs/2001.08361) can be understood from this perspective.

Theory also fits here. Start from explicit assumptions, derive what is possible and where limitations arise, and examine how those conditions relate to real problems. A reliable pattern, an explanation, or a counterexample can change subsequent research decisions. There is no need to add a marginally improving module merely to make the work look like a method paper.

Another path is **Simplification / Reassessment**: checking whether existing complexity is necessary. Which components of a successful but complicated method are indispensable? Is a supposedly weaker baseline still weaker after fair tuning and budget alignment? [DPO](https://arxiv.org/abs/2305.18290) can also be viewed through the lens of simplifying training. Under its modeling assumptions, it expresses preference learning as an objective that directly optimizes the policy, removing the separate reward-model training and subsequent RL optimization steps.

This path depends heavily on rigorous comparison. Failing to reproduce a result does not by itself refute the original conclusion. Removing a module without losing performance may only mean that the current task does not need it. But with sufficient evidence, showing that a complicated design is unnecessary, or that a conclusion holds only under narrow conditions, is valuable in its own right.

There is also **Problem Formulation**: redefining what is worth studying and measuring. Existing tasks and metrics sometimes miss the capability we care about. [SWE-bench](https://arxiv.org/abs/2310.06770), for example, organizes real GitHub issues and their repositories into tasks that require models to solve problems by modifying code. Such contributions include the task definition, data construction, and evaluation method. They also influence what people choose to study next.

This work needs to show what the earlier evaluation missed and whether the new score reflects the intended capability. Collecting more examples or making questions harder does not automatically create a good benchmark. A useful new task makes a previously vague problem concrete and lets different methods be compared under trustworthy conditions.

The final path I would call **Building**: creating new conditions for research. This might mean high-quality data, an interactive and reproducible environment, or a system design that reduces computational cost. [FlashAttention](https://arxiv.org/abs/2205.14135) is a concrete example: it improves the efficiency of exact attention by addressing data movement across the GPU memory hierarchy. Such work enables experiments that others previously could not run or considered too expensive.

Its value needs to show up in use. What gap does the data fill? What can the environment support studying? Under which hardware and workloads does the system save time and memory, and how much? A large amount of work is not automatically a large research contribution. What matters is whether the infrastructure changes which problems can be studied or substantially lowers the barrier to studying them.

A project can start with Searching, become Understanding through analysis, and then lead naturally to Evolution. It can also begin by following a trend and end with the realization that the real missing piece is a suitable benchmark. An unglamorous starting point is no reason to dismiss the work. Nor does choosing one path require turning every result into a new method.

This connects to the earlier discussion of taste. Throughout a project, we keep deciding where effort is worth spending next: improving the method, adding an experiment that distinguishes explanations, rebuilding the evaluation, or acknowledging that the evidence supports a narrower conclusion. Seeing more research paths can make those choices clearer. When it is time to write, explaining what the work has enabled us to know or do that we could not before is already a substantial achievement.
