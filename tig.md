<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Mac 下 `tig` 常用命令](#mac-%e4%b8%8b-tig-%e5%b8%b8%e7%94%a8%e5%91%bd%e4%bb%a4)
    - [Tig 进入 tig 模式](#tig-%e8%bf%9b%e5%85%a5-tig-%e6%a8%a1%e5%bc%8f)
    - [只关注某个文件夹的修改记录](#%e5%8f%aa%e5%85%b3%e6%b3%a8%e6%9f%90%e4%b8%aa%e6%96%87%e4%bb%b6%e5%a4%b9%e7%9a%84%e4%bf%ae%e6%94%b9%e8%ae%b0%e5%bd%95)
    - [展示某一段时间的 commit 记录](#%e5%b1%95%e7%a4%ba%e6%9f%90%e4%b8%80%e6%ae%b5%e6%97%b6%e9%97%b4%e7%9a%84-commit-%e8%ae%b0%e5%bd%95)
    - [显示存储库活动日志](#%e6%98%be%e7%a4%ba%e5%ad%98%e5%82%a8%e5%ba%93%e6%b4%bb%e5%8a%a8%e6%97%a5%e5%bf%97)
    - [查看某次 `commit` 的所有修改](#%e6%9f%a5%e7%9c%8b%e6%9f%90%e6%ac%a1-commit-%e7%9a%84%e6%89%80%e6%9c%89%e4%bf%ae%e6%94%b9)
    - [查看最近一次提交的详细修改](#%e6%9f%a5%e7%9c%8b%e6%9c%80%e8%bf%91%e4%b8%80%e6%ac%a1%e6%8f%90%e4%ba%a4%e7%9a%84%e8%af%a6%e7%bb%86%e4%bf%ae%e6%94%b9)
    - [查看某个文件所有历史修改](#%e6%9f%a5%e7%9c%8b%e6%9f%90%e4%b8%aa%e6%96%87%e4%bb%b6%e6%89%80%e6%9c%89%e5%8e%86%e5%8f%b2%e4%bf%ae%e6%94%b9)
    - [在 `git` 存储库中搜索](#%e5%9c%a8-git-%e5%ad%98%e5%82%a8%e5%ba%93%e4%b8%ad%e6%90%9c%e7%b4%a2)
    - [显示 `git` 存储库状态](#%e6%98%be%e7%a4%ba-git-%e5%ad%98%e5%82%a8%e5%ba%93%e7%8a%b6%e6%80%81)
    - [查看帮助](#%e6%9f%a5%e7%9c%8b%e5%b8%ae%e5%8a%a9)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Mac 下 `tig` 常用命令

[tig — 让 git 命令行可视化](https://juejin.im/post/5afabcb1f265da0b886d92b6)

[Tig: text-mode interface for Git](https://jonas.github.io/tig/)

### Tig 进入 tig 模式

在分屏状态下，使用 Tab 切换左右屏幕，也可以在选中右侧屏幕时，按住 【 shift 】上下切换操作效果会在左侧屏幕生效。

```js
tig

// 此时展现在面前的将会是本地所有的 commit 记录以及分支的演化。

// j/k: 下/上移动

// enter: 可分屏查看当前 commit 记录详情

// l: 全屏查看 commit 记录

// r: 进入 refs view 模式，查看所有分支，使用 【 j/k 】上下切换， 【 Enter 】查看分支演化

// s: 进入 status view，效果同 git status 命令，会展示所有 Untracked 和 UnStaged 文件。 选中 Unstaged 的文件键入【 u 】效果同 git add ，选中 staged 的文件键入 【 u 】效果同 git reset，即撤销 add 操作。【 Enter 】查看分屏查看当前文件的修改记录。status view 模式下键入 【 C 】进入 vim 编辑器，【 i 】进入编辑模式，在第一行输入 commit 信息，【 :x 】退出并保存。【 m 】查看 commit 记录。

// c: 进入 stash view 模式，全屏查看修改记录，可配合 【 s 】 使用。

// t: 进入 tree view 模式，git 目录会以文件夹的形式展示。【 Enter】进入子目录，【 , 】返回上一级目录。

// m: 进入 main view 查看当前分支的所有 commit 记录，使用 【 j/k 】上下切换，【 回车 】可分屏查看 commit 详情。同样，【 j/k 】上下移动，【空格】翻页。

// t: 进入 tree view 模式，git 目录会以文件夹的形式展示。【 Enter】进入子目录，【 , 】返回上一级目录。

// m: 进入 main view 查看当前分支的所有 commit 记录，使用 【 j/k 】上下切换，【 回车 】可分屏查看 commit 详情。同样，【 j/k 】上下移动，【空格】翻页。main view 可以认为是主页。

// /: 输入关键字可进行搜索。

// R: 刷新当前页面，可退出搜索的高亮状态。

// Q: 退出 tig。

// h: 查看快捷键帮助。

// q: 退出当前。
```

### 只关注某个文件夹的修改记录

tig 可以设置作用域，如果只想关注某个文件夹的修改记录，可使用 【 tig 文件夹名】。

### 展示某一段时间的 commit 记录

如果只想展示某一段时间的 commit 记录， tig --after=“2018-01-01 --before="2018-05-12”。如果希望不写引号，可以使用tig --after==May.10th`。

### 显示存储库活动日志

```js
tig log
```

### 查看某次 `commit` 的所有修改

```js
tig show [commit version]
```

### 查看最近一次提交的详细修改

```js
tig show commits
```

### 查看某个文件所有历史修改

```js
tig [filename]
```

### 在 `git` 存储库中搜索

```js
tig grep [query]
```

### 显示 `git` 存储库状态

```js
tig status
```

### 查看帮助

```js
tig -h
```