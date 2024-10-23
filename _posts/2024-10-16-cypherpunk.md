---
title: 隐私与透明：密码朋克运动的多维度探讨

date: 2024-10-16 12:00:00 +0800

categories: [Blockchain]

tags: [cypherpunk]

pin: true

math: false

image: https://fanwb.oss-cn-beijing.aliyuncs.com/img/cypherpunk-1.jpg

---

> 本文系统探讨了密码朋克运动的核心伦理观、认识论及实践策略，旨在深入剖析其在数字时代对个体隐私保护与权力机构透明度提升的重要贡献。密码朋克运动始于 20 世纪 90 年代，主张通过加密技术的广泛应用来维护个人隐私，对抗政府和企业日益增长的监控能力。其核心伦理观可概括为“弱者要隐私，强者要透明”，强调个人隐私权的同时，呼吁政府及大型机构提高透明度并接受公众监督。密码朋克认识论将加密技术作为数据行动主义的主要工具，通过主动与被动相结合的策略，在保护个人信息安全的同时促进社会公正。在实践层面，密码朋克运动通过创建维基解密等平台，实现了对大型权力机构的逆向监控，展现了加密技术在重塑权力关系和推动社会变革中的关键作用。本文通过对密码朋克理论与实践的分析，揭示了其在数字监控时代的重要意义，为理解与应对当前的全球数据监控环境提供了新的视角。
{: .prompt-tip }


---

## **引言**

密码朋克 (Cypherpunk) 运动始于 20 世纪 90 年代初，主张广泛应用强加密技术作为维护个人隐私及对抗数字时代权威政府的策略。加密技术被誉为“保持信息安全的艺术与科学”[^1]，对密码朋克而言，加密技术是抵御强势实体干预个人生活的核心工具。Robert Manne 阐述了密码朋克哲学的核心观点：“互联网时代的重大政治议题在于，国家是否会利用电子监控能力剥夺个人自由与隐私，抑或是自主的个人能否凭借新获得的电子武器破坏甚至瓦解国家权力。”[^2]密码朋克认为，审查与监控是计算机时代的双重威胁，Manne 进一步指出，“密码朋克最深层的体制对手即为国家安全局 (NSA)。”[^2]在 20 世纪 90 年代的加密战争 (Crypto War) 期间，密码朋克与国家安全局及联邦调查局 (FBI) 进行了正面交锋，挑战美国政府垄断密码学技术的企图[^3]。NSA 和 FBI 认为加密技术的普遍应用会阻碍国家安全情报和执法证据的搜集。而密码朋克则坚信，缺乏加密技术所提供的隐私保障，社会将不可避免地滑向威权主义。最终，密码朋克在加密战争中取得胜利，远促成了强加密技术向全球公众的普及。

尽管密码朋克运动在对抗监控的历史进程中发挥了重要作用，但其在监控研究领域的理论贡献，尤其是其对抗监控系统的策略，却未得到充分的认识，甚至时常遭到误解。例如 David Brin 曾批评密码朋克虚伪，认为其对隐私的关注源自一种“自我正义的狭隘视角，这种视角可能会阻碍我们探索未来数十年内可能遭遇的某些风险的有效解决方案”[^4]。Brin 认为，密码朋克的理论在两个自相矛盾的原则之间来回摇摆：“一方面，原则 A 认为增加信息或数据的流动性是危险的；另一方面，原则 B 则认为这种增加是有益的”。在 Brin 看来，密码朋克们是“以自我正义的态度要求”其对手提高透明度，同时却不愿自身受到相同的约束。此外，Mir Adnan Ali 与 Steve Mann 将密码朋克提倡的基于加密技术的隐私保护视为与“逆向监控” (sousveillance) 相对立。Ali 和 Mann 提出，“两者都能对交易中的信息进行控制，加密技术通过提供保持隐私的选项来实现这一点，而监控则通过提供分享信息的选项来实现。”[^5]


Brin 和 Mann 等人的观点源自于对密码朋克哲学中一些核心要素的误解。Ali 和 Mann 认为密码朋克仅专注于隐私问题，而缺乏对监控，尤其是逆向监控的关注。然而，正如 Suelette Dreyfus 所述：“密码朋克坚信个人应享有隐私权，同时政府应当公开透明并对公众负责”[^7]。密码朋克运动的核心理念可以浓缩为一句简洁而深刻的口号：“**弱者要隐私，强者要透明**”[^6]，密码朋克们认为，加密技术不仅能够保护个人隐私，还能通过特定形式的逆向监控促进透明度提升。换句话说，Ali 和 Mann 没有充分认识到密码朋克的观点，即**密码学既是反监控的工具，也是实施逆向监控的手段**。

而 Brin 则未能认识到**监控和透明度仅在权力关系的背景下才具有实质意义**。正如 Adam Moore 所指出的：“权力的一个显著特征是能够在要求他人公开信息的同时，自己却能保持信息的私密。”[^8] 当今密码朋克哲学的重要倡导者 Julian Assange 主张，隐私的价值不应仅基于其内在属性而被维护，而是应在“权力计算” (calculus of power) 的框架下得到保护，因为“隐私的丧失会加剧统治阶级与其他社会成员之间的权力失衡。”[^9]

本文的主要目标是系统化梳理密码朋克哲学的主要方面，以便更好地理解和学习该运动的思想和抵抗策略。文章分为四个部分。第一部分通过将密码朋克“弱者要隐私，强者要透明”的理念置于其历史和理论背景中，解释了密码朋克在 1990 年代加密战争中发挥的作用，并强调了权力在密码朋克对隐私、保密和透明度的理解中的重要性，概述了密码朋克伦理的基本规范性原则。与各种社会运动一样，密码朋克内部也存在意识形态和伦理上的分歧，同时存在明显的代际差异，本文所提供的视角主要反映了影响力最大的第三代密码朋克所表达的思想。

