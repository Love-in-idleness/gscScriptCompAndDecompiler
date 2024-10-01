# gscScriptCompAndDecompiler
## 下面主要是原来的帮助文档，文末则是利用本程序进行游戏汉化的指南

Tool for decompiling, compiling and rebuilding scripts .gsc from the visual novel's engine codeX RScript (also known as Liar-soft Engine or raiL-soft Engine).

用于对galgame引擎 codeX RScript（也称为 Liar-soft Engine 或 raiL-soft Engine）的脚本gsc进行反编译、编译和重建脚本的工具。 

The tool supports two GUI languages: English and Chinese.

该工具支持两种 GUI 语言：中文和英语。

There was some tools for the formats ealier, but it was always simple string dumpers. Sometime with an additional functionality.

也有其他工具可以处理这种gsc格式，但都是简单的字符串转储器，部分还带有附加功能。

Tested on:
- [Kusarihime \~Euthanasia\~](https://vndb.org/v37) <for the most part>
- [Sekien no Inganock -What a Beautiful People-](https://vndb.org/v417) <for the most part>
- [Hiragumo-chan -Sengoku Gekokujou Monogatari-](https://vndb.org/v10182) <for the some part>
- [Dungeons & Daimeiwaku -Great Edges in the Abyss-](https://vndb.org/v19579) <for the some part>
- [Alpha-Nighthawk](https://vndb.org/v24470) <for the some part>
- [Albatross Log](https://vndb.org/v3883) <for the most part>
- [Beta-Sixdouze Trial](https://vndb.org/r73649) <for the some part>
- [Kusarihime ~jamais vu~](https://vndb.org/v28009) <fail>

已测试：
- [腐姬](https://bangumi.tv/subject/1012) <绝大部分>
- [赫炎的印加诺克](https://bangumi.tv/subject/7942) <绝大部分>
- [战国下克上物语](https://bangumi.tv/subject/41059) <一部分>
- [大迷宮＆大迷惑](https://bangumi.tv/subject/185496) <一部分>
- [阿尔法夜莺](https://bangumi.tv/subject/263799) <一部分>
- [信天翁航海录](https://bangumi.tv/subject/13445) <绝大部分>
- [BETA-SIXDOUZE](https://bangumi.tv/subject/306850) <一部分>
- [腐姬归省](https://bangumi.tv/subject/302417) <失败>

Uncomplete game's on the engine list you can see on [here](https://vndb.org/r?fil=engine-codeX_01RScript).

此引擎上的不完整游戏列表可以查看 [此处](https://vndb.org/r?fil=engine-codeX_01RScript)。

For edition of the engine's archieves (.xfl), canvases (.lwg) and images (.wcg) use either [RailTools](https://github.com/EusthEnoptEron/RaiLTools) or [GARbro](https://github.com/morkt/GARbro) (the latter don't suit for canvases editing).

要修改引擎档案（.xfl）、画布（.lwg）和图片（.wcg），请使用 [RailTools](https://github.com/EusthEnoptEron/RaiLTools) 或 [GARbro](https://github.com/morkt/GARbro)（后者不适合编辑画布）。

# Common / 程序介绍

This program was developed for correctly working with .gsc files of the engine codeX Rscript, which also called as Liar-soft Engine and raiL-soft Engine. The engine is rather simple much like it's formats, for example .gsc, with which through may be some problematic moments. Still the moments are ceasing by the specific decompile and compile. But the scheme can also cause problems it some situations.

This program allow you to:
1. Rebuild .gsc-files from themselves so you can optimize them, for in many of .gsc-files there may be some trash elements. For example some number of zeros in the end. But this command is not garantee that all trash elements will be removed. This command also allow you to see .gsc-file's parametrs and unknown commands. It may be useful for code analysis.\2. .gsc to .ini decomple. It allow you to edit scripts as you like (with limitations of syntax, of course). For example, with this tool you can easily add new message.
3. .ini to .gsc compile. This allow you to rebuild .gsc from decompiled and may be edited ealier code. It doesn't need an ealier .gsc to present for run.

For usage:
1. Drag the .gsc script or .ini with decompiled data to the tool directory.
2. Write the file name in the tool entry and push the "DEFINE".
3. Use the commands below.

该程序旨在正确处理 codeX RScript 引擎（也称为 Liar-soft Engine 和 raiL-soft Engine）的 .gsc 文件。该引擎相对简单，其格式（尤其是 .gsc）也相对简单，但是，存在一些问题元素，会导致运行方案停止。因此，在某些情况下，程序会出现问题。

该程序允许您：
1. 从文件本身重新生成 .gsc 文件，从而从根本上对其进行优化，因为一些 .gsc 文件可能包含一些垃圾元素，特别是文件末尾的残余零。不过，并不是所有垃圾元素都会被清除。您还可以通过它查看 .gsc 参数和未知命令的进程，这在分析代码时非常有用。
2. 将gsc反编译为ini，这样就可以随心所欲地编辑脚本（在语法、命令和其他方面的限制范围内）。例如，使用该功能可以轻松添加新信息。
3. 将ini编译成gsc。这允许您重建gsc。该命令不需要旧的gsc脚本。

使用方法：
1. 将 .gsc 脚本或包含反编译数据的 .ini 文件放到工具目录中。
2. 在输入字段中输入名字，然后单击“选定文件”。
3. 使用来自下面的命令。

# Commands / 命令含义

Unfortunately, the number of known commands aren't big (but not of the structures). It may change it the future. All known commands are defined in decomilated file as a string.

Well, let's show you a basic known commands with the arguments:

遗憾的是，能了解的元素含义很少（不了解他们的结构），他们的论点就更少了。不过，这种情况将来可能会改变。文件中的每个已知命令都用字符串标注。

下面是已知的带有参数的基本命令：

- 3 (0x03): JUMP_UNLESS.  
Arguments: [label].   
(In the original script offset from the beginning of command block)   
（在脚本中，偏移量是相对于 command 部分的开头的）  
- 5 (0x05): JUMP.  
Arguments: [label].    
(In the original script offset from the beginning of command block)   
（在脚本中，偏移量是相对于 command 部分的开头的）  
- 12 (0x0C): CALL_SCRIPT.  
Arguments: [script number, ???].     
- 13 (0x0D): PAUSE.  
Arguments: [time in seconds].  
- 14 (0x0E): CHOICE:  
Arguments: [variant's number, -1, label1, label2, label3, label4, label5, -1, -1, -1, -1, -1, ???, ???, ???].  
In the original script is not -1, but choice's strings.  
在脚本中，有时会以选项的字符串开头，而不是以 -1 开头。  
- 20 (0x14): IMAGE_GET.  
Arguments: [image index (from the name), ???].  
- 26 (0x1A): IMAGE_SET.  
Arguments: [].  
- 28 (0x1C): BLEND_IMG.  
Arguments: [???, type1, type2].  
- 30 (0x1E): IMAGE_DEF.  
Arguments: [???, ???, ???, ???, ???, ???].  
- 81 (0x51): MESSAGE.  
Arguments: [???, voice index (from the name), ???, -1, -1, ???].  
In a .gsc itself is not a -1, but a string numbers.  
在gsc中，它本身不是-1，而是一个字符串。  
- 82 (0x52): APPEND_MESSAGE.  
Arguments: [???, ???, ???, ???, -1, ???].  
In a .gsc itself is not a -1, but a string numbers.  
在gsc中，它本身不是-1，而是一个字符串。  
- 83 (0x53): CLEAR_MESSAGE_WINDOW.  
Arguments: [???].  
- 121 (0x79): GET_DIRECTORY.  
Arguments: [???, -1].  
In a .gsc itself is not a -1, but a string numbers.  
在gsc中，它本身不是-1，而是一个字符串。  
- 200 (0xC8): READ_SCENARIO.  
Arguments: [label, ???, ???, ???, ???, ???, ???, ???, ???, ???, ???].  
- 255 (0xFF): SPRITE.  
Arguments: [mode, position, image index, ???, ???].  
- 13568 (0x3500): AND.  
Arguments: [???, ???, ???].  
- 18432 (0x4800): EQUALS.  
Arguments: [???, ???, ???].  
- 21504 (0x5400): GREATER_EQUALS.  
Arguments: [???, ???, ???].  
- 43520 (0xAA00): ADD.  
Arguments: [???, ???, ???].  
- 61696 (0xF100): ASSIGN.  
Arguments: [???, ???].  


# Syntax / 语法解释

For those who desire for scripts to edit it's very important. The syntax is rather simple, but it have some specific moments.

对于想要编辑脚本的人来说，了解这一点非常重要。语法一般比较简单，但也有一些特殊之处。

- "$"   
In the string's beginning, it is for one-string   comment.  
在字符串的开头用于单字符串注释。  
- "#"   
In the string's beginning, it is for defination of command.  
在字符串开头，用于定义命令。  
- "[..., ..., ...]"   
It is for function argument's splitted with "," form. It goes strictly on the next line after the command defination.  
用", "形式分割的参数。它严格放在命令定义后的下一行。  
- "@"   
It is a label, to which some arguments are connecting.  
这是一个标签，用于连接着一些参数。
- "-1"  
This argument means it connected with next string index.  
该参数表示连接到下一个字符串索引。  
- ">"
It is for string beginning. 
After its goes mark of primary index of string or -1. 
If it's -1, the string is connected. Connected strings always goes after the defination of connected arguments.  
**  
DO NOTE: INDEXES AFTER ">" SHOWS ONLY PRIMARY INDEXES! THEN COMPILE PROGRAM TAKE A STRING INDEX ONLY FROM THE NUMBER OF ">" IN SCRIPT!  
DO NOTE: NOT AN ALL OF CONNECTED INDEXES WAS FOUND!  
**  
（这一段看的不是很懂，大概翻译了一下）  
用于字符串的开头。
其后是字符串的起始索引或-1。
如果是-1，则连接到下一个字符串。被连接的字符串总是位于连接参数定义之后。  
**  
注意：">"后面的索引只显示起始索引！编译程序时，只从脚本中">"的数量中提取字符串索引！  
注意：没有找到所有的连接的索引！  
**  
# 游戏汉化指北
