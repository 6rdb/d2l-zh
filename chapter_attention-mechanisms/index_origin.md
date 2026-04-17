# Attention Mechanisms
# 注意力机制
:label:`chap_attention`
# 标签：第10章 注意力机制（书籍内部交叉引用标记）

# 灵长类视觉系统的视神经会接收海量感官输入，
# 远超大脑能够完全处理的信息量。
The optic nerve of a primate's visual system
receives massive sensory input,
far exceeding what the brain can fully process.

# 幸运的是，并非所有刺激都具有同等重要性。
# 意识的聚焦与集中能力让灵长类能够在复杂视觉环境中
# 将注意力投向关注的目标，如猎物或天敌。
Fortunately,
not all stimuli are created equal.
Focalization and concentration of consciousness 
have enabled primates to direct attention
to objects of interest,
such as preys and predators, 
in the complex visual environment.

# 仅关注信息中一小部分的能力具有重要的进化意义，
# 使人类能够生存并发展。
The ability of paying attention to 
only a small fraction of the information
has evolutionary significance,
allowing human beings 
to live and succeed.

# 自19世纪以来，科学家就在认知神经科学领域研究注意力。
Scientists have been studying attention 
in the cognitive neuroscience field
since the 19th century.

# 本章中，我们首先回顾一个主流的解释
# 注意力如何在视觉场景中分配的理论框架。
# 受该框架中注意力线索的启发，
# 我们将设计利用这些注意力线索的模型。
In this chapter,
we will begin by reviewing a popular framework
explaining how attention is deployed in a visual scene.
Inspired by the attention cues in this framework,
we will design models
that leverage such attention cues.

# 值得注意的是，1964年的 Nadaraya-Waston 核回归
# 是机器学习中**注意力机制**的简单示范。
Notably, the Nadaraya-Waston kernel regression
in 1964 is a simple demonstration of machine learning with *attention mechanisms*.

# 接下来，我们将介绍在深度学习注意力模型设计中
# 被广泛使用的注意力函数。
Next, we will go on to introduce attention functions 
that have been extensively used in 
the design of attention models in deep learning.

# 具体来说，我们将展示如何使用这些函数
# 设计 Bahdanau 注意力（巴达诺注意力）。
# 这是深度学习中具有里程碑意义的注意力模型，
# 支持双向对齐且可微。
Specifically,
we will show how to use these functions
to design the *Bahdanau attention*,
a groundbreaking attention model in deep learning
that can align bidirectionally and is differentiable.

# 最后，借助更近提出的**多头注意力**和**自注意力**结构，
# 我们将介绍完全基于注意力机制的 Transformer 架构。
In the end,
equipped with 
the more recent
*multi-head attention*
and *self-attention* designs,
we will describe the *Transformer* architecture
based solely on attention mechanisms.

# 自2017年提出以来，Transformer 在现代深度学习中无处不在，
# 广泛应用于自然语言、计算机视觉、语音、强化学习等领域。
Since their proposal in 2017,
Transformers
have been pervasive in modern 
deep learning applications,
such as in areas of
language,
vision, speech,
and reinforcement learning.

```toc
# 目录配置（Jupyter Book 自动生成目录）
:maxdepth: 2
# 目录最大深度：2级

attention-cues                # 注意力线索
nadaraya-waston               # Nadaraya-Waston 核回归
attention-scoring-functions   # 注意力评分函数
bahdanau-attention            # Bahdanau 注意力
multihead-attention           # 多头注意力
self-attention-and-positional-encoding  # 自注意力与位置编码
transformer                   # Transformer 模型
