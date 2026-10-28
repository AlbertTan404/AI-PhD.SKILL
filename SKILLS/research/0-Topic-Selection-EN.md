# AI-PhD.SKILL: Choosing a Research Topic

[← Index](../../README.md) · [中文原文](0-Topic-Selection.md) · English

Things have finally settled down. I am starting AI-PhD.SKILL, a series where I share some of the useful, and perhaps not-so-useful, things I have learned.

Let's start with choosing a research topic.

Given your resources, especially compute and access to advisors, there are four main routes:

0. Take an assigned topic.
1. Follow a trend.
2. Follow your interests.
3. Invest in a direction you expect to matter later.

None is inherently better than the others. To judge whether a project can get off the ground, I would also consider three questions:

- Is the problem nontrivial and valuable right now?
- Is there enough compute to support the research?
- Is there an advisor or mentor who can guide you? Do you have research experience in this field yourself?

These three considerations are not ranked either.

I'll start with my own experience. What follows is mostly autobiographical, with the main points highlighted. If you would rather skip that, jump to Section 6.

## 0. A good start: discovering deep learning as an undergraduate

I entered a direct-entry PhD program in 2022. Before that, my undergraduate advisor **assigned me** a graph neural network project. It was an interesting direction, and both my advisor and senior labmates had **substantial experience in the field**, so I received plenty of guidance. With my advisor's help, I eventually **published a paper in a Q1 journal**. Still, the direction did not feel quite like the kind of artificial intelligence I had imagined, so I moved into multimodal learning when I started my PhD.

## 1. A complete change: entering multimodal research

Getting started was difficult because the research approach was completely different. As an undergraduate, I had designed various network modules. In multimodal learning, the emphasis seemed to be more on training paradigms. My first PhD project was **given to me by my advisor**: adapting FP-BERT to the image-text setting. But our group **did not have much experience in this area**, and I was spending more time on coursework. The project ultimately **produced little**, and we moved on.

## 2. An early start: moving into embodied AI at MSRA

In the second semester of my first year, I received some good news. Professor Fu at MSRA, a former colleague of my PhD advisor, was moving from computer vision into embodied AI and needed interns. My advisor asked whether I would be interested in a research internship there. As soon as I heard MSRA, I said yes. It was my first research internship, and the opportunity had essentially **been handed to me**.

Looking back, embodied AI is a direction I strongly believe in. In 2023, though, I might not have given the same answer. Across 2023 and 2024, I went through **eight consecutive rejections across three papers**. :) The main reasons were familiar: little accumulated experience, since we were effectively starting from scratch; a new direction, alongside a fairly established robotics community; and my own lack of experience in research writing.

## 3. A small insight: continuing embodied AI back in the lab

After a year at MSRA, I returned to my university group in 2024 to continue embodied AI research. By then, I had built some experience and **formed a few views of my own about research and papers**. Since our group did not have robot arms, I moved toward simulation, specifically human motion generation. A senior labmate had started this direction, so we already had **some code and data to build on**.

I extended my earlier work on robot-object interaction to human-human interaction. Partway through, I noticed something simple: before reacting to another person, people seem to pause and think. I made that idea work, and Think-Then-React was accepted at ICLR 2025. Meanwhile, the robot latent diffusion project from MSRA won a Best Paper award at MMM 2025, after a borderline result at an A-ranked venue and a transfer to a C-ranked one.

Those acceptances gave me a lot of **confidence** and helped me see **the potential of reasoning**. o1 appeared around the time we submitted Think-Then-React, and R1 appeared around the time it was accepted.

## 4. Following the momentum: going all in on reasoning at Xiaomi

After Think-Then-React was accepted, my advisor began a research collaboration with Xiaomi on video understanding. I went there intending to bring video into motion research. But I kept feeling that **reasoning was the future**. Then I read Meta's Coconut paper. Latent reasoning matched my picture of where AI reasoning might ultimately go.

My mentor was very supportive and immediately agreed to let me explore it. With the machines available through Xiaomi's large-model program, I spent three intense months building CoLaR, which was eventually accepted at NeurIPS 2025. That acceptance depended heavily on Xiaomi's compute support and the guidance of my advisor and mentor. During my year there, I had first-author papers accepted at NeurIPS, CVPR, and ICML, all on their first submission. Their topics were latent reasoning, multimodal agentic reasoning, and the study of reasoning mechanisms.

## 5. Unfinished business: completing CoLaR-2 at Xiaohongshu ACE

As soon as my year at Xiaomi ended, I started looking for my next internship. Xiaohongshu ACE made the first offer. The compensation was hard to turn down, and the research direction was a close fit, so I accepted.

Once there, I immediately began CoLaR-2. With **extensive internal support for AI coding tools**, I made substantial changes to SGLang and ms-swift to accommodate this new way of reasoning. I finally released CoLaR-2 a few days ago. If you have a moment, I would appreciate you taking a look at my previous post.

## 6. Looking ahead: where is the future?

In 2025, video understanding and reasoning were gaining momentum. By 2026, agentic reasoning and coding agents had taken over much of the job market. It is a bit like farming: this year's seeds are harvested next year, but who knows what the crop will sell for then? A popular topic attracts large numbers of graduate students. By the time they produce results, will the market still value their work?

**A farmer's harvest does not itself make the next round of planting faster.**

What does seem clear is that research and paper writing will become easier to enter, and building code will become faster. 99% of what exists only on paper is being replaced at an accelerating pace. Humanity's last refuge lies in the complex physical world.

I am not saying everyone should switch to embodied AI or stop following trends. As I said at the beginning, following a trend and investing in a longer-term direction are not inherently ranked. In a rapidly changing environment, a greedy strategy can sometimes be a reasonable second-best solution. But while following trends, we should keep building what lets us adapt: the ability to learn and change direction, the taste to distinguish stronger work from weaker work, and the ability to manage relationships upward and downward so we can keep going.
