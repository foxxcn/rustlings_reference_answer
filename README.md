### [ForkBy](https://github.com/rust-lang/rustlings)

<div class="oranda-hide">

# rustlings 🦀❤️

</div>

欢迎来到 `rustlings`。这个项目包含一些小练习，帮助你习惯阅读和编写Rust代码。这包括阅读和响应编译器消息！

_...在找旧版基于网络的Rustlings吗？试试[这里](https://github.com/rust-lang/rustlings/tree/rustlings-1)_

另外，对于第一次学习Rust的用户，还有其他一些资源：

- [The Book](https://doc.rust-lang.org/book/index.html) - 学习Rust最全面的资源，但有时比较理论化。你将和Rustlings一起使用它！
- [Rust By Example](https://doc.rust-lang.org/rust-by-example/index.html) - 通过解决小练习来学习Rust！它几乎像`rustlings`，但在线。

## 入门

_注意：如果你使用的是MacOS，请确保你已通过输入`xcode-select --install`安装了Xcode及其开发者工具。_
_注意：如果你使用的是Linux，请确保你已安装gcc。Deb: `sudo apt install gcc`。Yum: `sudo yum -y install gcc`。_

你需要安装Rust。你可以访问 <https://rustup.rs> 获取它。这也会安装Cargo，Rust的包/项目管理器。

## MacOS/Linux

运行：

```bash
curl -L https://raw.githubusercontent.com/rust-lang/rustlings/main/install.sh | bash
```

或者如果你想安装到不同的路径：

```bash
curl -L https://raw.githubusercontent.com/rust-lang/rustlings/main/install.sh | bash -s mypath/
```

这将安装Rustlings并让你可以使用`rustlings`命令。运行它以开始！

### Nix

基本上：克隆最新标签的仓库，然后运行`nix develop`或`nix-shell`。

```bash
# 在 https://github.com/rust-lang/rustlings/releases/latest 找到最新版本（编辑时为5.6.1）
git clone -b 5.6.1 --depth 1 https://github.com/rust-lang/rustlings
cd rustlings
# 如果 nix 版本 > 2.3
nix develop
# 如果 nix 版本 <= 2.3
nix-shell
```

## Windows

在PowerShell中（以管理员身份运行），将`ExecutionPolicy`设置为`RemoteSigned`：

```ps1
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

然后，你可以运行：

```ps1
Start-BitsTransfer -Source https://raw.githubusercontent.com/rust-lang/rustlings/main/install.ps1 -Destination $env:TMP/install_rustlings.ps1; Unblock-File $env:TMP/install_rustlings.ps1; Invoke-Expression $env:TMP/install_rustlings.ps1
```

以安装Rustlings。与在MacOS/Linux上相同，之后你将可以使用`rustlings`命令。请注意，这在PowerShell中效果最好，其他终端可能会给你带来错误。

如果你收到权限被拒绝的消息，你可能需要在杀毒软件中排除克隆Rustlings的目录。

## 浏览器

[![在Gitpod中打开](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/rust-lang/rustlings)

[![在Codespaces中打开Rustlings](https://github.com/codespaces/badge.svg)](https://github.com/codespaces/new/?repo=rust-lang%2Frustlings&ref=main)

## 手动

基本上：克隆最新标签的仓库，运行`cargo install --path .`。

```bash
# 在 https://github.com/rust-lang/rustlings/releases/latest 找到最新版本（编辑时为5.6.1）
git clone -b 5.6.1 --depth 1 https://github.com/rust-lang/rustlings
cd rustlings
cargo install --force --path .
```

如果有安装错误，确保你的工具链是最新的。要获取最新版本，运行：

```bash
rustup update
```

然后，和上面一样，运行`rustlings`以开始。

## 做练习

这些练习按主题分类，可以在子目录`rustlings/exercises/<topic>`中找到。每个主题都有一个附加的README文件，其中包含一些帮助你入门该主题的资源。我们强烈建议你在开始之前看看它们。

任务很简单。大多数练习包含一个阻止它们编译的错误，你需要修复它！一些练习也作为测试运行，但rustlings处理它们的方式是相同的。要按推荐顺序运行练习，执行：

```bash
rustlings watch
```

这将尝试按预定顺序验证每个练习的完成情况（我们认为这是新手的最佳顺序）。每次你更改`exercises/`目录中的文件时，它也会自动重新运行。如果你只想运行一次，可以使用：

```bash
rustlings verify
```

这将与watch相同，但它将在运行后退出。

如果你想按自己的顺序进行，或只想验证单个练习，可以运行：

```bash
rustlings run myExercise1
```

或者简单地使用以下命令运行课程中的下一个未解决的练习：

```bash
rustlings run next
```

如果你卡住了，可以运行以下命令获取练习的提示：

```bash
rustlings hint myExercise1
```

你也可以使用以下命令获取下一个未解决练习的提示：

```bash
rustlings hint next
```

要检查你的进度，可以运行以下命令：

```bash
rustlings list
```

## 测试自己

每隔几节课会有一个测验，测试你对多个章节的知识。这些测验可以在`exercises/quizN.rs`中找到。

## 启用`rust-analyzer`

运行命令`rustlings lsp`，这将在项目根目录生成一个`rust-project.json`，这允许[rust-analyzer](https://rust-analyzer.github.io/)解析每个练习。

## 继续学习

完成Rustlings后，利用你的新知识！继续通过构建自己的项目、为Rustlings做贡献或寻找其他开源项目来贡献代码来练习你的Rust技能。

## 卸载Rustlings

如果你想从系统中删除Rustlings，有两个步骤。首先，你需要删除安装脚本为你创建的练习文件夹：

```bash
rm -rf rustlings # 或你的自定义文件夹名，如果你选择并/或重命名了它
```

其次，运行`cargo uninstall`以移除`rustlings`二进制文件：

```bash
cargo uninstall rustlings
```

现在你应该完成了！

## 贡献

请参阅 [CONTRIBUTING.md](https://github.com/rust-lang/rustlings/blob/main/CONTRIBUTING.md)。

## 贡献者 ✨

感谢列在 [AUTHORS.md](https://github.com/rust-lang/rustlings/blob/main/AUTHORS.md) 中的精彩人士 🎉