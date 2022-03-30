# LaTeX-Package: xchoices

A package for flexibly LaTeXing choice items based on hlist environment and coffin.

Github Repository: https://github.com/xkwxdyy/xchoices

Gitee Repository: https://gitee.com/xkwxdyy/xchoices

Author: Kangwei Xia <kangweixia_xdyy@163.com>

## 宏包简介
`xchoices`宏包是一个用于排版选项的宏包, 包含但不限于以下特点：
- 可以排版任意数量的选项
- 可以方便切换标签风格 `label-style`
- 可以更改标签 `label` 与内容的相对位置
- 可以调整标签 `label` 的偏移

## 宏包开发背景

已经存在用 [`ifthen`宏包](https://www.latexstudio.net/index/details/index/mid/2270.html) 或者用 [`xcoffins`宏包](https://www.latexstudio.net/index/details/index/mid/2191.html) 写的相关选项命令, 用于排版试卷中的选择题, 常见的形如 `\xx{arg1}{arg2}{arg3}{arg4}`, 但是有几个不足（以 `\xx` 命令为例）:
- 从用户接口角度看：这样定义的命令只能且必须接受四个参数
  - 如果输入少于四个, 那么就会有空白项出现, 比如`D.  `
  - 如果想要输入多于四个固然可以用同样的方式再定义相应的命令, 但是可能事先并不知道有多少个选项, 通常的解决办法是先建立很多个命令分别作用于`1, 2, ... , 9`个命令, 比较麻烦不够简洁, 而且问题又来了: 通常的LaTeX命令参数最多有9个, 如果有排版更多项的需求时, 传统的方法一般是通过多个命令嵌套实现，但是无论是代码实现还是用户接口都不令人满意, 十分繁琐！
  ** 所以希望存在一个相同接口的命令或环境, 可以排版任意个选项 **
- 从代码实现角度看, 已有命令的代码在实现上有很大的优化空间
- 从功能的延拓性看：现有的一些命令中，“ABCD”往往是手动输入进行封装, 对 `label` 样式切换造成了困难。而在选项排版中，不同的 `label`  样式的方便切换（ 比如 `arabic`, `roman`等）也是一个大需求，所以需要在排出来的基础上提供方便的 `<key> = <val>`接口来进行控制

## 宏包说明

本宏包为本人前段时间编写的宏包`choices`的重新推翻编写的版本，并增添完善了许多功能
（choices宏包仓库：[github](https://github.com/xkwxdyy/xchoices), [gitee](https://gitee.com/xkwxdyy/xchoices)）


### 变更
- `choices`宏包更名为`xchoices`宏包，`x`寓意为`etra`，可以避免与`exam.cls`冲突，并能同时使用
- 更改全局设置接口为`\xchoicesetup`
- 统一所有选项排版命令为`xchoices`环境

### 新增
- 新增了选择题的括号命令`\xparen`，默认到该行行尾，内容多时自动到下一行行尾
- 增加了代码风格类似于`list`环境的`xchoices`环境，用`\item`分隔每一项，使选项分隔结构更清晰
- 基于`xchoices`环境下增加了答案的控制显示，`\item*`表示该项为正确答案，支持多选题。示例如下
```tex
<题干内容>，下面正确的是\xparen
\begin{xchoices}[
  showanswer = true,
  label-style = quan
]
  \item* 正确选项
  \item  \includegraphics[width = 2cm]{example-image-a}
  \item* 正确选项
  \item  错误选项
\end{xchoices}
```
![](https://raw.githubusercontent.com/xkwxdyy/image/main/postimage/image-hosting/20220201100404.png)

- 增加和完善了一系列键值，目前有
  - items：每行排多少个，系统会根据选项宽度自动计算合适值，可用此键值手动干预
  - pre-label：label前的内容，初始为空
  - post-label：label后的内容，初始值为"."
  - label-style：label的样式
    - arabic：阿拉伯数字
    - roman：小写罗马数字
    - Roman：大写罗马数字
    - chinese：中文数字
    - quan：带圈数字
    - alph：小写英文字母
    - Alph：大写英文字母
    - none：没有label
  - label-pos：label相对于内容的位置
    - top, top-center：正上方
    - top-left：上左方
    - top-right：上右方
    - bottom, bottom-center：正下方
    - bottom-left：下左方
    - bottom-right：下右方
    - left, left-center：正左方
    - left-top：左上方
    - left-bottom：左下方
    - right, right-center：正左方
    - right-top：左上方
    - right-bottom：左下方
  - label-vsep：label本身的垂直偏移
  - label-hsep：label本身的水平偏移
  - v-sep：两行选项之间的额外垂直偏移量（通过`\sethlist`接口实现）
  - h-sep：两列选项之间的额外垂直偏移量（通过`\sethlist`接口实现）
  - v-offset：垂直的额外偏移
  - h-offset：水平的整体偏移
  - showanswer：控制答案显示
    - `showanswer`, `showanswer = true`表示显示答案
    - `showanswer = false`表示隐藏答案
  - answer-label-content：答案label的内容，初始值为“【参考答案】”
  - answer-label-color：答案label的颜色，初始值为`violet`

更多细节和示例请阅读[发行版](https://gitee.com/xkwxdyy/xchoices/releases)中的用户手册

## TO-DO

- `NewXChoices`：新建样式
- 显示答案中，答案的连接符设置
## 参与贡献
感谢[zepinglee](https://github.com/zepinglee)在本宏包编写过程中提供的大量建议和帮助！

### Github
issues: https://github.com/xkwxdyy/xchoices/issues

### Gitee
issues: https://gitee.com/xkwxdyy/xchoices/issues
