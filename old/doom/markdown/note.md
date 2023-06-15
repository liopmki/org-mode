<!-- markdown-toc start - Don't edit this section. Run M-x markdown-toc-refresh-toc -->
**Table of Contents**

- [使用 doom emacs 下的 Markdown mode](#使用-doom-emacs-下的-markdown-mode)
    - [Markdown mode 参考文档](#markdown-mode-参考文档)
    - [基本语法的实现和快捷键](#基本语法的实现和快捷键)
        - [标题](#标题)
        - [行内元素](#行内元素)
        - [块级元素](#块级元素)
        - [链接和图片](#链接和图片)
        - [列表](#列表)
        - [水平线](#水平线)
        - [移动](#移动)
            - [按段落移动](#按段落移动)
            - [按块移动](#按块移动)
            - [按章节移动](#按章节移动)
            - [在大纲和列表间移动](#在大纲和列表间移动)
        - [展开和折叠](#展开和折叠)
        - [大纲子树编辑](#大纲子树编辑)
        - [区域编辑](#区域编辑)
    - [Markdown mode 实用命令](#markdown-mode-实用命令)
    - [切换和设置](#切换和设置)
    - [Others](#others)

<!-- markdown-toc end -->

# 使用 doom emacs 下的 Markdown mode

## Markdown mode 参考文档

[Markdown Mode for Emacs : Jason Blevins](https://jblevins.org/projects/markdown-mode/)
[Markdonw Mode Github](https://github.com/jrblevin/markdown-mode)

## 基本语法的实现和快捷键

### 标题

| Action             | Keybinding                  |
|--------------------|-----------------------------|
| 根据上下文插入标题 | <kbd>C-c C-s h</kbd>        |
| 直接插入标题       | <kbd>C-c C-s H</kbd>        |
| 插入带级别的标题   | <kbd>C-c C-s <number></kbd> |

### 行内元素

| Action                 | Keybinding           |
|------------------------|----------------------|
| 加粗                   | <kbd>C-c C-s b</kbd> |
| 斜体                   | <kbd>C-c C-s i</kbd> |
| 行内代码               | <kbd>C-c C-s c</kbd> |
| kbd 标签（代表键盘）   | <kbd>C-c C-s k</kbd> |
| Wiki Link (两个方括号) | <kbd>C-c C-s w</kbd> |

### 块级元素

| Action                            | Keybinding           |
|-----------------------------------|----------------------|
| 代码块                            | <kbd>C-c C-s p</kbd> |
| 代码块（区域）                    | <kbd>C-c C-s P</kbd> |
| 引用块                            | <kbd>C-c C-s q</kbd> |
| 引用块（区域）                    | <kbd>C-c C-s Q</kbd> |
| GFM 代码块(常用的格式)            | <kbd>C-c C-s C</kbd> |
| GFM 代码块 (在另一个buffer中编辑) | <kbd>C-c '</kbd>     |

### 链接和图片

| Action               | Keybinding           |
|----------------------|----------------------|
| Link                 | <kbd>C-c C-l</kbd>   |
| image                | <kbd>C-c C-i</kbd>   |
| 打开链接             | <kbd>C-c C-o</kbd>   |
| 在定义和链接之间跳转 | <kbd>C-c C-d</kbd>   |
| 移动至下一个链接     | <kbd>M-n</kbd>       |
| 移动至上一个链接     | <kbd>M-p</kbd>       |
| 脚注                 | <kbd>C-c C-s f</kbd> |
| 在脚注和定义之间跳转 | <kbd>C-c C-d</kbd>   |

### 列表

| Action            | Keybinding                                      |
|-------------------|-------------------------------------------------|
| 插入无序列表      | <kbd>M-RET</kbd> or <kbd>C-c C-j</kbd>          |
| 插入父级列表项    | <kbd>C-u C-c C-j</kbd>                          |
| 插入子级列表项    | <kbd>C-u C-u C-c C-j</kbd>                      |
| 上移列表项        | <kbd>C-c <up></kbd>                             |
| 下移列表项        | <kbd>C-c <down></kbd>                           |
| 改变列表项的级别  | <kbd>C-c <right></kbd> or <kbd>C-c <left></kbd> |
| 切换复选框 (状态) | <kbd>C-c C-x C-x</kbd>                          |

### 水平线

| Action | Keybinding           |
|--------|----------------------|
| 水平线 | <kbd>C-c C-s -</kbd> |

### 移动

#### 按段落移动

| Action     | Keybinding     |
|------------|----------------|
| 上一个段落 | <kbd>M-{</kbd> |
| 下一个段落 | <kbd>M-}</kbd> |
| 标记段落   | <kbd>M-h</kbd> |

#### 按块移动

| Action                                 | Keybinding         |
|----------------------------------------|--------------------|
| 上一个块                               | <kbd>C-M-{</kbd>   |
| 下一个块                               | <kbd>C-M-}</kbd>   |
| 缩减块(将一个块放到一个单独的位置编辑) | <kbd>C-x n b</kbd> |
| 扩展块(返回到全文编辑)                 | <kbd>C-x n w</kbd> |
| 标记块                                 | <kbd>C-c M-h</kbd> |

#### 按章节移动

| Action         | Keybinding           |
|----------------|----------------------|
| 移动到章节开头 | <kbd>C-M-a</kbd>     |
| 移动到章节结束 | <kbd>C-M-e</kbd>     |
| 标记章节       | <kbd>C-M-h</kbd>     |
| 标记子树       | <kbd>C-c C-M-h</kbd> |
| 缩减章节       | <kbd>C-x n d</kbd>   |
| 缩减子树       | <kbd>C-x n s</kbd>   |
| 扩展章节       | <kbd>C-x n w</kbd>   |

#### 在大纲和列表间移动

| Action                     | Keybinding         |
|----------------------------|--------------------|
| 下一个标题或列表项         | <kbd>C-c C-n</kbd> |
| 上一个标题或列表项         | <kbd>C-c C-p</kbd> |
| 下一个标题或列表项(同级别) | <kbd>C-c C-f</kbd> |
| 上一个标题或列表项(同级别) | <kbd>C-c C-b</kbd> |
| 移动到父标题或列表项       | <kbd>C-c C-u</kbd> |

### 展开和折叠

| Action                   | Keybinding       |
|--------------------------|------------------|
| 全局展开和折叠           | <kbd>S-TAB</kbd> |
| 展开和折叠(在标题处使用) | <kbd>TAB</kbd>   |

### 大纲子树编辑

> 子树就是标题及以下内容

| Action   | Keybinding             |
|----------|------------------------|
| 上移子树 | <kbd>C-c <up></kbd>    |
| 下移子树 | <kbd>C-c <down></kbd>  |
| 子树升级 | <kbd>C-c <left></kbd>  |
| 子树降级 | <kbd>C-c <right></kbd> |

### 区域编辑

| Action   | Keybinding       |
|----------|------------------|
| 增加缩进 | <kbd>C-c ></kbd> |
| 减少缩进 | <kbd>C-c <</kbd> |

## Markdown mode 实用命令

| Action                                     | Keybinding           |
|--------------------------------------------|----------------------|
| 打开Markdown输出列表(一些输出的操作)       | <kbd>C-c C-c m</kbd> |
| 导出到文件                                 | <kbd>C-c C-c e</kbd> |
| 在浏览器中预览                             | <kbd>C-c C-c p</kbd> |
| 导出并预览                                 | <kbd>C-c C-c v</kbd> |
| 切换实时预览模式                           | <kbd>C-c C-c l</kbd> |
| 打开外部预览器                             | <kbd>C-c C-c o</kbd> |
| 检查缓冲区中的引用(检查有没有未定义的引用) | <kbd>C-c C-c c</kbd> |
| 重新编号缓冲区中的有序列表                 | <kbd>C-c C-c n</kbd> |

## 切换和设置

| Action                   | Keybinding             |
|--------------------------|------------------------|
| 切换标记和隐藏           | <kbd>C-c C-x C-m</kbd> |
| 切换URL隐藏              | <kbd>C-c C-x C-l</kbd> |
| 切换原始的代码块字体锁定 | <kbd>C-c C-x C-f</kbd> |
| 切换内联图像             | <kbd>C-c C-x C-i</kbd> |
| 切换LaTeX数学支持        | <kbd>C-c C-x C-e</kbd> |

## Others

| Keybinding         | action               | Doom-Keybinding                                |
|--------------------|----------------------|------------------------------------------------|
|                    | 插入表格             | <kbd>SPC m i t</kbd>                           |
|                    | 插入TOC              | <kbd>SPC m i T</kbd>                           |
| <kbd>C-c C-d</kbd> | Markdown-do 格式化   | <kbd><ENTER></kbd>                             |
|                    | 插入Check list       | <kbd><ENTER></kbd> in blank (normal mode)      |
|                    | 修改Check list state | <kbd><ENTER></kbd> in Check list (normal mode) |

  * [ ] todo
    * [ ] 继续补充 `Doom-Keybinding`
