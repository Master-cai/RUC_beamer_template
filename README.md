# beamer简介
Beamer是LaTeX 软件中用于制作演示文稿(PPT)的拓展包，排版方便精美，对数学公式支持很好，常用于各种学术会议的汇报中。Beamer只是LaTeX的一部分，所以大部分语法和命令都和基础的LaTeX相同，使用前需要安装好LaTeX以及**掌握一定的LaTeX基础知识**。
# 模版简介
首先从github下载模版：
```bash
git clone https://github.com/Master-cai/RUC_beamer_template.git
```
项目文件结构如下：
```bash
├── RenminUniv.sty
├── asset
│   ├── Info_Logo.jpg
│   ├── Inlab_logo.png
│   ├── RUC_Logo.png
│   ├── Renmin_Univ_Logo.eps
│   └── background.pdf
├── missfont.log
├── pic
├── ref.bib
├── slide.dvi
├── slide.pdf
└── slide.tex
```
其中，`slide.tex`是主文件，PPT的主要内容就在这里修改；`slide.pdf`为编译得到的PPT文件(pdf格式). 
`asset`文件夹里是一些静态资源，一般不需要修改；`RenminUniv.sty`是LaTeX的style文件，一般也不需要修改，如果要自定义命令或修改格式时才会用到；`pic`用来存放PPT中会用到的所有图片资源。

# 用法

项目下载之后，需要使用`XeLaTeX`进行编辑！！！
可以先使用编译一下`slide.tex`文件，检查一下是否能够编译成功以及看一下效果。下列所有修改都是在`slide.tex`文件内完成。

## 基础用法

beamer和普通的LaTeX用法非常类似，前面部分为首页，可以根据需要修改作者，标题，子标题等信息；第二部分是目录部分，这一部分不需要手动修改，会自动根据后面内容的`\section{}`自动生成；最后一部分就是内容主体，以`\section{}`分割章节，也可以添加`\subsection{}`继续细分子章节。每一页ppt需要用如下命令生成：
```latex
\begin{frame}{frame name}
	some content...
\end{frame}
```
使用`\section{}`和`frame`就能构成最基础的PPT了.
## 常用命令
beamer最好用的就是它可以通过LaTeX命令的方式进行快速的排版，并且工整美观，下面就介绍一些常用的以及自定义的模块/命令。
### removeBullets

该命令可以移除最上方导航栏中用于指示页数的原点，可以用于页数较多的情况。该命令需要加在`\begin{document}`之前。效果对比如下：
使用前：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/453013/1673168377877-7ee863a5-959c-44c1-8b97-8d64b66a3060.png#averageHue=%234b1c21&clientId=ua4f4c9a4-2492-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=51&id=uf88fe05b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=102&originWidth=2876&originalType=binary&ratio=1&rotation=0&showTitle=false&size=116183&status=done&style=none&taskId=ue653c268-cd65-40b0-9494-f9909a6c279&title=&width=1438)
使用后：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/453013/1673168476544-ed9a51b5-c518-4ec6-9f2e-4db184e6740d.png#averageHue=%23b9a7a8&clientId=ua4f4c9a4-2492-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=51&id=uc995467a&margin=%5Bobject%20Object%5D&name=image.png&originHeight=102&originWidth=2876&originalType=binary&ratio=1&rotation=0&showTitle=false&size=34233&status=done&style=none&taskId=u866d4fc6-6afa-49d5-816b-72c504f4a9d&title=&width=1438)

