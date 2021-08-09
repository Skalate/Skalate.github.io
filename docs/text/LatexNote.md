


# LaTeX的安装

## TeX Live

## MikTeX

## Overleaf

## TexPage


# LaTeX的使用



## 基本使用语法


``` latex
\documentclass[UTF8,11pt,titlepage,a4paper]{article} % LaTex开头必备，
% 必需项：文档类说明，一般ctexart即可，不一般的时候看你需要选择，
% []里的是可选项，UTF8表示中英混排，11磅，标题单独成页，纸张大小a4纸。若不设置则为默认值


% 导言区
\usepackage{ctex} % 支持中文
\usepackage{geometry} % 设定页边距
\geometry{left=2.8cm,right=2.8cm,top=2.54cm,bottom=2.54cm}
\usepackage{amsmath} % 使用宏包，支持数学公式输入
\usepackage{amssymb} % 加载数学字体宏包，花体数学字符 % \mathbb{Q}
\usepackage{amsthm} % 可以插入证明
\usepackage{xcolor} % 支持改变字体色彩
\usepackage{hyperref} % 支持插入超连接 % \href{link}{超链接}
\usepackage{booktabs} % 支持插入三线表
\usepackage{graphics} % 支持插入图形

\title{Electromagnetic field and electromagnetic wave} % 标题
\author{Li Luan \\ Beijing Jiaotong University} % \and name \\ unversity 
\date{\zhtoday} % 日期，有\today和\zhtoday两种形式


% 正文区
\begin{document}

% 这里会显示标题信息
\maketitle
% 摘要，只有article类型才有。
\begin{abstract}
   这里是摘要文字
\end{abstract} 
% 目录
\setcounter{tocdepth}{4} % 设定目录深度                      
\tableofcontents % 列出目录

\part{部} % 只有book类型的documentclass才支持
\chapter{章} % 
\section{节} % 一级标题
\subsection{小节} % 二级标题
\subsubsection{小小节} % 三级标题
\paragraph{段} % 段落



% \hologo % 
% \par % 
% \newpage % 手动分页


\textbf{加粗} % 加粗

\emph{斜体} % 字体倾斜

\href{http://www.baidu.com}{超链接：百度}






\end{document}
% 正文区结束
```



必备结构，在语句`\begin{document}`的部分为**导言区**（模板定义），导言区可以留空。
``` latex
\documentclass[options]{doc-class} % LaTex开头必备，
% 导言区
\begin{document}
···
\end{document}
```
| doc-class | 文档类 | options | 设定 |
| - | - | - | - |
| book | 书籍 |  |  |
| article | 期刊 |  |  |
| report | 报告 |  |  |
| slides | 幻灯片 |  |  |
| proc | 会议论文集 |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |

## 公式篇



``` latex

```

``` latex

```

``` latex

```

``` latex

% 行内公式
$E = mc^2$

% 行间公式，不带有标号
$$E=mc^2$$

% 用于写大公式，写出来的公式带有标号
\begin{equation}
E=mc^2
\end{equation}

% \usepackage{cases}    % 需要导入这个包
\begin{numcases}{f(x)=}    %左大括号，多行公式，左对齐
    E=mc^2 \\
    E=mc^2
\end{numcases}

% \usepackage{amsmath}    % 数学宏包，里面有很多数学函数。
\begin{gather}  %  多行公式，居中对齐，会产生编号。用{gather*}没有编号，或者
% \notag % 在每行公式后加这个可以阻止编号
	a+b=b+a \\
	ab=ba 
\end{gather}

%case环境
%每行公式使用&分割成两部分，通常表示值和后面的条件
\begin{equation}  % cases 好像不需要导入宏包\usepackage{cases}，不过以防万一
	D(x) = \begin{cases}  % 带大括号，但是只有一个编号。
	1, &\text{如果} x \in \mathbb{Q}\\  % mathbb花体字符
	0, &\text{如果} x \in \mathbb{R}\setminus\mathbb{Q}	
		   \end{cases}%\text是为了在数学公式中处理中文
\end{equation}

% \begin{aligned}  公式换行
% 在需要换行的地方需要加两个反斜杠“\\”。
% 在每段对齐的地方（我的例子中需要在等号处对齐）加一个“&”。
\begin{equation} 
　\begin{aligned} 
　　f(x) & =f(x_0)+f\[x_0,x_1\](x-x_0)+f\[x_0,x_1，x_2\](x-x_0)(x-x_1)+\cdots \\ 
&\ \ \ \ \ \ +f\[x_0,x_1\cdots,x_n\](x-x_0)\cdots(x-x_{n-1}) \\  
&\ \ \ \ \ \ +f[x,x_0\cdots,x_n]\omega_{n+1}(x) \\
　　& =P_n(x)+R_n(x) 
　\end{aligned} 
\end{equation}

% 矩阵
\\[  
　　\begin{bmatrix}  
　　　　3.01 & 6.03 & 1.99 \\\  
　　　　1.27 & 4.16 & -1.23 \\\  
　　　　0.987 & -4.81 & 9.34  
　　　　\end{bmatrix}  
　　　　\begin{bmatrix}  
　　　　x_1 \\\ x_2 \\\ x_3  
　　　　\end{bmatrix} =  
　　　　\begin{bmatrix}  
　　　　1 \\\ 1 \\\ 1  
　　\end{bmatrix}   
\\]



```


