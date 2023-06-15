# org mode 使用手册（我的精简版）

## 1. 文档结构

### 1.1 标题

```
* Top level headline
** Second level
*** Third level
    some text
*** Third level
    more text
* Another top level headline
```

### 1.2 可见性循环

- 在标题上使用 TAB 可以切换内容是否可见（这个过程是循环的）

- 使用 S-TAB 可以全局的切换内容的可见性

- ```
  ;; 参数有：'overview','content','showall','showeverything','show<n>levels'(n=2..5)
  #+startup: content
  ```

### 1.3 跳转标题

|  操作   |      action      |
| :-----: | :--------------: |
| C-c C-n |    下一个标题    |
| C-c C-p |    上一个标题    |
| C-c C-f | 下一个同级别标题 |
| C-c C-b | 上一个同级别标题 |
| C-c C-u |    返回父标题    |

### 1.4 结构编辑

- **M-RET** 在一个标题末尾处使用可以创建一个统计标题
- **M-S-RET** 创建一个同级的TODO标题
- **TAB** 在新的没有文本的标题可以改变标题的等级
- **M-LEFT** 标题降级； **M-RIGHT** 标题升级
- **M-UP** 标题上移； **M-DOWN** 标题下移
- **C-c C-w** 归档该标题及内容，需要输入归档的位置（一个标题的名称）
- **C-x n s** 缩小buffer；**C-x n w** 扩大buffer
  - ![1](C:\Users\Administrator\Desktop\配置emacs\emacs官方教程.assets\1.png)

### 1.5 稀疏树

- C-c / 这会提示输入一个额外的键来选择稀疏树创建命令
- C-c / r 提示输入正则表达式并显示包含所有匹配项的稀疏树
- 使用 C-c C-c 取消高亮

### 1.6 无序和有序列表

```
- 无序列表
+ 无序列表
1. 有序列表
1) 有序列表
- item :: describe 描述列表
```

- **TAB** 可以折叠带子列表的列表
- **M-RET** 插入新的同级列表
- **M-S-RET** 插入带复选框的同级列表
- **M-S-UP** 和 **M-S-DOWN** 可以上下移动列表项
- **M-LEFT** 和 **M-RIGHT** 增加减少缩进
- **M-S-LEFT** 和 **M-S-RIGHT** 增加减少缩进，包括子项目
- **C-c C-c** 切换复选框状态，验证列表符号和缩进的一致性
- **C-c -** 循环切换列表使用的符号

## 2. 表格

```
| Name  | Phone | Age |
|-------+-------+-----|
| Peter |  1234 |  17 |
| Anna  |  4321 |  25 |
```

### 创建和转换

1. 输入 '|姓名|电话|年龄' ，然后，**C-c RET**，直接RET可以得到没有标题行的表格
2. 输入 '|姓名|电话|年龄 RET |- TAB' 

### 格式化和移动

| key                      | action                                     |
| ------------------------ | ------------------------------------------ |
| **C-c C-c**              | 不移动光标格式化                           |
| **TAB**                  | 格式化，移动光标到下一个位置，创建一个新行 |
| **S-TAB**                | 重新对齐，移动到上一个位置                 |
| **RET**                  | 对齐表格，移动到下一行，创建一个新行       |
| **S-UP/DOWN/LEFT/RIGHT** | 在表格中移动单元格                         |

### 列和行编辑

#### 列编辑

| key                 | action         |
| ------------------- | -------------- |
| **M-LEFT, M-RIGHT** | 左右移动当前列 |
| **M-S-LEFT**        | 删除当前列     |
| **M-S-RIGHT**       | 在左侧插入一列 |
|                     |                |
|                     |                |

#### 行编辑

| key             | action                                                       |
| --------------- | ------------------------------------------------------------ |
| **M-S-UP**      | 删除当前行                                                   |
| **M-UP,M-DOWN** | 向上/向下移动当前行                                          |
| **M-S-DOWN**    | 在当前行上方插入一个新行<br/>使用前缀参数，该行将创建在当前行的下方 |
| **C-c -**       | 在当前行下方插入一条水平线<br/>使用前缀参数，该行创建在当前行之上 |
| **C-c** **RET** | 在当前行下方插入一条水平线，并将点移动到该线下方的行中       |
| **C-c ^**       | 对表格进行排序                                               |

## 3. 超链接

```
[[LINK][DESCRIPTION]]
;; or 
[[LINK]]
```

### 3.1 内部链接

```
[[heading1]] ==> 叫heading1的标题
```

### 3.2 外部链接

