---
layout: post
title: Gary Marcus提出对深度学习的系统性批判
description:
date: 2018-01-02 8:13:41 +0800
image: assets/images/DL.jpg
---

作者：Gary Marcus

机器之心编译 [原文下载地址](https://arxiv.org/ftp/arxiv/papers/1801/1801.00631.pdf)


在人们对于`AI`技术的应用逐步走向正轨的同时，人工智能的先驱者们却早已将目光投向远方。2018 年伊始，纽约大学教授、前`Uber AI Lab`主管`Gary Marcus`就发表了一篇长文对深度学习的现状及局限性进行了批判性探讨。在文中，`Marcus`表示：我们必须走出深度学习，这样才能迎来真正的通用人工智能。

尽管深度学习历史可追溯到几十年前，但这种方法，甚至深度学习一词都只是在`5`年前才刚刚流行，也就是该领域被类似于`Krizhevsky`、`Sutskever`和`Hinton`等人合作的论文这样的研究成果重新点燃的时候。他们的论文如今是`ImageNet`上经典的深度网络模型。

在随后`5`年中，该领域都发现了什么？在语音识别、图像识别、游戏等领域有可观进步，主流媒体热情高涨的背景下，我提出了对深度学习的十点担忧，且如果我们想要达到通用人工智能，我建议要有其他技术补充深度学习。

>在深度学习衍生出更好解决方案的众多问题上（视觉、语音），在 2016 -2017 期间而变得收效衰减。——François Chollet, Google, Keras 作者，2017.12.18  

>「科学是踩着葬礼前行的」，未来由极其质疑我所说的一切的那批学生所决定。——Geoffrey Hinton，深度学习教父，谷歌大脑负责人，2017.9.15  

### 1.深度学习撞墙了？

尽管，深度学习的根源可追溯到几十年前`（Schmidhuber,2015)`，但直到`5`年之前，人们对于它的关注还极其有限。`2012`年，`Krizhevsky`、`Sutskever` 和`Hinton`发布论文`《ImageNet Classification with Deep Convolutional Neural Networks》``(Krizhevsky, Sutskever, & Hinton, 2012)`，在`ImageNet`目标识别挑战赛上取得了顶尖结果`（Deng et al.）`。随着这样的一批高影响力论文的发表，一切都发生了本质上的变化。当时，其他实验室已经在做类似的工作`（Cireşan, Meier, Masci, & Schmidhuber, 2012）`。在`2012`年将尽之时，深度学习上了纽约时报的头版。然后，迅速蹿红成为人工智能中最知名的技术。训练多层神经网络的思路并不新颖（确实如此），但因为计算力与数据的增加，深度学习第一次变得实际可用。

自此之后，深度学习在语音识别、图像识别、语言翻译这样的领域产生了众多顶尖成果，且在目前众多的`AI`应用中扮演着重要的角色。大公司也开始投资数亿美元挖深度学习人才。深度学习的一位重要拥护者，吴恩达，想的更远并说到，「如果一个人完成一项脑力任务需要少于一秒的考虑时间，我们就有可能在现在或者不久的未来使用`AI`使其自动化。」`（A,2016)`。最近纽约时报星期天杂志的一篇关于深度学习的文章，暗示深度学习技术「做好准备重新发明计算本身」。

如今，深度学习可能临近墙角，大部分如同前面我在深度学习崛起之时`（Marcus 2012）`预期到的，也如同`Hinton``(Sabour, Frosst, & Hinton, 2017)`、`Chollet``（2017）`这样的重要人物近几月来暗示的那样。


深度学习到底是什么？它展示了智能的什么特性？我们能期待它做什么？预计什么时候它会不行？我们离「通用人工智能」还有多远？多近？在解决不熟悉的问题上，什么时候机器能够像人类一样灵活？该文章的目的既是为了缓和非理性的膨胀，也是为了考虑需要前进的方向。

该论文同时也是写给该领域的研究人员，写给缺乏技术背景又可能想要理解该领域的`AI`消费者。如此一来，在第二部分我将简要地、非技术性地介绍深度学习系统能做什么，为什么做得好。然后在第三部分介绍深度学习的弱点，第四部分介绍对深度学习能力的误解，最后介绍我们可以前进的方向。

深度学习不太可能会消亡，也不该消亡。但在深度学习崛起的`5`年后，看起来是时候对深度学习的能力与不足做出批判性反思了。

### 2.深度学习是什么？深度学习能做好什么？  

深度学习本质上是一种基于样本数据、使用多层神经网络对模式进行分类的统计学技术。深度学习文献中的神经网络包括一系列代表像素或单词的输入单元、包含隐藏单元（又叫节点或神经元）的多个隐藏层（层越多，网络就越深），以及一系列输出单元，节点之间存在连接。在典型应用中，这样的网络可以在大型手写数字（输入，表示为图像）和标签（输出，表示为图像）集上进行训练，标签代表输入所属的类别。
![](/assets/images/dl01.jpeg)

随着时间的进展，一种叫作反向传播的算法出现了，它允许通过梯度下降过程调整单元之间的连接，以使任意给定输入可以有对应的输出。

大体上，我们可以把神经网络所学习的输入与输出之间的关系理解为映射。神经网络，尤其是具备多个隐藏层的神经网络尤其擅长学习输入-输出映射。

此类系统通常被描述为神经网络，因为输入节点、隐藏节点和输出节点类似生物神经元，不过已经大大简化。节点之间的连接类似神经元之间的连接。

大部分深度学习网络大量使用卷积技术`（LeCun, 1989）`，该技术约束网络中的神经连接，使它们本能地捕捉平移不变性`（translational invariance）`。这本质上就是物体可以围绕图像滑动，同时又保持自己的特征；正如上图中，假设它是左上角的圆，即使缺少直接经验，也可以最终过渡到右下角。

深度学习还有一个著名的能力——自生成中间表示，如可以响应横线或图结构中更复杂元素的内部单元。

原则上，对于给定的无限多数据，深度学习系统能够展示给定输入集和对应输出集之间的有限确定性「映射」，但实践中系统是否能够学习此类映射需要依赖于很多因素。一个常见的担忧是局部极小值陷阱，即系统陷入次最优解，附近求解空间内没有更好的解。（专家使用多种技术避免此类问题，达到了比较好的效果。）在实践中，大型数据集的结果通常比较好，因其具备大量可能的映射。

例如，语音识别中，神经网络学习语音集和标签（如单词或音素）集之间的映射。目标识别中，神经网络学习图像集和标签集之间的映射。在`DeepMind`的`Atari`游戏系统`（Mnih et al., 2015）`中，神经网络学习像素和游戏杆位置之间的映射。

深度学习系统最常用作分类系统，因其使命是决定给定输入所属的类别（由神经网络的输出单元定义）。只要有足够的想象力，那么分类的能力是巨大的；输出可以表示单词、围棋棋盘上的位置等几乎所有事物。

在拥有无限数据和计算资源的世界，可能就不需要其他技术了。

### 3.深度学习的局限性

深度学习的局限性首先是这个逆否命题：我们居住的世界具备的数据并不是无穷多的。依赖于深度学习的系统经常要泛化至未见过的数据，这些数据并不是无穷大的，确保高质量性能的能力更是有限。

我们可以把泛化当作已知样本之间的内插和超出已知训练样本空间的数据所需的外插`（Marcus, 1998a）`。

对于泛化性能良好的神经网络，通常必须有大量数据，测试数据必须与训练数据类似，使新答案内插在旧的数据之中。在`Krizhevsky`等人的论文`（Krizhevsky, Sutskever, & Hinton, 2012）`中，一个具备`6000`万参数和`65`万节点的`9`层卷积神经网络在来自大概`1000`个类别的约`100`万不同样本上进行训练。

这种暴力方法在`ImageNet`这种有限数据集上效果不错，所有外部刺激都可以被分类为较小的类别。它在稳定的领域效果也不错，如在语音识别中，数据可以一种常规方式映射到有限的语音类别集中，但是出于很多原因，深度学习不是人工智能的通用解决方案。

以下是当前深度学习系统所面临的十个挑战：

#### 3.1 目前深度学习需要大量数据
人类只需要少量的尝试就可以学习抽象的关系。如果我告诉你`schmister`是年龄在`10`岁到`21`岁之间的姐妹。可能只需要一个例子，你就可以立刻推出你有没有`schmister`，你的好朋友有没有`schmister`，你的孩子或父母有没有`schmister`等等。

你不需要成百上千甚至上百万的训练样本，只需要用少量类代数的变量之间的抽象关系，就可以给 `schmister`下一个准确的定义。

人类可以学习这样的抽象概念，无论是通过准确的定义还是更隐式的手段`（Marcus，2001）`。实际上即使是`7`月大的婴儿也可以仅在两分钟内从少量的无标签样本中学习抽象的类语言规则`（Marcus, Vijayan, Bandi Rao, & Vishton, 1999）`。随后由`Gervain`与其同事做出的研究`（2012）`表明新生儿也能进行类似的学习。

深度学习目前缺少通过准确的、语词的定义学习抽象概念的机制。当有数百万甚至数十亿的训练样本的时候，深度学习能达到最好的性能，例如`DeepMind`在棋牌游戏和`Atari`上的研究。正如`Brenden Lake`和他的同事最近在一系列论文中所强调的，人类在学习复杂规则的效率远高于深度学习系统`（Lake, Salakhutdinov, & Tenenbaum, 2015; Lake, Ullman, Tenenbaum, & Gershman, 2016）`（也可以参见`George`等人的相关研究工作，`2017`）。我和`Steven Pinker`在儿童与神经网络的过度规则化误差的对比研究也证明了这一点。

`Geoff Hinton`也对深度学习依赖大量的标注样本表示担忧，在他最新的`Capsule`网络研究中表达了这个观点，其中指出卷积神经网络可能会遭遇「指数低效」，从而导致网络的失效。还有一个问题是卷积网络在泛化到新的视角上有困难。处理转换（不变性）的能力是网络的内在性质，而对于其他常见类型的转换不变性，我们不得不在网格上的重复特征检测器之间进行选择，该过程的计算量是指数式增长的，或者增加标记训练集的规模，其计算量也是指数式增长的。

对于没有大量数据的问题，深度学习通常不是理想的解决方案。

#### 3.2 深度学习目前还是太表浅，没有足够的能力进行迁移
这里很重要的一点是，需要认识到「深」在深度学习中是一个技术的、架构的性质（即在现代神经网络中使用大量的隐藏层），而不是概念上的意义（即这样的网络获取的表征可以自然地应用到诸如「公正、「民主」或「干预」等概念）。

即使是像「球」或「对手」这样的具体概念也是很难被深度学习学到的。考虑`DeepMind`利用深度强化学习对`Atari`游戏的研究，他们将深度学习和强化学习结合了起来。其成果表面上看起来很棒：该系统使用单个「超参数」集合（控制网络的性质，如学习率）在大量的游戏样本中达到或打败了人类专家，其中系统并没有关于具体游戏的知识，甚至连规则都不知道。但人们很容易对这个结果进行过度解读。例如，根据一个广泛流传的关于该系统学习玩打砖块`Atari`游戏`Breakout`的视频，「经过`240`分钟的训练，系统意识到把砖墙打通一个通道是获得高分的最高效的技术。」

但实际上系统并没有学到这样的思维：它并不理解通道是什么，或者砖墙是什么；它仅仅是学到了特定场景下的特定策略。迁移测试（其中深度强化学习系统需要面对和训练过程中稍有不同的场景）表明深度强化学习方法通常学到很表明的东西。例如，`Vicarious`的研究团队表明`DeepMind`的更高效的进阶技术——`Atari`系统`「Asynchronous Advantage Actor-Critic」`（也叫`A3C`）在玩多种`Breakout`的微改动版本（例如改变球拍的`Y`坐标，或在屏幕中央加上一堵墙）时遭遇了失败。这些反例证明了深度强化学习并不能学习归纳类似砖墙或球拍这样的概念；更准确地说，这样的评论就是生物心理学中的过度归因所造成的。`Atari`系统并没有真正地学习到关于砖墙的鲁棒的概念，而只是在高度训练的情景的狭隘集合中表面地打破了砖墙。

我在初创公司`Geometric Intelligence`的研究团队（后来被`Uber`收购）的滑雪游戏情景中发现了类似的结果。`2017`年，伯克利和`OpenAI`的一个研究团队发现可以轻易地在多种游戏中构造对抗样本，使得`DQN`（原始的`DeepMind`算法）、`A3C`和其它的相关技术（`Huang`,`Papernot`,`Goodfellow`,`Duan`, &`Abbeel`,`2017`）都失效。

最近由`Robin Jia`和`Percy Liang`（`2017`）做的实验在不同的领域（语言）表明了类似的观点。他们训练了多种用于问答系统任务（被称为`SQuAD，Stanford Question Answering Database`）的神经网络，其中任务的目标是在特定的段落中标出和给定问题相关的单词。例如，有一个已训练系统可以基于一段短文准确地识别出超级碗`XXXIII`的胜利者是`John Elway`。但`jia`和`Liang`表明仅仅插入干扰句（例如宣称谷歌的`Jeff Dean`在另一个杯赛中获得了胜利）就可以让准确率大幅下降。在`16`个模型中，平均准确率从`75%`下降了到了`36%`。

通常情况下，深度学习提取的模式，相比给人的第一印象，其实更加的表面化。

##### 3.3 迄今深度学习没有自然方式来处理层级架构
对乔姆斯基这样的语言学家来说，对`Robin Jia`和`Percy Liang`记录的难题并不惊讶。基本上，目前大部分深度学习方法基于语言模型来将句子表达为纯粹的词序列。然而，乔姆斯基一直以来都认为语言具有层级架构，也就是小的部件循环构建成更大的结构。（例如，在句子`「the teenager who previously crossed the Atlantic set a record for flying around the world」`中，主句是`「the teenager set a record for flying around the world」，「who previously crossed the Atlantic」`是指明青年身份的一个从句。

在上世纪`80`年代，`Fodor`和`Pylyshyn`（`1988`）也表达了同样的担忧，这是关于神经网络的一个早期分支。我在 2001 年的文章中也同样揣测到，单个循环神经网络（`SRN`；是今天基于循环神经网络（也就是`RNN`）的更复杂的深度学习方法的前身；`Elman`,`1990`) 难以系统表达、扩展各种不熟悉语句的递归结构（从引用论文查看具体是哪种类型）。

