---
layout: post
title:  "python read western character"
date:   2015-04-27 11:17:54
categories: python
---
处理stanfordSentimentTreebank数据集过程中，python读取文件的时候，有些西文字符是乱码，导致匹配的时候对不上。在读取的时候转成unicode，就可以解决。

unicode(line,"ISO-8859-1")

ISO 8859-1 大部分的西欧语系，例如英文、法文、西班牙文和德文等（Latin-1）(参见页面http://www.fmddlmyy.cn/text16.html)
