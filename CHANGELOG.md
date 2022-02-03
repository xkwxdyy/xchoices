# 更新日志
## [Unrelease]
- `\__xchoices_env_determine_show_answer:N`函数，如何实现
```tex
\bool_if:NT \__xchoices_env_show_answer_bool
  { \q_recursion_stop }   % 看上去像停止循环的代码但是实际使用会一直编译不停
```
- 保持答案正常的乱序功能

## [v0.1.1] - 2022-02-03
### Changed
- 修改部分`label-pos`的垂直上方和下方距离

## [v0.1.0] - 2022-02-02
### Changed
- 将`hlist`的设置从`sethlist`改为环境的可选参数
- 去掉`xchoices`环境中`varwidth`环境的`- \leftmargin`

### Removed
- 删去`mode`键值

### Fixed
- 修复标签对齐问题并重新调整不同`label-pos`的参数（[#4](https://github.com/xkwxdyy/xchoices/issues/4)）

## [v0.0.4] - 2022-02-01
### Added
- 上传用户手册
### Changed
- 更新`README.md`的“宏包开发背景”内容
### Fixed
- 修正`README.md`的示例代码和图片问题
- 更改`\paren`名为`\xparen`
- 更新示例文件`xchoices-test.tex`
- 解决基线对齐问题（[#2](https://github.com/xkwxdyy/xchoices/issues/2)）
- 修复不会自动换行的bug（[#3](https://github.com/xkwxdyy/xchoices/issues/3)）
- 修复自动换行后长度的问题（[#3](https://github.com/xkwxdyy/xchoices/issues/3)）

## [v0.0.3] - 2022-01-31
### Added
- 增加`label-style`的chinese值
- chinese的label-style时post-label设置为“、”

### Changed
- 完善a4paper下的`label-pos`参数

### Fixed
- 修复`\item`与`enumerate`环境冲突bug

## [v0.0.2] - 2022-01-30
### Added
- 基本完成`coffinchoice`命令的重写
- 增加插图判断
- 完善`coffinchoice`不同方位的细节调整
- 增加基于coffin的`xchoices*`环境
- 增加环境上下方间距控制

### Changed
- 当`label-pos`为`right`系列时，修改label样式为形如".A"
- `xchoice`环境更名为`xchoices`环境
- 修改`\xitem`为`\item`

### Removed
- 移除`\xchoices`命令，只保留`xchoices`环境（[#I4SKCL](https://gitee.com/xkwxdyy/xchoices/issues/I4SKCL)）
- 去掉环境的“解析”接口
- 合并`xchoices`环境和`xchoices*`环境为`xchoices`环境

### Fixed
- 修复`xchoice`环境的垂直位移偏差bug

## [v0.0.1] - 2022-01-29

### Added

- 新建仓库，增加`CHANGELOG.md`和`xchoices.sty`
- 完成`xchoice`环境的编写
- 完成数据预处理函数的编写
- 完成原`choices`宏包中`hlistchoice`命令的迁移改写
- 在`choices`宏包基础上增加了`hlistchoice`命令的`vsep`和`hsep`的键值设置（通过sethlist接口）
- 完成答案显示与解析控制
- 增加选择题括号命令`\paren`

### Changed
- 重新修订`README.md`文件

## 仓库地址

Github：https://github.com/xkwxdyy/xchoices

Gitee：https://gitee.com/xkwxdyy/xchoices

