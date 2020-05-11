=======================================
常用工作技巧
=======================================

请容许我再次重申：对于我们这样的小团队而言，工作效率是团队能否存活下来的重要方面。

让我说的更直白一些：作为实习生，你的工作效率是否达到我的最低要求，直接决定了是否可以留在团队。
工作效率这里是指：第一，是否能够在DDL前完成交付；第二，培养你需要占用的我的时间，是否超过了我自己做这项工作的平摊时间。
平摊时间是指我的时间投入加上以后通过将同类（不需要我再投入时间指导或返工）工作 Offloading 给你而扣除的我的时间的期望（E）。

如果做消化理解性质的技术分享
====================================================

不管是全职员工还是实习生，我们都是非常强调技术报告能力和组内分享。

对于实习生而言，我的培养原则是「如果不能够报告清楚一项技术内容，那么就不能说真正理解了这项技术内容的内涵」（ref： **原则03** ）。

每个实习生平均两周就会被要求进行一次技术报告。刚加入团队的实习生一般是一周一次。

消化理解型的报告形式是，对于 **已经有人做过整理或报告的技术内容，进行同样内容的报告** 。

前人做过的技术报告的内容，包括：

* 技术演讲（视频）
* 技术演讲的幻灯片（Slides）
* 技术博客文章，内容是完整的教程或者一步一步探索的过程。
* 教程（Tutorial）

消化理解型报告的特点：

1. 报告人一定是一开始没有掌握需要报告的知识的。报告所用素材中的知识点的掌握，是报告的目标之一。
2. 报告的听众中除了mentor，还有其他的初学者。技术报告的目的是能够让其他的初学者能够更加快速的掌握所需的知识。
3. 往往是跟后续的代码开发任务直接相关。
4. 一般通过在线视频会议形式进行报告，报告结果会留存作为团队的资料，或作为公开课（MOOC）开放出来。
5. 一般从拿到自学任务到进行报告，时间不会超过一周（5天）。超过一周的工作需要进行拆分。

做消化理解型技术报告的注意事项：

1. 名誉权和出处。参考原则06。消化理解型的报告基本上不会有新内容创新，都是第三方资料以及进一步检索得到的资料汇总。因此，对于前人工作的引用和致谢就分量更重。
    a) 所有的资料都需要在PPT的最后给出参考出处。
    b) 没有出处的不能引用；
    c) 使用的截图等信息需要给出URL，在那一页引用，就在那一页的下方贴上URL。
    d) 在做资料检索的时候就养成用一个 txt 文件或备忘录记载出处的习惯。
    e) 不要漏掉任何 non-trivial 的引用。
2. 拿到一个slides或者视频，并不是只看这一个材料，这只是开始。从一个素材出发，根据自己知识背景的不同，要进行不同的检索。例如，V8的Turbofan视频，要理解，就先要理解 JavaScript 语言的一般特点，需要知道 hidden class 到底什么意思，为什么会有 deoptimization。
3. 要考虑受众。估计到有人可能不理解的术语和概念，要去查资料补充解释。PPT的字不能太小，颜色不能太刺眼，一页不要放太多内容。
4. 最终交付和公开是用PDF的形式。因此不要在PPT中使用特效或者按键触发的特技。
5. 默认报告会进行留存，用于后续的团队内部培训，根据需要有可能会以团队名义作为公开课开放。所以请务必注意质量。
6. 使用团队指定的PPT模版。
7. 第一页统一写上「日期、身份、姓名、邮箱、网址」。例如PLCT，就需要写 「软件所PLCT实验室实习生 某某某」，邮箱写「 https://github.com/isrc-cas 」
8. 正式报告前最好提前一天交给mentor做review，提供一些建议。
9. 当对外公开发布的时候，作者承担主要责任和荣誉。因此，第一页的名字需要写大一点 :-)

正式的学术论文比较难，需要的背景知识比较多，因此并不算在消化理解型报告中，属于专门的论文讨论型报告。

如何通过 GitHub 的 Pull Request 提交工作
====================================================

实习生相关的工作有超过半数是在 GitHub 上公开进行的。
因此，如何熟练的使用 GitHub 的各种功能就显得对于效率的提升尤为重要。

第一次提交PR的时候
----------------------------------------------------

如果是第一天在一个 GitHub 公开仓库上工作，那么遵守 fork-commit-push-PR 流程。具体流程可以 Google 到 GitHub 的官方文档或者其他优秀的教程。

需要注意的是，任何工作最好都不要在已经有的分支上进行。默认应该是每次工作开一个新的分支。