### exampleblock
最常用的block块：
```latex
\begin{frame}{Background}

\begin{exampleblock}{block name}
some content...
\end{exampleblock}

\end{frame}
```
![image.png](https://cdn.nlark.com/yuque/0/2023/png/453013/1673168693891-d1a2cbf3-315a-4389-a125-c1fce5500e54.png#averageHue=%23fdfdfd&clientId=ua4f4c9a4-2492-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=349&id=uf1ee63da&margin=%5Bobject%20Object%5D&name=image.png&originHeight=698&originWidth=1459&originalType=binary&ratio=1&rotation=0&showTitle=false&size=170770&status=done&style=none&taskId=u0059b58f-00de-4fb6-95c6-0a95f783f4e&title=&width=729.5)
### block
另一种block块
```latex
\begin{frame}

\begin{block}{block name}
Some content...
\end{block}

\end{frame}
```
![image.png](https://cdn.nlark.com/yuque/0/2023/png/453013/1673178669183-7e866524-baa3-44d8-b09b-306d9bb64a63.png#averageHue=%23d5ac3b&clientId=ua4f4c9a4-2492-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=750&id=ub8516e13&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1500&originWidth=2878&originalType=binary&ratio=1&rotation=0&showTitle=false&size=572894&status=done&style=none&taskId=u0855602f-397c-4800-943b-d83072435ef&title=&width=1439)
### rb
用于对特定内容进行变红加粗
```latex
\begin{frame}

Some \rb{content}...

\end{frame}
```
![image.png](https://cdn.nlark.com/yuque/0/2023/png/453013/1673178764417-0df509c6-c261-466b-9e6b-7d076e414108.png#averageHue=%23fdfdfd&clientId=ua4f4c9a4-2492-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=750&id=u83b76334&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1500&originWidth=2878&originalType=binary&ratio=1&rotation=0&showTitle=false&size=598855&status=done&style=none&taskId=u7b6e6977-1b3b-4891-9fd4-cb6116329c1&title=&width=1439)
### itemize/enumerate
用于构建列表。itemize是无序列表，enumerate是有序列表，可以任意组合嵌套使用。
```latex
\begin{frame}

\begin{itemize}
\item first item...
\item second item...
\begin{enumerate}
	\item first item...
	\item second item..
\end{enumerate}
\end{itemize}

\end{frame}
```
![image.png](https://cdn.nlark.com/yuque/0/2023/png/453013/1673184067220-016fe315-678a-4117-9499-7bdb0b23ef63.png#averageHue=%23fcfcfc&clientId=ua4f4c9a4-2492-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=750&id=u7a75a678&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1500&originWidth=2878&originalType=binary&ratio=1&rotation=0&showTitle=false&size=631800&status=done&style=none&taskId=ud1f864b2-1b86-4d25-96ab-1c5d87d3460&title=&width=1439)
### columns
用于分栏排版
```latex
\begin{frame}

\begin{columns}[t]
\column{0.33\textwidth}
this is column one
\column{0.33\textwidth}
this is column two
\column{0.33\textwidth}
this is column three
\end{columns}

\end{frame}
```
![image.png](https://cdn.nlark.com/yuque/0/2023/png/453013/1673184691768-dabb7b8b-8d99-4ab9-a2ce-3720b95ebfd4.png#averageHue=%23fcfcfc&clientId=ua4f4c9a4-2492-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=750&id=u3b264a45&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1500&originWidth=2878&originalType=binary&ratio=1&rotation=0&showTitle=false&size=604451&status=done&style=none&taskId=uce3a0340-33f6-4e51-acbe-a2c407f9289&title=&width=1439)
### footnote
用于在当前页面添加论文脚注
```latex
\begin{frame}

some content...\footnote{I am a footnet!}

\end{frame}
```
![image.png](https://cdn.nlark.com/yuque/0/2023/png/453013/1673185277587-93bb4de5-47f2-4afc-971f-e6db6341b843.png#averageHue=%23fdfdfd&clientId=ua4f4c9a4-2492-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=750&id=u7b2f8712&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1500&originWidth=2878&originalType=binary&ratio=1&rotation=0&showTitle=false&size=604332&status=done&style=none&taskId=uf5d55f90-a2e9-4adb-8eff-8da1aee53d3&title=&width=1439)
### justifying
用于将文本设置为两端对齐，默认为左对齐。
```latex
\begin{frame}

\justifying some very long long long long long long long long long long long long long long long long long long long long long long long long long long content...

\end{frame}
```
![image.png](https://cdn.nlark.com/yuque/0/2023/png/453013/1673185414762-5c809488-53fb-44c5-862d-f19d7f30de34.png#averageHue=%23faf9f9&clientId=ua4f4c9a4-2492-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=750&id=uc44444ea&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1500&originWidth=2878&originalType=binary&ratio=1&rotation=0&showTitle=false&size=621385&status=done&style=none&taskId=u173e1c14-8131-4341-93c1-4c031e441d6&title=&width=1439)
