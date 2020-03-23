---
layout: post
title: pycharm for anaconda配置
---
> pycharm非常好，conda非常好，pycharm for anaconda=非常非常好
>
> \-鲁迅

1. 下载pycharm for anaconda并安装

   [https://www.jetbrains.com/pycharm/promo/anaconda/](<1. https://www.jetbrains.com/pycharm/promo/anaconda/>)

   > 使用迅雷下载可以提高速度
2. 安装下载的pycharm

   > 其中一个必要的下载组件是miniconda，另一个可选的下载组件是markdown，这会在你首次启动pycharm出现。当然，即使当时没有下载，也可在在pycharm界面中下载并安装。
3. 配置你的pycharm for anaconda

   1. 首先建议更改字体和主题

      在File &#124; Settings &#124; Editor &#124; Font中更改字体和大小，我的建议是Font为Monospaced，Size为16

      在File &#124; Settings &#124; Appearance & Behavior &#124; Appearance中更改主题，个人喜欢Darcula


   2. 更改conda执行目录和终端

      在File &#124; Other Settings &#124; Settings for New Project &#124; Tools &#124; Terminal中添加一个目录为“C:\Users\用户名\miniconda3\condabin”的PATH环境变量，下面的Shell path你也可以按照喜好来更改，但是不建议更改为powshell，否则黄色的powshell文字会让人无法忍受。
   3. conda与pip改源

      C:\Users\用户名\pip.ini中添加

      ```
      [global]
      index-url = https://pypi.douban.com/simple

      ```

      C:\Users\用户名\.condarc中添加

      ```
      ssl_verify: true
      channels:
        - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
        - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
      show_channel_urls: true

      ```

      好了，你的源已经配置完成了
   4. 尝试conda

      新建一个Terminal，输入`conda -V`来查看输出，输出版本号即正常工作。

      现在可以开始新建环境了，输入`conda create -n 名字`来创建一个新的虚拟环境。

      如果你想指定版本，那么`conda create -n 名字 python=2.7`即可

      更多conda用法参照[这里](https://docs.conda.io/projects/conda/en/latest/commands.html)。
   5. 现在你的配置已经完成，`C:\Users\用户名\miniconda3\envs`即可找到你的环境，一个文件夹对应一个环境。在pycharm配置了解释器之后，你打开一个终端后会自动进入虚拟环境。当然，你也可以用`conda activate 名字`或`conda deactivate`来进出虚拟环境。