# AI-PhD SKILL 之 一套可执行的科研 Pipeline

[← 返回目录 / Index](../../README.md) · 中文原文 · [English](1-Research-Pipeline-EN.md)

先说结论。入门一个领域的科研 pipeline 通常是这样：

0：确定【大方向】
比如 LLM、多模态、Generation、Agent、Robotics 等。
这通常对应论文的第一个 keyword。

1：确定【具体研究领域】
比如 LLM Efficient Reasoning、长视频理解、图像编辑、Multimodal RAG 等。
这通常对应论文的第二个 keyword。

2：阅读该领域近三年来有价值的相关工作
目标是建立 problem map、method map 和 evaluation map。

3：找最合适的几个 baseline 并复现
目标是建立可靠实验环境和领域直觉。

4：看 case，找创新点并验证
很多 idea 来自失败样本、边界样本和现有方法的系统性缺陷。

5：整理成文，完成故事
最终要把问题、动机、方法、实验和结论串成一个完整的 research story。

下面逐个展开。

0、确定【大方向】

科研入门的第一步，是先确定一个大方向。

比如：

LLM
Multimodal Learning
Generation
Efficient AI
Embodied AI
Agent
Robotics
Medical AI
AI4Science

这个层级的问题通常还比较宽，但它决定了你接下来会进入哪个学术社区，关注哪些会议，读哪些论文，使用哪些 benchmark，熟悉哪些工具栈。

比如你说自己想做 LLM，这还远远不够。LLM 下面还有 reasoning、alignment、agent、tool use、long context、efficient inference、post-training、evaluation 等方向。每个方向的核心问题、实验范式和投稿口味都不同。

在这个阶段，重点是回答三个问题：

第一，这个方向有没有【长期学术价值】？

它是否对应一个长期存在的问题，而非只依赖短期热点或工程迭代。

第二，这个方向是否和自己的【资源条件】匹配？

比如算力、数据、代码基础、导师资源、合作资源。很多 idea 理论上有意义，但对单个博士生来说推进成本过高。

第三，这个方向是否有相对清晰的【评价体系】？

如果一个方向缺少稳定 benchmark、指标或 case study，新手很容易陷入各说各话的状态。

这一步的产出：

确定一个一级方向，并知道它主要对应哪些会议、关键词、代表性论文和研究群体。

1、确定【具体研究领域】

确定大方向之后，需要继续收敛到具体研究领域。

比如，大方向是 LLM，具体领域可以是：

LLM Efficient Reasoning
Long-context Reasoning
Tool-augmented LLM
LLM Agent Evaluation
Test-time Scaling
Multimodal Reasoning

大方向是多模态，具体领域可以是：

长视频理解
图像编辑
多模态检索
视觉指令微调
Multimodal Hallucination
Video-language Alignment

大方向是 Generation，具体领域可以是：

Text-to-Image
Image Editing
Text-to-3D
Video Generation
Personalized Generation
Controllable Generation

这一步的关键是控制粒度。

太宽，比如“我想做 LLM”，会导致你不知道该读什么、复现什么、比较什么、解决什么。

太窄，比如“我想改某篇论文里的一个小模块”，又容易过早陷入局部优化，最后很难形成有价值的 paper。

一个合适的具体研究领域，通常满足几个条件：

有近两三年的连续论文积累；
有相对稳定的数据集、指标或评测方式；
存在明显未解决的问题；
有若干 strong baseline 可以复现；
改进空间不完全依赖大算力。

这一步的产出：

确定一个二级 keyword，并能用一句话描述这个领域在解决什么问题。

例如：

LLM Efficient Reasoning 关注如何在尽量少的 token、算力或时间成本下保持甚至提升模型推理能力。

长视频理解关注模型如何在长时序、多事件、多粒度的视频输入中完成问答、定位、摘要和推理。

图像编辑关注如何在保持原图身份、结构和语义一致性的前提下，根据文本或其他条件进行局部或全局修改。

能写出这样一句话，说明你已经从泛兴趣进入了具体问题域。

2、阅读近三年相关工作

入门一个领域，读论文是必须的。但关键不在于读了多少篇，而在于有没有建立结构化认知。

我建议把论文分成四类。

第一类：【奠基论文】

这类论文可能没有那么新，但定义了这个领域的问题、任务或基本方法。

第二类：【强 baseline 论文】

这类论文通常实验扎实、性能强、代码可用，是之后做实验绕不开的比较对象。

