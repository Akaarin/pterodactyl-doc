# 使用 SFTP 管理服务器

## 为什么使用 SFTP？

翼龙面板提供网页端管理服务器文件，参见：

{% page-ref page="../jin-jie-jiao-cheng/wen-jian-guan-li.md" %}

那为什么还要使用 SFTP 呢？

### 迫不得已

如果你要上传一个完整的服务端，一个一个传文件显然不现实。即使使用解压缩功能，也会受到面板上传大小的限制，部分服务商在这块把的死死的，一整个服务端在这样的限制下显然无法被上传。

另外你懂的，网页上传大文件总会出现各种奇葩的问题，文件损坏也是非常容易出现的\(在部分环境下\)，甚至解压缩出来都可能乱码、或者多出少出一个文件夹来。所以使用 SFTP 恐怕是唯一的方案。

### 追求完美

网页上传大文件会出现很多问题，速度也不会很快，可能已经是老生常谈了 —— 经历过的都懂 😭 所以，在上传大文件时，为了追求稳定或者更快的速度，我们会选择 SFTP。另外，编码也是一个考虑的因素。

当然，并不是用 SFTP 就是最优解，一个重命名或者一个简单的配置文件/插件，其实没必要大动干戈。

## 下载软件

SFTP Windows 原生应该是不支持的\(吧, 2333\)。所以，我们需要先安装一些软件来使用 SFTP。

我通常推荐使用老牌的 [FileZilla](https://filezilla-project.org/)，或者你喜欢的话可以用更现代的 [XShell](https://www.netsarang.com/zh/xshell/)，都可以建立 SFTP。接下来，本教程将以 FileZilla 为例演示如何连接面板服的 SFTP。

下载 FileZilla 非常简单，请先进入网站 [https://filezilla-project.org/download.php?type=client](https://filezilla-project.org/download.php?type=client)

![](../.gitbook/assets/image%20%2821%29.png)

如果你是 Windows 系统，按照上面的指示点击 **Download FileZilla Client，然后看下一步。**

如果不是，~~我就假设你一定知道怎么安装了~~。

![](../.gitbook/assets/image%20%2819%29.png)

这一步是选择版本，我们这里选择第一个**“纯净版”**，第三个需要付费，第二个是带教程的但是也是英文，咱也看不懂 😂。然后按照图片指示点击第一个 FileZilla 最下方的 **Download**。

![](../.gitbook/assets/image%20%2831%29.png)

最后，**稍等一会儿，**出现窗口 **Thank you**，这一波感谢你，你的安装包也应该开始下载了。不要点击下方的“广告”，直接点击 **Close** 即可。（当然你想看的话也行）

![](../.gitbook/assets/image%20%2825%29.png)

打开安装程序，先会让你同意协议，点击 **I Agree**。

![](../.gitbook/assets/image%20%2832%29.png)

![](../.gitbook/assets/image%20%2818%29.png)

这一步可以不用动，继续 Next。下两步会让你选择安装路径还有开始菜单列表，不需要动的话可以直接 Next。

![](../.gitbook/assets/image%20%2827%29.png)

安装成功。点击 Finish 就可以启动我们安装好的客户端了。

## 获得服务器 SFTP 地址

![](../.gitbook/assets/image%20%2824%29.png)

进入到翼龙面板，在侧边栏点击**配置**, 然后点击 **SFTP 设置**。

![](../.gitbook/assets/image%20%2837%29.png)

这里是你的 **SFTP链接地址** 和 **SFTP用户名**，请记好，另外特别说明的是SFTP的密码就是你面板账户的密码。

## FileZilla 添加服务器

为了我们以后每次都可以快速连接到服务器而不必每次都看一眼信息，我们直接添加一个服务器，方便之后连接。

![](../.gitbook/assets/image%20%2822%29.png)

点击 文件 -&gt; 站点管理器。

![](../.gitbook/assets/image%20%2836%29.png)

![](../.gitbook/assets/image%20%2833%29.png)

接下来，按照上面的图片填写服务器信息。

![](../.gitbook/assets/image%20%2820%29.png)

可以按照你的喜好选择。

![](../.gitbook/assets/image%20%2826%29.png)

点击总是信任该主机然后点击确定。

![](../.gitbook/assets/image%20%2828%29.png)

成功连接后的界面如上所示，你可以点击放大来看，界面分为四个区域。你可以拖拽左边的本地文件到右边，这是上传；也可以拖动右边面板服上的文件到左边的本地，这是下载。

## 传输文件

![](../.gitbook/assets/image%20%2823%29.png)

假设我们要下载我们的 world 文件夹到本地，来备份世界，那么如图所示，我们拖动右边的 world 文件夹到左边的 `C:\Users\Administrator\Documents\我的面板服的世界备份\`。当然这只是个 VPS，不建议把备份存到 C 盘，更不建议你直接用 administrator 登录Windows。

![](../.gitbook/assets/image%20%2829%29.png)

拖动完成之后，你应该能够看到下方的文件列队增加了一些任务，这就代表开始传输了。

![](../.gitbook/assets/image%20%2830%29.png)

队列空了，成功传输变多了，没有失败的传输，完美👍，这就代表下载结束了。

## 上传一个插件吧！

![](../.gitbook/assets/image%20%2838%29.png)

这回我们从左边拖到右边，上传一个名为 TrashBin.jar 的插件到 plugins。

![](../.gitbook/assets/image%20%2835%29.png)

看一下，传输成功，完美。

## 批量传输

![](../.gitbook/assets/image%20%2834%29.png)

长按鼠标，选择多个文件，或者我们直接 Ctrl+A 选择所有，备份整个服务端到本地，也是完全OK的。

自此，你应该已经学会了如何使用 SFTP 上传和下载文件。开服愉快！