``` latex

```


``` latex

```


``` latex

```


``` latex

```


``` latex

```

``` latex

```

## 图表篇


``` latex

% LaTEX插入图片
\usepackage{graphicx}  %插入图片的宏包
\usepackage{float}  %设置图片浮动位置的宏包
\usepackage{subfigure}  %插入多图时用子图显示的宏包

% 插入图片使其不跑到每页的开头而紧跟插入的文字之后 使用float宏包
% \usepackage{float} 在插入图片的语句后面加个 [H] 即可



```


``` latex

```


``` latex

```


``` latex

```


``` latex

```

``` latex

```



## 引用篇



``` latex
% \cite{AndersonMore}  % cite命令表示引用参考文献
% \bibliographystyle{plain}  % 引入参考文献格式
% \bibliography{reference}  %引入的bib格式参考文献
```


``` latex

```


``` latex

```


``` latex

```


``` latex

```

``` latex

```



## 代码篇

% \lstinline{行内代码}
% \begin{lstlisting}  \end{lstlisting}

``` latex
% 代码块 代码高亮
% \usepackage{listings}  % 代码块宏包，默认的高亮是关键词加粗
% 可以自定义高亮格式，例如添加以下设置，为了能够使用\color，需引入包\usepackage{xcolor}
\lstset{
    %backgroundcolor=\color{red!50!green!50!blue!50},%代码块背景色为浅灰色
    rulesepcolor= \color{gray}, %代码块边框颜色
    breaklines=true,  %代码过长则换行
    numbers=left, %行号在左侧显示
    numberstyle= \small,%行号字体
    %keywordstyle= \color{blue},%关键字颜色
    commentstyle=\color{gray}, %注释颜色
    frame=shadowbox%用方框框住代码块
}
% 以上写在导言区，以下写在正文区。
\begin{lstlisting}[language={java}]
    public class Main {
        public static void main(String[] args)
        {
            System.out.println("Hello World");
        }
    }
\end{lstlisting}
```


``` latex

```


``` latex

```


``` latex

```


``` latex

```

``` latex

```



# LaTeX 排版国标样式的数学符号

正体与斜体
国标要求普通的变量和函数名使用斜体字母表示，数学常数（如 ）和特殊函数使用正体。但是 LaTeX 的习惯是，大写希腊字母默认使用正体，不提供正体的小写字母。amsmath 宏包提供了 \varGamma  等斜体大写希腊字母命令；newtxmath 的 slantedGreek 选项可以使大写希腊字母的命令变为默认斜体，并且还提供了 \upalpha 和 \upGamma 等正体希腊字母命令；unicode-math 可以使用 math-style=ISO 选项和 \symup 正体符号命令。

粗体
LaTeX 传统使用粗正体表示向量和矩阵，所以只有一个 \mathbf 命令，但是这个命令对希腊字母无效。而国标要求使用粗斜体表示向量和矩阵，可以使用 bm 宏包的 \bm 得到粗斜体字母。unicode-math 可以设置 bold-style=ISO，并提供 \symbf 命令用于粗斜体的数学符号。

平行四边形符号
LaTeX 默认没有提供平行四边形符号，通常需要自己画。unicode-math 宏包提供了 \parallelogram 命令。

平行号
LaTeX 默认的平行号 \parallel 是竖直的；国标对竖直的和倾斜的平行号都允许，但是常见的更多的是斜的，可以在 LaTeX 中使用 \renewcommand\parallel{\mathrel{/\mskip-2.5mu/}}。

