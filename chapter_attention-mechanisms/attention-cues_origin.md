# Attention Cues
# 注意力提示 / 注意力线索
:label:`sec_attention-cues`

Thank you for your attention
to this book.
# 感谢你将注意力投入到本书中。
Attention is a scarce resource:
# 注意力是一种稀缺资源：
at the moment
you are reading this book
and ignoring the rest.
# 此刻你正在阅读本书，而忽略了其他一切。
Thus, similar to money,
your attention is being paid with an opportunity cost.
# 因此，就像金钱一样，你付出注意力的同时，也承担了机会成本。
To ensure that your investment of attention
right now is worthwhile,
# 为了让你当下投入的注意力物有所值，
we have been highly motivated to pay our attention carefully
to produce a nice book.
# 我们也投入了大量心血，用心打磨，力求写出一本好书。
Attention
is the keystone in the arch of life and
holds the key to any work's exceptionalism.
# 注意力是生命这座拱门的基石，
# 也是让任何工作脱颖而出的关键。


Since economics studies the allocation of scarce resources,
# 经济学研究的正是稀缺资源的配置问题，
we are
in the era of the attention economy,
# 而我们正身处**注意力经济**时代，
where human attention is treated as a limited, valuable, and scarce commodity
that can be exchanged.
# 在这个时代，人类的注意力被视为一种有限、宝贵、稀缺且可交易的商品。
Numerous business models have been
developed to capitalize on it.
# 大量商业模式都围绕着变现注意力而建立。
On music or video streaming services,
# 在音乐或视频流媒体平台上，
we either pay attention to their ads
or pay money to hide them.
# 我们要么付出注意力观看广告，要么花钱屏蔽广告。
For growth in the world of online games,
# 在网络游戏中想要变强，
we either pay attention to
participate in battles, which attract new gamers,
# 我们要么投入精力参与对战（从而吸引新玩家），
or pay money to instantly become powerful.
# 要么直接花钱快速变强。
Nothing comes for free.
# 天下没有免费的午餐。

All in all,
# 总而言之，
information in our environment is not scarce,
attention is.
# 环境中的信息并不稀缺，稀缺的是注意力。
When inspecting a visual scene,
# 当我们观察一个视觉场景时，
our optic nerve receives information
at the order of $10^8$ bits per second,
# 视觉神经每秒接收的信息量约为 10^8 比特级别，
far exceeding what our brain can fully process.
# 这远远超出了大脑能够完全处理的极限。
Fortunately,
# 幸运的是，
our ancestors had learned from experience (also known as data)
that not all sensory inputs are created equal.
# 我们的祖先从经验（也就是数据）中得知：
# 并非所有感官输入都同等重要。
Throughout human history,
# 在整个人类历史中，
the capability of directing attention
to only a fraction of information of interest
# 只将注意力集中在一小部分感兴趣信息上的能力，
has enabled our brain
to allocate resources more smartly
# 让大脑能够更聪明地分配资源，
to survive, to grow, and to socialize,
# 从而得以生存、繁衍和社交，
such as detecting predators, preys, and mates.
# 例如发现天敌、猎物和配偶。

## Attention Cues in Biology

To explain how our attention is deployed in the visual world,
a two-component framework has emerged
and been pervasive.
This idea dates back to William James in the 1890s,
who is considered the "father of American psychology" :cite:`James.2007`.
In this framework,
subjects selectively direct the spotlight of attention
using both the *nonvolitional cue* and *volitional cue*.

The nonvolitional cue is based on
the saliency and conspicuity of objects in the environment.
Imagine there are five objects in front of you:
a newspaper, a research paper, a cup of coffee, a notebook, and a book such as in :numref:`fig_eye-coffee`.
While all the paper products are printed in black and white,
the coffee cup is red.
In other words,
this coffee is intrinsically salient and conspicuous in
this visual environment,
automatically and involuntarily drawing attention.
So you bring the fovea (the center of the macula where visual acuity is highest) onto the coffee as shown in :numref:`fig_eye-coffee`.

![Using the nonvolitional cue based on saliency (red cup, non-paper), attention is involuntarily directed to the coffee.](../img/eye-coffee.svg)
:width:`400px`
:label:`fig_eye-coffee`

After drinking coffee,
you become caffeinated and
want to read a book.
So you turn your head, refocus your eyes,
and look at the book as depicted in :numref:`fig_eye-book`.
Different from
the case in :numref:`fig_eye-coffee`
where the coffee biases you towards
selecting based on saliency,
in this task-dependent case you select the book under
cognitive and volitional control.
Using the volitional cue based on variable selection criteria,
this form of attention is more deliberate.
It is also more powerful with the subject's voluntary effort.

![Using the volitional cue (want to read a book) that is task-dependent, attention is directed to the book under volitional control.](../img/eye-book.svg)
:width:`400px`
:label:`fig_eye-book`


