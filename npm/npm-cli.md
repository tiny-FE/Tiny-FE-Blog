# 如何发布alpha(α)预览版/内部测试版
## 什么时候需要：
当刚开发完成需要提测时，一般发布alpha版本
## 怎么发：
场景一：在非alpha版本上第一次发alpha版本时，运行npm version prerelease --preid=alpha

场景二：在alpha版本上发布可以省略--preid=alpha，直接运行npm version prerelease即可

**以上就是如何发布alpha(α)预览版的命令了，下面是一些示例**
## 示例：
示例一：第一次运行npm version prerelease --preid=alpha时，会将版本号的修订号patch+1，同时prerelease号设置为alpha.0；

示例二：再次运行时，则将预发布号prerelease+1；

示例三：再运行npm version patch时，patch号不变，去掉prerelease号
```js
// $后面的命令表示输入命令(不用输入$)，$下一行表示输出
// 前置：先运行npm ls查看下当前包的版本
$ npm ls
xxx@1.0.4
// 示例一 patch+1 prerelease为alpha.0
$ npm version prerelease --preid=alpha
v1.0.5-alpha.0
// 示例二 prerelease+1
$ npm version prerelease
v1.0.5-alpha.1
// 示例三 去掉prerelease
$ npm version patch
v1.0.5
```

## 后言：
1. npm version prerelease --preid=alpha中的preid顾名思义是前置标识符的意思，可以不传，alpha.0就变成了0；也可以传beta或rc等
2. 如果在git项目中，运行npm version xxx命令会自动生成一个commit和tag，所以在推送代码时除了git push之外，还可以运行git push --tags将自动生成的tag进行推送。如果不需要自动生成，可以通过npm --no-git-tag-version version来禁用这个功能。以下引用来自npm cli官网
> If run in a git repo, it will also create a version commit and tag. This behavior is controlled by git-tag-version (see below), and can be disabled on the command line by running npm --no-git-tag-version version

更多详细解释请参考以下文档

掘金博客：[https://juejin.im/post/5d08d3d3f265da1b7e103a4d](https://juejin.im/post/5d08d3d3f265da1b7e103a4d)

npm cli官网：[https://docs.npmjs.com/cli/version.html](https://docs.npmjs.com/cli/version.html)