# 第一次使用Git：先设置身份，再检查配置

安装好Git后，先告诉它提交记录该署谁的名字。下面是原文示例，执行时把姓名、邮箱换成自己的：

```bash
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

这两项会写进以后创建的提交。`--global`表示当前用户的设置，通常在这台电脑上设一次即可，升级后仍保留。某个项目需要另一套身份时，在该仓库内去掉`--global`重新设置。

Git还可以配置编辑器；不设置时使用系统默认编辑器。新仓库的初始分支名，则可在Git 2.28及以后设置：

```bash
git config --global init.defaultBranch main
```

最后查看配置及来源：

```bash
git config --list --show-origin
```

看到同名设置出现多次，不一定是出错。配置分系统、当前用户和当前仓库三个层级，仓库设置会覆盖更宽范围的设置。要确认当前生效的姓名，可以运行`git config user.name`。

本文为本轮约400字精简重构，保留身份、作用范围、分支名与检查方法；编辑器的具体配置和Windows路径请对照原文，不代替全篇操作详解。这里只展示命令，未实际执行。

来源：[Pro Git第二版：First-Time Git Setup](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)。
