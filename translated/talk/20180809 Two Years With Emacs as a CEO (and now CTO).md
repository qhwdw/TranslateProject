[#]: collector: (lujun9972)
[#]: translator: (oneforalone)
[#]: reviewer: ( )
[#]: publisher: ( )
[#]: url: ( )
[#]: subject: (Two Years With Emacs as a CEO (and now CTO))
[#]: via: (https://www.fugue.co/blog/2018-08-09-two-years-with-emacs-as-a-cto.html)
[#]: author: (Josh Stella https://www.fugue.co/blog/author/josh-stella)

作为 CEO 使用 Emacs 的两年经验之谈（现任 CTO）
======

两年前，我写了一篇[博客][1]，并取得了一些反响。这让我有点受宠若惊。那篇博客写的是我准备将 Emacs 作为我的主办公软件，当时我还是 CEO，现在已经转为 CTO 了。现在回想起来，我发现我之前不是做程序员就是做软件架构师，而且那时我也喜欢用 Emacs 写代码。重新考虑 Emacs 是一次很不错的尝试，但我不太清楚具体该怎么实现。在网上，那篇博客也是褒贬不一，但是还是有数万的阅读量，所以总的来说，我写的还是不错的。在 [Reddit][2] 和 [HackerNews][3] 上有些令人哭笑不得的回复，说我的手会变形，或者说我会因白色的背景而近视。在这里我可以很肯定的回答 —— 完全没有这回事，相反，我的手腕还因此变得更灵活了。还有一些人担心，说使用 Emacs 会耗费一个 CEO 的精力。把 Fugue 从在家得到的想法变成强大的产品，并有一大批忠实的顾客，我觉得 Emacs 可以让你从复杂的事务中解脱出来。我现在还在用白色的背景。

近段时间那篇博客又被翻出来了，并发到了 [HackerNews][4] 上。我收到了大量的跟帖者问我现在怎么样了，所以我写这篇博客来回应他们。在本文中，我还将重点讨论为什么 Emacs 和函数式编程有很高的相关性，以及我们是怎样使用 Emacs 来开发我们的产品 —— Fugue，一个使用函数式编程的自动化的云计算平台。由于我收到了很多反馈，比较有用的是一些细节的详细程度和有关背景色的注解，因此这篇博客比较长，而我确实也需要费点精力来解释我的想法，但这篇文章的主要内容还是反映了我担任 CEO 时处理的事务。而我想在之后更频繁地用 Emacs 写代码，所以需要提前做一些准备。一如既往，本文因人而异，后果自负。

### 意外之喜

我大部分时间都在不断得处理公司内外沟通。交流是解决问题的唯一方法，但也是反思及思考困难或是复杂问题的敌人。对我来说，作为创业公司的 CEO，最需要的是有时间专注工作而不别打扰。一旦开始投入时间来学习一些命令，Emacs 就很适合这种情况。其他的应用弹出提示，但是配置好了的 Emacs 就可以完全的忽略掉，无论是视觉上还是精神上。除非你想修改，否则的话他不会变，而且没有比空白屏幕和漂亮的字体更干净的界面了。在我不断被打扰的情况下，这种简洁让我能够专注于我在想什么，而不是电脑。好的程序能够默默地对电脑的进行访问。

一些人指出，原来的帖子既是对现代图形界面的批判，也是对 Emacs 的赞许。我既不赞同，也不否认。现代的接口，特别是那些以应用程序为中心的方法(相对于以内容为中心的方法)，既不是以用户为中心的，也不是面向进程的。Emacs 避免了这种错误，这也是我如此喜欢它的部分原因，而它也带来了其他优点。Emacs 是进入计算机本身的入口，这打开了一扇新世界的大门。它的核心是发现和创造属于自己的道路，对我来说这就是创造的定义。现代电脑的悲哀之处在于，它很大程度上是由带有闪亮界面的黑盒组成的，这些黑盒提供的是瞬间的满足感，而不是真正的满足感。这让我们变成了消费者，而不是技术的创造者。我不在乎你是谁或者你的背景是什么;你可以理解你的电脑，你可以用它做东西。它很有趣，令人满意，而且不是你想的那么难学!

我们常常低估了环境对我们心理的影响。Emacs 给人一种平静和自由的感觉，而不是紧迫感、烦恼或兴奋——后者是思想和沉思的敌人。我喜欢那些持久的，不碍事的东西，当我花时间去关注它们的时候，它们会给我带来真知灼见。Emacs 满足我的所有这些标准。我每天都使用 Emacs 来创建内容，我也很高兴我很少考虑它。Emacs 确实有一个学习曲线，但不会比学自行车更陡，而且一旦你完成了它，你会得到相应的回报，你就不必再去想它了，它赋予你一种其他工具所没有的自由感。这是一个优雅的工具，来自一个更加文明的时代。我很高兴我们步入了另一个计算机时代，而 Emacs 也将越来越受欢迎。

### 放弃用 Emacs 规划日程及处理待办事项

在原来的文章中，我花了一些时间介绍如何使用 Org 模式来规划日程。我放弃了使用 Org 模式来处理待办事项之类的,因为我每天都有很多会要开，很多电话要打, 而我也不能让其他人来适应我选的工具,我也没有时间将事务转换或是自动移动到 Org 上 。我们主要是用 Mac shop，使用谷歌日历等，原生的 Mac OS/iOS 工具可以很好的进行协作。我还有支比较旧的笔用来在会议中做笔记，因为我发现在会议中使用笔记本电脑或者说键盘很不礼貌，而且这也限制了我的聆听和思考。因此，我基本上放弃了用 Org 帮我规划日程或安排生活的想法。当然，Org 模式对其他的方面也很有用，它是我编写文档的首选，包括本文。换句话说，我与其作者背道而驰，但它在这方面做得很好。我也希望有一天也有人这么说我们在 Fugue 的工作。

### Emacs 在 Fugue 已经扩散

我在上篇博客就有说，你可能会喜欢 Emacs，也可能不会。因此，当 Fugue 的文档组将 Emacs 作为标准工具时，我是有点担心的，因为我觉得他们可能是受了我的影响。几年后，我确信他们做出了个正确的选择。那个组长是一个很聪明的程序员，但是那两个编写文档的人却没有怎么接触过技术。我想，如果这是一个经理强加错误工具的案例，我就会得到投诉并去解决，因为 Fugue 有反威权文化，大家不怕惹麻烦，包括我在内。之前的组长去年辞职了，但[文档组][5]现在有了一个灵活的集成的 CI/CD 工具链。并且文档组的人已经成为了 Emacs 的忠实用户。Emacs 有一条学习曲线，但即使很陡，也不会那么陡，翻过后对生产力和总体幸福感都有益。这也提醒我们，学文科的人在技术方面和程序员一样聪明，一样能干，也许不应该那么倾向于技术而产生派别歧视。

### 我的手腕得益于我的决定

上世纪80年代中期以来，我每天花12个小时左右在电脑前工作，这给我的手腕（以及后背）造成了很大的损伤，在此我强烈安利 Tag Capisco 的椅子。Emacs 和人机工程学键盘的结合让手腕的 [RSI][10](Repetitive Strain Injury/Repetitive Motion Syndrome) 问题消失了，我已经一年多没有想过这种问题了。在那之前，我的手腕每天都会疼，尤其是右手，如果你也遇到这种问题，你就知道这很让人分心和担心。有几个人问过键盘和鼠标的问题，如果你感兴趣的话，我现在用的是[这款键盘][6]。虽然在过去的几年里我主要使用的是真正符合人体工程学的键盘。我已经换成现在的键盘有几个星期了，而且我爱死它了。键帽的形状很神奇，因为你不用看就能知道自己在哪里，而拇指键设计的很合理，尤其是对于 Emacs, Control和Meta是你的固定伙伴。不要再用小指做高度重复的任务了!

我使用鼠标的次数比使用 Office 和 IDE 时要少得多，这对我有很大帮助，但我还是会用鼠标。我一直在使用外观相当过时，但功能和人体工程学明显优越的轨迹球，这是名副其实的。

撇开具体的工具不谈，最重要的一点是，事实证明，一个很棒的键盘，再加上避免使用鼠标，在减少身体的磨损方面很有效。Emacs 是这方面的核心，因为我不需要在菜单上滑动鼠标来完成任务，而且导航键就在我的手指下面。我肯定，手离开标准打字姿势会给我的肌腱造成很大的压力。这因人而异，我也不是医生。

### 还没完成大部分配置……

有人说我会在界面配置上花很多的时间。我想验证下他们说的对不对，所以我留意了下。我不仅让配置基本上不受影响，关注这个问题还让我意识到我使用的其他工具是多么的耗费我的精力和时间。Emacs 是我用过的维护成本最低的软件。Mac OS 和 Windows 一直要求我更新它，但在我我看来，这远没有 Adobe 套件和 Office 的更新的困恼那么大。我只是偶尔更新 Emacs，但也没什么变化，所以对我来说，它基本上是一个接近于零成本的操作，我高兴什么时候跟新就什么时候更新。

有一点然你们失望了，因为许多人想知道我为跟上 Emacs 社区的更新及其输出所做的事情，但是在过去的两年中，我只在配置中添加了一些内容。我认为也是成功的，因为 Emacs 只是一个工具，而不是我的爱好。也就是说，如果你想和我分享，我很乐意听到新的东西。

### 期望实现控制云端

我们在 Fugue 有很多 Emacs 的粉丝，所以我们有一段时间在用 [Ludwing 模式][7]。Ludwig 是我们用于自动化云基础设施和服务的声明式、功能性的 DSL。最近，Alex Schoof 利用飞机上和晚上的时间来构建 fugue 模式，它在 Fugue CLI 上充当 Emacs 控制台。要是你不熟悉 Fugue，我们会开发一个云自动化和管理工具，它利用函数式编程为用户提供与云的 api 交互的良好体验。它做的不止这些，但它也做了。fugue 模式很酷的原因有很多。它有一个不断报告云基础设备状态的缓冲区，而由于我经常修改这些设备，所以我可以快速看到编码的效果。Fugue 将云工作负载当成进程处理，fugue 模式非常类似于云工作负载的 top 模式。它还允许我执行一些操作，比如创建新的设备或删除过期的东西，而且也不需要太多输入。Fugue 模式只是个雏形，但它非常方便，而我现在也经常使用它。

![fugue-mode-edited.gif][8]

### 模式及监听

我添加了一些模式和集成插件，但并不是真正用于 CEO 工作。我喜欢在周末时写写 Haskell 和 Scheme，所以我添加了 haskell 模式和 geiser。Emacs 对具有 REPL 的语言很友好，因为你可以在不同的窗口中运行不同的模式，包括 REPL 和 shell。Geiser 和 Scheme 很配，要是你还没有这样做过，那么用 SICP 工作也不失为一种乐趣，在这个有很多土鳖编程的例子的时代，这可能是一种启发。安装 MIT Scheme 和 geiser，你就会感觉有点像 lore 的符号环境。

这就引出了我在 15 年的文章中没有提到的另一个话题:屏幕管理。我喜欢使用用竖屏来写作，我在家里和我的主要办公室都有这个配置。对于编程或混合使用，我喜欢 fuguer 提供的新的超宽显示器。对于宽屏，我更喜欢将屏幕分成三列，中间是主编辑缓冲区，左边是水平分隔的 shell 和 fugue 模式缓冲区，右边是文档缓冲区或另一个或两个编辑缓冲区。这个很简单，首先按 'Ctl-x 3' 两次，然后使用 'Ctl-x =' 使窗口的宽度相等。这将提供三个相等的列，你也可以使用 'Ctl-x 2' 进行水平分割。以下是我的截图。

![Emacs Screen Shot][9]

### 最后一篇 CEO/Emacs 文章……

首先，我现在是 Fugue 的 CTO，其次我也想要写一些其他方面的博客，而我现在刚好有时间。我还打算写些更深入的东西，比如说函数式编程、基础结构类型安全，以及我们即将推出一些的新功能，还有一些关于 Fugue 在云上可以做什么。

--------------------------------------------------------------------------------

via: https://www.fugue.co/blog/2018-08-09-two-years-with-emacs-as-a-cto.html

作者：[Josh Stella][a]
选题：[lujun9972][b]
译者：[译者ID](https://github.com/oneforalone)
校对：[校对者ID](https://github.com/校对者ID)

本文由 [LCTT](https://github.com/LCTT/TranslateProject) 原创编译，[Linux中国](https://linux.cn/) 荣誉推出

[a]: https://www.fugue.co/blog/author/josh-stella
[b]: https://github.com/lujun9972
[1]: https://blog.fugue.co/2015-11-11-guide-to-emacs.html
[2]: https://www.reddit.com/r/emacs/comments/7efpkt/a_ceos_guide_to_emacs/
[3]: https://news.ycombinator.com/item?id=10642088
[4]: https://news.ycombinator.com/item?id=15753150
[5]: https://docs.fugue.co/
[6]: https://shop.keyboard.io/
[7]: https://github.com/fugue/ludwig-mode
[8]: https://www.fugue.co/hubfs/Imported_Blog_Media/fugue-mode-edited-1.gif
[9]: https://www.fugue.co/hs-fs/hubfs/Emacs%20Screen%20Shot.png?width=929&name=Emacs%20Screen%20Shot.png
[10]: https://baike.baidu.com/item/RSI/21509642