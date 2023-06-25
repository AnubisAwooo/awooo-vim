# awooo-vim

## 1. 模式 mode

### normal 一般模式

> 快速移动游标

`esc`

`ctrl` + `[`

### insert 插入模式

> 左下角出现 -- INSERT --，可以输入字符

`i` 插入位置为当前游标字符**前** `I`插入位置为当前行**首**

`a` 插入位置为当前游标字符**后** `A`插入位置为当前行**尾**

`o` 当前行**下**方新开一行 `O` 当前行**上**方新开一行

### visual 视觉模式

> 左下角出现 -- VISUAL --，选择字符

`v` 以当前字符作为起始字符，进入视觉模式

> 还有个 -- VISUAL LINE --，整行选择

`V` 以当前字符所在行作为起始，进入视觉行模式

> 还有个 -- VISUAL BLOCK --，多行选择

`ctrl + v` 进入视觉块模式,，选中多行，可以同步编辑

## 2. 保存和退出 [normal mode]

`:w` 保存

`:q` 退出

`:q!` 强制退出，放弃保存修改

`:wq` 保存并退出

`ctrl` + `z` 最小化

`fg` 恢复最小化的界面

## 3. 移动游标 [normal mode]

HJKL 左 下 上 右

← h  ↓ j  ↑ k  → l

`w` 下个单词  `W`下个单词、跳过符号

`b`上个单词 `B`上个单词、跳过符号

`g` + `hjklwb` 先按 g，可以在当前行的内容进行移动，对自动换行的文本很有用

`}` 下个段落  `{` 上个段落

`G` 最后一行  `gg` 第一行

`0` 当前行首 `^` 也可以，正则符号

`$` 当前行尾，正则符号

`f` + `字母` 快速移动到下一个该字母的位置

## 4. 平移 [normal mode]

`zz` 当前行处于屏幕中间

`zt` 当前行处于屏幕最上面

`zb` 当前行处于屏幕最下面

## 5. 检索 [normal mode]

`/` + `内容` 向下检索

`:set hlsearch` 高亮检索匹配的内容

`:set nohlsearch` 取消高亮

`n`下一个匹配  `N`上一个匹配

`?` + `内容` 向上检索（注意：这时 n 和 N 是向上）

`*` 快速检索当前游标所在的单词 相当于快速使用 `/` + `当前游标所在的单词`

`#` 快速检索当前游标所在的单词 相当于快速使用 `?` + `当前游标所在的单词`

## 6. 复制和粘贴 [visual mode]

`y` 复制 yank

`yy` normal模式下，直接按下 yy 就是复制当前行

`数字` + `yy` 复制多行

`y$` 复制当前游标到行尾

`yG` 复制当前游标到文件尾

`"ay` 把内容复制到 a 暂存器（a-z）26 个暂存器可用 `"ap`使用

`p` normal模式下，粘贴复制的内容 `P`大写是在游标字符前面粘贴

`数字` + `p` 粘贴多次数

`u` undo 上一步

`ctrl` + `r` redo 下一步

`:set clipboard=unnamed` 让暂存器和系统剪贴板一致（盲猜unnamed指的是未命名的暂存器）

## 7. 编辑

`x` 删除当前字符 如果在视觉模式，是删除所选中的字符

`d` 删除所选中的字符 `D` 删除当前游标后面的字符, 到行尾

`dd` 直接删除当前行

`数字` + `dd` 删除指定行数

`dG` 删除到文档尾部

`dgg` 删除到文档头部

`c` 视觉模式: 删除并进入插入模式 `C` 删除到行尾并进入插入模式 change

`r` 替换输入

`>>` 往右边移动, 类似 tab 视觉模式下,按一下即可

`set shiftwidth=2` 设定默认宽度

`<<` 往左边移动 视觉模式下,按一下即可

`=` 缩进排列

## 8. 多文件

`:e` 文件名

`:tabe` 有页签

`gt` 下一个页签

`gT` 上一个标签

`:new` 下面会开一个水平视窗 `ctrl` + `w`  + `w` 循环切换视窗

`:vnew` 右面会开一个水平视窗

`vim -o file1 file2` 水平打开多个文件 O 垂直打开多个文件 *不用输入文件名

`vim -p *` 以页签的方式打开

`:ls` 列出打开的文件

`:b3` 切换到打开的第 3 个文件 `:bn` 下一个 `:bp` 上一个 `:bl` 最后一个 `:bf` 第一个 `:bd` 关闭当前文件

`ctrl + ^` 切换上一个文件

`tab ba` 把打开的文件展开成 tab

## 9 更多选择

`vw` 当前单词尾部

`viw` 当前单词

`vaw` 当前单词包括空格

`vi"` 内部字符串 `va"`

`vit` 尖括号内部  `vat` 

`v}` 下面整个块

`v{` 上面真个块



d 开头删除

c 开头删除并进入到插入模式

i inner

a around

w word

t tag

## 文本属性

#### 名词

w word

s sentence

p paragraph

t tag



#### 动词

y yank

p paste

d delete

c change



#### 范围

i inner

a around? after

## 其他技巧

`^` 行首字符

`set nu` 行号 number

`set nonu` 取消

`10G` 跳到第 10 行

`ctrl + f` 下一页

`ctrl + b` 上一页

`zf` 折叠

`zd` 展开 `l` 向右移动也可以展开

`zfip` 折叠当前段

`~`大小写互换

`.` 重复上个操作

`J` 合并行

`ctrl + u` 删除当前光标前面的

`ctrl + w` 删除当前光标前面的一个单词

`:! ls -al` 当前文件压栈，执行命令，任意键恢复

`:r !ls -al` 输出结果可以直接贴到当前位置

`vimtutor` 教程 `vimtutor zh`中文版

## 设定档

~/.vimrc 初始配置文件

`set clipboard=unnamed` 设置剪贴板同步

`set hlsearch` 高亮检索内容

`set cursorline` 鼠标所在行有下划线提示

`set noswapfile` 不需要 swap 文件暂存修改



`set softtabstop=2` 使用 2 格空格替代 tab

`set shiftwidth=2` 使用>时候用 2 格空格作为缩排

`set expandtab` tab 是空格

`retab`重新按照 tab 重排

`set tabtabline=2` 总是显示页签

`set splitbelow` 水平视窗在下面 `:new` 新文档

`set splitright` 垂直视窗再右边 `vnew` 新文档

`set ignorecase` 检索忽略大小写

`set incsearch` 渐进的检索

`syntax on` 语法检测

`colorscheme darkblue` 颜色主题

`filetype on` 

`filetype indent on`

`filetype plugin on`

## 按键映射

`map` `vmap` `imap` `vmap`

`help key-notation`

`unmap` `vunmap` `iunmap` `vunmap`

`mapclear`
