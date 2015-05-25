#	浅谈软件版本控制——Git
这两天学习了软件版本控制工具—Git，现在，就通过这个博客来浅谈一下我对于Git理解和使用。

   Git是一个免费的，分布式的软件版本管理工具。相信对于免费大家会比较情有独钟，但是Git的真正吸引人的地方不在于免费这一方面，更是一个速度快的源代码管理工具。Git的出现，减轻了许多开发者管理代码的压力，更能鼓励开发者开发出自己感兴趣的内容。对于我们初学者来说，我们可以将我们所写的代码提交到网上以及查看代码版本。

   现在，就让我简单介绍Git的使用方法：

   1、我们需要在Linux系统的命令行中输入“sudo apt-get install git”安装Git，以便开始我们Git的学习之旅。

   2、安装好Git之后，我们需要选择一个我们自己的工作目录，例如在家目录下创建工作目录，执行“mkdir work”命令，然后 “cd work”进入到work工作目录下；

   3、创建一个远程仓库：在github页面右上角用户名旁边有一个“+”（create new...）按钮，点击可出现 New repository，点击进入该 模块进行填写，填写完后点击Create repository，一个新的远程仓库就建好了。

   4、对于Git来说，我们需要在开始的时候初始化一个空的仓库，这就要用到“git init”这句命令来实现，或许有的人会发现，当前目录下多了一个隐藏的.git的目录，其实，这个目录是用来git跟踪管理版本库的。

   5、此时，执行"git status" 命令，我们可以查看所在工程的状态，是说我们没有什么东西可以进行提交，这就是对的，因为我们只是初始化了一个空的仓库而已。

   6、现在，让我们添加一个文件到暂存区中，使用“git add filename(例如：file.md)”，执行完毕命令后，没有任何显示，这就对了，说明添加成功。

   7、我们已经将一个文件添加到了暂存区中，而现在，我们要做的是将这个文件添加描述，从暂存区中取出文件改变到本地Git库中。使用“git commit -m "文件描述”“，此时，命令会提示我们，1 file changed ，那么恭喜你，语句执行成功，文件已经被添加到仓库中了。

   8、我们已经实现了对文件添加到本地Git仓库中，之前的过程就像一个舞者在上台表演前做的大量准备，充满艰辛，但是又对于追求优美无瑕的舞蹈的期望，对于我们来说，就是对于拥有完美代码的无限期望。现在，我们就需要将我们的本地Git库中的文件拉到舞台上进行演出，首先，我们需要实现远程仓库的连接，使用“git remote add origin +GitHub项目地址”实现。这样，我们就能实现同步。

   9、上一步，我们已经连接了远程仓库，现在，我们就要push我们的Git本地库中的文件，我们需要输入“git push -u origin master”去实现push，若是在此之前你没有配置SSH密钥，那么，系统会提示你输入账户密码，像:
                    username for 'https://github.com'(输入用户名)                        password for 'https://fang-inspring@github.com':(输入密码)
                    Counting object :4 ,done
                    那么，我们自己本地GIt库中的文件已经被同步到GitHubs上了，刷新项目，此时，你会非常的自豪，因为我们的项目文件已经显示在GitHub的网站上了。

       至此，我们已经完成了一个文件通过Git上传到GItHub网站了，这就像舞者在群光璀璨的舞台上完成了一次优美的舞蹈，光彩夺目，让人赏心悦目。