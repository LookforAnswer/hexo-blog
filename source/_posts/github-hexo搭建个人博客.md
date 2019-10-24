---
title: github+hexo搭建个人博客(Mac版)
date: 2019-10-25 01:07:18
categories: Hexo建站
tags: [Hexo]
---

# 安装Node

```shell
brew install node
```

执行此命令发现 brew 一直处于更新状态，度娘一波，找到如下解决方法：

```shell
# 1. 编辑配置文件
vim ~/.bash_profile

# 2. 文件内新增一行
export HOMEBREW_NO_AUTO_UPDATE=true

# 3. 重新加载配置文件
source ~/.bash_profile
```

参考：

[https://www.jianshu.com/p/77c60428569d]: https://www.jianshu.com/p/77c60428569d

之后就可以飞快的安装完 node，你可以通过如下命令验证是否安装成功

```
node -v
```



# 安装Hexo

```shell
npm install -g hexo-cli
```

执行此命令时，你会发现老是超时，这个问题困扰我很久，查了好久，终于找到解决方式：

```shell
# 删除代理 参考：https://blog.csdn.net/yanzi1225627/article/details/80247758
npm config delete proxy

# 添加淘宝的源 https://npm.taobao.org/
npm install -g cnpm --registry=https://registry.npm.taobao.org

# 通过此命令查看源是否已更改
npm config get registry
```

到此，你应该也可以愉快的安装 hexo，验证是否安装成功，使用如下命令

```shell
hexo -v
```



# Hexo建站

```shell
hexo init 博客文件路径

# 清理
hexo clean 

# 生成
hexo g

# 启动服务
hexo s
```

常用命令：

```shell
hexo n “我的博文”  #新建文章
hexo generate #生成,也可简写成 hexo g 
hexo server  s #启动服务预览（监视文件变动并自动更新，无需重启服务器）,也可简写成 hexo
hexo deploy  #部署,也可简写成 hexo d
hexo server -s #静态模式
hexo server -p 5000 #修改端口
hexo server -i 192.168.1.1 #自定义IP
hexo clean #清楚缓存
```

详细教程可参考：

[https://juejin.im/post/5b3ed1d4e51d45194e0b7884]: https://juejin.im/post/5b3ed1d4e51d45194e0b7884
[https://hexo.io/zh-cn/docs/configuration]: https://hexo.io/zh-cn/docs/configuration

# Hexo主题

官方主题汇总：https://hexo.io/themes/

个人觉得最好看的主题：https://github.com/klugjo/hexo-theme-clean-blog