# Rust 程序设计语言

![Build Status](https://github.com/rust-lang-cn/book-cn/workflows/CI/badge.svg)

> Chinese translation of [The Rust Programming Language][github-en]  
> 鉴于目前网上的中文版已经滞后英文内容，所以重新开启本书翻译，跟进原书。

[github-en]: https://github.com/rust-lang/book

[可以从 No Starch Press 购买本书英文版][nostarch]。

中文译版注：

1. 中文出版书名为《Rust 权威指南》，可以在中文线上或线下购书平台购买。
2. 出版的版本翻译独立于本仓库翻译。

[nostarch]: https://nostarch.com/rust

在线上可以[阅读中文版][book-cn]或[阅读英文版][book-en]。另外英文版在线阅读可以选择 [stable]、[beta] 和 [nightly] 三个不同的分支版本，这几个分支版本可能滞后于[英文仓库]的最新内容。

[book-cn]: https://rustwiki.org/zh-CN/book
[book-en]: https://doc.rust-lang.org/book/
[stable]: https://doc.rust-lang.org/stable/book/
[beta]: https://doc.rust-lang.org/beta/book/
[nightly]: https://doc.rust-lang.org/nightly/book/

## 依赖

构建这本书需要 [mdBook] 。执行以下命令安装：

[mdBook]: https://github.com/azerupi/mdBook

```bash
$ cargo install mdbook
```

或指定安装版本：

```bash
$ cargo install mdbook --vers [version-num]
```

## 构建

构建此书，请输入：

```
$ mdbook build
```

输出内容存放在 `book` 子目录中。可使用浏览器打开来查看内容。

_Firefox:_
```bash
$ firefox book/index.html                       # Linux
$ open -a "Firefox" book/index.html             # OS X
$ Start-Process "firefox.exe" .\book\index.html # Windows (PowerShell)
$ start firefox.exe .\book\index.html           # Windows (Cmd)
```

_Chrome:_
```bash
$ google-chrome book/index.html                 # Linux
$ open -a "Google Chrome" book/index.html       # OS X
$ Start-Process "chrome.exe" .\book\index.html  # Windows (PowerShell)
$ start chrome.exe .\book\index.html            # Windows (Cmd)
```

To run the tests:

```bash
$ mdbook test
```

运行测试:

```
$ mdbook test
```

## 参与贡献

您的帮助，我们将感激不尽(We'd love your help)！请参见 [CONTRIBUTING.md][contrib-cn]（英文原项目参与贡献指引 [CONTRIBUTING-EN.md][contrib]）。

[contrib-cn]: https://github.com/rust-lang-cn/book-cn/blob/master/CONTRIBUTING.md
[contrib]: https://github.com/rust-lang/book/blob/master/CONTRIBUTING.md

## Graphviz dot

> 译注：Graphviz 是一种图形绘制工具，使用 dot 语言来编写绘制

这主要是给 Carol 参考的，因为她不得不检查这些内容（原文：This is mostly for Carol's reference because she keeps having to look it up）。

我们使用 [Graphviz](http://graphviz.org/) 来绘制一些书中需要的图表。这些文件的源文件位于 `dot` 目录中。要将 `dot` 文件转换成 `svg` 文件，如转换 `dot/trpl04-01.dot` 文件，运行：

```
$ dot dot/trpl04-01.dot -Tsvg > src/img/trpl04-01.svg
```

在生成的 SVG 中，从 `svg` 元素中删除了宽度和高度属性，并将 `viewBox` 属性设置成 `0.00 0.00 1000.00 1000.00` 或其他不会截断图像的值。

## 拼写检查（仅对英文检查起作用）

要扫描源文件的拼写错误，可以使用 `spellcheck.sh` 脚本。这需要一个带有有效单词的字典文件，由 `dictionary.txt` 提供。如果脚本产生了一个假阳性（比如说，你使用了 `BTreeMap` 单词，但脚本认为无效），就需要将这个单词添加到 `dictionary.txt` 文件（保持排序的顺序以确保一致性）。

## 将 Windows 换行符转换为 Unix 的

这主要是给 Carol 参考，因为她不得不检查不规范的换行符。（原文：This is mostly for Carol's reference because she keeps having to look it up.）

```
$ tr -d '\015' < DOS-file > UNIX-file
```


## 翻译

我们很乐意翻译这本书！请参阅[“翻译”][Translations]标签（在[英文原仓库][github-en]）以加入当前正在进行的工作。新建一个 Issue，开始使用新语言！在我们合并任何内容之前，我们正在等待 [mdbook 对多种语言的支持][mdbook support]，只要支持后将随时可以开始！

[github-en]: https://github.com/rust-lang/book
[Translations]: https://github.com/rust-lang/book/issues?q=is%3Aopen+is%3Aissue+label%3ATranslations
[mdbook support]: https://github.com/rust-lang-nursery/mdBook/issues/5

## 拼写检查

要扫描源文件是否存在拼写错误，可以使用 `ci` 目录中的脚本 `spellcheck.sh`。这需要一个有效词词典，该词典为 `ci/dictionary.txt`。如果脚本产生误报（例如，使用了词语 `BTreeMap` 被脚本认为无效），则需要在 `ci/dictionary.txt` 中添加该单词（保持排序顺序以保持一致性）。