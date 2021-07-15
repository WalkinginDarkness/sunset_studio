---
description: 那么，重要的考虑因素就变成了「系统如何运作」，以及最重要的「你提供给系统了什么」
---

# 再重聚：音频驱动的游戏设计视角 Re-Reunion: Audio-Gameplay Design

本文是我与沈希辰2021年6月26日在上海温哥华电影学院举办的 [Audiokinetic 中国2021互动音乐沙龙](https://mp.weixin.qq.com/s?__biz=MzAwMTMxMjQwOA==&mid=2247494999&idx=1&sn=f3a1f74bffa4e242b4314895ab57bc5d&scene=21#wechat_redirect)上分享的部分文字版本。

![](../../.gitbook/assets/image%20%2828%29.png)

除了这一场外，我推荐非音频专业的朋友听听侯老师谈的《[线性音乐创作与非线性音乐创作距离到底有多远](https://www.bilibili.com/video/BV1Nb4y1k7Ht)》以及最后重轻老师参与的[行业讨论会](https://www.bilibili.com/video/BV1d54y1J7oj)。

这是同时希望面向音频设计师与游戏设计师的分享，当然我认为没有门槛，所以也推荐任何对游戏、声音艺术有兴趣的朋友进行阅读和观看。

《[再重聚：音频驱动的游戏设计视角 Re-Reunion: Audio-Gameplay Design](https://www.bilibili.com/video/BV14o4y1X7v3)》

介于我在分享中使用了大量的视频与游戏展示，文字内容会有缩减，

建议直接观看视频，文本作为补充。

（侯老师，希辰，还有重轻老师的视频和节目都给了我很大的帮助）。



## **再重聚：音频驱动的游戏设计视角 Re-Reunion: Audio-Gameplay Design**

本次分享的内容主要分为三个层次。

首先我会谈论这样一个奇怪的主题**「Re-Reunion」**从何而来，其次下落到具体的游戏设计与例子、Demo实践层面去谈论我所说的「**音频-游戏设计 Audio-Gameplay Design**」，最后我希望重思电子游戏作为「**视-听-交互的递归系统**」，从而试图在生成式音乐（Generative Music）与音频-游戏设计（Audio-Gameplay ）之间做一次展望与勾连。

### Reunion

今天我分享的题目是 再重聚：音频驱动的游戏设计视角 Re-Reunion: Audio-Gameplay Design，这个Re-Reunion是我一个生造的词，首先要问的是：Reunion是什么？

Reunion是在1968年的一次当代艺术实践，是由大家想必熟悉的蘑菇学者（顺便是个做音乐的）传世沉默之作《4：33s》的作者约翰凯奇 John Cage, 和国际象棋大师（顺便也是个艺术家）马歇尔杜尚 Marcel Duchamp 以及其夫人Teeny Duchamp进行的实践。

![](../../.gitbook/assets/image%20%2822%29.png)

> _Reunion is an event without a score; originally performed by playing a game of chess on a chessboard created by Lowell Cross. The game works as an indeterminate structure: as a game of chess is played, the moves of the players on the board activate four compositions and distribute them to eight speakers surrounding the audience._

> _《团圆》是一个没有乐谱的活动；最初是通过在洛厄尔-克洛斯（Lowell Cross）创造的棋盘上下棋来表演。这个游戏作为一个不确定的结构起作用：随着棋局的进行，棋盘上的棋手们的动作激活了四个作品，并将它们分配给观众周围的八个扬声器。_

![](../../.gitbook/assets/image%20%2827%29.png)

今天在网上有人重置了这个行为的网络版本（[https://johncage.org/reunion/](https://johncage.org/reunion/) ），区别在于，当时的演奏是即兴，而现在的网络版本是保存的版本。

我其实尝试了几次，与我想象的不同，我以为是完全由下棋来触发的各类音乐的生成，但似乎不是，音乐和下棋之间的逻辑似乎没有那么容易可以被辨识出来。

关于这个这个棋盘的设计者后来写了一篇论文分享，有兴趣的朋友可以去读读看：[Lowell Cross Reunion: John Cage, Marcel Duchamp, Electronic Music, and Chess](https://en.chessbase.com/post/50th-anniversary-of-reunion-and-the-death-of-marcel-duchamp) __

![](../../.gitbook/assets/image%20%287%29.png)

这或许是一次难得的 前电子游戏时代的游戏互动音乐设计的例子。

![](../../.gitbook/assets/image%20%281%29.png)

我理解这里的Reunion，是Reunion of Play and Audio，是作为游戏高手杜尚，与作曲家John Cage之间的交锋、也是「玩」与「声音」之间、棋盘与乐手之间的交锋与某种重聚。

![](../../.gitbook/assets/image%20%284%29.png)

或许从这里，我们可以观察到在那个可能可以作为标志性的，交互和声音还未分化的点，在这个作品中，声音和游戏是各自以某种独立的逻辑结合并且运行，之间更多是一种平行的状态。

### Re-Reunion

但如果我们看今天的游戏中的音频设计，就像是希辰常常跟我开玩笑的，在代码中，往往是这样写的

```text
instantiate(ParticleEffect,transform.position,Quaternion.identity); //生成粒子特效
ak.soundengine.postEvent("soundEvt"); //发送声音事件
```

这里想要说的是今天的声音常常被人所忽视，在大部分的游戏中，它仅仅只是一个纯粹反馈的增加，甚至可以在工作流的最末端才被添上，作为效果的补充与Polish，不参与任何gameplay意义上的内容。

这样的问题原因想来有很多，对于声音的滥用，今天不同媒介都寻求响度上能够夺人耳目，声音嘈杂，滥用高音量，叙事性音频的强化，使得声音的丰富的意义被压扁了，人们平均的音乐和声音的素质并不高，而其从表现上也远不及类似视觉，交互等刺激性强烈地东西来得容易抓人眼球，而今天的音乐制作对一般人也有高的门槛，合成器的使用和理解都显得复杂不易上手。

这就导致了某种双向的问题，游戏设计师可能会无意识地忽略声音设计的重要地位，而就算有意识，或许无论在工作流或者是在理论能力上有难有办法在早期便与作曲家做深入的交互音乐的设计。

美国作曲家艾伦·科普兰写道：

> 富有意味的音乐要求聆听者全神贯注，唯有当个体愿意全心接纳时才能做到一心一意，才能感受到对音乐的需要。将音乐看作用来挑逗听觉感官的仙馔密酒，与此同时，思想意识又被其他事务所侵占，任何严肃对待创作的作曲家对这种做法皆深恶痛绝。—— 艾伦·科普兰 《论音乐》

在今天的游戏声音中听来显得有些讽刺，因为这正是如今游戏中的声音的存在，某种意义上，今天大部分的游戏声音更多之所以存在是为了不存在，存在是为了让玩家不注意到自己（为了让玩家不感觉到异样，「不出戏」，自然地认为这就是一个真实可信的虚拟世界）

所谓标题中的Re-Reunion，**这里的Reunion涉及到的是声音和游戏之间的某种联结**，而我加这个Re首先是我们或许应该重新回到杜尚和John Cage的那次合作中去重思电子游戏和音乐声音之间的相互关系，寻找到另一种可能性的道路；

![](../../.gitbook/assets/image%20%2814%29.png)

而Re当然也有反的意思，那也是我这次的分享的主要内容：我们能不能构想出为了声音呈现，或者是声音作为核心的驱动的那类电子游戏，颠倒 Gameplay-Centric 的逻辑，寻找某些声音应该在其中占有核心地位，而不总是「第二性」的创作可能。



## Audio-Gameplay Design 音频-游戏设计

### Audio-Driven

（这一部分叙述最好参考视频内容）

![](../../.gitbook/assets/image%20%283%29.png)

我试图谈论这部分内容的框架来自一种抽象，在这种系统视角式的抽象中，就如同前文谈论的Reunion，我将游戏的交互与游戏系统Gameplay System / Mechanics 与声音相关的 Audio 区分开来，并且构造出两条谈论的回路：音频驱动（Audio-Driven）系统设计，与系统驱动音频设计 System-Driven，除此之外，我还希望简单谈论一下其他声音的可能。

这里我使用 Audio-Gameplay 连字符的表达 声音-游戏，来试图说明在这样的游戏创作中，声音与游戏玩法紧密联系，难解难分的状态，互相生成。

#### Audio-Driven: Audio as Level Design

首先谈论到声音游戏最先想到的是音游，而音游的某种意义上可以理解为是将音乐作为关卡设计 Level Design + Visual Feedback \| Gameplay 。本质是**将音乐的乐音（Notes）映射为对玩法系统有意义的关卡讯号**，例如今天借助Unity的插件便可直接将Midi文件导入并且转化为可使用的映射到不同位置的下落音符：Midi - System - Level Signal。

（此处有视频展示）

![](../../.gitbook/assets/image%20%2816%29.png)

在我希望展示的以下这些作品中《Dynamix》《Muse Dash》《Dancing Line》还有《Beat Racer》《再见：狂野之心 sayonara wild hearts》《Just Shapes & Beats》《Rez: Infinite》中。

我希望你们以游戏设计视角留心观察的是：乐音是在多少个维度上出现的？是离散的还是连续的？对应了多少种交互？为什么？（音乐游戏、muse dash、跳舞的线）。

![](../../.gitbook/assets/image%20%289%29.png)

其次的观察是，在这些游戏中，乐音是完全作为关卡挑战一定需要玩家去精确响应，或只是作为非必要的关卡要素来进行引导或躲避?（电音超跑，sayonara wild hearts，just shapes & beats）。

这会造成不同的影响，例如在《再见：狂野之心 sayonara wild hearts》中，设计虽然大量使用的音画协同，但是我觉得他们希望呈现的是某种自由和解放的感觉，所以你能看到玩家移动空间是连续的，而这些乐音只是作为非必要的引导与强化，并不强制玩家的交互;

而在《只有形状与节奏 Just Shapes & Beats》中，即便音画如此具有表演性与反馈，但是本质上玩家是作为一个躲避者而不是响应者——意味着是其音画讯号所勾勒的负空间在起作用而不是乐音的讯号本身。

所以这个是这种做法的优劣：

优势在于，输入与输出的音乐的mapping带来了强烈的演奏快感，而这种效果的身体性的体验，增强了反馈，与视觉形成了呼应，并且在玩法成立了之后内容生产成本较低，重玩性高。

缺点也明显，在于on-rails 的轨道式体验，固定化，每首歌每关都是相对固定且与时间点一一对应的，而对于类似音画协同表演性的作品，其中音乐讯号追求视听表现，但玩法层面难以掌控，难以保证其有其Gameplay意义。

#### Audio Driven - Beat

![](../../.gitbook/assets/image%20%282%29.png)

除了旋律乐音之外，声音的重要属性便是节奏/节拍，而其本身的玩法，即对于节奏的时间性掌握，预测，重复，本身就完全可以单独作为作品加以扩大。

大家也很熟悉：例如处理节奏 Timing的《太鼓达人》，对节奏进行预测与变化的独立游戏《节奏医生 Rhythm Doctor》，对节奏进行重复的《节奏天国》与《Planet Quest》

但这里希望谈论的两个更复杂的设计（此处有视频展示）

#### Audio Driven - Beat-Driven

首先是由**节拍来驱动游戏性 Beat-Driven**，可以理解为节拍可以触发玩家/游戏世界中的某些改变，在诸如《140》《Laserwave》中是这样做的，玩家的角色会在不同节拍点上自动触发对应动作，其好处在于节拍驱动非常容易浮现出不同种的模式，并可进行参数式的替换。

![](../../.gitbook/assets/image%20%2815%29.png)

例如在我制作的Demo中，其展现为当玩家在进行OOXOOOXX的节拍，并且当O的时候触发冲刺，而X的时候触发攻击，那我们完全可以轻易地替换OX的节拍和循环风格（Style），可以从不同的BPM中去构造出不同的游戏战斗体验，而仅仅只需要去调整速度，替换武器类型，替换动作，那如果整体游戏世界调校清楚，那近乎可以浮现出无限的战斗体验。而缺点也很明显，这类游戏往往较为不可控，体验不是所有人都能接受。

#### Audio Driven - Beat- Driven Input Timing

![](../../.gitbook/assets/image%20%2823%29.png)

此处为另外一种节拍驱动的方式，节拍驱动输入时间窗。

在《节奏地牢 Crypt of the NecroDancer》以及《每分钟子弹数 BPM: BULLETS PER MINUTE》中，我们可以看到这种设计，不同于节拍直接驱动游戏，而是节拍在这里如同音游一样，创造了一个时间窗口，玩家的行为节奏被固定在了这样一个窗口中。

![](../../.gitbook/assets/image%20%2826%29.png)

而这实际上构成了一层输入滤镜，使得某些你会立刻反应的交互需要延迟（开枪节奏），而某些你来不及反应的交互（瞄准）需要提前，并且从声音上强化了游戏的世界逻辑（例如给回合制作品加入了动作感，带动整体游戏循环的递进和展开）。

其效果是惊人的，这使得一个如果脱离了节拍玩法就乏善可陈，内容稀少的射击游戏，加上了这层滤镜后，拿到了很高的评价，并且在我游玩了四五个小时之后，才堪堪掌握其基础的快速射击与换弹的逻辑，并且有很深的乐趣。

#### Audio as Input

还有值得一提的，便是声音作为输入，无论是在节拍输入上做文章的《啪嗒砰 Patapon》，还是曾经在主播圈备受欢迎的，处理响度检测的《八分音符酱 休むな！8分音符ちゃん》，再或是前段时间推出的，进行频率和音高判断的《One Hand Clapping - sing your song》都是很不错的例子。

![](../../.gitbook/assets/image%20%2812%29.png)

### System Driven 系统驱动

就如同前文所说，大部分今天的游戏音频是服务于玩法的，即由玩法系统驱动和触发的，这里我所要谈论的是类似的逻辑，但不同的是：**在有些游戏中，这样的由玩法驱动的 System-Driven 却有着声音的呈现效果为目的的！**

即希望玩家所触发的这些声音能够形成具有良好可听性的声音，其核心在于如何将游戏的音效Audio Effect作为音乐性的一个有机组成，进入电子游戏的整体性系统holistic system之中。（而这部分也正是下文可与Generative Music进行的对照）

（此处有视频展示）

![](../../.gitbook/assets/image%20%2825%29.png)

这块的内容可能大家会比较熟悉，我自己认为比较好的例子是《Ape Out》的爵士鼓的即兴设计，背景音乐的虚拟鼓手会随着整体游戏情形改变其激烈程度，音色，伴随着玩家的击杀，会有鼓手的即兴的加花等等。

《Tetris Effect》是《Rez：Infinite》的游戏设计师水口哲野的作品，他的作品一向以联觉著称，通过分层和类似Stinger，节奏量化的方式让整个游玩的过程非常顺畅，以至于能够进行沉浸和代入。

《My Singing Monster》也是一个很好的例子，在这个游戏里，声音成为了一个玩家主要搜集的对象，这是非常性价比的设计，对照现在的大家动辄卡面动辄剧情故事动画皮肤的高制作成本，而声音本身制作成本可能较低，并且能够通过在首页的组合出各种有趣的音效Loop，完全就是一个鼓机。

（此处有视频展示）

![](../../.gitbook/assets/image%20%286%29.png)

我做了一个构想，这样的一个System driven需要的是是什么？需要循环，其中的某些部分可以被量化处理，玩家需要去改变和调整这样的整体的音色，循环等等。基于这样的考虑，我做了两个塔防Demo，塔本身在攻击的时候是有一定各自的声音和循环的，而我根据位置制作了一个鼓机，其触发是由其位置决定的，玩家去改变塔的位置，那么同时也会改变整体音乐的循环，甚至玩家可以使用某些覆盖式的法术（Filter），由此带来对其中某些声音的改变效果Effects（音调、响度、高通、低通等等）等等。

这部分的内容其实完全可以与Generative Music以及声音玩件结合在一起思考：《Play Ground》《The Sound Forest 》友人Wenzy 的《[Bouncing Music](https://mp.weixin.qq.com/s?__biz=MzA5OTgyMDk3Mg==&mid=2651227148&idx=1&sn=b65e7fd7fbd851d1b22c37e0db9c6835&scene=21#wechat_redirect)》John Mak 的《Everyday Shotter》，《Get Even》《ELECTROPLANKTON》等等有许多实践。

### Audio-Itself 音频自身的可能

除了我刚才说的这种更加粗线条的audio-driven，system-driven的思路外，其实audio还有无数的维度可以供挖掘，我不是专业的，这些例子仅供参考。

![](../../.gitbook/assets/image%20%2818%29.png)

例如前段时间放出Demo的《[The Signal State](https://mp.weixin.qq.com/s?__biz=Mzg2NDU1NDcxMA==&mid=2247486546&idx=1&sn=42c2d5f781d6181faef30d187b984ec8&scene=21#wechat_redirect)》本身就是对于模块合成器的信号处理逻辑而做的数学解谜，《Circuits》作为以多轨音乐还原为目的，间接让我体会到了对于音乐不同层的觉察。

《140》我是极推荐的，它也是2014年的IGF最佳音效奖的得主，对于声音微妙属性变化的视觉式呈现，以及以140bpm为节拍贯穿始终的平台跳跃设计都很巧妙。《Dark Echo》将声音的音波传播的方式作为恐怖游戏进行制作，腾讯功能游戏《长空暗影》则采用声像（Panning）来标识方位，确实构造出可以给盲人游玩的游戏。

![](../../.gitbook/assets/image%20%2824%29.png)

而从VJ的角度，同样以Shader作为主要调制玩法的《Mu Cartographer》让人想到了频谱分析，而从一些互动音频的教程上也能看到更多的交互可能，例如Ableton Live 的 Learning Synth 中具象的小蜜蜂对应frequency，以及图形化的合成器应用 ROTOR的交互。

##  重思电子游戏作为视-听-交互的递归系统

### Music as Generative System

在分享的前几天，我正好翻译了氛围音乐的开创者 Brian Eno的演讲《[生成式音乐 Generative Music](https://mp.weixin.qq.com/s?__biz=MzIzMjM0NDk1NQ==&mid=2247485867&idx=1&sn=def82fe71f58a5ac31e2e6e77f9eaf8a&scene=21#wechat_redirect)》，他是这样描述和理解生成式音乐的创作的：

The Considerations that are important, then, become questions of how system works and most important of all what you feed into the system. 那么，重要的考虑因素就变成了**「系统如何运作」**，以及最重要的**「你提供给系统了什么」**

 —— Generative Music. Brian Eno, 1996

Brian Eno自己晚年也做了很多交互式的音乐软件，其中最有名的就是他讲自己的一张专辑Reflection以交互应用的方式发布，如今依旧可以在AppStore找到这个208块人民币的应用

![](../../.gitbook/assets/image%20%2817%29.png)

除此之外John Cage 也同样说过类似的话：

 _"ask questions rather than make choices", then the answers, instead of coming from my likes and dislikes, come from chance operations, and that has the effect of opening me to possibilities that I hadn't considered. Chance-determined answers will open my mind to the world around._

_问问题，而不是做决定。其给出的回答，与其说来自于我个人的喜好，不如说来自于运气（chance）的运作，并且为我敞开某种我从未考虑过的可能性，这种取决于运气的回答打开了我对于周遭世界的思维。_

—— John Cage 1985

我们能在他们对于系统音乐的设计过程的描述中寻找到许多与游戏设计相类似的表述，因为游戏设计本身也是对可能性空间的探索与约束：无论是Jonathan Blow在演讲《游戏设计的真如 Truth in Game Design》中的谈的「系统会你答案你」Systems give you something back that you didn't put in，亦或是在Steve Swink 的《游戏感 Game Feel》一书中将电子游戏和游戏设计同样理解为关于可能性空间的设计（Game Design is also about set up possibilities space），这其中有非常类似的思路：

![](../../.gitbook/assets/image%20%285%29.png)

即我们完全可以将游戏系统理解为一个已经成型的系统，即回答了Brian Eno的第一个问题：「系统如何运作？」，而将我们音频设计师需要进行的声音设计理解为对第二个问题的回答「你提供给系统了什么？」，当然这需要的是音频设计高度了解游戏的互动层面甚至算法与数据层面的事情并且将其用做自己创作的领域。

这在2018年IGF 最佳音效奖获奖作品《Mini Metro 迷你地铁》的作者Rich Vreeland分享《GDC 2018 Serialism & Sonification in Mini Metro 》（笔记可见豆瓣@叶梓涛）中可以窥见这种合作的影子：

![](../../.gitbook/assets/image%20%2821%29.png)

在这个短小只有16分钟的演讲中，他叙述了一种Generative的方式，来自于Game Data 游戏数据与Authored Data 作者赋予的数据之间的结合（Reunion），即如何将这些数据进行十二音阶化，使其变得可听sonification，不使用循环的音轨，而是使用sequential sets of data to generate music and sound. 用游戏数据来设置声音的音高，响度，节奏，音长... 例如通过玩家的不同线路上的车站数量和位置进行不同节拍的生成，将车站形状映射为不同声音，将X轴的位置映射为声像，乘客映射为音量等等。

![](../../.gitbook/assets/image%20%2819%29.png)

在采访《The Programmed Music of Mini Metro》中，他也提到了启发了他的作曲家Steve Reich and Philip Glass，还有远被低估和在中文世界被忽视的动画大家，Norman McLaren的两分钟的实验动画作品《Dots 舞动的点》（[Norman McLaren - Dots \(1940\)](https://mp.weixin.qq.com/s?__biz=MzI5NTI1NDkxNw==&mid=2247483805&idx=1&sn=a072b73ba9fb6bff1a86916de0a6c3d2&scene=21#wechat_redirect)）。

![](../../.gitbook/assets/image%20%2810%29.png)

而实际上McLaren可能最令人惊叹的作品是他对于卡农的可视化表达和实验，1964年拍摄的实验短片《卡农 Canon》，可以说是在视觉动画与声音上开了先河与做了大量的工作，而这也是在视觉和声音上可能是更早的某种未被完全揭示（可能之后我会写McLaren以及音画协同）的Reunion。

![](../../.gitbook/assets/image%20%2820%29.png)

但实际上在这里希望揭示的是在玩法系统与声音之外再讲视觉同样作为一个生成式的存在拉入考量，这样的System Reunion所面向的某种目标，Rich Vreeland 也有很好的描述，对此，我认为对于一个游戏「好」的评价，至少需要有这个标准 —— **Holistic 整体化**，这或许来自于对于交互、视觉、声音之间不同颗粒度切分与展开的对应，某种意义上，所有的生成性的音乐与视觉都是对于不同系统的规则的设定与颗粒度切分。

_Granularity of System allows the soundscape to respond to game state instaneously and evolve with the metro system as it grows and a holistic system handles all of the gradation for you, ambient signature just becomes a part of music._

_系统的颗粒性允许了整体的声景去立刻地回应并且随着游戏的状态生长，就像是一个整体性的系统为你展现出每段层次，氛围式音效缓缓成为整体音乐的一部分。_

所以在这个角度上来说，游戏音频设计在于如何用将声音与整个游戏贯穿起来，然后你可以用无人深空的那个的表达，就是将整个乐队搬进游戏中，也可以用另一个比方：

**把整个游戏变成一件量身定做的乐器。**

![](../../.gitbook/assets/image%20%288%29.png)

所以在这个意义上，Reunion不仅仅是指声音和游戏系统之间的某种纠缠与重聚，背后也是对于音频设计师与游戏设计师的双向要求，如何相互理解对方所拥有的工具，如何对于整体游戏系统有精细化的理解并且能够相互协作构建映射，这样的整体性系统的一定是建立在视-听-玩法三方相互深刻理解的上的。

这也是我这次演讲希望给大家带出的我的一点对电子游戏的整体性思考，希望能有所启发。

### \*\*\*\*

### **End**

此外我与音频设计师Xichen在今年与去年的Global Game Jam 中进行了两次48小时的紧密合作，其中《C\(8,3\) [游戏0x007C：Là-bas \#1](http://mp.weixin.qq.com/s?__biz=MzIzMjM0NDk1NQ==&mid=2247484955&idx=1&sn=4aa44d5d16a4e36fe827b8cd12941b39&chksm=e8971a0fdfe09319ebf945fccc84106c8d68633cc95d6b7dfbe97a2b9f193fe8ad8bd6f6c3e4&scene=21#wechat_redirect)》可能更多是在今天所说的音乐分层Layering，节奏驱动输入时间窗 Audio Driven - Beat- Driven Input Timing，以及尝试性的做出了Generative Music的一次尝试；

而《剑入禅境》 [剑入禅境 Sword Zen \| Global Game Jam 2021](http://mp.weixin.qq.com/s?__biz=MzIzMjM0NDk1NQ==&mid=2247485641&idx=1&sn=a886a170c2add461c3ec4413504f333d&chksm=e89714dddfe09dcbdc9013e6c075ffa1ae04f26eccc7a8448cd7369ca7966362068b6456e70c&scene=21#wechat_redirect) 则可能是更完整的关于声音叙述的体验，核心在于用一个判断玩家呼吸是否控制好的一个参数驱动Wwise的RTPC曲线来控制不同声音状态的变化，以此来传递出「控制好呼吸则感知更敏锐」的体验。

可以算是我作为非典型游戏设计师，Xichen作为非典型作为游戏开发者的音频设计师 Audio Designer as Game Developer的两次Reunion的成果。

（视频的后面对这两个Game Jam作品的解说，并且Xichen也谈论如何直接在UE4中使用Wwise的回调来生成关卡的技术分享）

![](../../.gitbook/assets/image%20%2811%29.png)

分享者：叶梓涛 NExT Studios 游戏设计师，媒体实验室落日间主理人

感谢Wwise邀请及视频的录制编辑。

## 后记

关于这段时间为什么落日间谈论Audio和游戏音频的原因：

前些天在看爵士钢琴家比尔·埃文斯Bill Evans的一场谈话纪录片《比尔·埃文斯的普世性音乐思维 The Universal Mind of Bill Evans：The Creative Process and Self-Teaching》（B站 掘火中译），开场埃文斯就谈到了一种常人容易犯下的错误：

> 大部分人只是大而化之的地想要得到一个答案，一个差不多的成品 approximate the product ，却不肯去钻进去哪怕从一个真实的小的地方去做研究，从任何基本的层面与之发生实际的、真实的正面交锋，无论这种交锋多么基础，但一定要是全然真实，准确，且真刀真枪的。

他谈论到学习爵士在于，在实践中一点点地处理例如和声/节奏/变换等内容，对于每个问题都有意识地投入极其专注的注意力，直到这一处理过程退居二线而变为一种潜意识，而在这种过程中并不是依靠天赋，也不仅仅是粗略地某种感觉。

所以回到这次的分享以及这段时间落日间涉及到的音乐/声音问题也是如此，作为一个超高维的设计求解问题，**游戏设计同样需要对于程序/物理/文字/声音/图形各层次地解构性理解，或许有助于在其中寻找到能够相互映照地创作地机会**，而我认为从这个角度去做研究分析推进对系统与声音、图像的关系是有益的。

过几天可能会谈一下自己在7/11-7/12的CiGA Game Jam中个人制作的声音解谜的交互式小原型的开发始末以及其背后这段时间的技术和设计思路复盘与分享。