`2017`早些时候，`Brenden Lake`和`Marco Baroni`测试了这样的悲观揣测是否依然正确。就像他们文章标题中写的，当代神经网络「这么多年来依然不体系」。`RNN`可能「在训练与测试差别... 很小的时候泛化很好，但当需要系统地组合技能做泛化时，`RNN`极其失败。」

类似的问题在其他领域也可能会暴露出来，例如规划与电机控制，这些领域都需要复杂的层级结构，特别是遇到全新的环境时。从上面提到的`Atari`游戏`AI`难以迁移问题上，我们可以间接看到这一点。更普遍的是在机器人领域，系统一般不能在全新环境中概括抽象规划。

至少，目前深度学习显现的核心问题是它学习特征集相对平滑或者说非层级的关联关系，犹如简单的、非结构化列表，每个特征都平等。层级结构（例如，句子中区分主句和从句的语法树）在这样的系统中并不是固有的，或者直接表达的，结果导致深度学习系统被迫使用各种根本不合适的代理，例如句子中单词的序列位置。

像`Word2Vec（Mikolov, Chen, Corrado, & Dean, 2013)`这样的系统将单个单词表达为向量，有适当的成功。也有一批系统使用小技巧试图在深度学习可兼容的向量空间中表达完整语句 `(Socher, Huval, Manning, & Ng, 2012）`。但是，就像`Lake`和`Baroni`的实验表明的，循环网络能力依然有限，不足以准确可靠地表达和概括丰富的结构信息。

