---
tags: []
text: 转载至RM_Vision_Library，作者刘与铮
---
# 理解环境基础知识

## 集成开发环境（IDE）

如果您不是第一次接触编程，那么这个词汇应该不会陌生。IDE 是开发者和程序员进行软件设计和开发所需的工具和设施的集合，它提供了一个可以编写和测试代码的环境。

对于 C++开发而言，目前流行的 IDE 包括 JetBrains 的 CLion、微软的 Visual Studio 等。在这里，我们推荐使用微软的开源编辑器 Visual Studio Code（VSCode），通过安装插件，可以实现强大的 IDE 功能。

## 环境变量

环境变量是任何操作系统中都非常重要的概念，无论是 Windows、macOS 还是 Linux。让我们从终端开始简单介绍这个概念。简而言之，当一个应用程序 A 运行依赖于另一个应用程序 B 的某些文件时，比如原神运行依赖于 Visual C++（vc++），我们需要将 vc++的路径添加到环境变量中，以便原神启动器可以找到它（实际上，vc++不需要手动添加到环境变量中，它已经包含在环境变量中）。环境变量就像是一个应用程序的地址簿，一个程序想要运行另一个程序时，可以通过查找这个表来找到它。

# 配置环境

对于 C++开发环境，在 Windows 下，可选择的环境包括 Visual Studio (VS)和 Dev-C++等。然而，VS 使用的编译器是 MSVC，与 Linux 上使用的 GCC 有很大的不同。Dev-C++界面较为简陋，开发效率较低。因此，我们主要介绍 MSYS 2 作为包含 GCC 的工具链，并使用 Visual Studio Code（VSCode）作为代码编辑器进行环境配置。以下是一个不错的配置教程链接：[给初学者的C/C++环境配置指南（VSCode和MSYS2）- 知乎](https://zhuanlan.zhihu.com/p/401188789)

## MSYS 2

### 下载与安装

您可以从官方网站下载 [MSYS2](https://www.msys2.org/)，请注意，安装包下载速度可能较慢，如果有代理，安装速度会更快。

安装过程包括选择安装目录等常规步骤。建议不要选择 C 盘作为安装目录。在安装过程中，勾选"运行 MSYS 2"选项。

![[msys2-UCRT64.png]]

在 Windows 10/11 中，您可以在"设置" > "系统" > "关于" > "高级系统设置" > "环境变量"中：

![[环境变量.png]]

找到系统变量中的 Path：

![[编辑环境变量.png]]

然后将 MSYS 2 的安装路径添加到环境变量中。只需要添加 ucrt 64 的环境变量，如下所示：

![[新建环境变量.png]]

确定后，环境变量就已配置完成。

### 安装编译工具

MSYS 2 本质上是一个编译工具链的管理工具，我们还需要使用它来安装一些工具。

在刚才打开的 ucrt 64 界面中，运行以下命令以更新软件源：`pacman -Syu`，此过程可能会较慢，如果遇到下载速度慢的问题，您可以查找有关在 MSYS 2 中更换国内软件源的相关信息。

然后，输入以下命令来安装编译工具链：`pacman -S mingw-w64-ucrt-x86_64-toolchain`。接下来，安装 Clangd 工具链，输入：`pacman -S mingw-w64-ucrt-x86_64-clang mingw-w64-ucrt-x86_64-clang-tools-extra`。以上安装步骤大约需要 $3 \mathrm{GB}$ 的硬盘空间。

要验证您的安装是否成功，打开终端：

![[WindowsPowerShell.png]]

运行以下命令：`gcc` 和 `clangd`。如果能够看到与下图中类似的输出，说明安装成功，环境变量已生效。

![[验证gcc与clangd.png]]

## CMake

CMake 是一种用于组织 C++项目的工具，它能够实现多个 C++文件的构建，并提高头文件的查找效率。我们未来将使用 CMake 构建项目，特别是在使用 ROS 2 时，因此学习 CMake 是有必要的。

您可以从以下链接下载 CMake：[Download | CMake](https://cmake.org/download/)。请使用 64 位 Windows 安装包。在安装过程中，选择添加环境变量。

![[安装cmake.png]]

要验证 CMake 是否安装成功，打开终端并运行以下命令：cmake。

![[验证cmake.png]]

## Visual Studio Code

为什么将 Visual Studio Code 放在最后呢？因为实际上使用哪个 IDE 并不是非常重要。在未来，我们将花大量时间直接在终端中运行 CMake，所选择的 IDE 只是用来提高开发效率的工具。Visual Studio Code 与记事本之间没有本质区别，它只是带有语法高亮和 CMake 相关插件工具的文本编辑器，这些插件使其具备了 IDE 的功能。如果有人只安装了 Visual Studio Code，并询问为什么无法编写代码，那么我只能说，绝大多数问题可能源于缺少上述配置中所描述的编译工具链。

您可以从官方网站下载 Visual Studio Code：[Visual Studio Code - Code Editing. Redefined](https://code.visualstudio.com/)。推荐使用 System Installer 版本，因为它更容易获得管理员权限。

在安装过程中，选择添加环境变量。

虽然 Visual Studio Code 只是一个文本编辑器，但我们仍然欢迎大家使用它。它强大的插件功能足以支持各种编程语言，可以在大学毕业后继续使用。

点击左侧的四个方块图标以开始安装插件。在搜索栏中键入插件名称，插件会在左侧列出。以下是我们目前需要的插件，它们将显示在左侧列中。其中，Synthwave 是本人个人喜欢的黑色主题，但您可以搜索并选择适合自己喜好的主题。此外，. NET 插件会自动下载一些内容，如果由于网络速度问题下载失败，也不会影响使用。

![[VSCode应用拓展.png]]

然后，打开一个空文件夹并进入，勾选"信任此作者"，进入如下界面：

![[VSCode工作区.png]]

在这里，我们将介绍一下 Visual Studio Code 中 CMake 插件的用法。

按下 `Ctrl+Shift+P`，输入"cmake"，选择"CMake: Quick Start"：

![[VSCode-CMake快速入门.png]]

之后的步骤不再放图片，您需要选择 GCC 13 作为编译器，输入"cmake_test"作为项目名称，创建 C++项目，并创建可执行文件（executable）。最后，将生成一些文件。

![[生成CMakeLists.png]]

其中 CMakeLists 是用于管理 CMake 项目的工具，而 main. cpp 是默认生成的示例代码。关于 CMake 的更多知识，我们将在之后介绍。现在，我们重点是确保能够成功编译。

直接点击下方的"Generate"按钮，您将看到如下结果：

![[CMake编译成功.png]]

三角形符号表示运行，点击后您将看到"Hello"的输出：

![[CMake编译运行.png]]

至此，C++开发和运行环境已基本配置完成，您现在可以在此基础上学习编写 CMake 脚本和掌握 C++语法知识。