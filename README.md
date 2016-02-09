《Practical Vim》（《Vim实用技巧》）笔记，参考了[gitig/Practical-Vim-Notes](https://github.com/gitig/Practical-Vim-Notes) 和`中文版 Practical Vim`，加入了一些我的理解和例子

## 第1章 Vim 解决问题的方式
技巧 1. [认识`.`命令](part0/tip1.md):  `.`,`x`,`u`,`dd`,`>G`,`h`,`j`,`k`,`l` <br>
技巧 2. [不要自我重复](part0/tip2.md): `$`,`I`,`i`,`a`,`A` <br>
技巧 3. [以退为进](part0/tip3.md): `f{char}`,`;`,`,`,`s` <br>
技巧 4. [执行、重复、回退](part0/tip4.md): `.`,`u` <br>
技巧 5. [查找并手动替换](part0/tip5.md): `:%s/content/copy/g`,`*`,`#` <br>
技巧 6. [结识`.`范式](part0/tip6.md): `.`  <br>

# 第一部分 模式

> 在不同的模式上按键,产生的效果可能不同

## 第2章 普通模式

> 1. 普通模式在执行时可以指定执行次数
> 2. 指定执行次数可以减少按键次数,但是有的时候多按几次更好: 计算按键次数可能费脑子, 不如直接next,next一直到目的地
> 3. 普通模式:操作符+动作命令

技巧 7. [停顿时请移开画笔](part1_pattern/chapter2_normal_pattern/tip7.md)  <br>
技巧 8. [把撤销的单元切成块](part1_pattern/chapter2_normal_pattern/tip8.md): `<Esc>o` <br>
技巧 9. [尽量构造可重复的修改](part1_pattern/chapter2_normal_pattern/tip9.md): [VimGolf](http://vimgolf.com), `daw` vs `dbw` vs `dbx`  <br>

技巧 10. [用次数做简单的算术运算](part1_pattern/chapter2_normal_pattern/tip10.md): `<C-a>`,`<C-x>`,`yyp`,`cw` <br>
技巧 11. [能够重复,就别用次数](part1_pattern/chapter2_normal_pattern/tip12.md): `d3w` vs `3dw` vs `dw..`   <br>
技巧 12. [操作+操作符 双剑合璧](part1_pattern/chapter2_normal_pattern/tip12.md): `gu`,`gU`,`g~`,`=`,`<`,`>` <br>


## 第3章 插入模式

> 1. 大多数操作都在非插入模式中实现(复制\删除\剪切\黏贴)
> 2. 不离开插入模式就可以黏贴寄存器中的文本
> 3. 如何插入键盘上不存在的字符?
> 4. 替换模式是插入模式的特例
> 5. `插入-普通模式`是插入模式的子集


技巧 13. [在插入模式中回退/撤销](part1_pattern/chapter3_insert_mode/tip13.md): `<C-x>`,`<C-w>`,`<C-u>` <br>
技巧 14. [返回普通模式](part1_pattern/chapter3_insert_mode/tip14.md): `<` <br>
技巧 15. [不离开插入模式, 粘贴寄存器中的文本](part1_pattern/chapter3_insert_mode/tip15.md): `yt,`,`<C-r>0`  <br>
技巧 16. [随时随地做运算](part1_pattern/chapter3_insert_mode/tip16.md): `<C-r>=` <br>
技巧 17. [用字符编码插入非常用字符](part1_pattern/chapter3_insert_mode/tip17.md):  `<C-v>{123}`,`<C-v>u{1234}`,`<C-v><CR>`<br>
技巧 18. [用二合字母(digraph)插入非常用字符](part1_pattern/chapter3_insert_mode/tip18.md): `<C-k>35`,`<C-k>?I`,`<C-k><<` <br>
技巧 19. [使用替换模式替换已有文本](part1_pattern/chapter3_insert_mode/tip19.md): `R`,`r` <br>

## 第4章 可视模式

> 1. 可视模式允许在选中的文本区域上操作
> 2. 可视模式分为在字符文本\行文本\块文本上的操作
> 3. `.`命令对于行文本的操作用处较大, 其他可视模式里使用`.`意义不大

技巧 20. [深入理解可视模式](part1_pattern/chapter4_visual_mode/tip20.md): `viw`, `<C-g>`,`c` <br>
技巧 21. [选择高亮区域](part1_pattern/chapter4_visual_mode/tip21.md): `v`,`V`,`<C-v>`,`o`  <br>
技巧 22. [重复执行面向行的可视命令](part1_pattern/chapter4_visual_mode/tip22.md): `Vj>.`  <br>
技巧 23. [尽可能使用操作符命令,而不是可视命令](part1_pattern/chapter4_visual_mode/tip23.md): `vitU`, `gUit`  <br>
技巧 24. [用面向__列块__的可视模式编辑**表格数据**](part1_pattern/chapter4_visual_mode/tip24.md): `<C-v>3jr|`  <br>
技巧 25. [修改列文本](part1_pattern/chapter4_visual_mode/tip25.md): `<C-v>jjec<Esc>` <br>
技巧 26. [在长短不一的高亮块中添加文本](part1_pattern/chapter4_visual_mode/tip26.md): `<C-v>jj$c<Esc>`  <br>

## 第5章 命令行模式

> 1. `ex` 本来是一个行编辑器, 是`vi`的祖先
> 2. 基于行的编辑任务, Ex 命令是最佳工具

技巧 27. [结识Vim的命令行模式](part1_pattern/chapter5_ex_mode/tip27.md): `:`,`<C-w>`  <br>
技巧 28. [在一行或多个连续行上执行命令](part1_pattern/chapter5_ex_mode/tip28.md): `:2,5p`,`:%s/old/new/gc`,`:/<html>/-1,/<\/html>/+1p`  <br>
技巧 29. [使用`:t` `:m` 进行复制和移动行](part1_pattern/chapter5_ex_mode/tip29.md): `:6t.`,`Vjj:m$`  <br>
技巧 30. [在指定范围上执行普通模式命令](part1_pattern/chapter5_ex_mode/tip30.md): `:'<,'>normal .`  <br>
技巧 31. [重复上次的Ex命令](part1_pattern/chapter5_ex_mode/tip31.md):`:@:`, `:bp`,`:bn`  <br>
技巧 32. [自动补全Ex命令](part1_pattern/chapter5_ex_mode/tip32.md):`<Tab>`,`<C-n>`,`<C-p>`  <br>
技巧 33. [把当前单词插入到命令行](part1_pattern/chapter5_ex_mode/tip33.md): `/<C-r><C-w><CR>`, `*:%s//<C-r><C-w>/g`  <br>
技巧 34. [回溯历史命令](part1_pattern/chapter5_ex_mode/tip34.md):`q:`  <br>
技巧 35. [运行Shell命令](part1_pattern/chapter5_ex_mode/tip35.md): `:ls`,`:write! sh`,`:write !sh`,`:2,$!sort -t',' -k2,2`  <br>

# 第二部分 文件

## 第6章 管理多个文件

> 1. 缓冲区列表记录打开的所有文件
> 2. 缓冲区文件分组方法
> 3. 将Ex命令作用在缓冲区每个文件上
> 4. 标签页分割窗口

技巧 30. [](part1_pattern/chapter5_ex_mode/tip30.md):  <br>
