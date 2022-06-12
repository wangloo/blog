---
title: "Vim Tutorial"
date: 2022-05-09T19:28:12+08:00
---

Search a word quickly: put cursor on the word, press `/` and press `<C-R>` `<C-W>`.


&nbsp;
## Bookmark
`ma`: create bookmark `a` inside file.  
`mA`: create global bookmark `A`.  
`` `a ``: jump to bookmark `a`. 


`:marks`: display all bookmarks



## 缩进: indent
`>`: increase indent  
`<`: decrease indent  
`=`: auto indent  

### Trick
> 以下命令都可以配合visual mode使用

`>>`: 增加当前行的缩进

`gg=G`: 缩进全文, 无论当前光标在哪


## `F`ind and `T`ail
`f(`: 从当前cursor处向右查找下一个`(`, 并将光标移动到`(`处.  
`F(`: Like `f(`, but 向左查找.  
`t(`: Like `f(`, but 将cursor移动到`(`的前一个.  
`T(`: You can guess.

#### Trick
`vt(c`: With visual, 删除当前光标到下一个`(`前的所有内容.

`;`/`,`: 查找下一个/上一个 `f/F/t/T` 的内容. 

&nbsp;
## 大小写转换

| cmd  | description |
|------|-------------|
| `g~` | 翻转大小写  |
| `gu` | 转换为小写  |
| `gU` | 转换为大写  |

以上命令(严格来说叫操作符)需要配合**动作命令**来使用.
* `gUaw`: 将光标所在位置的*单词*转为大写
* `gUap`: 将光标所在位置的*段落*转为大写


## 单词间跳转
`w`: Move cursor to begin of next word.  
`b`: Move cursor to begin of last word.  
`e`: Move cursor to end of next word.


#### Trick
`w`/`b`配合`ce`使用可达到在某一行中快速移动到某个单词, 然后删除该单词开始edit.

`daw`: 即 Delete A Word, 可以删除一个完整的单词, 无论当前光标的位置在哪.

&nbsp;
## Good plugin & script
> Reference: [The Ultimate vimrc](https://github.com/amix/vimrc)

### TODO


### Installed
[NERD Commneter - 快速注释](https://github.com/preservim/nerdcommenter#settings)

[NERD Tree - 目录树](https://github.com/preservim/nerdtree)

[Open File Under Cursor - 打开光标处的文件目录](https://github.com/amix/open_file_under_cursor.vim)
* 不支持`vim-plug`安装. 直接clone源码到`plugged`目录即可.
* Usage: `gf`: 在当前window打开文件. `<C-w><C-f>`: **new vertical windows**中打开文件.

[Ack.vim - 快速定位内容](https://github.com/mileszs/ack.vim)