```
‘http://www.astro.uva.nl/=dominik’	on the web
‘file:/home/dominik/images/jupiter.jpg’	file, absolute path
‘/home/dominik/images/jupiter.jpg’	same as above
‘file:papers/last.pdf’	file, relative path
‘./papers/last.pdf’	same as above
‘file:projects.org’	another Org file
‘docview:papers/last.pdf::NNN’	open in DocView mode at page NNN
‘id:B7423F4D-2E8A-471B-8810-C40F074717E9’	link to heading by ID
‘news:comp.emacs’	Usenet link
‘mailto:adent@galaxy.net’	mail link
‘mhe:folder#id’	MH-E message link
‘rmail:folder#id’	Rmail message link
‘gnus:group#id’	Gnus article link
‘bbdb:R.*Stallman’	BBDB link (with regexp)
‘irc:/irc.com/#emacs/bob’	IRC link
‘info:org#Hyperlinks’	Info node link

‘file:~/code/main.c::255’	Find line 255
‘file:~/xx.org::My Target’	Find ‘<<My Target>>’
‘[[file:~/xx.org::#my-custom-id]]’	Find entry with a custom ID
```

### 3.3 处理链接

|key|action|
| --------------------------------- | ------------------------------------------------------------ |
| C-c C-l                           | 插入一个链接。它会让你输入，你可以输入一个链接，也可心用上/下键来获取保存的链接。它还会让你输入描述信息。 |
| C-c C-l（光标在链接上）           | 当光标处于链接上时，你可以修改链接                           |
| C-c C-o 或者 mouse-1 或者 mouse-2 | 打开链接                                                     |
| C-c &                             | 跳回到一个已记录的地址。用 C-c % 可以将地址记录下来，内部链接后面的命令也会自动将地址记录下来。使用这个命令多次可以一直往前定位。 |

## 4. TODO

### 4.1 基本的TODO功能

以 ’TODO‘ 开头的标题，被视为TODO list

| key                                  | action                     |
| ------------------------------------ | -------------------------- |
| **C-c C-t**                          | 切换TODO状态               |
| **S-RIGHT、S-LEFT**                  | 切换TODO状态               |
| **C-c / t**                          | 查看稀疏树中的 TODO 项     |
| **M-x org-agenda t**<br/>**C-c a t** | 显示全局 TODO 列表         |
| **S-M-RET**                          | 下方插入一个新的 TODO 条目 |

### 4.2 自定义TODO工作流

1. ```
   (setq org-todo-keywords
         '((sequence "TODO" "FEEDBACK" "VERIFY" "|" "DONE" "DELEGATED")))
   ```

2. ```
   (setq org-todo-keywords
         '((sequence "TODO(t)" "|" "DONE(d)")
           (sequence "REPORT(r)" "BUG(b)" "KNOWNCAUSE(k)" "|" "FIXED(f)")))
   ```

3. ```
   #+TODO: TODO(t) | DONE(d)
   #+TODO: REPORT(r) BUG(b) KNOWNCAUSE(k) | FIXED(f)
   #+TODO: | CANCELED(c)
   ```

使用 **C-c C-t** 可以获得提示

### 4.3 进度记录

当一个TODO状态改变时，可以有一些记录

for example:

```
;; TODO ==> DONE 时可以记录时间戳
(setq org-log-done 'time)
```

```
;; TODO ==> DONE 时可以记录时间戳和一个笔记
(setq org-log-done 'note)
```

```
;; ！ for a timestamp ， @ for a note
;; 当 STATE ==> WAIT 时，记录时间戳和笔记
;; 当 STATE ==> DONE 时，记录时间戳
;; 当 STATE ==> CANCELED 时，记录笔记
#+TODO: TODO(t) WAIT(w@/!) | DONE(d!) CANCELED(c@)
```

### 4.4 优先级（Priorities）

|  key   |        action        |
| :----: | :------------------: |
|  S-UP  | 增加当前标题的优先级 |
| S-Down | 减少当前标题的优先级 |

### 4.5 任务细分

在TODO标题的后面添加 '[/]', '[%]'

可以监控完成状态

### 4.6 复选框

 ```
  *** TODO organize party[1/2]
  - [-] call people
    - [ ] Peter
    - [x] Sarah
  - [x] order food
 ```

## 5. 标签

标签可以包含字母，数字， `‘_’` 和 `‘@’` 。

标签的前面和后面都有一个冒号

### 5.1 标签继承

```
* Meeting with the French group     :work:
** Summary by Frank                 :boss:notes:
*** TODO Prepare slides for him     :action:
```

最后一个标题有”:work:“、”:boss:“、`:notes:`、”:action:“ 四个标签

**文件标签**：文件里的所有标题都有这些标签

```
#+FILETAGS: :Peter:Boss:Secret:
```

### 5.2 设置标签

- **C-c C-q**：为当前标题输入新标签
- **C-c C-c**：当光标在标题中时，这与C-c C-q相同.

