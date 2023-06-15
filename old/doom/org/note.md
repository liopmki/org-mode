
# Table of Contents

1.  [使用 doom emacs 中的 org mode](#orgc2e6830)
    1.  [文档结构和基本语法](#org1a196e4)
        1.  [标题](#org9267c1b)
        2.  [内容可见性](#org92869c7)
        3.  [移动](#orgf5c2f43)
        4.  [结构编辑](#org09e5f0c)
        5.  [稀疏树 Sparse Trees](#org4a05989)
        6.  [普通列表 Plain Lists](#orgd20019d)
    2.  [表格 table](#org10acf16)
        1.  [Intro](#org0534814)
        2.  [创建表格和移动单元格](#org4b53d5b)
        3.  [列操作](#orgc999317)
        4.  [行操作](#org8800df2)
        5.  [表格排序](#org3e4cb64)
    3.  [链接 Hyperlinks](#org6a0d2e0)
        1.  [两种基本的连接形式](#org4de6bfe)
        2.  [内部链接](#org0d0ee8c)
        3.  [外部链接](#orgbeb5516)
        4.  [处理链接](#org4054c32)
    4.  [待办 TODO Items](#org829b4f0)
        1.  [基本TODO功能](#org288fe29)
        2.  [多状态工作流](#orgd31be57)
        3.  [进度日志记录](#orge17f056)
        4.  [优先级](#org4ec4536)
        5.  [将任务分解成子任务](#orgb02219b)
        6.  [复选框](#org5ffcc4d)
    5.  [标签 Tags](#org436d7c3)
        1.  [标签的形式](#org1e64ed9)
        2.  [标签的继承](#orgf18c4bd)
        3.  [设置标签](#orgc134bf1):Keybndings:
        4.  [标签组](#org88fb0b1)
        5.  [搜索标签](#orgebf2606)
    6.  [属性 Properties](#org5238e79)
        1.  [Intro](#org01e1916)
        2.  [Keybinding](#org02508c1)
    7.  [日期和时间 Dates and Times](#org1252ad4)
        1.  [时间戳 Timestamps](#org57616bb)
        2.  [创建时间戳 Creating Timestamps](#org1fc59b3)
        3.  [截止日期和日程安排 Deadlines and Scheduling](#org5f9736f)
        4.  [Clocking Work Time](#orgb81692a)
    8.  [Capture,Refile,Archive 捕获，重新存档，存档](#org40c73b9)
        1.  [Capture](#orgcf4001b)
        2.  [Refile and Copy](#org764a1ac)
        3.  [Archiving](#org2cdb9bc)
    9.  [Agenda Views 议程视图](#org1a368a0)
        1.  [Agenda Files](#org0be3465)
        2.  [The Agenda Dispatcher](#org1e57ab3)
        3.  [The Weekly/Daily Agenda](#orge770e6e)
        4.  [The Global TODO List](#org52b3386)
        5.  [Commands in Agenda Buffer](#orgf33614c)
    10. [Markup for Rich Contents](#org8306210)
        1.  [Paragraphs](#orgd83155a)
        2.  [Emphasis and Monospace 强调和等宽](#org97bd455)
        3.  [Embedded LaTeX](#orgfaaf743)
        4.  [Literal example](#orgd8e5e58)
        5.  [Images](#org1a70ab4)
        6.  [Creating Footnotes](#orgeb7fbec)
    11. [Exporting](#org2f30789)
        1.  [The Export Dispatcher](#org581466f)
        2.  [Export Settings](#orgde9235b)
        3.  [Table of Contents 目录](#orga3ece49)
        4.  [Inculude Files](#org1573be8)
        5.  [Comment Lines](#org448515d)

> Org Mode compact guide    
> Org Mode Version: 9.6


<a id="orgc2e6830"></a>

# 使用 doom emacs 中的 org mode


<a id="org1a196e4"></a>

## 文档结构和基本语法


<a id="org9267c1b"></a>

### 标题

使用 \* 区分标题层级


<a id="org92869c7"></a>

### 内容可见性

1.  子树循环

    使用 TAB 控制子树的状态
    
        ,-> FOLDED -> CHILDREN -> SUBTREE --.
        '-----------------------------------'

2.  全局循环

    使用 S-TAB 控制整个Buffer的状态
    
        ,-> OVERVIEW -> CONTENTS -> SHOW ALL --.
        '--------------------------------------'

3.  控制默认的显示状态

        #+startup: overview
        # overview, content, showall, showeveryting, show<n>levels


<a id="orgf5c2f43"></a>

### 移动

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">Doom-Keybinding</th>
<th scope="col" class="org-left">Keybinding</th>
<th scope="col" class="org-left">Action</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">&#xa0;</td>
<td class="org-left">C-c C-n</td>
<td class="org-left">下一个标题</td>
</tr>


<tr>
<td class="org-left">&#xa0;</td>
<td class="org-left">C-c C-p</td>
<td class="org-left">上一个标题</td>
</tr>


<tr>
<td class="org-left">&#xa0;</td>
<td class="org-left">C-c C-f</td>
<td class="org-left">下一个同级标题</td>
</tr>


<tr>
<td class="org-left">&#xa0;</td>
<td class="org-left">C-c C-b</td>
<td class="org-left">上一个同级标题</td>
</tr>


<tr>
<td class="org-left">&#xa0;</td>
<td class="org-left">C-c C-u</td>
<td class="org-left">回到更高级别的标题</td>
</tr>
</tbody>
</table>


<a id="org09e5f0c"></a>

### 结构编辑

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">Doom-Keybinding</th>
<th scope="col" class="org-left">Keybinding</th>
<th scope="col" class="org-left">Action</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">&#xa0;</td>
<td class="org-left">M-RET</td>
<td class="org-left">插入同级标题或列表项</td>
</tr>


<tr>
<td class="org-left">&#xa0;</td>
<td class="org-left">M-S-RET</td>
<td class="org-left">插入同级TODO</td>
</tr>


<tr>
<td class="org-left">&#xa0;</td>
<td class="org-left">M-Left / M-Right</td>
<td class="org-left">标题升级 / 降级</td>
</tr>


<tr>
<td class="org-left">&#xa0;</td>
<td class="org-left">M-Up / M-Down</td>
<td class="org-left">向上 / 向下移动子树</td>
</tr>


<tr>
<td class="org-left">&#xa0;</td>
<td class="org-left">C-c C-w</td>
<td class="org-left">将条目或区域重新归档到不同的位置(标题下的内容会移动到选择的位置并降级)</td>
</tr>


<tr>
<td class="org-left">&#xa0;</td>
<td class="org-left">C-x n s / C-x n w</td>
<td class="org-left">缩小子树和展开子树</td>
</tr>
</tbody>
</table>


<a id="org4a05989"></a>

### 稀疏树 Sparse Trees

> 在大纲树中选中信息构建稀疏树，从而尽可能折叠整个文档，但选中的信息连通其上方的标题结构一起可见。

-   C-c /
    提示输入一个额外的键来选择稀疏树的创建命令


<a id="orgd20019d"></a>

### 普通列表 Plain Lists

1.  3种列表

    -   无序列表
        以 &ldquo;-&rdquo;, &ldquo;+&rdquo;, &ldquo;\*&rdquo; 开头
    -   有序列表
        以 &ldquo;1.&rdquo;, &ldquo;1)&rdquo; 开头
    -   描述列表
        以 &ldquo;::&rdquo; 将术语与描述分开
        example: aaa :: bbb

2.  列表操作

    -   列表内容可以用 TAB 来显示和折叠
    -   M-RET
        插入新项目
    -   M-S-RET
        插入有复选框的新项目
    -   M-S-Up / M-S-Down
        向上 / 向下移动项目包括子项目
    -   M-Left / M-Right
        减少和增加缩进
    -   M-S-Left / M-S-Right
        减少和增加缩进包括子项目
    -   C-c C-c
        切换复选框的状态
    -   C-c -
        循环切换列表使用的符号


<a id="org10acf16"></a>

## 表格 table


<a id="org0534814"></a>

### Intro

在表格中使用 TAB or RET or C-c C-c
可以重新对齐表格

完成表格的第一行后 C-c RET 即可创建
表格


<a id="org4b53d5b"></a>

### 创建表格和移动单元格

-   C-c |
    可以创建表格也可以将符合标准的内容转换
    成表格
-   S-Up / Down / Left / Right
    移动单元格（通过交换相邻两个单元格）


<a id="orgc999317"></a>

### 列操作

-   M-Left,M-Right
    向左，向右移动当前列
-   M-S-Left
    Kill the current column
-   M-S-Right
    在左侧插入一个新列


<a id="org8800df2"></a>

### 行操作

-   M-Up, M-Down
    向上，向下移动当前行
-   M-S-Up
    Kill the current row or horizontal line
-   M-S-Down
    在上方插入新行
-   C-c -
    在下方插入水平线
-   C-c RET
    在下方插入水平线,并将光标移动到水平线下方


<a id="org3e4cb64"></a>

### 表格排序

-   C-c ^


<a id="org6a0d2e0"></a>

## 链接 Hyperlinks


<a id="org4de6bfe"></a>

### 两种基本的连接形式

    [[LINK][DESCRIPTION]]
    or
    [[LINK]]


<a id="org0d0ee8c"></a>

### 内部链接

1.  第一种
    
        [[#my-custom-id]]
        这个链接 --> "CUSTOM_ID"属性为 my-custom-id 的标题
2.  第二种
    
        [[target]] or [[target][Click to target]]
        --> <<target>>


<a id="orgbeb5516"></a>

### 外部链接

    ‘http://www.astro.uva.nl/=dominik’	    on the web
    ‘file:/home/dominik/images/jupiter.jpg’	file, absolute path
    ‘/home/dominik/images/jupiter.jpg’	    same as above
    ‘file:papers/last.pdf’	                file, relative path
    ‘./papers/last.pdf’	                    same as above
    ‘file:projects.org’	                    another Org file
    ‘docview:papers/last.pdf::NNN’	        open in DocView mode at page NNN
    ‘id:B7423F4D-2E8A-471B-8810-C40F074717E9’	link to heading by ID
    ‘news:comp.emacs’	                        Usenet link
    ‘mailto:adent@galaxy.net’	                mail link
    ‘mhe:folder#id’	                        MH-E message link
    ‘rmail:folder#id’	                        Rmail message link
    ‘gnus:group#id’	                        Gnus article link
    ‘bbdb:R.*Stallman’	                    BBDB link (with regexp)
    ‘irc:/irc.com/#emacs/bob’	                IRC link
    ‘info:org#Hyperlinks’	                    Info node link
    
    ‘file:~/code/main.c::255’	                Find line 255
    ‘file:~/xx.org::My Target’	            Find ‘<<My Target>>’
    ‘[[file:~/xx.org::#my-custom-id]]’	        Find entry with a custom ID


<a id="org4054c32"></a>

### 处理链接

-   C-c C-l
    编辑链接
    插入链接
-   C-c C-o
    打开链接
-   C-c &
    跳回记录点
    记录点使用 C-c % 标记


<a id="org829b4f0"></a>

## 待办 TODO Items


<a id="org288fe29"></a>

### 基本TODO功能

以 TODO 开头的标题是一个 TODO

-   C-c C-t
    选择TODO状态
-   S-Right,S-Left
    切换TODO状态
-   C-c | t
    查看稀疏树中的TODO
-   M-x org-agenda t
    全局TODO List
-   S-M-RET
    插入新TODO


<a id="orgd31be57"></a>

### 多状态工作流

doom-emacs 默认


<a id="orge17f056"></a>

### 进度日志记录

当任务变化时，进行的操作

1.  任务完成 DONE

        (setq org-log-done 'time) ; 任务为DONE时，添加一个"CLOSED:[timestamp]"
        (setq org-log-done 'note) ; 任务为DONE时，添加一个"CLOSED:[timestamp]" 和 note

2.  跟踪TODO状态变化

        #+TODO: TODO(t) WAIT(W@/!) | DONE(d!) CANCELED(c@)
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    
    <col  class="org-left" />
    </colgroup>
    <thead>
    <tr>
    <th scope="col" class="org-left">标记</th>
    <th scope="col" class="org-left">作用</th>
    </tr>
    </thead>
    
    <tbody>
    <tr>
    <td class="org-left">&ldquo;!&rdquo;</td>
    <td class="org-left">时间戳</td>
    </tr>
    
    
    <tr>
    <td class="org-left">&ldquo;@&rdquo;</td>
    <td class="org-left">note</td>
    </tr>
    </tbody>
    </table>


<a id="org4ec4536"></a>

### 优先级

org 有3个优先级 A B C
B 是默认值

-   C-c ,
    设置优先级
-   S-Up, S-Down
    增加,减少优先级


<a id="orgb02219b"></a>

### 将任务分解成子任务

在标题后面添加 &ldquo;<code>[/]</code>&rdquo; &ldquo;<code>[%]</code>&rdquo;


<a id="org5ffcc4d"></a>

### 复选框

-   M-S-RET
    insert checkbox
-   C-c C-c
    toggle checkbox status

-   [-] item1<code>[1/3]</code>
    -   [-] item1-1 <code>[50%]</code>
        -   [ ] item1-1-1
        -   [X] item1-1-2
    -   [X] item1-2
    -   [ ] item1-3


<a id="org436d7c3"></a>

## 标签 Tags


<a id="org1e64ed9"></a>

### 标签的形式

每个标题都可以有一个标签列表

标签包含字母,数字,下划线，@

    :work:
    
    :work:urgent:


<a id="orgf18c4bd"></a>

### 标签的继承

1.  子标题会继承父标题的 Tags
2.  设置文件中所有标题都继承的 Tags
    
        #+FILETAGS: :Peter:Boss:Secret:


<a id="orgc134bf1"></a>

### 设置标签     :Keybndings:

-   C-c C-q
    插入标签
-   C-c C-c
    同上,但需要焦点在标题上

设置默认的标签列表：

    #+TAGS: @work @home
    #+TAGS: laptop car pc sailboat
    #+TAGS: @work(w) @home(h) laptop(l) pc(p)


<a id="org88fb0b1"></a>

### 标签组

    #+TAGS: [ GTD : Control Persp ]
    #+TAGS: { Context : @Home @Work }


<a id="orgebf2606"></a>

### 搜索标签

-   C-c | m or C-c |
    创建一个稀疏树，其中所有标题都匹配标签
    搜索。使用前缀参数，忽略不是TODO的标题
-   M-x org-agenda m
    从所有议程文件（agenda files）中创建标签匹配的全局列表
-   M-x org-agenda M
    从所有议程文件中创建标签匹配的全局列表，但仅检查TODO项目并强制检查子项目


<a id="org5238e79"></a>

## 属性 Properties


<a id="org01e1916"></a>

### Intro

    :PROPERTIES:
    :Title:     Goldberg Variations
    :Composer:  J.S. Bach
    :Publisher: Deutsche Grammophon
    :NDisks:    1
    :END:

可以定义Xyz<sub>ALL来定义Xyz的允许值</sub>

设置可以被文件中的任何标题继承的属性:

    #+PROPERTY: NDisks_ALL 1 2 3 4


<a id="org02508c1"></a>

### Keybinding

-   C-c C-x p or SPC m o
    设置属性
-   C-c C-c d
    从当前标题中删除属性


<a id="org1252ad4"></a>

## 日期和时间 Dates and Times


<a id="org57616bb"></a>

### 时间戳 Timestamps

时间戳

    <2003-09-16 Tue> or <2003-09-16 Tue 09:39> or <2003-09-16 Tue 12:00-12:30>

1.  普通时间戳

    一个简单的时间戳只是为一个项目分配一个日期/时间。

2.  有重复间隔的时间戳

        <2007-05-16 Wed 12:30 +1w>
    
    在特定间隔后仍然应用
    
    间隔：
    
    -   d
        days
    -   w
        weeks
    -   m
        months
    -   y
        years

3.  日记式的格式 Diary-style expression entries

    对于更复杂的日期范围，Org mode 支持在emacs日历中实现特殊表达式日记条目。例如，可选时间：
    
        *  22:00-23:00 The nerd meeting on every 2nd Thursday of the month
            <%%(diary-float t 4 2)>

4.  时间范围

    由 “&#x2013;” 连接的两个时间戳表示一个范围

5.  非活动时间戳

    使用方括号包裹时间戳，这些时间戳不会触发


<a id="org1fc59b3"></a>

### 创建时间戳 Creating Timestamps

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">Keybinding</th>
<th scope="col" class="org-left">Action</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">C-c .</td>
<td class="org-left">插入时间戳，修改时间戳，使用两次添加时间范围</td>
</tr>


<tr>
<td class="org-left">C-c !</td>
<td class="org-left">和上一条一样，但是插入的是不活跃的时间戳</td>
</tr>


<tr>
<td class="org-left">S-Left,S-Right</td>
<td class="org-left">将日期更改一天</td>
</tr>


<tr>
<td class="org-left">S-Up,S-Down</td>
<td class="org-left">在尖括号处，更改时间戳类型；在时间戳中，更改年、月、日等</td>
</tr>
</tbody>
</table>


<a id="org5f9736f"></a>

### 截止日期和日程安排 Deadlines and Scheduling

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">Keybinding</th>
<th scope="col" class="org-left">Action</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">C-c C-d</td>
<td class="org-left">插入Deadline和时间戳(预计的项目截止时间)</td>
</tr>


<tr>
<td class="org-left">C-c C-s</td>
<td class="org-left">插入Scheduled和时间戳(预计的项目开始时间)</td>
</tr>
</tbody>
</table>


<a id="orgb81692a"></a>

### Clocking Work Time

工作时间计时

记录的是从开始时间到结束时间

-   clock-in
    开始计时（签到）
-   clock-out
    停止计时（下班）

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">Keybinding</th>
<th scope="col" class="org-left">Action</th>
<th scope="col" class="org-left">Doom-Keybinding</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">C-c C-x C-i</td>
<td class="org-left">开始计时（签到）</td>
<td class="org-left">SPC m c i</td>
</tr>


<tr>
<td class="org-left">C-c C-x C-o</td>
<td class="org-left">停止计时（下班）</td>
<td class="org-left">SPC m c o</td>
</tr>


<tr>
<td class="org-left">C-c C-x C-e</td>
<td class="org-left">更新工作量估计</td>
<td class="org-left">SPC m c e</td>
</tr>


<tr>
<td class="org-left">C-c C-x C-q</td>
<td class="org-left">取消时钟（开始计时后）</td>
<td class="org-left">SPC n C</td>
</tr>


<tr>
<td class="org-left">C-c C-x C-j</td>
<td class="org-left">跳转到打卡任务的标题</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>


<a id="org40c73b9"></a>

## Capture,Refile,Archive 捕获，重新存档，存档


<a id="orgcf4001b"></a>

### Capture

快速笔记，可以定义模板

1.  Setting up capture

        (setq org-default-notes-file (concat org-directory "path/to/filename.org"))

2.  Using capture

    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    
    <col  class="org-left" />
    
    <col  class="org-left" />
    </colgroup>
    <thead>
    <tr>
    <th scope="col" class="org-left">Keybinding</th>
    <th scope="col" class="org-left">Action</th>
    <th scope="col" class="org-left">Doom-Keybinding</th>
    </tr>
    </thead>
    
    <tbody>
    <tr>
    <td class="org-left">M-x org-capture</td>
    <td class="org-left">start capture</td>
    <td class="org-left">SPC X</td>
    </tr>
    
    
    <tr>
    <td class="org-left">C-c C-c</td>
    <td class="org-left">return to before</td>
    <td class="org-left">&#xa0;</td>
    </tr>
    
    
    <tr>
    <td class="org-left">C-c C-w</td>
    <td class="org-left">通过将笔记重新归档到不同的地方来完成捕获</td>
    <td class="org-left">&#xa0;</td>
    </tr>
    
    
    <tr>
    <td class="org-left">C-c C-k</td>
    <td class="org-left">abort the capture and return to the previous state</td>
    <td class="org-left">&#xa0;</td>
    </tr>
    </tbody>
    </table>

3.  Capture templates

        (setq org-capture-templates
                '(("t" "Todo" entry (file+headline "path/to/todo.org" "Tasks")
                    "* TODO %?\n %i\n %a")
                  ("j" "Journal" entry (file+datetree "path/to/journal.org")
                   "* %?\nEntered on %U\n  %i\n  %a")))
    
    动态插入的内容：
    
    -   %a
        注释，通常是用org-store-link创建的连接
    -   %i
        初始内容，调用捕获时的区域
    -   %t，%T
        时间戳
    -   %u，%U
        不活跃的时间戳
    -   %？
        加载模板完成后，光标的位置


<a id="org764a1ac"></a>

### Refile and Copy

将Capture的数据重新归档或复制到不同的列表中，例如将Capture的数据复制到项目中。

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">Keybinding</th>
<th scope="col" class="org-left">Action</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">C-c C-w</td>
<td class="org-left">Refile the entry or region at piont</td>
</tr>


<tr>
<td class="org-left">C-u C-c C-w</td>
<td class="org-left">Use the refile interface to jump to a heading</td>
</tr>


<tr>
<td class="org-left">C-u C-u C-c C-w</td>
<td class="org-left">Jump to the location where org-refile last moved a tree to</td>
</tr>


<tr>
<td class="org-left">C-c M-w</td>
<td class="org-left">Copying works like refiling,except that the original note is note deleted</td>
</tr>
</tbody>
</table>


<a id="org2cdb9bc"></a>

### Archiving

When a project represented by a (sub)tree is finished, you may want to move the tree out of the way and to stop it from contributing to the agenda.

当一个（子）树代表的项目完成时，你可能想把这个树移出并停止它参与议程。

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">Keybinding</th>
<th scope="col" class="org-left">Action</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">C-c C-x C-a</td>
<td class="org-left">使用变量 org-archive-default-command 中指定的命令归档当前条目</td>
</tr>


<tr>
<td class="org-left">C-c C-x C-s or short C-c $</td>
<td class="org-left">将子树从光标位置开始归档到 org-archive-location 给定的位置</td>
</tr>
</tbody>
</table>

默认存档位置与当前文件位于同一目录，名称是&ldquo;<sub>archive</sub>&rdquo;与文件名连接而成。


<a id="org1a368a0"></a>

## Agenda Views 议程视图


<a id="org0be3465"></a>

### Agenda Files

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">Keybinding</th>
<th scope="col" class="org-left">Action</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">C-c [</td>
<td class="org-left">将当前文件添加到议程文件列表中</td>
</tr>


<tr>
<td class="org-left">C-c ]</td>
<td class="org-left">将当前文件移除到议程文件列表中</td>
</tr>


<tr>
<td class="org-left">C-c &rsquo; or C-c ,</td>
<td class="org-left">循环浏览议程文件列表，依次展示文件</td>
</tr>
</tbody>
</table>


<a id="org1e57ab3"></a>

### The Agenda Dispatcher

-   DOOM-Keybinding
    
        open the agenda dispatcher
        SPC o A


<a id="orge770e6e"></a>

### The Weekly/Daily Agenda

时间戳可以触发


<a id="org52b3386"></a>

### The Global TODO List

SPC o A t or SPC o A T


<a id="orgf33614c"></a>

### Commands in Agenda Buffer

-   t
    
        下一行
-   p
    
        上一行
-   SPC
    
        在另一个窗口中显示项目的原始位置
-   TAB
    
        转到项目在另一个窗口中的原始位置
-   RET
    
        转到项目的原始位置并删除其他窗口
-   o
    
        删除其他窗口
-   d
    
        切换到日视图
-   w
    
        切换到周视图
-   f
    
        显示进度
-   b
    
        显示更早的日期
-   .
    
        今天
-   j
    
        日期提示，并切换到该日期
-   l
    
        切换日志模式
-   r
    
        重新创建缓冲区
-   s
    
        保存


<a id="org8306210"></a>

## Markup for Rich Contents


<a id="orgd83155a"></a>

### Paragraphs

Paragraphs are separated by at least one empty line.

Use &ldquo;\\\\&rdquo; at the end of a line to enforce a line break within a paragraph.

Format poetry:

<p class="verse">
第一行<br />
第二行<br />
&#xa0;&#xa0;&#xa0;&#xa0;&#x2013;someone<br />
</p>

Center:

<div class="org-center">
<p>
Hello World!
</p>
</div>


<a id="org97bd455"></a>

### Emphasis and Monospace 强调和等宽

    *bold*
    /italic/
    _unerlined_
    =verbatim=
    ~code~
    +strike-through+

**bold**
*italic*
<span class="underline">unerlined</span>
`verbatim`
`code`
<del>strike-through</del>


<a id="orgfaaf743"></a>

### Embedded LaTeX

The radius of the sun is R<sub>sun</sub> = 6.96 x 10<sup>8</sup> m.  On the other hand,
the radius of Alpha Centauri is R<sub>Alpha Centauri</sub> = 1.28 x R<sub>sun</sub>.

\begin{equation}                        % arbitrary environments,
x=\sqrt{b}                              % even tables, figures
\end{equation}                          % etc

If $a^2=b$ and $ b=2 $, then the solution must be
either $$ a=+\sqrt{2} $$ or $$ a=-\sqrt{2} $$.


<a id="orgd8e5e58"></a>

### Literal example

示例，使用等宽字体,不受标记影响

    this is a exmaple

Here is an example

    Some example from a note.org
    another line


<a id="org1a70ab4"></a>

### Images

图像链接

    [[./link/to/image.png]]

定义图片的标题和引用标签

![img](./image.png "This is the caption for the next image link (or table)")

-   Doom-Keybinding: z i
    toggle the display of image


<a id="orgeb7fbec"></a>

### Creating Footnotes

脚注的定义

    this is a footnotes[fn:1]
    ...
    [fn:1] I am footnote

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">Keybinding</th>
<th scope="col" class="org-left">Action</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">C-c C-x f or SPC m f</td>
<td class="org-left">脚注的相关操作</td>
</tr>


<tr>
<td class="org-left">C-c C-c</td>
<td class="org-left">在定义和引用之间跳转</td>
</tr>
</tbody>
</table>


<a id="org2f30789"></a>

## Exporting


<a id="org581466f"></a>

### The Export Dispatcher

C-c C-e   
SPC m e


<a id="orgde9235b"></a>

### Export Settings

    #+title: this is title
    #+author: default taken from user-full-name
    #+date: a date, fixed, or an Org timestamp
    #+email: default from user-mail-address
    #+LANGUAGE: language code


<a id="orga3ece49"></a>

### Table of Contents 目录

    #+options: toc:2    (only include two levels in TOC)
    #+options: toc:nil  (no default TOC at all)


<a id="org1573be8"></a>

### Inculude Files

    #+include: "path/to/file" src emacs-lisp

第一个参数是文件路径，第二个参数是指定块的类型，第三个参数指定格式化内容的源代码语言。

使用 C-c &rsquo; 可以访问包含的文件

    print("Hello World!")

    print("Hello World!")


<a id="org448515d"></a>

### Comment Lines

    # this is comment
    
    #+begin_comment
    this is comment
    #+end_comment

-   C-c ;
    将标题前加COMMENT,会注释掉子树