相似和全等符号
LaTeX 默认虽然提供了 \sim 和 \cong 表示相似和全等，但是国标中要求的符号的弯曲方向是相反的。amssymb 提供了 \backsim，unicode-math 提供了 \backsim 和 \backcong，但是曲线部分仍略小于国标的样式。

省略号
LaTeX 传统的省略号的垂直位置通常取决于两端操作符的位置，比如  使用居下的省略号 \ldots，而  使用居中的省略号 \cdots。国标沿用中文省略号的习惯，不管操作符的位置一律居中，可以使用 \renewcommand\mathellipsis{\cdots} 将 \ldots 改为居中。

小于等于号
LaTeX 默认的小于等于号 \leq 的横线是水平的，但是国标的横线是倾斜的，这个符号对应于 amssymb 或 unicode-math 提供的 \leqslant 命令。大于等于号同理。

波浪号
国标规定了波浪号表示数字范围，如”5～10”，这个符号事实上源自中文的符号使用习惯，其 Unicode 编码是 U+FF5E。但是在西文里，几乎不会使用波浪号表示数字范围（https://en.wikipedia.org/wiki/Tilde#Range ），而一般只用连接号。而且这个符号容易与 LaTeX 传统和 ISO 标准的“∼”（U+223C，表示正比于或者等价关系）混淆，所以应该避免使用波浪号。

有限增量 
国标的有限增量符号 \Delta 是正体的，应该使用 。ISO 标准新定义了一个符号∆（U+2206）表示有限增量，可以在 unicode-math 中使用 \increment 得到。

微分和偏微分
国标要求微分和偏微分符号使用正体，LaTeX 中正确的用法是 \newcommand\dif{\mathop{}\!\mathrm{d}}，但是 \partial 符号默认没有提供正体的字形  符号；newtx 宏包提供了 \uppartial 命令；unicode-math 可以设置 partial=upright，但是有的字体没有正体的字形。

积分号
积分号有两点需要注意，一是积分号的形状：LaTeX 遵循英美国家的习惯使用右倾的积分号，而国标则使用直立的积分号，这可以通过 newtx 的 upint选项得到，也可以使用 ‘unicode-math’ 调用一些字体的 stylistic set 特性。

另外一点是积分号上下限的位置，LaTeX 习惯将其放在积分号的右边，但是 ISO 的上下限位于积分号上下。国标对两者都允许，但是国内的教材普遍使用上下位置。这可以通过 amsmath 的 intlimits 选项来设置；unicode-math 需要使用 \removenolimits 命令。

复数的实部和虚部
LaTeX 默认的实部和虚部函数 \Re 和 \Im 是 Fraktur 体的字母“R”和“I”，但是国标要求使用罗马体的“Re”和“Im”，设置的方法是 \renewcommand{\Re}{\operatorname{Re}}。

nabla 符号
国标的 nabla 符号要求使用粗正体，所以正确的使用方法是 。unicode-math 直接提供了 \mbfnabla 命令表示粗正体的 nabla。


多个连续的空白字符等同为一个空白字符（空格、制表符），空白字符视为相同的空白距离（space）。
每行开始的空白字符将被忽略，而单个的回车符被视为一空格。


LATEX 使用空行来结束段落，两行文本中的空行标志上一段落的结束和新段落的开始。如同空格一样，多个空行所起的作用和一个空行的作用是相同的。

特殊字符（保留字符）：#  $  %  ^  &  _  {  }  ~  \
这些字符前面加上反斜线，就可以在文本中得到它们。
\\是一个用来断行的命令
命令 $\backslash$，生成 \。
\TeX{} 
\Tex
\today
\newline
\textsl{hi}
%  注释

\usepackage{verbatim}
\begin{comment}
非常笨拙的，
然而却很有效。
\end{comment}

每个 LATEX 文档必须以如下的命令开始：
\documentclass{...}
\documentclass[options]{class}
这个命令指定了你所写的文档的类别。在此之后，你可以加入控制文档式样的命令，或者使用如下的命令来调入一些宏集，进而为 LATEX 系统增添一些新的功能。
当完成所有的设置5后，你可利用如下的命令来开始你的文档：
\begin{document}
\end{document}

