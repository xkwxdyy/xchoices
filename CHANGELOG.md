## 更新日志
### [Unrelease]
- `\__xchoices_env_determine_show_answer:N`函数，如何实现
```tex
\bool_if:NT \__xchoices_env_show_answer_bool
  { \q_recursion_stop }   % 看上去像停止循环的代码但是实际使用会一直编译不停
```

### [v0.0.1] - 2022-01-29

#### Added

- 新建仓库，增加`CHANGELOG.md`和`xchoices.sty`
- 完成`xchoice`环境的编写
- 完成数据预处理函数的编写
- 完成原`choices`宏包中`hlistchoice`命令的迁移改写
- 在`choices`宏包基础上增加了`hlistchoice`命令的`vsep`和`hsep`的键值设置（通过sethlist接口）
- 完成答案显示与解析控制
- 增加选择题括号命令`\paren`

## 仓库地址

Github：https://github.com/xkwxdyy/xchoices

Gitee：https://gitee.com/xkwxdyy/xchoices