设置全局的标签

```
(setq org-tag-alist '(("@work" . ?w) ("@home" . ?h) ("laptop" . ?l)))
```

设置本文件的标签

```
#+标签：@work(w) @home(h) @tennisclub(t) laptop(l) pc(p)
```

### 5.3 标签组

```
#+TAGS: [ GTD : Control Persp ]
```

```
#+TAGS: { Context : @Home @Work }
```

### 5.4 标签搜索

| C-c \   |                                                              |
| ------- | ------------------------------------------------------------ |
| C-c / m | 用匹配标签搜索的所有标题构造一个稀疏树。带前缀参数C-u时，忽略所有还是TODO行的标题。 |
| C-c a m | 用所有议程文件匹配的标签构造一个全局列表。                   |
| C-c a M | 用所有议程文件匹配的标签构造一个全局列表，但只搜索 TODO 项，并强制搜索所有子项（见变量 org-tags-match-listsublevels）。 |

## 6. 属性 （Properties）

属性是一些与条目关联的键值对

```
* CD collection
** Classic
*** Goldberg Variations
    :PROPERTIES:
    :Title:    Goldberg Variations
    :Composer: J.S. Bach
    :Publisher: Deutsche Grammophon
    :NDisks:   1
    :END:
```

通过设置属性 `“:Xyz_ALL:”` ，你可以为属性 `“:Xyz:”` 设置所有合法的值。这个特定的属性是有 *继承性* 的，即，如果你是在第 1 级别设置的，那么会被应用于整个树。当合法的值设定之后，设置对应的属性就很容易了，并且不容易出现打字错误。用CD唱片集为例，我们可以预定义发行商和盒中的光盘数目：

```
* CD collection
  :PROPERTIES:
  :NDisks_ALL: 1 2 3 4
  :Publisher_ALL: "Deutsche Grammophon" Philips EMI
  :END:
```

也可以在全局设置 org-global-properties ，或者在文件级别设置：

```
#+PROPERTY: NDisks_ALL 1 2 3 4
```

| C-c C-x p     | 设置一个属性。会询问属性名和属性值。 |
| ------------- | ------------------------------------ |
| **C-c C-c d** | **从当前项中删除一个属性。**         |

## 7. 日期和时间

### 7.1 时间戳

#### 普通时间戳

```
* Meet Peter at the movies <2006-11-01 Wed 19:15>
* Discussion on climate change <2006-11-02 Thu 20:00-22:00>
```

#### 具有时间间隔的时间戳

一个时间戳可以包含一个时间间隔，表示事件不只在指定的时间发生，还在每隔一个特定的时间如 N 天（d）、周（w）、月（m）或者年（y）之后重复发生。下面的事件每周二在议程中显示：

```
* Pick up Sam at school <2007-05-16 Wed 12:30 +1w>
```

#### 日记样式的 sexp 条目

为了能定义更复杂的时间，Org 模式支持 Emacs 日历/日记包（calendar/diary package）中的日记条目。例如：

```
* The nerd meeting on every 2nd Thursday of the month
  <%%(diary-float t 4 2)>
```

#### 时间/日期段

两个时间戳用‘–’连接起来就定义了一个时间段：

```
** Meeting in Amsterdam
   <2004-08-23 Mon>--<2004-08-26 Thu>
```

#### 非激活的时间戳

跟普通时间戳一样，但是这里是方括号而不是尖括号。这种时间戳是未激活的，它 *不* 会让一个条目显示在议程中。

```
* Gillian comes late for the fifth time [2006-11-01 Wed]
```

**非激活的时间戳**

跟普通时间戳一样，但是这里是方括号而不是尖括号。这种时间戳是未激活的，它 *不* 会让一个条目显示在议程中。

```
* Gillian comes late for the fifth time [2006-11-01 Wed]
```

### 7.2 创建时间戳

| C-c .            | 询问日期并输入正确的时间戳。当光标处理一个时间戳之上时，是修改这个时间戳，而不是插入一个新的。如果这个命令连用再次，就会插入一个时间段。加上前缀会附带当前时间。 |
| ---------------- | ------------------------------------------------------------ |
| **C-c !**        | **功能同C-c .，但是插入的是一个未激活的时间戳。**            |
| **S-LEFT/RIGHT** | **将光标处理的时间戳改变一天。**                             |
| **S-UP/DOWN**    | **改变时间戳中光标下的项。光标可以处在年、月、日、时或者分之上。当时间戳包含一个时间段时，如 “15:30-16:30”，修改第一个时间，会自动同时修改第二个时间，以保持时间段长度不变。想修改时间段长度，可以修改第二个时间。** |

### 7.3 截止期限和计划安排

计划安排： 计划开始的时间

截止日期： 计划截止的时间