``` tex
\documentclass[a4paper, 11pt]{article}  % define the title
\author{L.Li}
\title{}
\begin{document}
\maketitle  % generates the title
\tableofcontents  % insert the table of contents
\section{Start}
Well, and here begins my lovely article.
\section{End}
\ldots{} and here it ends.
\end{document}
```

扩展名  .tex
文本格式 ASCII

{article}  论文版式
{report}  排版多章节的长报告、短篇的书籍、博士论文等。
{book}  排版书籍。
{slides}  排版幻灯片。其中使用了较大的 sans serif 字体。也可以考虑使用 FoilTEX 来得到相同的效果。a
[a4paer]  A4纸输出
[11pt]  11磅字体，缺省将使用 10pt 字体。
缺省的设置为letterpaper。此外，还可以使用a5paper，b5paper，executivepaper 和 legalpaper。


# Beamer


最常用代码套用
frame

``` latex
begin{frame}
    frametitle{FrameTitle}
    
end{frame}
```
block


``` latex
begin{block}{BlockTitle}

end{block}
```
公式 (equation)

```
begin{align*}
    f(z)&=b
    &=c+d
end{align*}
```



无序列表

```
begin{itemize}
  item $9+8=17$
  item $2+1=3$
end{itemize}
```


图片

```
hicspath{{images/}}
begin{figure}[h]
    centering
    includegraphics[width=0.8textwidth]{image.png}
end{figure}
```


最后感谢页

```
begin{frame}
    frametitle{}
    Huge
    begin{center}
        Thank You!
    end{center}
end{frame}
% 文字可选：The End | Thank You for Your Attention! | Thank You for Listening!
% 文字可选：谢谢！| 感谢聆听！
```



代码片段
零碎

```
% 强调文本
alert{Kernel trick}
{color{red} text}

% frame中调整行间距
addvspace{-0.6cm}

% block中调整行间距
vspace*{-baselineskip}setlengthbelowdisplayshortskip{0.6pt}

% 文本内容加框
usepackage{tcolorbox}
begin{tcolorbox}
    text
end{tcolorbox}

% 封面页
frame{titlepage}

% 章节
part{PartName}
section{SectionName}
subsection{SubsectionName}
section[ShortName]{LongName}

% 介绍
title[ShortVersion]{YourTitle}
author[short]{YourName}
date{November 26th, 2018}
subtitle{Your Subtitle Here}
institute[short]{institute}
titlegraphic{includegraphics[width=2cm]{logo.png}} % 在页面中间位置加图片
logo{includegraphics[width=1.3cm,height=1.3cm]{logo.jpg}} % 封面上没有图片，这会加到之后每一页右下角

% author中换行，一种是名字足够长它会自动换行；另一种如加指导教师，则在author中使用\\换行，但这会有warning

% 多作者机构对应
author[shortname]{author1 inst{1} and author2 inst{2}}
institute[shortinst]{inst{1} institute for author1 and 
                      inst{2} institute for author2}

% 机构字体放大
setbeamerfont{institute}{size=normalsize}

% 插入直线
noindentrule{textwidth}{1pt}

% 页脚只留页码
setbeamertemplate{footline}[frame number]
```



更多环境

```
% remark环境
begin{alertblock}{Remark}

end{alertblock}

% 其他环境
theorem
examples
```


目录
```
% 加目录页
begin{frame}frametitle{Outline}
    tableofcontents
end{frame}

% 每个section自动添加目录页
AtBeginSection[]{
    frame{frametitle{Outline}tableofcontents[
        sectionstyle=show/shaded,
        subsectionstyle=show/show/shaded]}
}

% section自动目录，不在handout中生成
AtBeginSection[]{
    begin{frame}<beamer>
        frametitle{Outline}tableofcontents[
        sectionstyle=show/shaded,
        subsectionstyle=show/show/shaded]
    end{frame}
}
```



分栏
```
begin{columns}

    column{0.5textwidth}
    This is a text in first column.
    $$E=mc^2$$
    
    column{0.5textwidth}
    This is a text in second column.

end{columns}


% 2个 0.5linewidth 可以左右分，两个 linewidth 可以上下分
begin{minipage}{0.5linewidth}
    begin{figure}[h]
        includegraphics[width=textwidth]{minipage.jpg}
    end{figure}
end{minipage}
```



