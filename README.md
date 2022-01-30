# LaTeX-Package: xchoices

A package for flexibly LaTeXing choice items based on hlist environment and coffin.

Github Repository: https://github.com/xkwxdyy/xchoices

Gitee Repository: https://gitee.com/xkwxdyy/xchoices

Author: Kangwei Xia <kangweixia_xdyy@163.com>

## 宏包说明

本宏包为本人前段时间编写的宏包`choices`的重新推翻编写的版本，并增加了许多功能：
（choices宏包仓库：[github](https://github.com/xkwxdyy/xchoices), [gitee](https://gitee.com/xkwxdyy/xchoices)）

目前宏包还处于开发测试阶段，接口以及功能等随时可能会进行更改。

### 变更
- `choices`宏包更名为`xchoices`宏包，`x`寓意为`etra`，可以避免与`exam.cls`冲突，并能同时使用
- 更改全局设置接口为`\xchoicesetup`
- 去除了原有的`\choices`命令，而改用新增的`xchoices`与`\choices*`环境

### 新增
- 新增了选择题的括号命令`\paren`，默认到该行行尾，内容多时自动到下一行行尾
- 增加了代码风格类似于`list`环境的`xchoice`环境与`xchoices`环境，用`\item`分隔每一项，使选项分隔结构更清晰
- 基于`xchoice`环境下增加了答案的控制显示，`\item*`表示该项为正确答案，支持多选题。示例如下
```tex
\begin{xchoice}[
  showanswer = true
]
  \xitem* 正确选项
  \xitem  错误选项
  \xitem* 正确选项
  \xitem  错误选项
\end{xchoice}
```

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

### 未完成
- 修改\xitem为\item
- 增加乱序且答案显示正确的功能

## 参与贡献

### Github
issues: https://github.com/xkwxdyy/xchoices/issues

### Gitee
issues: https://gitee.com/xkwxdyy/xchoices/issues
