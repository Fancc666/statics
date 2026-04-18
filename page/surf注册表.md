## 概况

Edge浏览器中的Surf小游戏是我们喜爱的游戏，但是最近上课发现信息老师禁用了Surf。他是如何做到的？

## 如何禁用Surf

我在网上查找的时候发现了这篇文章<https://www.zhihu.com/question/529636649>

他指向了这个网页<https://www.tenforums.com/tutorials/162256-how-enable-disable-surf-game-microsoft-edge-chromium.html>

这是微软官方提供的解决办法，他修改了注册表！与我们遇到的情况一模一样，如下图

![Microsoft_Edge_surf_game_disabeled.png](https://s2.loli.net/2023/03/09/2RjC9ysVhafeZnD.png)

## 解决办法

### 手动修改注册表

老爹曾经说过，要用魔法打败魔法，使用注册表把禁用Surf的选项关掉

首先我们需要进入注册表修改页面，找到`HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge`，把`AllowSurfGame DWORD`里的`0`删掉

因为网站中提到0=Disable,(delete)=enable

![iShot_2023-03-09_20.41.30.png](https://s2.loli.net/2023/03/09/t1e6kfoNmVnYUgQ.png)

### 使用官网提供的文件

我也不知道我们有没有权限去运行注册表文件，但是官网中提供了我们至少也应该试一试，如果可以上网的话那是最好，如果不可以也可以考虑使用U盘拷进去

![iShot_2023-03-09_20.43.51.png](https://s2.loli.net/2023/03/09/65wfnVIbx9rudBc.png)

<https://www.tenforums.com/attachments/tutorials/292070d1597074099-how-enable-disable-surf-game-microsoft-edge-chromium-enable_microsoft_edge_surf_game.reg>

如果大家有更好的方法也欢迎留言