三线表格
```
usepackage{booktabs}

begin{center}
    begin{table}[!t]  
        % caption{Three line}
        % label{table_time}
        begin{tabular}{ccc}  
            toprule   
            first&second&third 
            midrule       
            1 & 2 & 3  
            4 & 5 & 6  
            7 & 8 & 9 
            bottomrule  
        end{tabular}
    end{table}
end{center}
```


首行缩进
```
usepackage{indentfirst} 
setlength{parindent}{2em}
```


将内容置于页面任意位置
```
usepackage{tikz}

begin{tikzpicture}[remember picture,overlay]
    node[xshift=5cm,yshift=6cm] at (current page.south west) {long sentence long sentence};
    node[xshift=5cm,yshift=4cm] at (current page.south west) {includegraphics[width=0.1textwidth]{image.png}};
end{tikzpicture}
```



更多操作

动态效果 (overlay)

动态列表

```
begin{itemize}
item 2 is prime (two divisors: 1 and 2).
pause
item 3 is prime (two divisors: 1 and 3).
pause
item 4 is not prime (alert{three} divisors: 1, 2, and 4).
end{itemize}
```
（动态文本也是用pause即可）

更灵活地控制

```
begin{itemize}
 item<1-> Text visible on slide 1
 item<2-3> Text visible on slide 2
 item<3-> Text visible on slide 3
 item<4-> Text visible on slide 4
end{itemize}
```


细节控制

```
definecolor{mygray}{gray}{0.6}
{color<1>{mygray} alpha} beta

onslide<2->{alpha} beta
```


缩小字体
frame 整体缩小
```
begin{frame}{framtitle}
    scriptsize
    small text
    small text
end{frame}
```

frame 部分缩小
```
begin{frame}{framtitle}
    begingroup
        scriptsize
        small text
        small text
    endgroup
    big text
    big text
end{frame}
```
这样也可以用于多个 frame 缩小

插入代码
涉及代码的 frame 都需要设置`[fragile]`。

同时，end{frame}必须另起一行并顶格（不允许有缩进）

```
begin{frame}[fragile]

end{frame}
```


代码块

使用`verbatim`环境
```
begin{verbatim}
    int main (void)
    {
        std::vector<bool> is_prime (100, true);
    }
end{verbatim}
```



使用 listings 宏包
```
usepackage{listings}

begin{lstlisting}[language=R]
    a <- c(1, 2)
    b <- a + 1
end{lstlisting}
```


行内代码

在`uncoverenv`环境中使用`verb`
```
begin{uncoverenv}
    Note the use of verb|std::|.
end{uncoverenv}
```


verb
```
Note the use of texttt{textbackslash alert}.
```


脚注引用

将参考文献放在当前页脚注，正文用footnotemark标注即可，脚注如下

```
footnotetext[1]{scriptsize Lei N, Luo Z, Yau S T, et al. Geometric understanding of deep learning[J]. arXiv preprint arXiv:1805.10451, 2018.}
```

注意：同一个 beamer 下如果有多个footnotetext，footnotemark会自动按数字顺序排下去，因此`footnotetext[n]`中n也要随之变化。

BibTex 引用

正常设置bib文件，也正常在正文中用cite引用，最后放参考文献列表，支持换页

```
begin{frame}[allowframebreaks]
    frametitle{References}
    scriptsize
    bibliographystyle{plain}
    bibliography{bibfile}
end{frame}
```


此外，还可以在前面进行一些样式

```
% 修改标号
setbeamertemplate{bibliography item}{insertbiblabel} 

% % 三部分不换行
% setbeamertemplate{bibliography entry title}{}
% setbeamertemplate{bibliography entry location}{}
% setbeamertemplate{bibliography entry note}{}

% % 三部分使用相同颜色
% setbeamercolor{bibliography entry author}{fg=black}
% setbeamercolor{bibliography entry title}{fg=black} 
% setbeamercolor{bibliography entry location}{fg=black} 
% setbeamercolor{bibliography entry note}{fg=black}  
% setbeamercolor{bibliography item}{fg=black}
```



支持中文
编译
xelatex 编译
```
documentclass{beamer}
    usepackage{ctex}  % 会引起一些公式排版问题，如hat U 所以加下面的字体主题
    usefonttheme{professionalfonts}
    author{作者}
    title{演讲主题}
    date{2018年11月29日}
    begin{document} 
        frame{titlepage}
        begin{frame}
            中文
        end{frame}
    end{document}
```


