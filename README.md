# 项目专用图床
本项目是为个人项目图片管使用`mock`数据配图专用的图床。

# Github + PicGo + jsdelivr 搭建免费个人图床

图床的作用是方便自己写文章、做项目需要用到图片的时候，可以通过一个链接方便的引入图片，这个时候就需要一个自己的管理图片的地方，目前图床能免费使用且比较安全可靠的，只有`github`了，这里就说下通过`github + PicGo + jsdelivr` 搭建免费图床。

`github`是用来管理图床项目的，`PicGo`需要去网上下载软件，主要用来上传图片，获得图片外链。`jsdelivr`是用来做免费的图片`CDN`的。

# github 新建项目
无论是写文章也好，做项目使用`mock`数据想使用一些真是图片也好，这些图片都可以存放在这个新建项目中，后期会通过与`jsdelivr`关联，形成`cdn`图片外链，有了图片链接在哪里都能方便使用自己的图片。

图床项目必须创建为公有项目，私有项目在其他地方引用图片可能会导致图片不显示问题。`github`单个仓库的容量现在是`2GB`，且个人共有仓库的个数不做限制，如果一个项目的容量不够用，再创建一个就是了。

1. 新建项目：
![](https://cdn.jsdelivr.net/gh/kaivin/image/article/image/readme/1.png)

2. 创建图片仓库：
![](https://cdn.jsdelivr.net/gh/kaivin/image/article/image/readme/2.png)

# 配置token key
生成一个`token`用于操作`github`项目。

1. 到设置页面：
![](https://cdn.jsdelivr.net/gh/kaivin/image/article/image/readme/3.png)

2. 进入页面后，点击`developer settings`按钮：
![](https://cdn.jsdelivr.net/gh/kaivin/image/article/image/readme/4.png)

3. 点击`personal access tokens`按钮，然后点击`Generate token`:
![](https://cdn.jsdelivr.net/gh/kaivin/image/article/image/readme/5.png)

![](https://cdn.jsdelivr.net/gh/kaivin/image/article/image/readme/6.png)

4. 填写描述，选择`repo`权限，然后拉到下面点击`Generate token`按钮（**注意：创建成功后，会生成一串token，这串token之后不会再显示，需要显示后自己保存下来，接下来会用到**）：
![](https://cdn.jsdelivr.net/gh/kaivin/image/article/image/readme/7.png)

![](https://cdn.jsdelivr.net/gh/kaivin/image/article/image/readme/8.png)

# 配置Picgo
软件下载可以[点击这里](https://mirrors.sdu.edu.cn/github-release/Molunerfinn_PicGo/)。windows系统选择`.exe`的就行。

软件下载完成后，运行软件，拿到刚刚记录的`github token`，按下图配置即可：
![](https://cdn.jsdelivr.net/gh/kaivin/image/article/image/readme/9.png)

1. 仓库名：这里输入自己刚创建的`github`仓库
2. 分支名：自己项目主分支名称
3. 设定token：上一步生成的`token`复制到这里
4. 指定存储路径：在使用该软件上传图片时，图片被上传到项目的文件夹路径。
5. 设定自定义域名：这里使用了`jsdelivr`的`cdn`用来加速访问，配置`https://cdn.jsdelivr.net/gh/GitHub用户名/图床仓库名`

以上配置完成后，就可以使用该软件进行图片上传了：
![](https://cdn.jsdelivr.net/gh/kaivin/image/article/image/readme/10.png)

上传成功的图片可以在相册中看到：
![](https://cdn.jsdelivr.net/gh/kaivin/image/article/image/readme/11.png)

这里只能看到通过该软件上传的图片，如果是命令行上传的图片，这里不会显示

这时可以打开`github`中创建的项目，可以看到上传的图片已经更新到了项目中。

# 命令形式上传图片
使用picgo进行图片上传文件夹是在配置时设定的，比较不太方便，也不能在这里新建文件夹，使用起来不是很方便，如果会使用命令行形式对项目进行管理，可以自己本地克隆项目，管理项目，方便自由。

**命令行形式管理图床项目，不用配置token key，不用下载配置picgo**

# jsdelivr配置说明
使用`jsdelivr`的免费`CDN`，不是必须需通过`picgo`进行配置，`jsdelivr`与`github`可以直接进行联通，只需要通过固定的链式：`https://cdn.jsdelivr.net/gh/`，这个是`jsdelivr`访问`github`的固定链式，`gh`是`github`的缩写，后面的部分就是用户名以及具体项目，最后是项目内某张图片的具体路径。