理由是如果是在已有的分支上进行commit（熟练实习生一般是偷懒或者习惯没有养成，新手实习生往往是不知道可以 checkout -b），
那么基本上是「单线程」的工作模式：在 master 分支上 commit 之后， push 到自己的 GitHub remote，
发起 PR，然后就什么都做不了了，等我来处理。

正确做法是每次工作都开一个新的分支来做。具体：

1. Clone 下来 repo，切换到 master 或者 develop 分支（具体根据项目约定）。
2. 从项目工作约定的分支 `checkout -b` 一个 local branch，分支名字可以是 `issueNNN`，对应任务的 id。
3. work，commit，work，commit，得到一个 commit list （有时候对应的patches叫 patch set）
4. push 到你自己的 GitHub remote 的新分支，注意是新分支，一般是跟本地分支名字相同（to save your time and life）。
5. 登陆进入 GitHub 网页，看到你的分支，按照提示进行 Pull Request 操作。注意一定要选对目标分支，如果不明白，跟你的mentor询问。
6. Reviewer （一般是你的mentor）进行 code review。一般会提一些意见，要求修改。
7. 如果要求修改，跳转到 3. 新的修改push到已经发起PR的分支之后不需要重复发起PR。
8. 如果被merge，那么恭喜🎉同时要注意，现在开始你的工作流程就不一样了。继续往下看。

第 N+1 次提交PR的时候
------------------------------------------------------

OK，现在恭喜你，已经有了被 merge 的 PR。同时有一个坏消息告诉你：
从现在开始你 fork 出来的 repo 已经跟上游的 repo 不一样了。
虽然我曾经惊奇的发现过一个简单粗暴的解决办法【1】但是我并不打算告诉你。

正确的做法如下：

1. 进入已经 clone 的 repo。运行 `git remote -v`。预期看到一个 remote，名字是 origin， URL 是你的 GitHub repo，forked from repo AAA。
2. 假设你的repo是从 repo AAA fork 出来的。例如 `<https://github.com/lazyparser/becoming-a-compiler-engineer-codes>`_ 运行 `git remote add lazyparser URL`。 这一步的作用是添加了一个新的 remote。 remote 的名字可以自己取一个，没有什么需要遵守的规律。
3. 运行 `git fetch lazyparser` 将上游仓库的代码也 clone 一份下来到你的本地机器（跟 origin 同样保存在 .git 目录下）
4. 本地创建一个分支，从你计划 push 的 branch。具体 `git help branch` or `git help checkout`。你会发现原来这些命令都可以带两个以上参数的。一条命令搞定。
5. work，commit，work，commit，得到一个 commit list （有时候对应的patches叫 patch set）
6. 【注意】 push 到 **你自己的** GitHub remote 的新分支，注意是新分支，一般是跟本地分支名字相同（to save your time and life）。
7. 其他都跟第一次类似了。
8. 以后，如果PR遇到冲突，表示上游分支已经更新了，你需要更新自己的本地分支已解决冲突。解决方法是 git fetch 然后 git rebase。遇到冲突的时候，用 git status 查看哪些是冲突的，打开，一个个修改。搜索类似 `<<<<HEAD` 这样的字样。
9. 修改（fix）了所有的conflicts之后，用 git rebase --continue 继续 rebase。
10. rebase完成之后，push到你自己的remote（一般是 origin）。如果已经发起了PR，那么PR应该自动更新了。

其它情况
-------------------------------------------------------
使用SSH方式clone 仓库源码
>>>>>>>>>>>>>>>>>>>>>>>>>>
使用SSH的方式下载仓库代码，需要个人在Github的 `SSH Keys设置 <https://github.com/settings/keys>`_ 里配置本机的SSH公钥。

否则无法clone 源码：
::
    $ git clone git@github.com:lazyparser/survivial-manual-for-interns.git
    Cloning into 'survivial-manual-for-interns'...
    Warning: Permanently added the RSA host key for IP address '52.74.223.119' to the list of known hosts.
    git@github.com: Permission denied (publickey).

具体配置步骤如下：

1. 本地机器上配置SSH
::

    $ ssh-keygen -t rsa -C "1132021192@qq.com"
    Generating public/private rsa key pair.
    Enter file in which to save the key (/home/chenjy/.ssh/id_rsa): 
    Enter passphrase (empty for no passphrase): 
    Enter same passphrase again: 
    Your identification has been saved in /home/chenjy/.ssh/id_rsa.
    Your public key has been saved in /home/chenjy/.ssh/id_rsa.pub.
    The key fingerprint is:
    SHA256:aCPtc0lxXkzqlawcjDbxOTo7pgIrY1wS2ig6D4iio8k 1132021192@qq.com
    The key's randomart image is:
    +---[RSA 2048]----+
    |        .   .    |
    |         = * .   |
    |        = O *    |
    | .   . o O *     |
    |.o. . = S =      |
    |*.o. + o +       |
    |O oo  o *        |
    |X=. .  = .       |
    |*E.  ..          |
    +----[SHA256]-----+

