> https://github.com/muwenzi/Program-Blog/issues/129

[Visual Studio Code](https://code.visualstudio.com/) 是我用起来最顺手方便和强大的`文本编辑器`，可以配合 IDAE 系列进行愉快的 coding。

一般稍大的工程项目我会用 IDAE 系列，而快速地看 github 上别人库，跑别人代码，写一个代码小片段，运行一段小程序，我通常会选择 `VS Code`。

小巧，强大，插件丰富，界面也很优雅，可定制化程度也很高，大厂支持。更新非常快速，基本上每月一更，[insiders](https://code.visualstudio.com/insiders/) 版更是每日更新。别的就不多说，这里给大家推荐一些比较不错实用的插件。

## 分类概览

- Markdown
  - [markdownlint](#markdownlint)
  - [Markdown Preview Github Styling](#markdown-preview-github-styling)
  - [Markdown Emoji](#markdown-emoji)
  - [Markdown TOC](#markdown-toc)
- Code Style
  - [ESLint](#eslint)
  - [TSLint](#tslint)
  - [Prettier](#prettier)
  - [Code Spell Checker](#code-spell-checker)
- Language Support
  - [Babel ES6/ES7](#babel-es6-es7)
  - [Code Runner](#code-runner)
- Tips
  - [explorer 区文件颜色](#explorer-file-color)

## Markdown

> :warning: 目前用 vscode 开预览模式 写 markdown 的时候会出现一堆不可识别字符的 bug，详情参考这篇文章 [vscode 控制字符引起的问题以及解决思路](https://wdd.js.org/vscode-control-characters-problem.html)

<h3 id="markdownlint">markdownlint</h3>

> 规范你的 markdown 写法，适合于有强迫症的程序员

<h3 id="markdown-preview-github-styling">Markdown Preview Github Styling</h3>

> 装上这个插件，基本可以模仿 github 上页面写 markdown 的样子，非常赞的插件，写 github markdown 必备。

<h3 id="markdown-emoji">Markdown Emoji</h3>

> 使用 `:emoji:` 语法即可在 markdown 里面加入 emoji 标签，preview 的时候即可见，搭配 `Markdown Preview Github Styling` 插件更赞。

<h3 id="markdown-toc">Markdown TOC</h3>

> 按照 markdown 语法自动生成目录，右击选择 `Markdown Sections: Insert/Update` 会自动更新标题前面的编号，再 `cmd + s` 的时候会自动更新目录。github 语法可用，但 issue 中无效，wiki 有效。

## Code Style

<h3 id="eslint">ESLint</h3>

> 你在编写代码的时候，利用这个软件可以轻易获取有关漏洞的提示，而且在编码过程中，它还可以帮助你养成良好的编码习惯。

<h3 id="tslint">TSLint</h3>

> 有了 ESLint，当然也少不了 TSLint

<h3 id="prettier">Prettier</h3>

> 自动代码格式化程序。忘掉那些你不得不手动缩进代码的日子吧，有了这个工具，事情就变得简单多啦。这个程序会比你自己做得更快更好。还有一个类似的`Beautify`，也挺火的。

<h3 id="code-spell-checker">Code Spell Checker</h3>

> 这一工具正如其名，是检查程序拼写。Bug 的另一个常见来源是变量或函数名。这一拼写检查工具可以查找不常见的单词，而且还可以把我们用 JS 编写的东西进行有效的审核。

## Language Support

<h3 id="babel-es6-es7">Babel ES6/ES7</h3>

> JavaScript Babel 的辅助工具。如果你用的是 Babel，这个工具可以让你更容易区分代码。如果你喜欢 JavaScript，那务必也不要错过这款插件。

<h3 id="code-runner">Code Runner</h3>

> 可以快速地运行一段代码片段，支持的语言有: C, C++, Java, JavaScript, PHP, Python, Perl, Perl 6, Ruby, Go, Lua, Groovy, PowerShell, BAT/CMD, BASH/SH, F# Script, F# (.NET Core), C# Script, C# (.NET Core), VBScript, TypeScript, CoffeeScript, Scala, Swift, Julia, Crystal, OCaml Script, R, AppleScript, Elixir, Visual Basic .NET, Clojure, Haxe, Objective-C, Rust, Racket, AutoHotkey, AutoIt, Kotlin, Dart, Free Pascal, Haskell, Nim, D。

目前发现跑 Java 代码的时候中文会出现乱码，Github 上已经有人提出这个问题了，目前作者推荐的临时解决方案是运行时候强制用 VS 自带的控制台去查看：

```json
"code-runner.executorMap": {
  "java": "cd $dir && javac -encoding utf-8 $fileName && java $fileNameWithoutExt"
},
"code-runner.runInTerminal": true
```

## Tips

<h3 id="explorer-file-color">explorer区文件颜色</h3>

VSCode 的版本控制系统会自动识别文件的改动给文件加颜色、文件名后面显示`M`（modify）、`U`（untracked）、`A`（add）和显示错误和警告的数量，就像下图这样：

<img width="318" alt="image" src="https://user-images.githubusercontent.com/12554487/41210381-dbf40f60-6d63-11e8-8cba-dd219e392575.png">

有些文件明明没有改动，文件名有时候却也变成绿色，其实是里面有一些错误或者警告而已。

```json
// Show Errors & Warnings on files and folder.
"problems.decorations.enabled": true,
```

把 `true` 改成 `false`，即可将文件名和文件夹名后面的错误警告数量去掉（如+9），且文件名的颜色也回归 git 本身的颜色，现在颜色的变化只有 git，更加容易辨识哪些文件发生了改动。

几个相关的配置说明：

```json
// git文件改动，文件名后面的U/M等是否显示，默认true
"git.decorations.enabled": true,
// git或者错误警告文件名是否用颜色标识，默认true
"explorer.decorations.colors": true,
// 文件名或者文件夹名后面是否显示Errors & Warnings的数量，默认true
"problems.decorations.enabled": false
```

<img width="318" alt="image" src="https://user-images.githubusercontent.com/12554487/41210327-95c6f85e-6d63-11e8-8516-d0e8894a7ea4.png">
