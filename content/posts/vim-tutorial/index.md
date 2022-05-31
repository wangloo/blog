---
title: "Vim Tutorial"
date: 2022-05-09T19:28:12+08:00
---

Search a word quickly: put cursor on the word, press `/` and press `<C-R>` `<C-W>`.


## `F`ind and `T`ail
`f(`: 从当前cursor处向右查找下一个`(`, 并将光标移动到`(`处.  
`F(`: Like `f(`, but 向左查找.  
`t(`: Like `f(`, but 将cursor移动到`(`的前一个.  
`T(`: You can guess.

#### Trick
`vt(c`: With visual, 删除当前光标到下一个`(`前的所有内容.

`;`/`,`: 查找下一个/上一个 `f/F/t/T` 的内容. 


## 单词间跳转
`w`: Move cursor to begin of next word.  
`b`: Move cursor to begin of last word.  
`e`: Move cursor to end of next word.

#### Trick
`w`/`b`配合`ce`使用可达到在某一行中快速移动到某个单词, 然后删除该单词开始edit.

&nbsp;
## Good plugin & script
> Reference: [The Ultimate vimrc](https://github.com/amix/vimrc)

### TODO
[open file under cursor](https://github.com/amix/open_file_under_cursor.vim)


### Installed

