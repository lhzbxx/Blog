---
title: 「半神」概念设计
tags:
  - 半神
date: 2016-07-28 01:38:57
updated: 2016-07-28 01:38:57
categories: 幻想故事
---

话说，我在建立这个博客网站的时候，当时的想法只是发布自己的一些构建软件或服务的流程和心得来做备忘和分享，顺便会发布一些自己设计的幻想框架，并尝试补全它们，用故事更好地描述脑海中的天马行空。但是感觉自己的拖延症确实到达一个境界了，特别是多线程、高并发地处理各种自己挖的坑，还要看许多干货，并且有计划补全一些之前没有接触或粗略地忽视了的技术细节和知识体系。

幻想故事却迟迟没有上架，噗噗！

不过自己挖的坑，含着泪也要填完！

当然，其实之前也有很多自认为很精彩的设计，不过就不一下子放出来了，保持神秘感，嘻嘻~

所以，这一次，就先介绍一下最近构建的「半神」。

<!-- more -->

## 起源

### Demigod

「半神」英文名为「Demigod」，实际上，这是我小时候玩过的一款当时并不称作MOBA的MOBA类游戏，当时沉迷了一段时间。

{% asset_image demigod-wallpaper-1920x1080.jpg [半神·Demigod] %}

图中所示是游戏中的一名英雄，也是最具有代表性的英雄（喂喂，这个游戏里只有10名英雄！），名为「岩塔战神」，非常适合新手入门，简单粗暴而又强力，因为它的技能是三个可以升级的被动，就是它背部的三座塔，而主动技能则是放置塔和吞噬建筑，可以说全自动输出，只需要奶奶奶就OK了。

咳咳，有点扯远了，这不是游戏攻略！

之所以起这个名字，其实也不是和这款游戏有多大的相关性，只是借用了这个名词，讲述的是另一种概念，仅仅作为自己对童年的怀念吧。

### 克苏鲁

说实话，其实我之前基本没有看过洛夫克拉夫特的系列小说，对于「克苏鲁神话」体系本身，仅仅是谜一般的对逼格的向往和隐隐约约自洽性体系构建的偏好，以及被那些受克苏鲁文化影响的电视剧或小说作品的熏陶，其实对克苏鲁本身也有一定的理解。比如说「True Detective」里的“The King in Yellow”，简直是有趣到恣意把玩而不腻味。

所以这个体系的构建也或多或少地被克苏鲁所影响了。

但其实，我表达的理念和洛夫克拉夫特相差甚远。

洛夫克拉夫特认为：

{% cq %} 我认为，人的思维缺乏将已知事物联系起来的能力，这是世上最仁慈的事了。人类居住在幽暗的海洋中一个名为无知的小岛上，这海洋浩淼无垠、蕴藏无穷秘密，但我们并不应该航行过远，探究太深。——洛夫克拉夫特，《克苏鲁的呼唤》{% endcq %}

所以，他的整个神话体系是无秩序的、黑暗向的、充满神秘感的。

而我，想要表达的是一个假想的、客观的、又带有世俗的哲学思考，比如三原神的设计，其实对我自己来说并不新鲜，我之前也有过类似的设计。

话不多说，下面就介绍具体的概念设计。

## 概念设计

### 三原神

三原神：混沌、光、纯粹。

混沌：最古老的真神、万物之源、不可被描述的存在，也是一切的起源，混沌代表了最为原始的状态，当混沌消失，迸发出无穷无尽的规则和力量，从而孕育了第二原神，即为光。没有人能够观想出混沌的形象，如果用凡间的词汇形容它，那就是无穷无尽的虚空。它无处不在，却又毫无踪迹，处于超越一切的时空之外。混沌没有起源，也没有结束，因为没有时间能够约束它；同时它也是不可描述的，因为“存在”本身，就是混沌“消失”后才诞生的概念。

光：宇宙规则的继承者、执法者之祖、时间与空间的管理者，从“历史”的角度来说，光才是第一位原神，他是一切物理规则的制定者和掌控者，任何在现实世界中的物质都要遵从光的意志。光只作为造物的观察者和监督者的身份而存在，从不干涉宇宙中的事务。

纯粹：亿万神明之神、不可被信仰的信仰之神、真实梦境的管理者。在光的时间与空间的集合中，漫漫长河洗礼之下，一种新的形态开始孕育，即为生命体。纯粹诞生于第一个生命体的萌芽，从某颗超巨星核心的剧烈爆炸中苏醒，并寄生于初始的肉身而成长起来，最终吞噬了整颗恒星——纯粹是三原神中唯一一个受制于时间的真神，同时也是唯一一个拥有具体形态、且可以复制与成长的真神。它为现实世界扩展了规则，并创建了真实梦境的维度，同时播种了自己的神格，故被称为亿万神明之神。但纯粹虽然为信仰之神，但却无法被观想，任何妄图描绘纯粹的形态的肉体都会被瞬间湮灭。

三这个概念在传统中的含义就不多提了，阐述的意味其实就是一生二，二生三，三生万物这样的富有中国特色的自然规律。

而这三个神虽然都被称为“原神”，但其实他们可以被视作是三代不同的“存在”。混沌其实从现代物理观来看，就是所谓的大爆炸理论中的“奇点”，或者说是“太初”。而光，则代表着“所有时间空间物质的总和”，亦即《淮南子》中所叙述的“往古来今谓之宙，四方上下谓之宇”。在神话体系中，光是一切的规则，代表着三维世界中的铁律，而光本身，则是超越三维世界的观察者。第三代神名为“纯粹”，其实也就意味着它的存在是可被读的、也是可被写的，它化身亿万，企图将意志延伸到宇宙的每处边缘，并且自创了超越宇宙的另一个维度的世界。所以，也可以说，纯粹才是生命体的始祖，它是最古老的“分布式”智能，但同时也具有非集中式管理的缺陷——那就是它无法掌控自己的每一个触角，这同时也导致了邪神的诞生，故事便起源于此。