## Queries, Keys, and Values

Inspired by the nonvolitional and volitional attention cues that explain the attentional deployment,
in the following we will
describe a framework for
designing attention mechanisms
by incorporating these two attention cues.

To begin with, consider the simpler case where only
nonvolitional cues are available.
To bias selection over sensory inputs,
we can simply use
a parameterized fully-connected layer
or even non-parameterized
max or average pooling.

Therefore,
what sets attention mechanisms
apart from those fully-connected layers
or pooling layers
is the inclusion of the volitional cues.
In the context of attention mechanisms,
we refer to volitional cues as *queries*.
Given any query,
attention mechanisms
bias selection over sensory inputs (e.g., intermediate feature representations)
via *attention pooling*.
These sensory inputs are called *values* in the context of attention mechanisms.
More generally,
every value is paired with a *key*,
which can be thought of the nonvolitional cue of that sensory input.
As shown in :numref:`fig_qkv`,
we can design attention pooling
so that the given query (volitional cue) can interact with keys (nonvolitional cues),
which guides bias selection over values (sensory inputs).

![Attention mechanisms bias selection over values (sensory inputs) via attention pooling, which incorporates queries (volitional cues) and keys (nonvolitional cues).](../img/qkv.svg)
:label:`fig_qkv`

Note that there are many alternatives for the design of attention mechanisms.
For instance,
we can design a non-differentiable attention model
that can be trained using reinforcement learning methods :cite:`Mnih.Heess.Graves.ea.2014`.
Given the dominance of the framework in :numref:`fig_qkv`,
models under this framework
will be the center of our attention in this chapter.


## Visualization of Attention

Average pooling
can be treated as a weighted average of inputs,
where weights are uniform.
In practice,
attention pooling aggregates values using weighted average, where weights are computed between the given query and different keys.

```{.python .input}
from d2l import mxnet as d2l
from mxnet import np, npx
npx.set_np()
```

```{.python .input}
#@tab pytorch
from d2l import torch as d2l
import torch
```

```{.python .input}
#@tab tensorflow
from d2l import tensorflow as d2l
import tensorflow as tf
```
To visualize attention weights,
we define the `show_heatmaps` function.
Its input `matrices` has the shape (number of rows for display, number of columns for display, number of queries, number of keys).

```{.python .input}
#@tab all
#@save
def show_heatmaps(matrices, xlabel, ylabel, titles=None, figsize=(2.5, 2.5),
                  cmap='Reds'):
    d2l.use_svg_display()
    num_rows, num_cols = matrices.shape[0], matrices.shape[1]
    fig, axes = d2l.plt.subplots(num_rows, num_cols, figsize=figsize,
                                 sharex=True, sharey=True, squeeze=False)
    for i, (row_axes, row_matrices) in enumerate(zip(axes, matrices)):
        for j, (ax, matrix) in enumerate(zip(row_axes, row_matrices)):
            pcm = ax.imshow(d2l.numpy(matrix), cmap=cmap)
            if i == num_rows - 1:
                ax.set_xlabel(xlabel)
            if j == 0:
                ax.set_ylabel(ylabel)
            if titles:
                ax.set_title(titles[j])
    fig.colorbar(pcm, ax=axes, shrink=0.6);
```

For demonstration,
we consider a simple case where
the attention weight is one only when the query and the key are the same; otherwise it is zero.

```{.python .input}
#@tab all
attention_weights = d2l.reshape(d2l.eye(10), (1, 1, 10, 10))
show_heatmaps(attention_weights, xlabel='Keys', ylabel='Queries')
```

In the subsequent sections,
we will often invoke this function to visualize attention weights.

## Summary

* Human attention is a limited, valuable, and scarce resource.
* Subjects selectively direct attention using both the nonvolitional and volitional cues. The former is based on saliency and the latter is task-dependent.
* Attention mechanisms are different from fully-connected layers or pooling layers due to inclusion of the volitional cues.
* Attention mechanisms bias selection over values (sensory inputs) via attention pooling, which incorporates queries (volitional cues) and keys (nonvolitional cues). Keys and values are paired.
* We can visualize attention weights between queries and keys.

## Exercises

1. What can be the volitional cue when decoding a sequence token by token in machine translation? What are the nonvolitional cues and the sensory inputs?
1. Randomly generate a $10 \times 10$ matrix and use the softmax operation to ensure each row is a valid probability distribution. Visualize the output attention weights.

:begin_tab:`mxnet`
[Discussions](https://discuss.d2l.ai/t/1596)
:end_tab:

:begin_tab:`pytorch`
[Discussions](https://discuss.d2l.ai/t/1592)
:end_tab:

:begin_tab:`tensorflow`
[Discussions](https://discuss.d2l.ai/t/1710)
:end_tab:
