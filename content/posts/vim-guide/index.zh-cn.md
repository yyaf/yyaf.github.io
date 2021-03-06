---
weight: 4
title: "VIM 指南"
date: 2021-05-13T21:52:40+08:00
lastmod: 2021-05-13T21:52:40+08:00
draft: false
author: "yyaf"
authorLink: "https://yyaf.github.io"
description: "这篇文章展示了 VIM 的基本使用方法."

featuredImagePreview: "https://cdn.jsdelivr.net/gh/yyaf/Boomb@main/images/文章配图/02/vim指南.jpg" 
tags: ["Vim"]
categories: ["编辑器"]

lightgallery: true
---

这篇文章展示了 VIM 的基本使用方法.

<!--more-->

![Vim 指南](https://cdn.jsdelivr.net/gh/yyaf/Boomb@main/images/文章配图/02/vim指南.jpg "Vim 指北")

{{< admonition >}}
图片来源网络，侵删。
{{< /admonition >}}

## 01 插入模式  

  i 当前位置插入。  
  a 当前位置追加。  
  A 当前行尾追加。  
  o 打开新的下一行，并进入插入模式。  
  O 打开新的上一行，并进入插入模式。  

## 02 移动光标  

  上 k  
  下 j  
  左 h  
  右 l  
  行首 0  
  ^ 回到首个非空字符。  
  $ 移动到行尾。  
  w 移动到下一个空格后的第一个字符。  
  W 移动到下一个空格后的第一个字符（忽略标点符号）。  
  b 移动到上一个空格后的第一个字符。  
  B 移动到上一个空格后的第一个字符（忽略标点符号）。  
  ctrl+f or Page Down 向下翻一页。  
  ctrl+b or Page Up 向上翻一页。  
  number+G 移动到第number行。  
  G 移动到文件末尾。  
> 注：vim许多命令可以在前面加上一个数字，例如“5j”将光标下移5行。  

## 03 删除文本  

  x 当前字符。  
  3x 当前字符及其后的两个字符。  
  dd 当前行。  
  dW(w) 从光标位置开始到下一个单词的开头。  
  d$ 从光表位置开始到当前行的行尾。  
  d0 从光标位置开始到当前行的行首。  
  d^ 从光标位置开始到文本行的第一个非空字符。  
  dG 从当前行到文件的末尾。  
  d20G 从当前行到文件的第20行。  

## 04 剪切、复制和粘贴  

p 粘贴。  
d 这个命令不仅删除文本，还剪切文本。  
J 连接当前行和下一行。  

### a 复制  

yy 当前行。  
yW 从当前光标位置到下一个单词的开头。  
y$ 从当前光标位置到当前行的末尾。  
y0 从当前光标位置到行首。  
y^ 从当前光标位置到文本行的第一个非空字符。  
yG 从当前行到文件末尾。  

## 05 查找和替换  

f 查找一行内的内容。  
/ 查找整个文件内的内容。(n查找下一个)  

### a 全局查找和替代  

将整个文件中的单词“Line”个很改为“line”：  
:%s/Line/line/g  
分解为：
`:` 运行一个ex命令。  
% 指定要操作的行署。%是一个快捷方式，表示从第一行到最后一行。令为，操作范围也可以用1，5来代替，或者用1，$来代替。  
s 制定操作。在这种情况下是，替换（查找与替代）。  
/Line/line 查找类型与代替文本。  
g 这是全局的意思。如果省略g，则只替换每个文本行中第一个匹配的字符串。  
在这个命令末尾添加一个“c”字符来添加提示。  
replace with Line (y/n/a/q/l/^E/^Y)?  

## 06 编辑多个文件  

### a 打开多个文件  

vim file1 file2 file3...  

### b 文件之间切换  

从当前文件切换到下一个文件：  
:n  
回到先前的文件使用：  
:N  
查看正在编辑的文件列表：  
:buffers  
切换第二个文件：  
:buffer 2  
vim中打开另一个文件：  
:e file  
跨文件复制粘贴：  
yy复制  
p 粘贴  

插入整个文件r(read)：  
:r file  

## 07 保存工作  

保存：  
:w  
保存并退出:  
:wq  
