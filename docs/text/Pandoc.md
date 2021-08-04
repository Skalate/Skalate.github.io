---
title: "Pandoc"
author: [李峦]
date: "2021-04-19"
keywords: [Markdown, Pandoc, LaTeX, PDF]
...


## Pandoc Install






## Use of Pandoc



### 命令行CMD操作



基本格式`Pandoc test.md -o test.pdf`配置项（加在基本格式后面）

`--template [template]`    使用模板（`ll\AppDate\Roming\pandoc\templates\eisvogel.latex`）

`--pdf-engine=xelatex`    生成pdf要使用xelatex引擎

`-V CJKmainfont="KaiTi"`    中文支持必须定义字体

`--to beamer`    生成beamer类型的PDF文件

`--listings`    代码加框




### md转换为pdf

pandoc 不能直接生成 pdf 文档，需要借助 LaTeX 引擎。

直接转换

下面这条代码可以生成pdf格式的文件，但是不能调整格式。
```
pandoc test.md -o test2.pdf --pdf-engine=xelatex -V CJKmainfont="KaiTi"
```
注意对于中文文档需要像以上命令这样指定pdf-engine和字体。不指定字体的话，汉字就会不显示。



使用模板

参考教程https://github.com/Wandmalfarbe/pandoc-latex-template。

```
pandoc example.md -o example.pdf --from markdown --template eisvogel.latex --listings
```
但原教程不支持中文，因此需要使用下列语句。
```
pandoc test.md -o test.pdf --from markdown --template eisvogel --listings --pdf-engine=xelatex -V CJKmainfont="KaiTi"
```
效果非常棒，可以尝试一下换字体



生成beamer文件

`pandoc "document.md" -o "document.pdf" --from markdown --to beamer --template "../../eisvogel.tex" --listings`

`pandoc pandoc.md -o pandoc.pdf --from markdown --to beamer  --template eisvogel.latex --pdf-engine=xelatex -V CJKmainfont="KaiTi"`






### md转换为word

这个很简单`pandoc test.md -o test.docx`。

同时在生成时也可以使用 -c 参数为文档指定样式文件（css文件）`pandoc test.md -o test.docx -c style.css`。
这里的样式与生成 html 时的样式一样，针对 markdown 文档各个部分生成的 html 标签来应用，如：在样式文档中定义的 `h1 { font-size: 24px; }`。就会应用在以 # 开头的一级标题行。



### md转换为html


`pandoc -s -f gfm -t html5 --css=css/markdownPad-github.css test.md -o test.html`

`-s` 表示使用标准模板输出

`-f gfm -t html5` 表示用 gfm 引擎来解析，从 Github Flavored MarkDown 到 HTML5。从网上看的别人写的是`-f markdown_github -t html`，试着使用这个来编译会产生Warning，提示找不到markdown_github，用gfm替代，索性就直接在命令里使用gfm。

`--css=css/markdownPad-github.css` 把 markdownPad-github.css 这个css文件加到生成的HTML文件中，是其呈现出不同的样式

`test.md -o test.html` 把test.md这个MarkDown文件输出成同的.html文件，这样使用有时候会有Warning，应该是需要把.html取一个与.md文件不同的名字

本想使用github-markdown.css来呈现 github 式的 MarkDown 文件，但生成的html文件并没有.markdown-body等 class 名字，应该是 html 模板的原因，后来改用markdownPad-github.css


### latex转word

```
pandoc input.tex -o output.docx -w docx --reference-doc ref.docx --pdf-engine xelatex
```

`input.tex`待转换文件；
`output.docx`输出文件；
`ref.docx`模板文件。




### 编辑器VSCode操作


在VSCode中的Setting.json文件内添加下述代码
``` json
{
    //-------- Pandoc Option Configuration --------

    // pandoc .pdf output option template that you would like to use
    "pandoc.pdfOptString": "--from markdown --template eisvogel.latex --pdf-engine=xelatex -V CJKmainfont=\"KaiTi\"",

    // pandoc .docx output option template that you would like to use
    "pandoc.docxOptString": "",

    // pandoc .html output option template that you would like to use
    "pandoc.htmlOptString": "-s -t html5",

}

```