第三类：【最新趋势论文】

这类论文通常来自最近一两年的顶会、arXiv 或大组工作，代表社区正在往哪里走。

第四类：【负样本论文】

也就是读完之后，你觉得问题定义不清、实验不够强、故事不成立、贡献不够稳的论文。负样本很重要，它能帮助你理解什么样的工作不容易被认可。

读论文时，不要只记方法细节。更重要的是整理三张 map。

第一张：【Problem Map】

这个领域里大家到底在解决哪些子问题？

第二张：【Method Map】

不同方法分别走什么路线？它们的核心假设是什么？

第三张：【Evaluation Map】

大家用什么数据集、什么指标、什么 baseline、什么 case 来证明方法有效？

举个例子，如果你入门 LLM Efficient Reasoning，读论文时需要关注：

大家是在减少 reasoning token，还是减少 inference latency，还是提升 test-time compute efficiency？

方法是 prompt-level、decoding-level、training-level，还是 model architecture-level？

评价时看 accuracy、token consumption、latency、cost，还是 accuracy-cost trade-off？

不同方法在哪些任务上有效，在哪些任务上失败？

很多人读了二三十篇论文，最后依然不知道能做什么。常见原因是阅读过程缺少结构化整理。

这一步的产出：

一个包含 20 到 50 篇核心论文的阅读表，以及 problem、method、evaluation 三张 map。

3、找 baseline 并复现

读完相关工作之后，不要立刻追求一个很大的 idea。更稳的做法是先找几个最合适的 baseline，并尽量复现。

baseline 的选择很重要。你不需要复现所有论文，而要重点选择三类。

第一类：【经典 baseline】

它可能已经不是最新最强，但代表了这个领域的基本方法。

第二类：【strong baseline】

它是当前性能较强、审稿人很可能要求比较的方法。

第三类：【与你的潜在 idea 最相关的 baseline】

即使它不是榜单第一，只要它和你的问题设定最接近，就值得重点复现。

复现 baseline 的目的，不只是为了之后写实验表格，更是为了建立实验直觉。

你会逐渐知道：

哪些结果比较稳定；
哪些指标容易波动；
哪些数据集质量有问题；
哪些实验成本很高；
哪些代码坑很多；
哪些改进很难复现；
哪些设置对结果影响巨大。

这里还有一个关键点：在复现 baseline 之前，要先确认【evaluation protocol】。

也就是说，你需要搞清楚：

用哪些数据集？
训练集、验证集、测试集怎么划分？
用哪些指标？
是否需要人工评估？
是否需要 GPT-based evaluation？
是否需要控制推理预算、参数规模、训练数据规模？
是否存在 data leakage？
是否存在不同论文设置不一致的问题？

如果 evaluation protocol 不稳定，后面的实验会非常混乱。你可能做了很多实验，但最后无法说服别人你的方法真的更好。

这一步的产出：

一套可运行、可复现、可扩展的实验代码，以及至少 2 到 3 个可信 baseline 结果。

4、看 case，找创新点并验证

很多新手找 idea 的方式是读完论文后直接设计方法。这个方式可以用，但效率通常不高。

我更推荐从【case study】入手。

尤其要看四种 case。

第一，baseline 成功而简单方法失败的 case。

这说明 baseline 可能抓住了某种关键机制。

第二，baseline 失败但人类觉得很容易的 case。

这通常说明模型存在明显缺陷，是潜在创新点。

第三，不同 baseline 表现差异很大的 case。

这说明这些方法的 inductive bias 不同，背后可能有值得分析的问题。

第四，指标提升但 case 质量没有明显提升的情况。

这说明当前 evaluation 可能有问题，或者方法只是优化了某种指标偏差。

很多好的 idea 都从一个具体问题开始：

为什么这个 case 会错？
模型是否没有看到关键上下文？
是否被无关信息干扰了？
是否因为 reasoning 过程太长导致错误累积？
是否存在视觉信息和语言指令没有对齐的问题？
是否训练数据里缺少某类组合？
是否 evaluation 指标无法反映真实质量？
是否现有方法只解决了 easy case，hard case 依然没有提升？

当你能把失败 case 归纳成一个稳定模式时，idea 就开始出现了。

注意：【一个 case 不是 idea，一类 case 才是 idea 的入口】。

如果只是找到几个零散例子，最多只能说明 baseline 有 bug。
如果你能证明某一类失败在数据集中系统性存在，并且现有方法普遍解决不好，那就有机会变成论文动机。

