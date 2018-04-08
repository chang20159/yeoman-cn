> 原文： http://yeoman.io/learning/index.html



Yeoman是一个可以创建任何类型应用程序的脚手架系统，它可以让我们快速开始新项目，并简化对现有项目的维护。

对语言种类没有限制，可以生成任何语言的项目（Web，Java，Python，C＃等），而创建过程由Yeoman环境中的各种插件来完成。Yeoman有很多公用的生成器，很容易创建一个新的生成器来匹配任何工作流程。

So, Yeoman永远是您搭建脚手架的正确选择。



以下是一些常见用例：

- 快速创建一个新项目
- 创建项目的某个模块，比如带单元测试的controller
- 创建模块或包
- 引导新的服务
- 强制实施标准，最佳做法和风格指南
- 让用户从简单示例开始使用来推广新项目
- 等等



## 开始

`yo`是Yeoman命令行工具，使用yo可以让我们选择脚手架模板创建项目（称为generators）。yo 和 generators都使用[npm](https://www.npmjs.com/)安装。

### 安装yo和generators

首先安装yo

```shell
npm install -g yo
```

然后安装需要的generator(s)，Generators 的 npm包名都是 `generator-XYZ`的形式。在我们的网站上搜索或在运行yo时选择“install a generator”选项。安装webapp生成器：

```shell
npm install -g generator-webapp
```

第一次使用node和npm可能会遇到权限问题，安装过程中会出现`EACCESS`错误提示，如果遇到这种情况，请参考[npm指南](https://docs.npmjs.com/getting-started/fixing-npm-permissions)修复权限问题。



npm是Node.js的包管理器，并与之捆绑在一起。在Windows上，建议使用更好的命令行工具改善体验，如cmder或PowerShell。

### 基本的脚手架

下面使用脚手架generator-webapp来搭建示例项目。执行以下命令：

```bash
yo webapp
```

大多数generator会询问一系列的问题来定制新项目，要查看哪些选项可用，请使用help命令：

```bash
yo webapp --help
```

例如：

```
Example:
    yo generator

    This will create:
        README.md: Description and minimal user instructions
        package.json: Development packages installed by npm

        generator/app/index.js: Main generator script
        generator/app/templates/: Templates for files created by your generator
        test/: Unit tests for your generator
```

许多generator依赖于构建系统（如Grunt或Gulp）以及包管理器（如npm和Bower）。可访问generator的网站了解如何运行和维护新应用，运行以下命令可访问生成器的主页（打开仓库的readme文件）：

```shell
npm home generator-webapp
```

使用Generators搭建复杂的项目框架，可能需要将项目分成多个部分，然后用sub-generators分别搭建，sub-generators通过generator:sub-generator 来访问。



以generator-angular为例，当生成完整的angular app 后，可以通过运行 sub-generator来添加其他部分：

```shell
yo angular:controller MyNewController
```

### 其他yo命令

除了前面介绍的基础知识外，`yo` 也是一个交互式工具。只需在终端中键入 `yo` 将提供一个选项列表，用于管理与生成器相关的所有内容：运行，更新，安装，帮助和其他实用程序。

Yo还提供以下命令:

- `yo --help `    获取帮助
- `yo --generators`  列出已安装的generators
- `yo --version`  获取yo的版本信息



### 故障排除

大多数问题可以通过运行以下命令来查找：

```
yo doctor
```

`doctor` 命令将诊断并提供解决最常见问题的步骤。

### 创建generator

参见 [authoring](http://yeoman.io/authoring/index.html)

