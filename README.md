# Introduction
### 1.安装 gitbool-cli
```node
    $ gitbook -V
    CLI version: 2.3.2
    GitBook version: 3.2.3
```
更多详情请参照 [GitBook 安装文档](https://link.juejin.im/?target=https%3A%2F%2Fgithub.com%2FGitbookIO%2Fgitbook%2Fblob%2Fmaster%2Fdocs%2Fsetup.md) 来安装 GitBook。
### 2.初始化目录
```node
    $ gitbook init
    warn: no summary file in this book
    info: create README.md
    info: create SUMMARY.md
    info: initialization is finished

```
### 3.编译build
```
    $ gitbook build
```
运行该命令后会在书籍的文件夹中生成一个 _book 文件夹, 里面的内容即为生成的 html 文件，我们可以使用下面命令来生成网页而不开启服务器。
### 目录结构
GitBook 基本的目录结构如下所示：
```
    .
    ├── book.json
    ├── README.md
    ├── SUMMARY.md
    ├── chapter-1/
    |   ├── README.md
    |   └── something.md
    └── chapter-2/
        ├── README.md
        └── something.md

```
### 4.启动运行
```
    $ gitbook serve
```
运行该命令，然后在浏览器地址栏中输入 http://localhost:4000 便可预览书籍。

### 5.其他
#### gitbook插件
GitBook 有 [插件官网](https://link.juejin.im/?target=https%3A%2F%2Fplugins.gitbook.com%2F)，默认带有 5 个插件，highlight、search、sharing、font-settings、livereload，如果要去除自带的插件， 可以在插件名称前面加 -，比如：
```
    "plugins": [
        "-search"
    ]
```
如果要配置使用的插件可以在 book.json 文件中加入即可，比如我们添加 plugin-github，我们在 book.json 中加入配置如下即可：
```$xslt
    {
        "plugins": [ "github" ],
        "pluginsConfig": {
            "github": {
                "url": "https://github.com/your/repo"
            }
        }
    }
```
然后在终端输入 gitbook install ./ 即可。

如果要指定插件的版本可以使用 plugin@0.3.1，因为一些插件可能不会随着 GitBook 版本的升级而升级。