文章第二部分阐述了密码朋克认识论的核心要素。密码朋克认识论是以加密技术为核心的数据行动主义，主张依靠主动（要透明）和被动（要隐私）相结合的策略积极应对监控数据化的趋势。第三部分通过维基解密的案例，探讨了“强者要透明”的原则如何通过“密码朋克逆向监控”这一社会运动模式在实践中得以体现。最后，本文将密码朋克的数据行动主义置于“信息通量”的语境下，展示其在现有监控架构中的潜在应用价值。例如，NSA 和谷歌等机构可被视为“信息黑洞”，这些实体大量吸收外部数据，却几乎不对外部公开任何内部信息。密码朋克提出的“弱者要隐私，强者要透明”的理念，连同其主动与被动相结合的数据行动主义策略，形成了一种全新的监控抵抗范式，或许能为系统性调整信息通量提供新的思考方向。

## **密码朋克伦理观中的隐私与透明度** 

要深刻理解密码朋克“弱者要隐私，强者要透明”这一核心原则的源起，就必须追溯至密码朋克运动作为对“加密战争”之回应的兴起背景。这场“战争”实为美国政府与计算机专家、隐私倡导者及黑客之间的一场激烈博弈[^3]。自 20 世纪 90 年代至 21 世纪初，随着密码朋克运动的发展，新一代密码朋克不仅承袭了前辈对于隐私保护的重视，更进一步强调了对机构透明度的诉求。尽管在维护弱者隐私权益方面，密码朋克群体内部达成了广泛共识，但在要求权力机构透明度的问题上，成员间却显现出了明显的代际差异。直至后续世代，密码朋克伦理的核心理念才得到了全面的阐述与深化。

密码朋克组织最初形成于美国政府企图垄断密码学技术，阻止其向公众开放之时。1991 年初，时任参议院司法委员会主席的 Joe Biden 与其他议员联合提出了立法提案，意在禁止公民利用不可破解的加密技术保障电子文档和通信的安全。该提案要求所有电信运营商与设备制造商有义务确保，在合法授权下，政府能够获取语音、数据及其他通信形式的明文内容。面对这一提案，旧金山湾区的一批密码学爱好者迅速集结，发起抗议行动，旨在反抗政府对数字加密技术公共使用的限制，进而催生了密码朋克运动。90 年代期间，密码朋克与众多活动家联手对抗政府试图垄断密码学技术的举措，通过揭露并传播政府内部有关加密技术的机密资料，促使国家采取应对措施。尽管政府屡次尝试对密码朋克及其支持者提起诉讼或实施打压，但当联邦地区法院裁定加密软件属于代码范畴，而代码等同于言论，且言论自由受到宪法第一修正案保护之时，所有指控均告无效。法官 Betty Fletcher 明确表示：“政府对加密技术的管控……不仅可能侵犯密码学家依据第一修正案享有的权利，同时也可能触及我们每一个人作为加密技术受益者的宪法权益”[^3]。