注：邮箱修改为自己的邮箱，Enter passphrase 默认回车即可。

2. 将公钥复制粘贴到 Github 的个人SSH Keys配置里。
产生的公钥一般为 `~/.ssh/id_rsa.pub`
::

    $ cat ~/.ssh/id_rsa.pub
    ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDa+LNRQuTAjMWZjRZ8d0CK9rZFjZZBQG2Q8UqBZpHQ7GQSBMdhO4mxRYYk/Zb7t7pMj3BpEyOOGKOFXRjic7ibREnki06TQ8LBolRAFDSBv6E4oOS5ei52mwh+NiL2mT7/5GdwZwgR2eDO22MxDRCHObFr2TBHkiThRs9NTi/28UPsy3MluyuPU/0IWZNwcjr1EKRL9qNOh9Ro+8GoEEb23A6sdG2zOjiV/VKiba8so5TqBt9ZFPvjnJtKINUb8TasusC49dSay5paDCJKnDCJQoDIiOn7ggg4ivkan2w9HK4lUK5oNHjQyQRPRiFBF+mm5DJJ7TW03dheOqZq6KPT 1132021192@qq.com

选中公钥复制粘贴到Github `SSH Keys设置 <https://github.com/settings/keys>`_ 的 NEW SSH key 的 key 里即可(Title自己命名)。

3. 启动SSH代理并添加密钥
::

    $ eval `ssh-agent -s`
    $ ssh-add

最后就可以使用SSH方式下载仓库文件了。比如：
::

    $ git clone git@github.com:lazyparser/survivial-manual-for-interns.git
	
TODO 由实习生遇到问题之后发起PR到这里。



如何正确的提问
====================================================

遇到问题以后，需要在y站开issue，简单而清楚的描述你遇到的问题并@你的上级或同事，最好配有截图或运行log以便他人帮助你解决。
注意不要在私下里询问技术问题，因为你遇到的问题别人也可能遇到，养成在y站中提问的好习惯，不仅可以帮助自己解决问题记录问题，也方便了其他实习同学学习参考。不要害怕去提问，问题也是宝贵的财富。发现问题，解决问题你才能变强。

如何正确的报告bugs
====================================================

项目运行时往往会产生各种bugs,明明是按说明来的，居然报错了...尝试半天没有解决的你准备向小组报告这个bug, 下面我们说明一下怎样正确报告bugs

1. 贴出error log—error log是最直观描述错误的材料，通常debug的过程都需要参考error log来进行，比如缺少安装某个库、多打了一个空格，error log可以直接给出大部分错误产生的原因，有利于其他人快速了解问题，给你修改建议。
2. 描述bug出现的过程—一些简单的问题往往会因为没有清晰的描述而变得难以琢磨，“电脑突然黑屏了，进不去系统”，这种问题抛给任何一个专家都是令人头疼的，详细描述bug产生的过程和你做的操作，“更新了显卡驱动，然后电脑突然黑屏了，进不去系统”，更仔细的会描述帮助问题定位更加精确，有时多几个文字就可以大幅减少处理问题需要的时间。
3. 提供bug的复现步骤——“能复现的bug都是好bug”，bug的复现步骤往往是判断bug属性的关键，如果bug能够复现，那么大家都可以参与到bug的解决中来，产生不同的思路和尝试，提出不同的解决方法，高效解决问题。（如果不能复现，那么这个bug对你来说是很危险的，请仔细查看有关说明和代码，必要时尝试不同机器。）
4. 提供bug截图——无图无真相，请在报告bug时配上bug的截图或照片

如何正确的进行情报收集（Google tips）
====================================================

学会利用专业平台进行资料搜索与问题交流，站在巨人的肩膀上去看远方。
Google的访问方式请自行百度学习VPS...，喝茶去了....

如何做进度报告
====================================================

TBD


ZIP文件的跨OS操作注意事项
====================================================

压缩和解压缩的文件的时候注意，如果是zip文件，中文文件名可能会有乱码。

中文 windows 默认会使用 GBK 编码文件名，macOS 和 Linux 使用 UTF8。

解决方法在 Linux 下是使用可以指定文件名编码格式的解压命令行工具。

