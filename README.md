# LaTeX-Package: xchoices

A package for flexibly LaTeXing choice items based on hlist environment and coffin.

Github Repository: https://github.com/xkwxdyy/xchoices

Gitee Repository: https://gitee.com/xkwxdyy/xchoices

Author: Kangwei Xia <kangweixia_xdyy@163.com>

## 宏包说明

本宏包为本人前段时间编写的宏包`choices`的重新推翻编写的版本，并增加了许多功能：
（choices宏包仓库：[github](https://github.com/xkwxdyy/xchoices), [gitee](https://gitee.com/xkwxdyy/xchoices)）

### 变更
- 原`\choices`命令更改为`\xchoices`
- 完成基于`hlist`环境的`\xchoices`命令的重写，用法不变，使用`&&`分隔
```tex
\xchoices{
  选项1 &&
  选项2 &&
  选项3 &&
  选项4 &&
  选项5 &&
  选项6 &&
}
```
![](https://raw.githubusercontent.com/xkwxdyy/image/main/postimage/image-hosting/20220129220920.png)
- 更改全局设置接口为`\xchoicesetup`

### 新增
- 新增了选择题的括号命令`\paren`，默认到该行行尾，内容多时自动到下一行行尾
- 增加了代码风格类似于`list`环境的`xchoice`环境，用`\xitem`分隔每一项（由于环境和命令不能重名，所以环境没有加s）
- 基于`xchoice`环境下增加了答案和解析的控制显示，`\xitem*`表示该项为正确答案，支持多选题。示例如下
```tex
\begin{xchoice}[
  analysis-content = {
    It's obvious that D is false, then ...
  }
]
  \xitem* 正确选项
  \xitem  错误选项
  \xitem* 正确选项
  \xitem  错误选项
\end{xchoice}
```
![](https://raw.githubusercontent.com/xkwxdyy/image/main/postimage/image-hosting/20220129202249.png)
- 增加和完善了一系列键值，目前有
  - items：每行排多少个，系统会根据选项宽度自动计算合适值，可用此键值手动干预
  - pre-label：label前的内容，初始为空
  - post-label：label后的内容，初始值为"."
  - label-style：label的样式
    - arabic：阿拉伯数字
    - roman：小写罗马数字
    - Roman：大写罗马数字
    - quan：带圈数字
    - alph：小写英文字母
    - Alph：大写英文字母
    - none：没有label
  - vsep：两行选项之间的额外垂直偏移量（通过`\sethlist`接口实现）
  - hsep：两列选项之间的额外垂直偏移量（通过`\sethlist`接口实现）
  - showanswer：控制答案显示
    - `showanswer`, `showanswer = true`表示显示答案
    - `showanswer = false`表示隐藏答案
  - answer-label-content：答案label的内容，初始值为“【参考答案】”
  - answer-label-color：答案label的颜色，初始值为`violet`
  - showanalysis：控制解析显示
    - `showanalysis`, `showanalysis = true`表示显示解析
    - `showanalysis = false`表示隐藏解析
  - analysis-label-conent：解析label的内容，初始值为“【解析】”
  - analysis-label-color：解析label的颜色，初始值为`violet`

### 未完成
- 可以改变label位置的`\coffinchoice`命令的重写
  - 命令的下方间距
- 增加乱序且答案显示正确的功能

## 参与贡献

### Github
issues: https://github.com/xkwxdyy/xchoices/issues

### Gitee
issues: https://gitee.com/xkwxdyy/xchoices/issues