说一句题外话，不得不说洛夫克拉夫特创造的“章鱼”和“触手”的形态设计是非常厉害的，因为我也实在想不到有什么更贴切的形象去表述纯粹所应有的姿态。

### 游牧人、邪神和半神

游牧人：灵魂工程师、游荡在星际的牧人、神王的具象化身、神格的播种者，游牧人是纯粹的化身，它在星际之中漫游，并为已孕育出生命体的星球播撒神格，为他们带来了信仰。

半神：被限制在肉体中的神，亦或是被称为拥有神格的生命体。

邪神：游牧人堕落后，被负面情绪所感染，力量不受控制地向创造和复苏的反面——毁灭与破坏而倾斜，它们往往挣脱生命体本身的桎梏，成为幻象中代表着疯狂与黑暗的元素拼凑的具象。邪神拥有甚至超越游牧人本身的力量，它们往往对其它生命体普遍怀有强烈的恶意。

从时间轴的维度上来说，游牧人就是纯粹的化身，它散播神格，将意志的源头、生命体的雏形、宿命的起点传递到宇宙中的各处。但是在这一过程中，出现了一些岔子。游牧人、或者说就是纯粹本身的意图是更多地复制自我，并让它们在不同环境中成长起来，繁荣整个宇宙，并且实现自己的真实梦境的“造物”的大工程计划（这也是称游牧人为工程师的一种解释）。

所以，半神是游牧人所想要的造物结果，然而其中却出现了邪神。

后续的一切便不受纯粹所控制的了，这也导致了真实梦境的污染。

### 肉身、精神体与法则

肉身：从宇宙规则中诞生的生命体，即现实世界中的躯壳，灵魂的容器。

精神体：即灵魂本身。

熔炉、梦境与潮汐法则：这三条法则是纯粹对现世的扩展规则。一是灵魂可以燃烧，并爆发出最猛烈的能量；二是日夜不仅带来明暗和引力的变化，同时会使生命体进入规律的起伏状态；三是灵魂在梦境与现世的交替之中，会如同潮汐一样释放出能量。

前面提到了，纯粹是唯一一个具象化的原神，虽然不可被观想，但智慧生命体对其较为准确的描述确是统一的“游弋在宇宙中的触手”和“亿万神明之神”。真实梦境虽然是非理性、抛弃了宇宙规则的世界，但它和真实世界的纽带却是一种“混合的规则”，那就是三大法则：熔炉、梦境与潮汐法则。

不过，还有一个有趣的问题，那就是人类作为地球上的第一代高智慧文明，这些凡人们是如何诞生的？那些茫茫多的、缺少神格、仅仅有微弱的灵魂的肉身是如何演化出来的？

事实上，是一切的根源——纯粹本身的属性所决定的。因为纯粹“可读”的属性，复制意志的本质其实是将其源头的信息序列化、并重写在其它载体上的结果，必然导致它的意志是会丢失的。而前面提到过，纯粹在宇宙中的存在实际上是受制于光的法则的，起码无法逃脱时间和空间的约束——这也就导致了在漫漫传播的过程中，神格的降级乃至丢失。而地球上的高智慧文明——人类，已经与纯粹大相背离，发展出的集中式智能与分布式差别极大，不兼容的情况愈加严重，信息丢失也就越来越多，在数十亿年的演化进程中，神格的觉醒成为了极小概率的事件。

此外，另一个值得探讨的问题是，神格到底是什么，它为何会展现出如此完全不同的形态。

神格的实质依旧是灵魂，即精神体——实际上，神格的威能主要还是体现在真实梦境之中。神格的形态与真实梦境密切相关，而在真实梦境中，世界的构建是随机和无序的，这也就导致了，孕育神格的环境实际上是不可预知的，也无法用现世中的物理规则所推测。只有神格释放，生成魔域的时候，才能在现世中初露端倪。

### 梦境、魔域与遗民

梦境：分为表征梦境和真实梦境，表征梦境是人类独有的幻想产物，借由物质世界中的物理规则和经历构筑的产物。而真实梦境是由古神所创造的精神世界，极少数人类可以褪去理性的外衣，回归灵魂的本质而被引导或直接进入真实梦境。

魔域：当神格寄生体释放出蕴含的巨大能量时，往往能造成真实梦境与现世的扭曲，导致真实梦境对现世造成违背理性和物理规则的影响。

遗民：没有灵魂的人类，亦不受宿命的牵连。是地球上一种特殊的存在，他们的始祖是代表着“恶性滋生”的大邪神“黑母羊”，它们的形态不断进化，却永远不会消亡。他们被赋予或者说被植入了唯一的、且不同的执念。遗民对于半神有着极强的杀伤力，因为他们不会被拖入魔域之中，同时他们拥有最完美的进化形态——摒弃了几乎所有生物特性上的缺点。

## 故事线

概念设计就先介绍到这里，虽然只是其中的一部分，但是也基本上表达出了我要构建的神话体系。

整个故事的脉络自然脱离不了半神之间的争斗。

暂时考虑有三条线吧，一是黑母羊的遗民宿命线、二是半神“冥府之握”的无限魔域大统治线、三是太古蛮荒复苏线。

OK，就这样吧，暂时写到这里。下一篇大概就是人物设计喽！

---