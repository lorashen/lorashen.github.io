---
layout: post
title:  "crontab run torch task"
date:   2015-05-05 11:12:54
categories: linux
---
想要用crontab定时运行torch程序，但是试了几次都没能正常运行。

开始怀疑是date的问题，时区是不是设的不对，于是在crotab里打印了时区。echo $(date) >> /home/username/testdate 打印后发现时区是对的。

查了网上的解决方法，怀疑是sh脚本没有执行。改了权限，确认脚本是可以执行的。发现是th run.lua 这一句没有执行，想到crontab执行的时候可能找不到th命令。于是参考页面http://www.cnblogs.com/wxjnew/p/3490736.html，加了以下几行，添加了环境，crontab任务就可以正常执行了。

if [ -f ~/.bash_profile ];

then

  . ~/.bash_profile

fi