鉴于密码朋克在加密战争中的角色，其规范理念中强调“为技术或资源有限的个体提供隐私”这一点就不足为奇了。密码朋克们常将数字时代的隐私威胁与美国十八世纪末期的情况相比较，那时美国宪法的制定者们正活跃于政坛[^10]。彼时，人们可以在远离城镇的地方进行私人对话，几乎不受任何形式的监控。然而，进入数字时代后，几乎所有的通讯和经济活动都发生在联网的计算机系统上，若不采用加密技术，个人隐私便难以维系。因此，[《密码朋克宣言》](https://www.activism.net/cypherpunk/manifesto.html)的作者 Eric Hughes 视密码学为“电子时代”保护隐私的关键手段。Hughes 将隐私定义为“**选择性地向外界展示自我的能力**”[^11]。但他发现在数字交易和通讯中，“一旦我的身份因交易的技术流程而被揭露，我就丧失了隐私”，也就意味着“我无法选择性地展现自我；我必须始终处于曝光状态”[^11]。但当个人采用加密技术时，便能重获掌控，因为人们能够自主决定如何向外界呈现自我。Hughes 指出，“我们不应期待政府、企业或任何大型、无名的组织会出于善意向我们提供隐私保护”，因此，“如果想要保留隐私，我们必须自行捍卫”。

密码朋克对隐私的关注已广为人知，但评论者往往仅聚焦于其对隐私的倡导，而忽视了他们对“强者要透明”的强烈呼吁，后者实际上同样重要的话题，但却鲜少被讨论。在透明度问题上，密码朋克内部的分歧比在隐私议题上的分歧要大得多。为了更好地理解“强者要透明”的规范含义，对比两种不同的透明度理论颇有裨益：一是 Tim May 提出的基于加密无政府主义的透明度理念，二是 Julian Assange 倡导的以正义为中心的透明度理念。这两种视角不仅揭示了密码朋克运动内部的多元性，也展示了其对社会变革的深远影响。

Tim May 认为，密码朋克运动的核心在于推动所谓的“加密无政府主义” (crypto anarchy)，这是一种融合了自由意志主义或无政府资本主义的思想体系，主张依靠密码技术的广泛应用来终结国家政府的权威。May 指出[^12]，数字加密技术有可能从三个方面对国家政府的稳定性构成挑战。首先，加密通信将极大地限制政府监控和审查信息的能力，从而削弱其对思想和言论的控制力。其次，加密货币的兴起将削减政府对货币流通的控制权以及征税的能力。第三，随着“信息流动市场”的兴起，秘密的保守将变得更加困难。在 May 的构想中，信息市场由经济利益所驱动，这会导致政府机密等敏感信息被高价出售。此外，一些市场将成为举报人和记者的聚集地，令其可借助加密技术匿名揭露文件。May 认为，即便是 CIA 也无力阻止其秘密被泄露至新闻组、网站或网页。但同时 May 也指出密码技术的应用并不等同于全方位的透明。他援引密码朋克的口号称：“加密无政府主义并不意味着一个没有秘密的社会；相反，它强调个人必须自行保护其秘密，不能依赖政府或公司。这也意味着像军队调动和生产计划这样的‘公共秘密’将难以长期保密”[^13]。总体而言，May 将透明度提升视为密码技术广泛运用的一种必然结果。

May 提出的密码朋克透明度理念主要聚焦于政府以及秘密文件交易。相比之下，Julian Assange [^14]则将透明度视为实现正义的手段，其对象涵盖了政府、企业、情报机构以及主要政党等一切不断寻求自身权力的扩大化的强势实体。Assange 反对将秘密文件当作商品在黑市上交易，他主张公开这些文件的目的在于促进正义、责任和知识共享，而非服务于个人或组织的经济利益[^15]。因此，Assange 将透明度视为推动机构改革、增强其公正性的手段，而非单纯市场力量的表现。作为第三代密码朋克的关键人物，Assange 为透明度的概念增添了道德维度，这是 May 所代表的第一代密码朋克未能充分探讨的。尽管 Assange 与 May 在透明度的具体实践中持有不同观点，但 Assange 同样认可加密技术作为社会和政治实践基石的重要性。Assange 通过构建加密的提交与发布平台维基解密 (WikiLeaks)，确保了举报者可以在不暴露身份的前提下，强制权力机构透明化，进而实现信息与权力的再分配。

在此背景下，可以看出某些针对密码朋克运动的批评其实具有误导性，甚至存在根本性的误解。例如，Brin 对密码朋克的批评[^4]其实源自未能准确把握该运动的核心理念，对数据收集问题的看法过于简单化，未能充分考虑不同个体和组织在分析和利用数据时的能力差异。这种忽视权力动态的观点，导致 Brin 错误地将“**隐私**” (privacy) 与“**保密**” (secrecy) 混为一谈，进而曲解了密码朋克的基本立场。在密码朋克看来，隐私与保密是截然不同的两个概念。隐私是个体及相对弱势群体应享有的权利，应通过加密技术加以保护；而保密则是强势组织掩盖其不义、不公乃至反民主行为的工具。在此背景下，透明度这一概念与个人及弱势组织的隐私无关，而是直接针对那些构成密码朋克所描述的“跨国监控反乌托邦”的政府、企业、主要政党及监控机构的保密行为。简而言之，对于密码朋克而言，隐私与保密是由权力关系界定的，而透明度是专门针对保密行为的。

其次，将密码朋克与主流加密宣传活动混为一谈，实际上是误判了密码朋克运动的视域。一些批评指出，部分加密倡导者过度关注西方中产阶级白人关切，而忽视了深受数据化和监控之害的被殖民及被种族压迫群体[^16]。这种批评揭示了一个关键问题：许多西方主流加密运动只是在反对政府对自己公民的监控，而对于本国推行的帝国主义和殖民主义外交政策则持默许态度。

此类批评在一定程度上是适用于以隐私为中心的第一代密码朋克的， 如 May 等人，其观点中确实含有西方优越论的成分。但第三代密码朋克在推广加密技术的过程中，则展现出了更为国际化的视野以及反帝国主义的立场。他们拒绝在全球政治讨论中采取“西方中心主义”的视角[^14]，并公开批评无人机战争、政权更迭行动、全球大规模监控以及帝国主义扩张等行为[^6][^17]。Julian Assange 本人更是明确表示，加密技术是反殖民主义斗争中的关键手段。他指出，“加密不仅能够保护个人的公民自由和权利，还能维护国家主权与独立，促进拥有共同目标的群体间的团结，以及推动全球解放的进程。它不仅是对抗国家对个人压迫的手段，也是抵制帝国对小国影响和控制的有效武器。”[^18]由此，我们能够更深刻地理解“弱者要隐私，强者要透明”这一密码朋克伦理核心原则在全球范围内的深远意义和实际应用。

密码朋克的观点体系包含了两大基本原则：一是保护个人隐私，二是追求机构透明度。一方面，密码学技术能够强化弱势群体的隐私保护，这是第一代密码朋克运动的核心主张；另一方面，密码学也被视为促进权力机构透明化的手段，这是后期密码朋克所坚持强调的重点。这一理念体系源自三十年前密码学倡导者们的政治参与实践，直到今天仍在为密码朋克运动在全球范围内开展的数据行动主义活动提供坚实的理论支撑。

## **数据行动主义视角下的密码朋克认识论** 

鉴于密码朋克运动主要利用信息技术和软件挑战当代社会的权力分配模式，在监控研究领域之外，该运动及其参与者常被贴上“黑客”或“黑客行为”的标签也就不足为奇了。密码朋克确实某种程度上继承了原始黑客文化的趣味性和创造性[^6]，但将密码朋克简单地归类为“黑客”可能会在多个层面上扭曲我们对该运动的理解。

首先，“黑客”一词本身具有高度争议性，对不同群体来说含义各异，将其应用于密码朋克可能会引发更多误解。其次，密码朋克运动的灵感主要来源于密码学家，而非传统意义上的黑客，这两个群体在起源上存在本质区别[^3]。第三，大多数将密码朋克视为黑客的研究倾向于将隐私与透明度视为互斥的概念，未能认识到在密码朋克的理念中，隐私与透明度实际上是相辅相成的两个方面。

为避免将密码朋克简单等同于黑客的模糊分类方式，我们应从数据行动主义的技术视角重新审视密码朋克。Stefania Milan 和 Lonneke van der Velden 提出[^19]，当代数据行动主义可以通过三个关键特征来定义：（1）它是对监控和社会数据化趋势的回应；（2）它倡导实践性的参与方式；（3）它不仅参与数字监控和数据技术的应用，同时对其进行批判性地挪用和改造。这些数据行动主义的特征共同构建了一种“另类认识论”，为描绘我们“数据化的社会现实”提供了新的叙事框架。他们认为，这种“概念框架”为更动态地理解以技术为中心的社会运动提供了有力工具。就其起源、倾向和原则而言，密码朋克运动完美诠释了这一数据行动主义概念，形成了一套独特的密码朋克认识论，加密技术在其中扮演着协调数字化社会关系的核心角色。

首先，Milan 和 van der Velden 指出，“数据化带来了根本性的范式转变”[^19]。自 20 世纪 80 年代末以来，学者们记录了从 20 世纪中叶的三重监控概念（物理监控、心理监控和数据监控）[^20]向数据化与数字化相结合的新模式转变，这种新模式将前三种监控方式统一于数据监控[^21]和数字监控[^22]的框架之下。20 世纪的数字数据监控取代并整合了几乎所有旧形式的音频/视频及电磁数据监控。元数据现已成为监控的主要手段，其背后是一种将数据视为待收割的原材料的意识形态[^23]。在此背景下，Milan 和 van der Velden 认为，数据行动主义者的驱动力在很大程度上源自其对数字数据监控普遍性的深刻认知。

密码朋克对数字数据监控的高度敏感敏感性可以追溯到该运动的根源。被誉为“数字匿名性的先知和教父”和“终极密码朋克”[^3]的 David Chaum 是一位数学家和密码学家，他的研究对密码朋克运动的形成产生了重要影响。早在 20 世纪 80 年代初，Chaum 就关注到国家和全球计算机系统中个人通信和交易的可追踪性问题，他警告说：“一个档案社会正在形成，在这个社会中，计算机可以通过收集日常消费交易中的数据来推断个人的生活方式、习惯、行踪和关系。” Chaum 对早期数据化趋势的观点受到 David Burnham 的《计算机国家的崛起》[^25]一书的启发，后者极具前瞻性地揭示了大规模计算机化官僚体系与数据库可能带来的风险，指出这些体系和数据库使得跟踪个人行为成为可能。Burnham 指出：“隐私的丧失是我们这个时代一个基本社会问题的关键症候，反映了大型公共与私人机构相对普通公民权力的日益增长”，特别是“计算机、数据库和计算机化通信网络”的使用，以及这些技术如何被权力机构用来“影响我们认为重要的事务”。可见密码朋克对强加密的倡导，根植于数据化引发的范式转变和对数字数据监控现象日益加剧的认识。

其次，Milan 和 van der Velden 指出，数据行动主义者采取实践导向的方法，不仅从事理论研究，更注重实际行动，这源于其对“信息获取、代码编写、合作以及通过技术创新改善世界”等理念的认同。这种实践精神在 Hughes 的密码朋克宣言中得到了充分展现。Hughes 曾言：“密码朋克编写代码。密码朋克积极投身于提升网络隐私安全。”[^11]实际上密码朋克也确实利用加密技术开发了众多数字工具，包括匿名邮件系统、加密货币以及其他隐私保护和匿名性应用程序。鉴于“隐私的维护有赖于社会成员之间的合作”，Hughes 强调，“密码朋克的代码向所有人免费开放”。密码朋克不仅编写代码，还将之共享给广大用户，这一做法至今仍被视为密码朋克社区的核心准则[^6]。

此外，Milan 和 van der Velden 注意到，数据行动主义者在对抗的同时还巧妙地利用数字监控和数据技术。数据行动主义具有多重意义和整体性：多重意义体现在其采用了“多种互补的手段来实现政治目标”；整体性则在于其深刻认识到“‘大数据’现象既存在负面影响也具备正面价值”。因此，数据行动主义既包括被动数据行动主义，即采取“加密或匿名网络等措施抵御国家和企业的监控”；也包括主动数据行动主义，即利用数据来“构建社会现实的替代性叙述、质疑其他描述的真实性和权威性、揭露不公并推动社会变革”[^19]。虽然在 Brin 等人的分析中，这两种策略看似冲突，但 Milan 和 van der Velden 认为二者实际是相辅相成的，因为“两者都视信息为塑造社会现实的关键社会力量”。

密码朋克的口号“弱者要隐私，强者要透明”十分恰当地概括了数据行动主义对数据化现象的回应。用加密技术保障弱势群体隐私实际上就是在实践被动的行动主义策略。诸如端到端加密的即时通讯应用、加密邮件服务、虚拟私人网络 (VPN)、Tor 浏览器和比特币等工具都是该策略的具体体现。而利用加密技术提高权力机构的透明度则代表了主动的行动主义立场。自 20 世纪 90 年代起，密码朋克不仅论述了加密技术在提升透明度方面的作用，还实际构建了若干基于加密技术的透明度平台，如 Tim May 的 BlackNet 及 John Young 的 Cryptome.org[^13]。Julian Assange 创办的维基解密，可能是这种主动数据行动主义模式最为成熟的实例。维基解密通过安全加密的匿名提交机制，为举报者提供了强大的保护，不仅减少了举报者被发现的风险，也由此降低了 Assange 所说的“勇气门槛”。鉴于大型权力机构的运行无法脱离大规模的数字官僚体系，Assange 认为，仅凭文件泄露的可能性，就足以迫使这些机构采取防御措施，从而削弱其执行秘密有害政策的能力。[^14]

Milan 和 van der Velden 将数据行动主义视为一个连续谱系，被动性和主动性数据行动主义分别位于谱系的两端。他们提到某些运动能够融合这两种极端，但未深入探讨密码朋克如何成为这种框架下数据行动主义的典范。以这种方式来理解作为数据行动主义者的密码朋克，不仅可以更深入地把握密码朋克伦理观的复杂性，也能更好地认识到将被动性和主动性数据行动主义相结合，形成一种连贯的社会与技术参与方式的重要性。

此外，尽管一些其他的社会运动也可被归类为数据行动主义，但只有密码朋克认识论着重强调了加密技术的重要性：该运动明确指出，其根基在于技术[^6]。很多社会运动都会利用加密来确保通信的安全性，但密码朋克的特别之处在于其将加密技术视为运动的核心。这种对加密技术的重视意味着**密码朋克认识论深入到了电子通信的本质逻辑之中**，这是其他认识论所难以企及的深度。在对最早的电子媒介——电报的研究中，James Carey 指出，“电报不仅是商业的新工具，也是一种新的思维方式，一种重塑思想的媒介”，它“重塑了意识的本质”[^26]。电报为加密通信革命奠定了基础。正如密码史学家 David Kahn[^27]所言，“电报造就了现代密码学。”结合 Carey 和 Kahn 的见解可知，加密技术已经成为电子时代人类意识的基本构成部分之一。如果将计算机视为电报的延续，那么密码朋克认识论将因其在技术和伦理层面对加密技术的重视而在各种形式的数据行动主义中独树一帜。作为数据行动主义的一种形式，密码朋克认识论不仅深入理解社会关系的数据化进程，还通过主动与被动、进攻与防御的策略来应对这一进程，一方面通过抵抗监控来挑战现有的权力结构，另一方面又积极参与到了促成当代监控体系的数字技术中，通过利用和改造将其转化为反抗的工具。

## **密码朋克逆向监控：重新审视维基解密** 

维基解密的创始人 Julian Assange 曾是密码朋克邮件列表的早期参与者之一，至今仍被视为该运动后继世代中最重要的代言人之一。在创立维基解密时，Assange 深受密码朋克“强者要透明”理念的启发。Assange 曾解释说：“密码朋克精神引导我思考如何最有效地对抗那些压迫性机构——无论是政府、企业还是监控组织……这些机构通常依赖于对数据的掌控，以此作为伤害、压迫或压制异议的手段。我认为，密码朋克精神能够保护人们免受此类伤害。”由此，维基解密成为了密码朋克逆向监控实践的典范。密码朋克逆向监控的理念与传统逆向监控理论一样，认为权力关系和权威是监控与逆向监控的核心议题[^28]，但同时也引入了更加现代的逆向监控形式，突破了传统的音/视频逆向监控框架，探索了利用网络和数据库来实现“对监控者的监控”。在从音/视频逆向监控到数字数据逆向监控演变的过程中，理论家们往往更关注逆向监控的内容，而相对忽略了逆向监控的形式。密码朋克逆向监控则在当代数字数据逆向监控的语境下，重新强调了**逆向监控形式的重要性**。

传统音/视频逆向监控理论明确指出，逆向监控的内容与形式均为实践的关键要素。在传统的逆向监控场景中，逆向监控者利用音/视频技术来对抗同类监控，形成了“摄像机对摄像机”的对峙局面。[^29]这种做法常被用来对抗执法机构，被称为“监控警察” (cop watching)。在这种情境下，逆向监控者会记录被拍摄对象（如警察或其他实体）的信息，相关资料日后可在法律诉讼等过程中作为权力滥用的证据。除了为逆向监控者提供**内容**之外，音频/视频逆向监控的**形式**还为其对象创造了一个全新的媒体环境，迫使其调整自身行为。在“监控警察”的情境中，公民不必等到警察暴力事件发生后才开始记录警察的行为，很多情况下，这种逆向监控都是预防性的。Singh 在其所谓的“预设监控” (Prolepticon) [^30]警务环境中观察到，“携带手机的公民不断预见到可能发生的负面执法行为并拍摄执法过程，影像由公民控制，并可通过互联网全球传播，这营造出了一个警察不确定自己是否正被监控的环境，进而促使警察成为自我约束的主体。在“预设监控”中，关键并不在于视频所记录下的具体内容，而在于手机摄像头的无处不在。当警察无法确定何时、何地或被何人拍摄时，就必须始终假定自己可能处于被拍摄的状态，进而避免采取不希望被记录和公开的行为。

维基解密作为深受密码朋克伦理影响的平台，实现了独特的密码朋克逆向监控模式。该平台利用数字技术收集文档与数据，并将其公之于众，利用网络实现信息的全球传播。与其它形式的数字逆向监控相仿，维基解密不仅促进了对监控内容的分析，还推动了对监控体系图景的描绘，进而揭露隐秘的权力运作模式。维基解密的部分公开资料，勾勒出了国家监控能力的轮廓，例如 Vault 7 系列资料中涵盖了“数千页详述中央情报局用于破解智能设备、电脑乃至互联网电视的高级软件工具与技术的文档”[^31]，首次向世界展示了未为人知的数据与设备安全漏洞，也为个人的安全与隐私保护措施调整提供了依据。此外，维基解密的其他公开资料，如伊拉克战争日志、阿富汗战争日记及美国国务院电报等，也为公众揭开了权力机构和军事人员在封闭决策过程中的真实样貌，为民主监督创造了机会[^17]。维基解密通过实践数据逆向监控的理念，向全球民众提供了关于其自身被监控状况的信息，并揭露了权力机构的行为模式。

但维基解密作为密码朋克逆向监控的典型代表，其意义远不止于此。维基解密不仅从内容上揭露监控实况、报道精英活动，更以其形式本身在系统层面干预并重塑了权力结构。维基解密所推动的逆向监控将每位内部人士都转变为了潜在的信息源、泄密者或举报人。与 Singh 所述的“预设监控”情境类似，维基解密力图营造一种令政治经济精英们无法确定自己是否处于监控之下的氛围，进而利用这种不确定性迫使其成为自我约束的主体。

要深入理解维基解密所带来的影响，可以参考 Steve Mann 关于开放系统、闭环系统以及反馈循环的论述[^32]。9·11 恐怖袭击事件后，美国政府出台了一系列旨在强化国家安全的措施，与此同时，政府的保密程度与监控力度也得到了显著提升。这些举措名义上是为了对抗恐怖主义，但 Mann 认为，政府在恐怖主义问题上的看法有误。政府倾向于认为，9·11 恐怖袭击得逞的原因在于情报机构的监控不足。而 Mann 则提出，恐怖主义实际上是对于政府不负责任行为的一种反应。在他看来，虽然政府认为隐私保护给予了恐怖分子可乘之机，但事实上正是过度的保密措施激发了恐怖主义情绪。因此，增强政府的保密性非但不能解决问题，反而可能使之恶化。缺乏有效的外部反馈，政府在不断加强保密的同时，也会无限制地扩张其权力。正如 Mann 所言：“秘密组织往往以开环模式运行，缺少能够提供关键制衡的正常反馈机制……问题的核心并不在于隐私。不应将责任归咎于那些没有被拍摄、没有留下指纹、没有被监控的公民，而是应当终止那套更大的高压锅式的机制。”只要实施有效的逆向监控，就能改变反馈机制进而影响系统的运行方式。

Assange 以相似的逻辑指出，保密性是所有政府腐败、不当行为和权威主义的核心诱因。他认为，通过构建看似无所不在的逆向监控环境，可以降低机构保密水平，进而减轻因腐败引发的负面影响。在此背景下，“阴谋”被定义为秘密策划并协同执行有害行为的过程；据此定义，任何因保密而产生的有害政府或企业政策均可被视为阴谋。政府之所以对其不道德的计划保密，是因为担心一旦公众知晓并持反对态度，这些计划就可能被阻止。然而，Assange 指出，现代政府依赖庞大的官僚体系来维持日常运作，进入数字时代后，这些官僚体系将记录存储于计算机网络之中，这为内部人员披露大量文件资料提供了更加便捷的渠道。尽管 Assange 的黑客伦理原则禁止非法窃取文件[^7]，但并不妨碍他建立一个加密的举报平台。Assange 在创立维基解密时写道：“我们认识到，发起一场全球范围内的大规模泄密运动，是我们所能采取的最为有效的政治干预手段”[^13]。当权力机构文件泄露时，原本开放的反馈循环将以两种方式得以闭合。首先是内容层面：公众能够阅读这些文件，对曝光的计划表达异议，这就可能阻止计划的实施[^14]。其次是形式层面：由于机构无法确定何时会遭受内部人员的监控，这会迫使其缩小内部通讯网络，从而削弱机构日常运作的效率，降低其实施不道德计划的能力[^33]。

密码朋克逆向监控对逆向监控的理论和实践做出了两项重要的贡献。一方面，在从音/视频逆向监控转向数字数据逆向监控的过程中，理论研究者逐渐将焦点更多地放在内容上。密码朋克逆向监控则重新引导我们关注数字数据逆向监控的形式，这有助于我们理解 Singh 的“预设监控”概念如何能够突破传统音/视频模式的局限，实现更广泛的扩展。另一方面，鉴于加密技术在密码朋克伦理观和认识论中的核心地位，密码朋克逆向监控进一步表明，加密技术的意义远不止于增强隐私保护，实践证明加密技术可以通过建立加密的举报和发布平台，有效促进逆向监控的发展。

## **密码朋克与信息黑洞** 

密码朋克伦理观为应对数字监控技术提供了规范性框架；密码朋克认识论则体现为一种结合了主动与被动策略的数据行动主义，旨在挑战现有的监控、信息流通和权力分配格局。作为这两者结合的产物，密码朋克反向监控为实现密码朋克追求的权力透明化目标提供了一条实现路径。整体而言，密码朋克的思想体系为我们理解和应对当前的监控环境带来了全新的视角，其核心理念和实践与当今最强大的公共和私有监控机构——美国国家安全局 (NSA) 和谷歌——形成了鲜明对比。借由 Bossewitch 和 Sinnreich[^34]提出的“信息流量” (information flux) 概念，我们可以更好地理解 NSA 和谷歌等机构的运作方式。这些机构力求成为所谓的“信息黑洞”，即尽可能多地收集外部数据，同时极力防止自身数据的外泄。在由这类监控机构主导的信息环境中，密码朋克提供了一种有效的应对策略。他们秉持“弱者要隐私，强者要透明”的理念，倡导使用加密技术来保护个人数据的安全的同时，也致力于对大型权力组织数据的收集。从这个角度讲，密码朋克伦理为大数据时代的个体提供了必要的概念框架、实践方法和工具，为构建更加公平的信息交流环境奠定了基础。

Bossewitch 和 Sinnreich 借鉴了物理学中的“通量”概念（即通过特定界面的物质流动速率）来描述现代信息流。他们指出，近年来网络空间中的信息通量呈现出指数级的增长趋势，但由于这些通量是多向的，在个人、组织和系统之间来回流动，因此理解信息网络中每个实体如何与网络交互变得尤为重要。研究整个信息网络，例如美国境内的总体信息通量，可以帮助我们了解信息流动的净方向，明确哪些实体在积极收发信息及其规模如何。Bossewitch 和 Sinnreich 进一步指出，分析信息通量有助于我们理解在当代监控体系和网络社会中“正在形成的知识/权力动态”。这种理解不仅能揭示信息控制的现状，也为探讨如何打破现有的不平衡、促进信息的公平流通提供了理论基础。

信息通量存在的三种模式：中性、正向和负向。这些术语不具备规范性含义，仅用于描述不同类型的流动，在特定情境下，负信息通量可能带来正面效果，而正信息通量则可能产生负面影响。中性通量则指所有参与者对信息享有平等和开放的访问权限，即实现了“完全透明”的状态。

在 Bossewitch 和 Sinnreich 看来，当前的监控环境下，最值得关注的是正向和负向两种通量。正向通量描述了一方比另一方更多地泄露或发送信息的情形，这表明前者在信息访问权方面处于劣势。相反，负向通量描述了一方比另一方收集更多信息的情况，这意味着前者在信息掌控上占据优势。基于“**信息即权力**”的原则，追求权力的个体或机构将努力保持最大的负向通量。某些行为体可能倾向于成为所谓的“贪婪收集者”，即采取积极的信息收集策略，但未必会严格防止自身数据的泄露。而追求更大权力的行为体，则会力求成为“信息黑洞”，即“试图从外部尽可能多地收集和分析信息，同时尽可能减少自身信息的泄露”[^34]的行为体。从这一点上看，信息黑洞的概念与数据行动主义其实有一定的相似性，因为成为黑洞意味着既要积极获取信息（主动策略），同时又要保护自身数据不被泄露（被动策略）。在 Bossewitch 和 Sinnreich 的构架中，信息黑洞是一个既多元又统一的概念，会通过一系列独立而互补的策略，不断增强其权力并巩固其在信息体系中的地位。

黑洞策略在全球两大监控巨头：NSA 和谷歌身上得到了完美体现。NSA 作为信息通量黑洞，其目标是全面掌握机构外部所有个人和组织的信息，同时极力保持自身的绝对机密性——即追求绝对的负向通量。Edward Snowden 泄露的文件揭示了 NSA 的一条监控原则：“嗅探一切，了解一切，收集一切，处理一切，利用一切”[^35]。而同时，NSA 对外部公开的信息则极其有限，以至于常被戏称为“不存在的机构” (No Such Agency)。NSA 在一项秘密行政命令下成立，在美国政府公开承认其存在之前，已经秘密运作了十多年。位于马里兰州米德堡的 NSA 总部，以其著名的“三层围栏”著称，象征着其对组织机密性的极致追求。正如 Steven Levy所述：“围绕 NSA 总部的三层电网和铁丝网不仅是物理障碍，更是 NSA 近乎偏执地隐藏其自身及活动信息的象征。”[^3]尽管 Snowden 的爆料说明即使是 NSA 级别的保密措施也无法完全防止数据泄露，但 NSA 仍在努力成为信息黑洞，力求实现信息的单向流动，所有信息只进不出。

谷歌同样追求成为信息黑洞的地位。为了满足广告收入的需求，谷歌在数据收集上表现得异常激进，几乎无孔不入地收集用户的各类信息；这种监控资本主义模式最终促使谷歌的业务从搜索引擎扩展至电子邮件、浏览器、操作系统和智能手机等多个领域，从而能够捕获大量的用户活动数据。从某种程度上讲，谷歌堪称私营领域中“嗅探一切，了解一切，收集一切”的机构。与 NSA 一样，谷歌对其核心技术和算法保持着高度的保密，因为在用户不知情的情况下收集数据的能力正是其商业成功的关键。前谷歌高管 Douglas Edwards 曾提到，联合创始人 Larry Page 坚决反对任何可能泄露技术秘密或引发隐私争议、威胁到公司数据收集能力的行为[^36]。谷歌并未给予用户对其数据收集过程的知情同意权，而是选择在“完全保密”的状态下运营。与 NSA 一样，谷歌虽然难以做到完全不泄露信息，但同样致力于通过维持最大的负信息通量成为信息黑洞。

面对诸如 NSA 和谷歌等庞大监控机构所构建的信息黑洞，密码朋克伦理提出了一种简洁而有力的应对策略：个人也应努力成为信息黑洞。密码朋克倡导的“弱者要隐私，强者要透明”不仅号召公民和活动家保护个人隐私，还鼓励大家积极参与到增强隐私保护和推动透明度提升的项目中。密码朋克伦理的指导原则赋予了个人学习、掌握并应用技术工具的能力，以便为自己创造负向信息通量，既能在监控环境中保护个人或组织的数据（被动防御），又能积极收集有关其网络环境的信息（主动进攻）。

隐私保护一直是密码朋克关注的焦点，当这一关注点与密码朋克逆向监控相结合时，便产生了更为深刻的意涵。例如，Julian Assange 曾将维基解密描述为“人民的情报机构”[^15]，这表明维基解密实际上是从弱势群体的角度出发在模仿 NSA 的工作方式。不过 Assange 强调，维基解密与传统国家情报机构的关键区别在于，前者公开分享其调查结果，而后者则维持高度保密。这一点至关重要，因为如果维基解密真正成为了人民的情报机构，且确实践行了密码朋克逆向监控的理念，那么它就成为了吹哨人、记者和活动家用来挑战如 NSA、谷歌等信息黑洞、抗衡当代监控社会中权力动态并实现对强者问责的工具。作为主动数据行动主义的象征，维基解密致力于阻止强大的监控机构实现绝对负向信息通量，从而为构建更加公平、透明的信息生态系统贡献力量。

当然，正如 NSA 和谷歌难以实现绝对负通量一样，个人也无法做到这一点。不过实现绝对负向通量并不是密码朋克伦理的最终目标。密码朋克强调的是保护隐私，而**隐私的本质是个体自由且选择性地向外界展示自己的能力**。因此，绝对负向通量不仅在现实中难以达成，而且也不符合密码朋克的精神，因为这将导致人际交往的隔绝。尽管如此，但密码朋克伦理至少提供了一个实用的基本框架，来帮助个人理解如何通过积极参与技术和网络通信系统来控制和调整信息流，进而以此恢复权力平衡。

关于信息通量和黑洞的讨论，使我们能更动态地理解监控机构与反抗社会运动之间的关系。Yasha Levine 曾将密码朋克运动描述为美国公私监控体系的对立面[^37]，他写道：

> 密码朋克对未来的展望是五角大楼和硅谷所追求的军事网络梦想的反面：不是利用全球计算机系统使世界更加透明和可预测，密码朋克希望通过计算机和密码学使世界变得不透明和不可追踪。这是一种反作用力，一种旨在保护个人隐私和自由的网络武器，用以对抗政府监控和控制的网络武器。

尽管该诠释揭示了密码朋克运动的核心理念，但此视角仍有一定的局限性。从信息通量的角度来看，五角大楼和硅谷与挑战其权威的社会运动之间的关系，并非简单的“反转”。实际上这是一个多方面竞争的过程，各方都在争夺对信息流的控制权。五角大楼和硅谷追求的不仅仅是透明度，而是希望他人透明同时自身保密。同样，密码朋克的关注点也不仅限于保护弱者的隐私，也同样追求强者的透明。因此，这场斗争并不是透明与隐私之间的零和博弈，而是一场黑洞间为了各自利益而争夺信息通量控制权的较量。

## **总结**

密码朋克运动为对抗当前的全球数据监控体系提供了简单有效的参与模型。密码朋克伦理提出了“弱者要隐私，强者要透明”的规范性原则，旨在保护权力结构中处于弱势地位的实体，并对权力机构进行制约。密码朋克认识论将加密技术视为有力的数据行动主义手段，通过主动与被动相结合的策略，可以有效实现其规范性原则。密码朋克逆向监控是追求权力机构透明化的一种实践范式，强调数字数据逆向监控在形式和内容上的双重效益。总体而言，密码朋克的世界观呼吁个体尽力成为信息黑洞，以从系统层面控制并改变信息通量，进而使权利结构的重塑成为可能。

实践者通过行动与反思构建其道德世界。理论与实践是相辅相成的，通过考察密码朋克等行动者的理念，我们得以更深入地反思和质疑主导自身认识环境的主流叙事与思维方式。密码朋克运动创造的新范式是对当代权力机构监控策略的有力回应，并在技术、道德、认知和实践层面为其愿景的实现提供了全面的支持。未来，密码朋克的核心理念和实践策略，以及对信息权力关系的深刻洞察，将继续为我们理解和应对复杂的数据监控社会提供帮助，为构建更加公平、透明的信息生态贡献力量。

---
**参考**

[^1]: Schneier, Bruce. 1996. Applied Cryptography: Protocols, Algorithms and Source Code in C. Second edition.
[^2]: Manne, Robert. 2011. The Cypherpunk Revolutionary. The Monthly, February 16. http://archive.fo/kwI60 .
[^3]:  Levy, Steve. 2001. Crypto: How the Code Rebels Beat the Government—Saving Privacy in the Digital Age. 
[^4]: Brin, David. 1998. The Transparent Society: Will Technology Force Us to Choose Between Privacy and Freedom? Reading, MA: Addison-Wesley.
[^5]: The Inevitability of the Transition from a Surveillance-Society to a Veillance-Society: Moral and Economic Grounding for Sousveillance. Presented at The IEEE International Symposium on Technology and Society, Ontario, CA, June 27–29, 243–254. Piscataway, NJ: IEEE.
[^6]: Assange, Julian, Jacob Appelbaum, Andy Müller-Maguhn, and Jérémie Zimmermann. 2012. Cypherpunks: Freedom and the Future of the Internet.
[^7]: Dreyfus, Suelette, and Julian Assange. 2012. Underground.
[^8]: Moore, Adam D. 2011. Privacy, Security, and Government Surveillance: WikiLeaks and the New Accountability. Public Affairs Quarterly 25 (2): 141–156.
[^9]: Assange, Julian. 2014. Who Should Own the Internet? New York Times, December 4. https://archive.fo/vxLJd
[^10]: Castronovo, Russ. 2013. Ben Franklin and WikiLeaks. Critical Inquiry 39 (3): 425–450
[^11]:Hughes, Eric. 2001. A Cypherpunk’s Manifesto. In Crypto Anarchy, Cyberstates, and Pirate Utopias, edited by Peter Ludlow, 81–84.
[^12]: May, Timothy. 2001a. The Crypto Anarchist Manifesto. In Crypto Anarchy, Cyberstates, and Pirate Utopias, edited by Peter Ludlow, 61–64.
[^13]:Greenberg, Andy. 2012. This Machine Kills Secrets: How WikiLeakers, Cypherpunks, and Hacktivists Aim to Free the World’s Information.
[^14]: Assange, Julian. 2016. When Google Met WikiLeaks.
[^15]: Assange, Julian. 2011. Of the People and For the People.
[^16]: Gürses, Seda, Arun Kundnani, and Joris Van Hoboken. 2016. Crypto and Empire: The Contradictions of Counter-Surveillance Advocacy. Media, Culture & Society 38 (4): 576–590.
[^17]: Assange, Julian. 2015. Introduction: WikiLeaks and Empire. In The WikiLeaks Files: The World According to US Empire, by WikiLeaks, 1–19.
[^18]: Assange, Julian. 2013. How Cryptography is a Key Weapon in the Fight Against Empire States. The Guardian, July 9.https://archive.ph/Mbsx4
[^19]: Milan, Stefania, and Lonneke van der Velden. 2016. The Alternative Epistemologies of Data Activism. Digital Culture and Society 2 (2): 57–74.
[^20]: Westin, Alan. F. 1967. Privacy and Freedom. 
[^21]: Clarke, Roger. A. 1988. Information Technology and Dataveillance. Communications of the AMC 31(5): 498–512.
[^22]: Graham, Stephen, and David Wood. 2003. Digitizing Surveillance: Categorization, Space, Inequality. Critical Social Policy 23 (2): 227–248.
[^23]: van Dijck, José. 2014. Datafication, Dataism and Dataveillance: Big Data Between Scientific Paradigm and Ideology. Surveillance & Society 12 (2): 197–208.
[^24]: Chaum, David. 1985. Security Without Identification: Transaction Systems to Make Big Brother Obsolete. Communications of the ACM 28 (10): 1030–1044.
[^25]: Burnham, David. 2014. The Rise of the Computer State: The Threat to Our Freedoms, Our Ethics and Our Democratic Process.
[^26]: Carey, James. 2009. Culture as Communication: Essays on Media and Society. Revised edition.
[^27]: Kahn, David. 1967. The Codebreakers: The Story of Secret Writing.
[^28]: Mann, Steve, and Joseph Ferenbok. 2013. New Media and the Power Politics of Sousveillance in a Surveillance-Dominated World. Surveillance & Society 11 (1/2): 18–34.
[^29]: Mann, Steve, Jason Nolan, and Barry Wellmann. 2003. Sousveillance: Inventing and Using Wearable Computing Devices for Data Collection in Surveillance Environments. Surveillance & Society 1 (3): 331–355.
[^30]: Singh, Ajay. 2017. Prolepticon: Anticipatory Citizen Surveillance of the Police. Surveillance & Society 15 (5): 676–688.
[^31]: Shane, Scott, Matthew Rosenberg, and Andrew W. Lehren. 2017. WikiLeaks Releases Trove of Alleged C.I.A. Hacking Documents. New York Times, March 7. https://archive.fo/nY9Hs
[^32]: Mann, Steve. 2002. Sousveillance, Not Just Surveillance, in Response to Terrorism. Metal and Flesh 6 (1): 1–8.
[^33]: Assange, Julian. 2006. Conspiracy as Governance. Cryptome.org, December 3. http://archive.fo/kr8Pr
[^34]: Bossewitch, Jonah, and Aram Sinnreich. 2012. The End of Forgetting: Strategic Agency Beyond the Panopticon. New Media & Society 15 (2): 224–242.
[^35]: Greenwald, Glenn. 2014. No Place to Hide: Edward Snowden, the NSA, and the US Surveillance State.
[^36]: Zuboff, Shoshana. 2019. The Age of Surveillance Capitalism: The Fight for a Human Future at the New Frontier of Power.
[^37]: Levine, Yasha. 2018. Surveillance Valley: The Secret Military History of the Internet.