FIXME： macOS 下的我还没有找到。

所以保守的建议是：不要使用中文文件名，使用英文名。


如何正确简洁的复制B站的链接
=====================================================

URL 是浏览器跟WWW服务器之间的通信协议。

URL 中从问号开始的部分，参数，这部分参数，有时候是用来跟踪用户会话，而不是用来唯一标识资源的。

例如如果直接在B站搜索视频，可以得到类似

https://www.bilibili.com/video/av83277184?from=search&seid=1289633595657602924

这样的链接。而实际上在B站，问号和问号后面的是不需要的，可以改成

https://www.bilibili.com/video/av83277184

在内部系统的时候贴的可以更加简洁。而对于B站而言，有一个约定俗称的编号系统就是av号，可以进一步所见为

av83277184

就足够唯一的表示出来要指称的对象了。在满足【原则08】的基础上做到了最大程度的简洁。


中文输入法中全、半角的正确使用
====================================================

日常工作中技术文档的撰写普遍会有中、英文夹杂的情况。在中文输入中，需要注意全角和半角概念。简单而言，
，在英文输入法中，一个英文字符和标点符号 （如 “a”）所占的位置是半角；而在中文输入中，一个汉字所占据
的位置等于两个半角，称为“全角”。默认状态下，英文输入法和中文输入法都是半角的设置，这意味这两种输入法
下所输入的英文字符、符号和数字，都只占据一个“半角”位置。

但是，在中文输入法下，可能会因为快捷键的误操作（如： shift + space ）导致全半角误切换，切换后，输入
的英文字符、符号和数字就会被当成汉字处理，看起来占据了“更宽”的位置，例如，从半角的“hello world123”
变成“ｈｅｌｌｏ　ｗｏｒｌｄ１２３”。这看起来是很别扭的，显得很不专业。

因此，在写文档时，一定要注意中文输入法中全、半角的正确使用。

文档中粘贴超链接时，前后务必加空格
====================================================

文档中的超链接是用来方便读者深入阅读的，读者要么直接点击链接跳转到相关链接，要么会选择复制粘贴链接
在浏览器中访问。无论是哪一种情况，编辑超链接时，在其前后加上空格都会极大地方便读者。

例如：

这样引用超链接 https://github.com/lazyparser/survivial-manual-for-interns 前后加空格是好的做法；

这样引用超链接https://github.com/lazyparser/survivial-manual-for-interns前后不加空格不是好的做法。

写中英文夹杂的文档时，在中文和英文之间加入空格
====================================================

这样做能够方便编辑器发挥其拼写检查功能。

在使用Word编辑文档时，将常用的术语加入“字典”
====================================================

这样做能够方便编辑器发挥其拼写检查功能。

拿到新电脑后可以做的事(从开箱到llvm)
====================================================

1. 进入系统后安装wsl/wsl2（默认ubuntu18.04），安装方法可以参考这篇官方文档 https://docs.microsoft.com/zh-cn/windows/wsl/install-win10 

2. 从开始菜单进入安装好的ubuntu系统中，进入 ``/etc/apt`` 更换软件源为国内源(以阿里云软件源为例),并更新软件列表:
::

    $ cd /etc/apt
    $ vi sources.list
    //vim中输入 :%:cn.archive.ubuntu:mirrors.aliyun:g ,进行查找替换源
    $ sudo apt-get update

3. 安装git、gcc、g++、cmake、make、ninja-build
::

    $ sudo apt-get install git gcc g++ cmake make ninja-build

4. 导入自己的ssh密钥(参考上方)

5. 克隆llvm项目到本地(没速度的话尝试去掉https中的s，或者从y站镜像clone)
::

    $ git clone https://github.com/llvm/llvm-project.git

6. 进入llvm-project，准备编译llvm+clang(由于wsl只能运行在系统盘，注意你新电脑的系统盘大小，建议剩余100G)
::

    $ cd llvm-project
    $ mkdir build
    $ cd build
    $ cmake -G "Unix Makefiles" -DLLVM_ENABLE_PROJECTS="clang;libcxx;libcxxabi" ../llvm

7. 编译llvm，并记录你的编译用时
::

    $ time make -j4

8. 验证llvm是否安装成功(参考 https://llvm.org/docs/TestingGuide.html )
::

    $ make check

【1】 我曾经指导过的一位实习生，每次要解决跟我（upstream）的repo不一致时候，都是删除自己的 fork，重新 fork。提交了多少次 PR 就删除了多少次。
更好玩的是，他还教会了周围的还处在迷茫中的实习生，一度成为了。