##### 3.4 迄今为止的深度学习无法进行开放推理
如果你无法搞清`「John promised Mary to leave」`和`「John promised to leave Mary」`之间的区别，你就不能分清是谁离开了谁，以及接下来会发生什么。目前的机器阅读系统已经在一些任务，如`SQuAD`上取得了某种程度的成功，其中对于给定问题的答案被明确地包含在文本中，或者整合在多个句子中（被称为多级推理）或整合在背景知识的几个明确的句子中，但并没有标注特定的文本。对于人类来说，我们在阅读文本时经常可以进行广泛的推理，形成全新的、隐含的思考，例如仅仅通过对话就能确定角色的意图。

尽管`Bowman`等人`（Bowman，Angeli，Potts & Manning，2015；Williams，Nangia & Bowman，2017）`在这一方向上已经采取了一些重要步骤，但目前来看，没有深度学习系统可以基于真实世界的知识进行开放式推理，并达到人类级别的准确性。

##### 3.5 迄今为止的深度学习不够透明
神经网络「黑箱」的特性一直是过去几年人们讨论的重点`（Samek、Wiegand & Müller，2017；Ribeiro、Singh & Guestrin，2016）`。在目前的典型状态里，深度学习系统有数百万甚至数十亿参数，其开发者可识别形式并不是常规程序员使用的`（「last_character_typed」）`人类可识别标签，而是仅在一个复杂网络中适用的地理形式（如网络模块`k`中第`j`层第`i`个节点的活动值）。尽管通过可视化工具，我们可以在复杂网络中看到节点个体的贡献`（Nguyen、Clune、Bengio、Dosovitskiy & Yosinski，2016）`，但大多数观察者都认为，神经网络整体看来仍然是一个黑箱。

从长远看来，目前这种情况的重要性仍不明确（Lipton，2016）。如果系统足够健壮且自成体系，则没有问题；如果神经网络在更大的系统中占据重要的位置，则其可调试性至关重要。

为解决透明度问题，对于深度学习在一些领域如金融或医疗诊断上的潜力是致命的，其中人类必须了解系统是如何做出决策的。正如 Catherine O』Neill（2016）指出的，这种不透明也会导致严重的偏见问题。