这一步可以按照这样的流程走：

先观察大量 case；
再归纳失败模式；
然后提出假设；
接着设计最小验证实验；
最后判断这个假设是否值得继续投入。

不要一开始就做完整方法。先做【最小验证】。

比如你怀疑长视频理解模型的问题是关键帧定位不准，可以先做 oracle experiment：如果给模型正确关键帧，性能是否明显提升？如果提升很大，说明这个假设有价值；如果提升不大，说明主要瓶颈可能在其他地方。

比如你怀疑 LLM reasoning 的问题是推理 token 冗余，可以先分析哪些 token 对最终答案真正有贡献，再看压缩、跳步或动态推理是否可行。

这一步的产出：

一个经过 case study 和初步实验支持的核心假设。

5、做创新点

科研中的创新点，不能只是加一个模块、换一个 loss、拼一个 pipeline。更重要的是说明：【为什么这个创新点是必要的】。

一个好的创新点通常需要同时满足三点。

第一，它解决了一个真实存在的问题。

这个问题最好能通过文献、case study 或实验观察支撑。

第二，它和已有方法有清晰区别。

区别可以体现在 problem formulation、modeling assumption、training strategy、inference strategy 或 evaluation protocol 上。

第三，它能被实验验证。

你的 claim 必须能对应到实验设计。不能写得很大，实验却只能支撑很小的一点。

常见创新点大概有几类。

一种是【问题定义创新】。

你发现现有领域忽略了一个重要问题，于是提出新的 task、benchmark 或 evaluation setting。

一种是【方法创新】。

你提出新的模型结构、训练目标、推理策略、数据构造方式或系统框架。

一种是【分析创新】。

你系统性分析了某个现象，解释现有方法为什么失败，并提出相应改进。

一种是【效率创新】。

你在相同性能下显著降低训练成本、推理成本、数据成本或人工标注成本。

一种是【评测创新】。

你指出现有评价指标或 benchmark 有缺陷，并提出更可靠的评测方式。

对新手来说，常见问题是过度追求方法新颖性，忽略问题重要性和实验支撑。

一个方法是否值得做，取决于它能否形成完整闭环：

现有方法有什么问题；
为什么会出现这个问题；
你的方法如何解决；
实验证明它确实解决了；
这个结论对领域有什么意义。

这一步的产出：

一句清晰的 contribution statement。

例如：

我们发现现有长视频问答模型在多事件时序推理中主要受限于关键事件定位错误，因此提出一种事件级记忆选择机制，在不增加显著推理成本的情况下提升长时序问题回答能力。

这句话里最好同时包含：问题、观察、方法、效果和意义。

6、整理成文，完成故事

最后一步是写论文，也就是完成一个可信的 research story。

写论文不是简单整理实验结果。更准确地说，它是在构建一条论证链：

这个问题重要；
现有方法没有很好解决；
我们发现了关键原因；
我们提出了针对性方法；
实验说明方法有效；
分析说明为什么有效；
消融说明哪些部分有效；
case study 说明方法在真实样本上确实改善；
局限性说明这个方法的边界在哪里。

这里最重要的是：【claim 要和 evidence 对齐】。

如果你的 claim 是提升推理效率，实验必须报告 accuracy-cost trade-off，不能只报告 accuracy。

如果你的 claim 是更好地理解长视频，实验不能只在短视频 benchmark 上做。

如果你的 claim 是减少 hallucination，就需要有能支撑 hallucination reduction 的指标、人工评估或 case study。

如果你的 claim 是 generalizable，就需要跨数据集、跨模型、跨任务或跨 setting 的实验。

论文写作不是把所有实验都塞进去。核心是选择最能支撑主线的证据。

这一步的产出：

一个完整 paper draft，包括 abstract、introduction、method、experiment、analysis 和 limitation。

最后总结

入门一个科研领域，不只是读很多论文。更完整的 pipeline 是：

确定大方向
收敛到具体研究领域
建立文献地图
复现 baseline
分析 case
提出假设
验证创新点
组织成 research story

对博士生来说，最重要的能力之一，是建立一套稳定的方法，让自己可以持续进入新领域、理解问题、发现缺口、验证假设，并最终产出论文。

科研没有完全标准化的流程，但有可复用的工作习惯。

这套 pipeline 的目标，是让做科研从一个模糊过程，变成一个可以执行、可以检查、可以迭代的系统。