| C-c C-d | 在标题下面一行插入一个带有“DEADLINE”关键字的时间戳。 |
| ------- | ---------------------------------------------------- |
| C-c C-s | 在标题下面插入一个带有“SCHEDULED”关键字的时间戳。    |

### 7.4 记录工作时间

|       key       |            action            |
| :-------------: | :--------------------------: |
| **C-c C-x C-i** | 在当前项目上开始计时（签到） |
| **C-c C-x C-o** |     停止计时（下班计时）     |
| **C-c C-x C-e** | 更新当前时钟任务的工作量估计 |
| **C-c C-x C-q** |         取消当前时钟         |
| **C-c C-x C-j** |   跳转到当前打卡任务的标题   |

## 8. 标记

### 8.1  段落

段落至少由一个空行分隔。如果您需要在段落中强制换行，请使用 '\\\\' 在一行的末尾。

要保留区域中的换行符、缩进和空行，但使用正常格式，您可以使用此结构，它也可用于格式化诗歌。

```
#+BEGIN_VERSE
 头顶上的大云
 小黑鸟起落
 白雪覆盖 Emacs

    ---亚历克斯·施罗德
#+END_VERSE
```

当引用另一个文档的段落时，习惯上将其格式化为左右两边缩进的段落。您可以像这样在 Org 文档中包含引文：

```
#+BEGIN_QUOTE
一切都应该尽可能简单，
但不是更简单---阿尔伯特·爱因斯坦
#+END_QUOTE
```

如果您想将一些文本居中，请这样做：

```
#+BEGIN_CENTER
一切都应该尽可能简单，\\
但并不简单
#+END_CENTER
```

### 8.2 强调和等宽

```
*ssssss*\\				加粗
/ssssss/				斜体
_sssss_  				下划线
=sssss=  				等宽
+sadjgklsd+				删除线
```

### 8.3 latex

```
The radius of the sun is R_sun = 6.96 x 10^8 m.  On the other hand,
the radius of Alpha Centauri is R_{Alpha Centauri} = 1.28 x R_{sun}.

\begin{equation}                        % arbitrary environments,
x=\sqrt{b}                              % even tables, figures
\end{equation}                          % etc

If $a^2=b$ and \( b=2 \), then the solution must be
either $$ a=+\sqrt{2} $$ or \[ a=-\sqrt{2} \].
```

### 8.4 文字

文字块：

```
#+BEGIN_EXAMPLE
  Some example from a text file.
#+END_EXAMPLE
```

文字块简单：

```
Here is an example
   : Some example from a text file.
```

代码块：

```
#+BEGIN_SRC emacs-lisp
  (defun org-xor (a b)
    "Exclusive or."
    (if a (not b) b))
 #+END_SRC
```

### 8.5 图片

```
#+CAPTION：这是下一个图形链接（或表格）的标题
#+NAME：fig：SED-HR4049
[[./img/a.jpg]]
```

### 8.6 脚注

**C-c C-x f**： 脚注操作命令。

**C-c C-c**： 在定义和引用之间跳转

## 9. 导出

使用 **C-c C-e** 导出文件

### 9.1  导出设定

```
#+TITLE: I'm in the Mood for Org
```

- title
- author
- date
- email
- language

### 9.2 目录设定

```
#+OPTIONS: toc:2 (目录中只包含两层)
#+OPTIONS: toc:nil（根本没有默认目录）
```

### 9.3  注释行

**C-c ;**

### 9.4 包含文件

```
#+INCLUDE: "~/.emacs" src emacs-lisp
```

## 10. 杂项

### 结构模板

要快速插入空的结构块，例如 '#+BEGIN_SRC’ … ‘#+END_SRC'，或将现有文本包装在这样的块中，使用

- C-c C-,

### 干净的景色

Org 的默认大纲带有星号且没有缩进，对于短文档来说可能会变得过于混乱。对于*像书一样的*长文档，效果不那么明显。Org 提供了另一种星号和缩进方案，如下表右侧所示。它仅使用一颗星和缩进文本来与标题对齐：

```
* 顶级标题 | * 顶级标题
** 二级 | * 第二级
*** 三级 | * 第三层
    一些文字 | 一些文字
*** 三级 | * 第三层
    更多文字 | 更多文字
* 另一个顶级标题 | * 另一个顶级标题
```

这种视图可以在显示时使用 Org Indent 模式 ( ) 动态实现，该模式在每行前面加上无形的空间。您可以通过自定义变量为所有文件打开 Org Indent 模式，或者您可以使用 M-x org-indent-mode RET`org-startup-indented`

```
#+startup: indent
```








































































[^1]: \<DEL>指的是Backspace
[^2]: 字符扩展。（x for eXtend） C-x之后输入另一个字符或者组合键