pdfLatex 编译
```
usepackage{CJKutf8}

author{名字}
title{Presentation Title}
date{January 1, 2018}

begin{document}
    begin{CJK}{UTF8}{song}   

    begin{frame}
        中文
    end{frame}

    end{CJK}
end{document}
```

下面小节若未做说明就都是基于xelatex+ctex

首行缩进问题

中文首行会自动缩进，中文后加无序列表会使列表看起来没有缩进，所以需要下面命令使列表缩进更多。

```
settowidth{leftmargini}{usebeamertemplate{itemize item}}
addtolength{leftmargini}{8labelsep}
```


如果取消首行缩进，文字可能会太靠近边缘，因此这里选择了缩进列表。如果想要让某一行取消缩进，可以在前面加上noindent。

字体
```
setCJKmainfont{宋体}
setCJKmainfont{黑体}
setCJKmainfont{楷体}
setCJKmainfont{微软雅黑}
setCJKmainfont{SimHei}  % 黑体
setCJKmainfont{MicrosoftYaHei}  % 微软雅黑，编译起来有点慢
```


更详细可以参考 latex 文章。

主题套用
```
% 套用主题
usetheme
usecolortheme
usefonttheme
useinnertheme
useoutertheme
```


寻找主题

内置Beamer Matrix)

第三方 (overleaf, github)

模板套用

```
documentclass{beamer}
    usepackage[english]{babel}
    usetheme{warsaw}
          
    author{Your Name}
    title{Your title}
    date{November 29th, 2018}

    begin{document}
        frame[plain]{titlepage}
        section{Introduction}
        begin{frame}
            frametitle{Latex and Beamer}
            LaTeX is a high-quality typesetting system; 
            it includes features designed for the production of 
            technical and scientific documentation.
        end{frame}
    end{document}
```
在这基础上变化

加载包
换主题: Simple, Madrid, CambridgeUS
加 outertheme: infolines, tree, split
我的主题 (simple)
下载主题，使用beamerthemeSimple.sty文件，使用方法与上面相比只需要换主题名称

```
% 基本用法
usetheme{Simple}
useoutertheme{tree} 

% 可选颜色配置
usetheme[RGB={12 72 66}]{Simple}
usetheme[HTML=A30000]{Simple}

HTML=096148      % green
RGB={12 72 66}   % bluegreen
HTML=8D742A      % brown
RGB={163 0 0}    % red

% 推荐导航配置
useoutertheme{split}
useoutertheme{tree}
useoutertheme{infolines}

documentclass[compress]{beamer}
    useoutertheme[subsection=false]{miniframes}
```


sidebar 版，使用beamerthemeBar169.sty文件

```
documentclass[aspectratio=169]{beamer}
    usepackage[english]{babel}
    usetheme[RGB={12 72 66}]{Bar169}

    author{Your Name}
    title{Your Title}
    date{November 29th, 2018}

    begin{document}
        frame[plain]{titlepage}
        section{Introduction}
        
        begin{frame}
            frametitle{Latex and Beamer}
            LaTeX is a high-quality typesetting system; 
            it includes features designed for the production of 
            technical and scientific documentation.
        end{frame}
    end{document}
```


加载包
```
usepackage{amsmath,amssymb,amstext} 
usepackage{float}
usepackage{array}           
usepackage[english]{babel}
usepackage{fancyhdr}        % header footer
usepackage{graphicx}        % figure
usepackage{algorithm2e}
usepackage{booktabs}        % three line table
usepackage{bookmark}        
usepackage{xcolor}
usepackage{color}
usepackage{lmodern}         % include more fontsize, e.g. 15pt
```


其他技巧
提高编译速度，draft
在不生成最终文件时，可以先不生成目录、导航、图片等东西，每一步只关注内容。

```
documentclass[draft]{beamer}
```


提高编译速度，加载指定页
给 frame 指定标签

```
begin{frame}[label=example1]{FrameTitle1}
    content1
end{frame}

begin{frame}[label=example2]{FrameTitle2}
    content2
end{frame}
```


在导言区指定加载的标签

```
includeonlyframes{example1, example2}
```


生成打印版本，handout
slides 的打印版本不希望有动态效果和章节封面

```
documentclass[handout]{beamer}

% 生成handout时重新定义这个颜色
mode<handout>{
    definecolor{mygray}{RGB}{0,0,0}
}
```


资源搜集
Beamer User Guide
Beamer Appearance Cheat Sheet

