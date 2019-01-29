# 写在18年底的后端社招面试经历(两年经验): 蚂蚁 头条 PingCAP

去年（18年）底想出来看看机会，最后很幸运地拿到了**PingCAP**，**今日头条**以及**蚂蚁金服** 的 offer。这篇所谓面经并不想像成功学文章那样教你"XX 步拿到 BAT offer"，这里我只想分享一下自己在"骑驴找马"中的心路历程（但说不定你看了这篇文章也能进入拿到心仪的 offer😜）。当然，一家之言，难免粗浅，如有不妥，敬请指正。

全文将相当长，假如只对一家公司感兴趣的话可以直接跳过去：

* [准备过程](#准备过程)
* [PingCAP](#pingcap)
* [蚂蚁](#蚂蚁)
* [头条](#头条)
* [总结](#总结)

# 准备过程

我自己是本科毕业后再老东家干了两年多，老东家算是一家"小公司"(毕竟这年头没有 BAT 或 TMD 的 title 都不好意思报出身)，毕业这两年多我也没有在大厂待过，因此找坑的时候我是非常非常虚的。迫于心慌，我好好思考了一阵来给自己打气，当时真正找坑和准备面试的过程大概分为这几个阶段：

- 反思：自己是不是真的要离职，假如不离职，在老东家接下来应该做什么才能继续提升？
- 定位：我在硬性技能（编码、架构）上的长处在哪？我在软技能（沟通，团队）上的长处在哪？这步顺带写了简历
- 寻找平台：哪些平台能同时满足：1、有挑战有上升空间；2、符合我的定位方向；3、团队氛围和老东家一样好（或更好）
- 找人内推：基本都是在 v2 上找的（诚挚感谢各位帮助我内推的大佬）
- 面试谈 offer

`定位`这一步其实花了好几天时间，我先是梳理了自己的项目经历和工作内容的专长，把 Java + Golang，做过的面比较广（业务，中间件，基础架构都做过）以及对 k8s 云原生有专长和兴趣作为自己的"硬招牌"。然后把学习能力强，喜欢沟通合作，渴望挑战作为我的"软招牌"，最后把自己定位成一个"在过往经历中展现出了过人学习能力和钻研能力，同时渴望挑战，不愿意呆在舒适区"的形象（妈呀打这段话的时候太羞耻了！！！）。

这个过程中，我的方法论是"换位思考"。我自己也面试过不少人（所以平时公司让我去面试，虽然累点苦点，但也都是积累呀），并且也和 HR 以及放出 HC 的业务方聊过我们希望放什么样的人进来。因此全程都在以面试官的心态来考察自己：

> 假如我是面试官，我会招怎样的人进来做我的同事？

举两个例子，下面都是我在这个过程中考虑过的问题（当然只是我自己的喜好）：

* 对于一个毕业两年多的人，我最希望他有什么特质？这个阶段的人其实还是"空杯"，我希望他有很强的学习能力和进取心，给自己部门培养出一个超级生产力；
* 什么样的行为会让我"讨厌一份简历"：把每个项目都大写特写，尤其是陈述细节没有重点；罗列框架当能力，用过了一类场景的框架就觉得能解决一类业务诸如此类；
* 面试的时候我会先问哪些问题？一是简历上写了"理解"或"精通"的语言与中间件；二是简历上写得比较有趣，又没有完全交代清楚的项目；

`定位`之后，我要找的下一个位置基本锁定在了 PaaS、云原生、中间件方向。那接下来就是找坑了，这段时间"寒冬论"炒的火热，好坑确实挺难找，最后兜兜转转找了四家的内推：Shopee（新加坡）、PingCAP、头条、蚂蚁。Shopee 其实挺遗憾的，12月初投完简历1月初才收到答复，而当时另几家面试已经临近尾声，于是选择了推掉。

这几家的简历投递出去之后，我着重把简历里"埋的几个坑"，也就是自己写了"理解并掌握"的语言与中间件以及专门用来勾引面试官问的项目好好复习了一遍。事后发现这一步还挺关键的，很多知识性的内容要是不复习一下真就全忘了，这也算临阵磨枪，不快也光了吧。

接下来就进入重头戏，逐家讲一下自己的面试体验：

- [PingCAP - Cloud 方向](#pingcap)
- [蚂蚁 - 容器调度方向（CTO线）](#蚂蚁)
- [头条 - 工程效能方向](#头条)

# PingCAP

![pingcap](/img/interview/pingcap.jpg)

* [面试前](#面试前-1)
* ["一面"](#一面-1)
* [二面](#二面-1)
* [三面](#三面-1)
* [四面](#四面-1)
* [五面](#五面-1)
* [PingCAP 小结](#pingcap-小结)

## 面试前

PingCAP 的简历响应是最快的，内推之后第二天 HR 小姐姐就联系了我。电话接通之后先是简单聊了一下人生，然后就是社招三问 ["**为啥离职啊?**","**现在待遇咋样啊?**","**期望待遇咋样啊?**"]，天知道这通电话是我开始投简历之后的第一通电话面试，之前还完全没有准备过类似的问题，只能稀里哗啦用["现在公司的发展有点瓶颈，加上一直对您公司钦慕有加☺️","我现在待遇是xxx但我司除了base之外还有xxx以及我马上要提薪了🤪‍","其实比起待遇我更看重平台和挑战(狗头)，但是基本的薪资需求我还是希望能xxx🤑"]这样的和稀泥应付过去。内心稍稍平静之后小姐姐跟我讲了讲我意向部门的结构和主体业务，然后交代了一下接下来的面试流程，约了"一面"并且加了微信。

"一面"加了引号，这是因为"一面"其实是在微信上布置了一个小项目，然后约定好时间验收。

> 这里要特别感谢一下 PingCAP 的 HR 小姐姐，加了微信之后全程帮助我协调面试时间并不厌其烦地回答我各种奇奇怪怪的问题，最后谈 offer 的时候还给我准备了一个惊喜。面试体验直接满星<3!

## "一面"

早就听说 PingCAP 一面要写小项目，我自己心里其实是跃跃欲试的。面试官给的项目要求大体是这样：

> K8S 容器化之后应用容器里几乎没有什么可用的调试工具，可以利用容器 Namespace 共享的思路，启动一个包含各种调试工具（比如 netstat, gdb）的容器，加入到 pod 的 pid、net 等 namespace 中， 实现对任意 pod 的 debug 功能。现在希望利用 kubectl plugin 机制实现一个插件，用于 debug 任意一个 pod 里的容器，达到 `kubectl exec` 的使用体验.

当时因为工作日抽不出时间，就隔了几天到周五晚上开始写，周六晚上写完并且把[项目地址](https://github.com/aylei/kubectl-debug) 分享到了 [Reddit 上](https://www.reddit.com/r/devops/comments/a8vnt5/i_wrote_a_tool_to_debug_kubernetes_pods_more/)。没想到运气不错收了 100 多个 star，这下我就觉得"哦豁，这轮应该稳了吧！"（结果后来发现这几乎是我唯一一把觉得自己"稳了的"面试...)

## 二面

二面是一位 Cloud 方向的前辈面我，全程大概微信语音聊了50多分钟：

- 问项目经历，聊了两个项目
- 对 Kubernetes 了解怎么样，看过源码吗？ 
    - k8s 的代码我以前其实只看过 kubelet，临阵磨枪的时候把 apiserver、scheduler、controller-manager 都看了一遍，笑容渐渐出现。
- Kubernetes 的 Service 是什么概念，怎么实现的？
- 你刚说到 Informer，Informer 是怎么实现的，有什么作用？
- StatefulSet 用过吗？有什么特点？
- StatefulSet 的滚动升级是如何实现的？
- 现在我们希望只升级 StatefulSet 中的任意个节点进行测试, 可以怎么做?
    - 这题没有思路，只好强答用"两个 StatefulSet"，后来一想起一个新的 StatefulSet 那 PV 里的数据就丢了，其实正确办法是利用 partition 机制，笑容渐渐消失。
- Kubernetes 的所有资源约定了版本号, 为什么要这么做?
    - 第二个拿不准的问题，我面试前就反复告诉自己"不要强答"以及"不知道的题就讲思路"，于是就说这块代码确实没看过，但是根据微服务 API 的设计理念，版本号的作用有巴拉巴拉。答完似乎面试官还算满意，于是又往下挖了一句：
- 假如有多几个版本号并存, 那么 K8S 服务端需要维护几套代码?
    - 这题完全不知道，内心逐渐焦灼，立马走老套路"这我没看过 k8s 代码怎么写的无法确定（想表达自己真正看过代码才会确认，凸显自己严谨...我的妈呀），但假如由我来写这份代码（装作非常自信），我会只会维护一份最新的 Model，然后设计对应一个版本段的 Adpater 将老版本的 Model 转化过来巴拉巴拉"。到这里我已经虚的不行了
- OK，那接下来我们聊聊 Golang （我：长舒一口气)
- 看一下这段代码有没有问题(一段 golang for-range 里 goroutine 闭包捕获的代码)，为什么?
- goroutine 是怎么调度的？
- goroutine 和 kernel thread 之间是什么关系？
- 有什么想问我的？

面完之后感觉可能要挂，结果第二天 HR 小姐姐就来安排三面了，长舒一口气：运气还可以哈。

## 三面

三面是和整个大部门的 Leader 聊，面试官很能聊（声音还很好听！）而且技术非常全面，全程大概微信语音聊了80多分钟：

- 给我介绍 PingCAP 相关团队的职责与挑战
- 聊为什么出来看机会，以及未来的职业规划
- 聊我之前做的一个数据同步的项目，大概内容是订阅 MySQL Binlog，sink 到搜索索引、分库分表以及业务事件订阅流中
- 为什么数据同步里选择了 xxxx 开源项目，优势在哪？
- 订阅分库分表的 Binlog 怎么订阅？
- 分库分表的数据源中假如存在主键冲突要怎么解决？
- 怎么保证下游对 Binlog 的消费顺序？
- 如何在下游保证消费时的事务原子性？
- 描述了一下 tidb 的 binlog 架构，问这种场景下怎么保证 Binlog 顺序
- 聊一个上了 Kubernetes 的项目，问了一些细节和坑
- 用 Kubernetes 之后，解决了哪些问题？
- 聊我之前做的监控警报项目，问背景和产出
- Prometheus 单实例数据量级 hold 不住了，有什么解决方案？
- 有什么想问我的？

简历里的"数据同步"这个项目我是好好复习过自己当年写的调研文档和架构文档的，也做了被问的准备（换位思考，是我我也问。这个其实就是我专门希望面试官来挖细节的项目）。最后确实被问最多的就是这个项目，运气真的不错😁。

## 四面

四面到了现场面，有两位面试官一起跟我聊，大约聊了 40 多分钟：

- 聊"配置中心"项目的细节
- 为什么不用 ZK，要自己再写一个"配置中心"
    - 这个问题让我措手不及，我只好坦白：当时年轻，想刷经验，事后才领悟到不要重复造轮子，当然最后系统的产出也不错（后面这两句是我临时加的，不能让面试官觉得我是一个不看全局只顾自己刷经验的人）
- 配置中心怎么做服务发现的？怎么做 failover 的？
- 用 Kubernetes 碰到过哪些坑？
- 对 Prometheus 做了哪些改动？
- 对 Alertmanager 做了哪些改动？
- 监控系统怎么做"自监控"？
- 跨机房的网络问题怎么监控？
- 有什么想问我们的？

四面是纯项目，里面的经验就不太通用了。但这里面有个细节，就是到中途的时候两个面试官互相对了一下"还有什么想问的吗？"我意识到面试官们想问的问题不多了，可时间大约才过了20分钟（面试时间过短是一个 bad smell）。于是之后几个监控的问题我都尽量说得很细，同时顺便提一下"还有一个方面我们当时也做了挺多工作"，暗示面试官往下挖的线索。不知道这招有没有奏效，反正这一面算是有惊无险过啦。

## 五面

技术面到四面就结束了，五面是创始人面（有幸和崔秋大佬聊了20多分钟人生），面完之后就是 offer call 了。

## PingCAP 小结

一些主观评价：

* 面试难度：正常
* 面试体验：我给满分
* 问题偏向：项目经历、工程能力

> 最后真的想夸一下 PingCAP（因为面试体验超棒呀！）。投 PingCAP 的初衷是觉得这个团队的工程师文化非常浓，大牛云集，同时 TiDB 够牛逼，项目开源的模式我内心也很认可。只是挂羊头卖狗肉的公司也不少，好多 JD 上写着工程师文化浓郁，其实很多根本不是那么回事儿。但是经过 PingCAP 的五轮面试之后，我是实打实地感受到了工程师文化：面试里没有一任何个"刁难人的问题"，每一位面试官感兴趣的是我的工程思维、学习能力、技术见解，同时还非常热衷于与我讨论和深挖一些坑与技术决策。这种感觉就很爽：**面试官是懂我的，我作为工程师的思维能力与技术见解得到了认可与尊重。** 这种氛围是口号喊不出来的，因为它的硬性指标就是这其中的每一个人要热爱技术并且工程经验丰富。

# 蚂蚁 - CTO线

![ant](/img/interview/antfinacial.jpeg)

* [面试前](#面试前-2)
* [一面](#一面-2)
* [二面](#二面-2)
* [三面](#三面-2)
* [四面](#四面-2)
* [五面](#五面-2)
* [六面（HR）](#六面-2)
* [小结](#小结-1)

## 面试前

蚂蚁的面试挺独特，每轮面试都没有 HR 约时间，一般是晚上 8 点左右面试官来一个电话，问是否能面试，能的话开始面，不能就约一个其它时间。这里面有两个蛋疼的点：

* 每轮面试之间间隔时间挺长的，最长一次隔了一周才有电话过来约下一面
* 电话都是座机打过来的，回拨需要分机号，因此我没法联系到任何人

这两点让我好几次都觉得自己已经挂了，结果在已经不抱希望的时候又收到面试官电话开始面试...可以说是大起大落很刺激了。

全程 6 面，前五面技术面，电话面试，最后一面是 HR 面，现场面。

## 一面

- 介绍一下自己
- 问项目经历, 聊"数据同步"
- 接着聊上了 K8S 的项目
- 有没有什么钻研得比较深得技术？（我：kubernetes, golang, prometheus, java）
- kubernetes 的架构是怎么样的?
    - 这个问题很大，拆成 apiserver、controller、kubelet、scheduler 讲了一下
- golang 与 java 的比较
    - 这个问题又很大，当时主要对比了 vm、协程支持、面向对象和泛型的区别、以及自己对各自使用场景的一些理解
- golang 的 gc 算法
    - 知道是三色标记，不过细节说不上来
- 从无限的字符流中, 随机选出 10 个字符 
    - 没见过也没想出来，查了一下是[蓄水池采样算法](https://www.jianshu.com/p/7a9ea6ece2af)，经典面试题，没刷题吃亏了
- 怎么扩展 kubernetes scheduler, 让它能 handle 大规模的节点调度
    - 单节点提速：优选阶段随机取部分节点进行优选；水平扩展 scheduler 节点，pod 做一致性 hash 来决定由哪个 scheduler 调度
- 你有什么想问我的?

一面其实有点僵，我自己完全没放开，面试官对我的回答没有什么反馈和深入，都是"哦好的"然后就过了。所以我当时面完觉得自己其实已经挂了（我自己要是对候选人不感兴趣，有时候也就问完问题走个过场溜了），后来收到二面电话着实吃惊了一下。

## 二面

- 先聊了聊项目
- 给 Prometheus 做了哪些改动？
- 自研配置中心, 具体做了哪些内容？
- 有用过 MySQL 的什么高级特性吗?
    - 这里不太理解，我问什么算高级特性，面试官就切换到了下一个问题
- 配置中心的核心数据表是怎么设计的?
- 为什么在业务里用 Redis, Redis 有什么优点?
    - 单线程：并发安全；高性能；原语与数据结构丰富；采用广泛，踩坑成本低
- 对 Redis 里数据结构的实现熟悉吗?
    - 说了一个 zset 跳表
- 用过 Redis 的哪些数据结构, 分别用在什么场景?
- Java 初始化一个线程池有哪些参数可以配置, 分别是什么作用?
- 自己写的 Java 应用调优过哪些 JVM 参数, 为什么这么调优?
    - 这个问住了，我只知道最大堆最小堆，开 G1，开 GC 日志以及 OOM dumper 这些基本的
- 用 Jetty 的时候有没有配什么参数, 为什么这么配?
- Jetty QTP 等待队列配置成无限的话, 你觉得好吗? 会有什么问题吗?
- 用过 Linux Bash 里的哪些命令, 分别用它们干嘛?
- 一道笔试题: 需要在给的链接中作答, 不能 google, 不能跳出, 不能用 IDE:

题目是这样的：

> 启动两个线程, 一个输出 1,3,5,7…99, 另一个输出 2,4,6,8…100 最后 STDOUT 中按序输出 1,2,3,4,5…100

我: 我用 Go 实现吧
面试官: 不可以，用 Java 的 notify 机制实现
我: (还没意识到问题的严峻) 那我用 Java BlockingQueue
面试官：说不可以, 要求用 Java 的 wait + notify 机制来实现

我完全没写过 wait + notify，只能表示不会（菜鸡本鸡了）, 面试官说那行吧你可以用 go 写

最后用 go channel 实现了一版, 不过给的网页上不能运行代码，也不知道写得对不对，然后面试结束。

这一轮面试官延续了一面的风格，打一枪换一个地方，问完一题就赶忙下一题了，似乎没有表现出对我的回答有兴趣或认可。因此这轮面完，我又觉得自己挂了...

## 三面

- 依然先聊项目
- 对监控警报的项目很感兴趣, 问了挺多细节, 最后问了一个问题: 现在要你实现一个语义不弱于 PromQL 的查询语言, 你能实现吗?
    - 这里虽然看过一些 Prometheus 的代码，但其实对 PromQL 的 lexer 和 parser 部分没有细看，还好之前因为数据同步项目里想写声明式 Stream SQL 研究过一点 ANTLR，用 ANTLR 写语法 + AST 遍历塞查询逻辑给糊弄过去了。
- 问我觉得做得最深入的项目是什么
    - 当然是数据同步（狗头）
- 聊数据同步项目（这个很符合我的预期，哈哈哈哈）
- 问 Linux 掌握得怎么样？
    - 没有系统学习过，基本上是自己运维踩坑积累的
- 问 Golang 掌握得怎么样？
    - 用了半年, 看过 effective go
- 问算法掌握得怎么样？
    - 到图为止都可以
- 问最短路算法
    - 只记得 dijkstra 了，描述了代码流程
- k8s 掌握得怎么样?
    - 不怎么样，没有自己写过 controller 和 scheduler，但是对概念都很熟悉，看过 xxx 这几部分的源码
- k8s 的 exec 是怎么实现的?
    - 这个问题正中下怀，之前写了 PingCAP 的小作业正好对这块特别熟悉

这轮聊得顺畅多了。同时发现蚂蚁的面试官似乎挺喜欢让你自己评价自己的："你觉得自己 xxx 掌握得怎么样？"（只有五位面试官，样本不够大，不能作数哦），这类问题其实我慌得要死，怕自己吹过头了答不上来，面试挂了事小，丢了面子事大。早知道就预习一下怎么吹嘘自己了。

## 四面

- 介绍一下自己
- 觉得自己基础知识掌握**怎么样**
- 平时一般会用到哪些数据结构？
- 链表和数组相比, 有什么优劣？
- 如何判断两个无环单链表有没有交叉点
- 如何判断两个有环单链表有没有交叉点
- 如何判断一个单链表有没有环, 并找出入环点
- TCP 和 UDP 有什么区别?
- 描述一下 TCP 四次挥手的过程中
- TCP 有哪些状态
- TCP 的 LISTEN 状态是什么
- TCP 的 CLOSE_WAIT 状态是什么
- 建立一个 socket 连接要经过哪些步骤
- 常见的 HTTP 状态码有哪些
- 301和302有什么区别
- 504和500有什么区别
- HTTPS 和 HTTP 有什么区别
- 写一个算法题: 手写快排

这一轮我是最懵逼的，很疑惑，是不是什么地方出了问题把我当校招来面了，可惜最后写完快排面试官就走了，没给我机会问。

## 五面

- 介绍一下自己
- 在 k8s 上做过哪些二次开发?
- 自己用 Helm 构建过 chart 吗？有哪些？
- 有没有考虑过自己封装一个面向研发的 PaaS 平台？
- 配置中心做了什么？
- 为什么不用 zookeeper？
- 配置中心如何保证一致性？
- Spring 里用了单例 Bean, 怎么保证访问 Bean 字段时的并发安全？
    - 用并发安全的数据结构，比如 ConcurrentHashMap；或者加互斥锁
- 假如我还想隔离两个线程的数据, 怎么办？
    - ThreadLocal，然后举了个例子
- Golang 里的逃逸分析是什么？怎么避免内存逃逸？
    - 这个不知道，认怂了
- 对比一下 Golang 和 Java 的 GC
    - 答了一下 CMS、G1和三色标记，我对比的点是 JVM 有分代回收，Go 的 Runtime 没有，没能深入地讲
- Golang 的 GC 触发时机是什么
    - 阈值触发；主动触发；两分钟定时触发；
- 有没有写过 k8s 的 Operator 或 Controller？（我：没有写过）
- 谈一谈你对微服务架构的理解
    - 大体思路"微服务本质是人员组织架构演进与关注点分离"
- 谈一谈你对 Serveless 的理解
    - 大体思路"Serveless 是继 docker 与容器编排之后的又一次应用开发与基础设施提供方之间的边界划分"
- 你认为 Serveless 是未来吗? 为什么?
    - 大体思路"是云服务的未来，把蛋糕从企业的IT、运维与中间件部门切走，形成规模效应，做得越多赚得越多；公司内的话 servless 能够帮助加速前台业务迭代，但对中后台的收益还看不到，未来可能会有比 servless 更适合中后台的架构"

- 面试官：最后你有什么要问我的？
- 我：为什么足足安排了五轮技术面，而且其中有两轮似乎和 k8s 没有关系啊？
- 面试官：我们觉得你做过的东西挺多的，各个方向都想让你尝试一下 (我的内心：......)
- 我：那这轮是最后一轮技术面吗？
- 面试官：不一定（我的内心：......)

五面最后的三个吹水问题我还挺感兴趣，可惜面试官只是听我讲，没有跟我讨论。还有就是问了面试官才知道，二面四面的面试官是 PaaS 平台那边的，因此主要问 Java 没有涉及到 k8s 和 go。

## 六面

HR 面，之前就听说阿里系的 HR 是来"闻味道的"（看你是否适合阿里的风格），而且有一票否决权。所以还是挺有压力的。

- 问经历
- 为什么要考虑出来看看呢？
- 现在公司的主营业务是什么？（这块往技术上问了很多，感觉是想考察我解释复杂问题的能力）
- 现在带人吗？report 层级是怎样的？
- 对自己这几年的经历满意吗？
- 觉得自己有什么缺点？
- 碰到过什么很挫败的事情吗？
- 未来的职业规划是怎样的？
- 看机会的时候，主要考虑的是待遇、平台、人员还是什么其他因素？
- 现在的待遇如何
- 有什么想问我的

整体聊了 40 多分钟，话题挺广的，面试官也说了系统部这边压力挺大的，优秀的人才才能留下来。个人觉得 HR 面里除了谈薪酬的部分没有什么可准备的，想说什么直说就行。因为到了 HR 面至少证明你的技术没什么问题，直说出来方便 HR 判断两边的价值观是否合拍，假如真的不合拍那其实在 HR 这一面挂了比起进去之后再后悔又跳槽要好很多，毕竟大家都不喜欢频繁跳槽的简历。

## 小结

一些主观评价：

* 面试难度：正常
* 面试体验：一般
* 问题偏向：基础知识，开发常识，技术见解

蚂蚁整体面试流程拖得比较长，挺影响体验的。我碰到的面试官整体比较"高冷"，不知道是不是个例。

# 头条

![bytedance](/img/interview/bytedance.jpeg)

* [面试前](#面试前-3)
* [一面](#一面-3)
* [二面](#二面-3)
* [三面](#三面-3)
* [四面](#四面-3)
* [小结](#小结-2)

## 面试前

头条每次面试前会有 HR 约时间，并提前发一个 zoom 地址过来，三场技术面与一场 HR 面全都是视频面试。不得不说视频面试体验比电话面试好很多（尤其是对我这种很关注面试官反应的），假如有 HR 同学看到这篇文章，推荐考虑一下用视频面试取代电话面试，效率会更高。

头条的三场技术面风格都很类似：

- 1. 问项目，抓出一些你擅长的领域或场景
- 2. 问系统设计题，每题都会不断深化需求让你应变和权衡
- 3. 问一道算法题(不难不偏)，先看思路，再要求写一下伪代码看边界条件能不能一次过

这个面试流程我自己也一直在用，尤其是系统设计加上不断的需求变更，能比较全面地考察后端的基本功和工程思维。因此头条的面试套路很对我胃口，甚至好多类似的问题我自己也都问过候选人。

## 一面

- 介绍一下自己, 为什么选择出来看看机会
- 聊项目, 警报怎么做的, 统一接入监控项怎么做的
- 聊项目, 配置中心项目, 问实时配置推送怎么做
- 讨论为什么选择所有的组件依赖放在配置中心中控制
- 我现在要做一个限流功能, 怎么做?
    - 令牌桶
- 这个限流要做成分布式的, 怎么做?
    - 令牌桶维护到 Redis 里，每个实例起一个线程抢锁，抢到锁的负责定时放令牌
- 怎么抢锁?
    - Redis setnx
- 锁怎么释放?
    - 抢到锁后设置过期时间，线程本身退出时主动释放锁，假如线程卡住了，锁过期那么其它线程可以继续抢占
- 加了超时之后有没有可能在没有释放的情况下, 被人抢走锁
    - 有可能，单次处理时间过长，锁泄露
- 怎么解决?
    - 换 zk，用心跳解决
- 不用 zk 的心跳, 可以怎么解决这个问题呢?
    - 每次更新过期时间时，Redis 用 MULTI 做 check-and-set 检查更新时间是否被其他线程修改了，假如被修改了，说明锁已经被抢走，放弃这把锁
- 假如这个限流希望做成可配置的, 需要有一个后台管理系统随意对某个 api 配置全局流量, 怎么做？
    - 在 Redis 里存储每个 API 的令牌桶 key，假如存在这个 key，则需要按上述逻辑进行限流
- 某一个业务中现在需要生成全局唯一的递增 ID, 并发量非常大, 怎么做
    - snowflake (这个其实答得不好，snowflake 无法实现全局递增，只能实现全局唯一，单机递增，面试结束后就想到了类似 TDDL 那样一次取一个 ID 段，放在本地慢慢分配的策略）
- 算法题, M*N 横向递增矩阵找指定数
    - 只想到 O(M+N)的解法
- 有什么想问我的?

限流，分布式锁，UUID 都属于后端的经典面试题，头条的面试参考价值挺大的。

## 二面

- 平时用的工具链和技术栈是什么
- golang 踩过坑吗?
    - 答了之前 PingCAP 面试时面试官问的 for-range 里的 go-routine 闭包捕获问题 
- 这段 golang 代码有没有 bug（还是一个 for-range 的坑)
    - 有 bug，for-range 的 value 引用拷贝问题
- Java 中 HashMap 的存储, 冲突, 扩容, 并发访问分别是怎么解决的
    - Hash 表，拉链法（长度大于8变形为红黑树）,扩容*2 rehash，并发访问不安全
- 拉链法中链表过长时变形为红黑树有什么优缺点?
    - 优点：O(LogN) 的读取速度更快；缺点：插入时有 Overhead，O(LogN) 插入，旋转维护平衡
- HashMap 的并发不安全体现在哪?
    - 拉链法解决冲突，插入链表时不安全，并发操作可能导致另一个插入失效
- HashMap 在扩容时, 对读写操作有什么特殊处理?
    - 不知道
- ConcurrentHashMap 是怎么做到并发安全的？
    - segment 分段锁
- Java 有哪些锁机制, 分别有什么特点?
    - Synchronized、可重入锁
- 知道 CAS 吗? Java 中 CAS 是怎么实现的?
    - Compare and Swap，一种乐观锁的实现，可以称为"无锁"(lock-free)，CAS 由于要保证原子性无法由 JVM 本身实现，需要调用对应 OS 的指令(这块其实我不了解细节)
- MySQL 的存储引擎用的是什么?（InnoDB）为什么选 InnoDB?
    - 几乎所有公司用 MySQL 都用 InnoDB，降低踩坑成本；聚簇索引，MVCC
- MySQL 的聚簇索引和非聚簇索引有什么区别?
    - 聚簇索引的叶子节点是数据节点（比如定义了主键时的主键索引），非聚簇索引叶子节点是指向数据块的指针
- B+树和二叉树有什么区别和优劣?
    - B+树是多叉树，深度更小，B+树可以对叶子节点进行顺序遍历，B+树能够更好地利用磁盘扇区；二叉树：实现简单
- 针对一个场景设计索引，具体场景忘记了，反正考察的是联合索引与列选择性的知识
- 现有一个新的查询场景, 要怎么解决?
- 假如要查 A in () AND B in (), 怎么建索引?
    - 只给选择性高的一列建索引，这里因为两个都是范围查询所以另一个是走不到索引的（这里答的不好，其实也可以建联合索引然后用 （A,B) in ((1,2),(3,4)) 的方式去查）
- 查 A in () AND B in () 时, MySQL 是怎么利用索引的?
    - 先走一个非聚簇索引，查询出行数据后再用另一列回表做筛选
- 假如查询 A in (), MySQL 是针对 N 个值分别查一次索引, 还是有更好的操作?
    - 不知道，有了解的同学可以留言
- 用过 Redis 的哪几种数据结构? (都用过) ZSET 是怎么实现的?
    - 跳表
- zrange start, stop, 总长度为 n, 复杂度是多少?
    - O(logN) (答得不好，实际是 O(M+log(N)), M 是结果集基数 stop-start)
- Kafka 的消费者如何做消息去重?
    - MySQL 去重、Redis 去重、假如场景量极大且允许误判，布隆过滤器也可以
- 介绍一下 Kafka 的 ConsumerGroup
    - 挺长的，略
- Kubernetes 和 Docker 用得怎么样? （我：在公司推行布道）
- 给它们贡献过代码吗?（我：没有...）
- 时序型数据库的存储结构是怎么样的? 
    - 讲了 prometheus 1.x 和 2.x 的存储结构
- LSM 树了解吗? 是一种什么存储结构?
    - Log-Structured Merge Tree，牺牲读性能换取性能，RocksDB、HBase、Cassandra 都在用，结构有点忘了，只说了先写 memtable 再刷盘成 sstable
- 在生产中用过 Cassandra 和 RocksDB 吗? 量有多大?
    - 用过，Cassandra 存调用链，RocksDB 做 flink 和 Kafka Stream 的本地状态存储
- Cassandra 的墓碑机制是什么?
    - 不知道，对 Cassandra 停留在使用阶段

二面问了好多中间件的基础知识，最后没有时间问算法了都。面完之后心里就想：头条的面试真是耿直啊，Java 的 HashMap、锁机制、CAS 到 MySQL 的索引，Redis 的 zset，再到 LSM 树，全都是后端或中间件相关的热门面试题。当然这些问题热门也是有原因的，即使候选人准备过，多扣一点细节也能很快就能看出来候选人是真的理解还是仅仅只是看了相关资料。

## 三面

- 聊项目和工作经验
- 用 Kubernetes 的过程中踩过哪些坑?
- 考虑一个业务场景: 头条的文章的评论量非常大, 比如说一篇热门文章就有几百万的评论, 设计一个后端服务, 实现评论的时序展示与分页
    - 我: 需不需要支持页码直接跳转? 
    - 面试官: 支持和不支持两种场景都考虑一下
    - 我: 不需要支持页码翻页就传评论 id 用 offset 翻页
- 假如用 id 翻页的方式, 数据库表如何设计? 索引如何设计?
    - (文章id, 评论id) 建联合索引，评论 id 需递增
- 假如量很大, 你觉得需要分库分表吗? 怎么分?
    - 需要分，分表有个权衡，按文章 id 分表，读逻辑简单，但写有热点问题；按评论 id 分表，读逻辑复杂，但写压力就平均了。写是要首先保证的，而读总是有缓存等方案来折中，因此按平均 id 分表好。
- 分库分表后怎么查询分页?
    - 每张表查 N 条数据由 client 或 proxy merge
- 分库分表后怎么保证主键仍然是递增的?
    - 讲了 TDDL 的办法：有一张专门用于分配主键的表，每次用乐观锁的方式尝试去取一批主键过来分配，假如乐观锁失败就重试
- 现在需要支持深分页, 页码直接跳转, 怎么实现?
    - 不能做精准深分页，否则压力太大，找产品进行妥协，在50或100页后数据分页是否可以不完全精确，假如可以，那么缓存深页码的起始评论 id
- 瞬时写入量很大可能会打挂存储, 怎么保护?
    - 断路器
- 断路器内部怎么实现的?
    - 可以用 ringbuffer
- 断路器会造成写入失败, 假如我们不允许写入失败呢?
    - 先写进消息队列，削峰填谷异步落库
- 算法题: N 场演唱会, 以 [{startTime, endTime}…] 的形式给出, 计算出最多能听几场演唱会
    - 先讲了思路, 按 endTime 升序排列，再顺序取最多场次
- (讲完思路之后)屏幕共享给我, 用你最熟悉的语言把这个算法实现
    - 用 go 实现了一版
- 你用了贪心法, 贪心可能会存在什么问题?
    - 局部最优，在这个问题里，只能找到一个可能解，无法找到所有排列方式

我觉得三面这个架构设计问得还不错，一个问题把后端的工程能力考的很全面了。

## HR 面

大同小异，问经历，问离职原因，问职业规划，问待遇，问期望。

## 小结

* 面试难度：正常
* 面试体验：挺好
* 问题偏向：架构设计，算法

头条面试流程很专业：每轮都会提前约好时间，面试时长都在40~50分钟，按时开始面，每轮之后发反馈短信邀请候选人评价面试，精准地过两天再约下一轮。整个像一台精密运作的机器。头条的面试我个人挺欣赏的，考察得比较全面，面试官会抓住你没有说清楚的地方来深入或者变换场景让你应变，大家可以试试看去面一下，即使不打算去也可以作为一次免费的能力评定。

再说说面试官，每位面试官都听得出来是在一线写代码的，而且很认真地在听我说话（这当中有视频的功劳，我可以看到面试官在认真听），感觉工作中也都会是好相处好合作的类型。

# 总结

回头看面试的过程，有好多不尽如人意的地方，不过最后能够拿到三家的 offer 还是很幸运。

一些经验：

* 简历里写了的项目，以及熟练程度在"掌握"以上的领域与中间件要好好准备，当面试官问你一个偏门的问题时，他内心其实也没希望你能答上来。而当面试官问你简历上涉及的问题时，假如你答不上来，那面试官就觉得这个人要么是眼界太低，会了一点就觉得自己掌握了，要么是简历造假在胡吹，这两种都非常不利；
* 在上一条的基础上，可以准备一个最得意的项目，在简历上和面试过程中引导面试官往这块聊；
* 面试前心里可以准备一个方法论：明确面试官想招怎样的人有哪些特质，在面试过程中努力表现出这些特质。这听起来是句正确的废话，但面试的过程不可控因素太多，有一个清晰的目标在脑子里能帮你在手足无措时想到说什么。举个例子，有一轮中面试官问我有什么问题时，我就问贵司的对应岗位会面临哪些技术挑战（当然要先说清楚这不是在质疑他们没有挑战，只是自己渴望挑战）；

一些各领域的资料与心得：

* [System Design Primer](https://github.com/donnemartin/system-design-primer)，入门架构设计必看的一篇资料。看完之后提醒自己始终记得：架构设计的本质是深入理解业务场景之后用工程经验做出最佳权衡。面试时的一个套路是先提纲挈领地把**舍弃什么来换取什么**讲明白；
* 云原生相关，[Kubernetes Concepts](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/) 部分建议再看一遍，源码部分推荐看 apiserver 中的 CRD 部分与 aggregation layer、kubelet 的 pod 状态同步、scheduler 的调度部分以及[Sample Controller](https://github.com/kubernetes/sample-controller) 如何写一个自己的 controller
* 语言方面，推荐看书《Effective Go》《Effective Java》，都很薄。这两本书我是以前看的，面试前没有专门准备语言相关；
* 算法相关，这部分我纯鶸，说实话我觉得大学里那本教材《数据结构与算法分析》就写得很不错...至于 leetcode，面试前没有刷过，最近为了练习 Rust 刷了60多题，并没有碰到面试里出现过的题目，看起来要刷 leetcode 的话就得走量多刷点，刷的少纯拼强运了；
* [Golang for range 的坑](https://studygolang.com/articles/9701) 有两轮面试都涉及到了这个话题，这里贴一下；

到这里就差不多啦，大家假如有什么建议或问题，可以直接留言，也可以给我发邮件。最后用 v2 侧边栏的一句话结尾：

> 换工作是一件经过深思熟虑的严肃事情。
