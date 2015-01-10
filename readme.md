#哈　尔　滨　工　业　大　学  
#PlutoThesis硕博士学位开题报告XeLaTeX模版

##版本介绍

该版本与[哈工大学位论文XeLaTeX模板](https://github.com/dustincys/PlutoThesis)来源一样。

##为什么要添加XeLaTeX？

XeLaTeX对中文的支持非常完美

##为什么原版本不支持XeLaTeX？

时过境迁，沧海桑田。  
Google code项目已经停滞2年，也许诸位先驱都已毕业?  
当年诸位先驱开发模班的时代是CJK的时代，而如今CJK逐渐被xeCJK所取代， 当年的命令作废的作废，冲突的冲突。  
新版本的texlive无法编译陈旧的源文件了。

##关于Ubuntu和Windows的冲突

ctexbook目标是为排版中文的用户极大解决麻烦的大杀器。
且看该模板中导言定义：

	\documentclass[cs4size,openany,twoside,UTF8,BoldFont,normalindentfirst,SlantFont,nofonts]{ctexbook}

这一串选项的定义足以说明大杀器的威力。
ctexbook在Ubuntu上认为用户不玩windows字体的，所以其定义文件：

	/usr/share/texlive/texmf-dist/tex/latex/ctex/fontset/ctex-xecjk-winfonts.def

中的所有字体样式都是跟随Windows而来。
这使得ubuntu用户出现字体错误, 如“找不到[SIMKAI.TTF]"之类。

Ubuntu用户安装好Windows字体之后，需要自己载入Windows字体。
一共分3步：

1.	在导言documentclass中加入nofonts选项，关闭默认载入字体选项
2.	在导言中自己载入字体
3.	定义一下默认的衬线和非衬线字体

Windows 用户没有这麻烦，可以直接用默认字体。

## 编译方法：

Windows:

	xelatex main.tex

Ubuntu (Ubuntu 14.04, texlive 2013, 已测):

	make

## 目录结构

├── body
│   ├── equations.tex
│   ├── figures.tex
│   ├── others.tex
│   └── tables.tex
├── clean.bat
├── cover.tex
├── figures
│   ├── golfer.eps
│   ├── latex.eps
│   ├── list.eps
│   ├── pdf.eps
│   └── word.eps
├── format.tex
├── GBT7714-2005NLang-HIT.bst
├── GBT7714-2005NLang-HIT.bst.tex
├── main.pdf
├── main.tex
├── Makefile
├── readme.md
└── reference.bib

