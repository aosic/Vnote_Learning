# manim-3b1b


```

(base) C:\Users\admin\Documents\Tridu33\!Py\!3b1b-video\manim>python -m manim text.py makeText -pl
Media will be written to ./media\. You can change this behavior with the --media_dir flag.
Writing "\centering 中文" to ./media\Tex\284678849bb8f9e8.tex

Sorry, but miktex-makemf did not succeed.

The log file hopefully contains the information to get MiKTeX going again:

  C:\Users\admin\AppData\Local\MiKTeX\2.9\miktex\log\miktex-makemf.log

Sorry, but miktex-makemf did not succeed.

The log file hopefully contains the information to get MiKTeX going again:

  C:\Users\admin\AppData\Local\MiKTeX\2.9\miktex\log\miktex-makemf.log
C:\Users\admin\Documents\Tridu33\!Py\!3b1b-video\manim\manimlib\mobject\svg\svg_mobject.py:125: UserWarning: g1-45 not recognized
  warnings.warn("%s not recognized" % ref)
C:\Users\admin\Documents\Tridu33\!Py\!3b1b-video\manim\manimlib\mobject\svg\svg_mobject.py:125: UserWarning: g0-135 not recognized
  warnings.warn("%s not recognized" % ref)
Writing "\centering So high!" to ./media\Tex\7b95102eae8141a8.tex
Writing "\centering Deal,delay no more," to ./media\Tex\49697cc7b0ddc558.tex
Writing "\centering Hi!" to ./media\Tex\70171d6705c04de1.tex
Writing "\centering Deal might late no doubt!" to ./media\Tex\3ad19e48e6f77dd6.tex

File ready at C:\Users\admin\Documents\Tridu33\!Py\!3b1b-video\manim\media\videos\text\480p15\makeText.mp4

Played 7 animations

文件中

2019-08-18 23:40:01,969+0800 INFO  miktex-makemf - starting with command line: miktex-makemf.exe unisong4e.mf
2019-08-18 23:40:01,982+0800 FATAL miktex-makemf - The unisong4e source file could not be found.
2019-08-18 23:40:01,982+0800 FATAL miktex-makemf - The unisong4e source file could not be found.
2019-08-18 23:40:01,982+0800 FATAL miktex-makemf - Info: 
2019-08-18 23:40:01,982+0800 FATAL miktex-makemf - Source: 
2019-08-18 23:40:01,982+0800 FATAL miktex-makemf - Line: 0








```


https://www.latexstudio.net/hulatex/download/TeXsystem.htm


**map	**字体名称与.tfm文件之间的字体映射文件。
.mbs	主控文件，包含全部 文献样式命令，用于生成.bst文献样式文件。
**.mf**	METAFONT字体描述文件，Knuth教授创立的矢量字体。
.pfa	Type 1字体文件，ASCII格式，一种高品质矢量字体，越放大越清晰。
.pfb	Type 1字体文件，二进制格式。
.pk	pk字体，一种点阵字体，用于dvi文件预览等。
.pl	字体属性列表，可读的字体描述文件。
.sfd	子字库定义文件。
.sty	宏包文件，可用命令\usepackage调用。
.tex	LaTeX源文件。
**.tfm	**字体描述文件，设定字体的宽、高和间距等，LaTeX用以规划页面。

C:\Users\admin\AppData\Local\Programs\MiKTeX 2.9\fonts\tfm\zhmetrics\unisong\unisong4e.tfm

miktex-makemf - starting with command line: miktex-makemf.exe unisong4e.mf


https://docs.miktex.org/manual/miktex-mf.html

miktex-mf - METAFONT，一种字体和徽标设计语言

安装宏包https://blog.csdn.net/memray/article/details/45248259


TDS定义了不同类型的文件存放的位置不同。比如sty格式文件，一般放在texmf/tex/latex下不同的文件夹下，文件夹的名字即是宏包的名字。下面的表格中给出了文件存放的规则：

<table class="wikitable" style="box-sizing: border-box; outline: 0px; margin: 0px auto; padding: 0px; border-collapse: collapse; border-spacing: 0px; display: table; width: 700px; text-align: left; overflow-wrap: break-word; font-size: 12.7273px; border: 1px solid rgb(170, 170, 170); color: rgb(0, 0, 0); font-family: sans-serif; line-height: 19.1903px;"><caption style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; font-weight: bold; overflow-wrap: break-word;">Where to put files from packages</caption><tbody style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; border: 0px; overflow-wrap: break-word;"><tr style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; border-width: 1px 0px 0px; border-right-style: initial; border-bottom-style: initial; border-left-style: initial; border-right-color: initial; border-bottom-color: initial; border-left-color: initial; border-image: initial; border-top-style: solid; border-top-color: rgb(221, 221, 221); background-color: rgb(255, 255, 255); overflow-wrap: break-word;"><th style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: 700; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: center; background-color: rgb(239, 243, 245);">Type</th><th style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: 700; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: center; background-color: rgb(239, 243, 245);">Directory (under&nbsp;<tt style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; overflow-wrap: break-word; font-family: monospace, Courier;">texmf/</tt>&nbsp;or&nbsp;<tt style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; overflow-wrap: break-word; font-family: monospace, Courier;">texmf-local/</tt>)</th><th style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: 700; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: center; background-color: rgb(239, 243, 245);">Description</th></tr><tr style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; border-width: 1px 0px 0px; border-right-style: initial; border-bottom-style: initial; border-left-style: initial; border-right-color: initial; border-bottom-color: initial; border-left-color: initial; border-image: initial; border-top-style: solid; border-top-color: rgb(221, 221, 221); background-color: rgb(247, 247, 247); overflow-wrap: break-word;"><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">.afm</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">fonts/afm/<em style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; font-style: italic; overflow-wrap: break-word;">foundry</em>/<em style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; font-style: italic; overflow-wrap: break-word;">typeface</em></td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">Adobe Font Metrics for Type 1 fonts</td></tr><tr style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; border-width: 1px 0px 0px; border-right-style: initial; border-bottom-style: initial; border-left-style: initial; border-right-color: initial; border-bottom-color: initial; border-left-color: initial; border-image: initial; border-top-style: solid; border-top-color: rgb(221, 221, 221); background-color: rgb(255, 255, 255); overflow-wrap: break-word;"><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">.bst</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">bibtex/bst/<em style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; font-style: italic; overflow-wrap: break-word;">packagename</em></td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">BibTeX style</td></tr><tr style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; border-width: 1px 0px 0px; border-right-style: initial; border-bottom-style: initial; border-left-style: initial; border-right-color: initial; border-bottom-color: initial; border-left-color: initial; border-image: initial; border-top-style: solid; border-top-color: rgb(221, 221, 221); background-color: rgb(247, 247, 247); overflow-wrap: break-word;"><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">.cls</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">tex/latex/base</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">Document class file</td></tr><tr style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; border-width: 1px 0px 0px; border-right-style: initial; border-bottom-style: initial; border-left-style: initial; border-right-color: initial; border-bottom-color: initial; border-left-color: initial; border-image: initial; border-top-style: solid; border-top-color: rgb(221, 221, 221); background-color: rgb(255, 255, 255); overflow-wrap: break-word;"><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">.dvi</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">doc</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">package documentation</td></tr><tr style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; border-width: 1px 0px 0px; border-right-style: initial; border-bottom-style: initial; border-left-style: initial; border-right-color: initial; border-bottom-color: initial; border-left-color: initial; border-image: initial; border-top-style: solid; border-top-color: rgb(221, 221, 221); background-color: rgb(247, 247, 247); overflow-wrap: break-word;"><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">.enc</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">fonts/enc</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">Font encoding</td></tr><tr style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; border-width: 1px 0px 0px; border-right-style: initial; border-bottom-style: initial; border-left-style: initial; border-right-color: initial; border-bottom-color: initial; border-left-color: initial; border-image: initial; border-top-style: solid; border-top-color: rgb(221, 221, 221); background-color: rgb(255, 255, 255); overflow-wrap: break-word;"><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">.fd</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">tex/latex/mfnfss</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">Font Definition files for METAFONT fonts</td></tr><tr style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; border-width: 1px 0px 0px; border-right-style: initial; border-bottom-style: initial; border-left-style: initial; border-right-color: initial; border-bottom-color: initial; border-left-color: initial; border-image: initial; border-top-style: solid; border-top-color: rgb(221, 221, 221); background-color: rgb(247, 247, 247); overflow-wrap: break-word;"><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">.fd</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">tex/latex/psnfss</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">Font Definition files for PostScript Type 1 fonts</td></tr><tr style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; border-width: 1px 0px 0px; border-right-style: initial; border-bottom-style: initial; border-left-style: initial; border-right-color: initial; border-bottom-color: initial; border-left-color: initial; border-image: initial; border-top-style: solid; border-top-color: rgb(221, 221, 221); background-color: rgb(255, 255, 255); overflow-wrap: break-word;"><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">.map</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">fonts/map/</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">Font mapping files</td></tr><tr style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; border-width: 1px 0px 0px; border-right-style: initial; border-bottom-style: initial; border-left-style: initial; border-right-color: initial; border-bottom-color: initial; border-left-color: initial; border-image: initial; border-top-style: solid; border-top-color: rgb(221, 221, 221); background-color: rgb(247, 247, 247); overflow-wrap: break-word;"><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">.mf</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">fonts/source/public/<em style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; font-style: italic; overflow-wrap: break-word;">typeface</em></td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">METAFONT outline</td></tr><tr style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; border-width: 1px 0px 0px; border-right-style: initial; border-bottom-style: initial; border-left-style: initial; border-right-color: initial; border-bottom-color: initial; border-left-color: initial; border-image: initial; border-top-style: solid; border-top-color: rgb(221, 221, 221); background-color: rgb(255, 255, 255); overflow-wrap: break-word;"><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">.pdf</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">doc</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">package documentation</td></tr><tr style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; border-width: 1px 0px 0px; border-right-style: initial; border-bottom-style: initial; border-left-style: initial; border-right-color: initial; border-bottom-color: initial; border-left-color: initial; border-image: initial; border-top-style: solid; border-top-color: rgb(221, 221, 221); background-color: rgb(247, 247, 247); overflow-wrap: break-word;"><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">.pfb</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">fonts/type1/<em style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; font-style: italic; overflow-wrap: break-word;">foundry</em>/<em style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; font-style: italic; overflow-wrap: break-word;">typeface</em></td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">PostScript Type 1 outline</td></tr><tr style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; border-width: 1px 0px 0px; border-right-style: initial; border-bottom-style: initial; border-left-style: initial; border-right-color: initial; border-bottom-color: initial; border-left-color: initial; border-image: initial; border-top-style: solid; border-top-color: rgb(221, 221, 221); background-color: rgb(255, 255, 255); overflow-wrap: break-word;"><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">.sty</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">tex/latex/<em style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; font-style: italic; overflow-wrap: break-word;">packagename</em></td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">Style file: the normal package content</td></tr><tr style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; border-width: 1px 0px 0px; border-right-style: initial; border-bottom-style: initial; border-left-style: initial; border-right-color: initial; border-bottom-color: initial; border-left-color: initial; border-image: initial; border-top-style: solid; border-top-color: rgb(221, 221, 221); background-color: rgb(247, 247, 247); overflow-wrap: break-word;"><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">.tex</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">doc</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">TeX source for package documentation</td></tr><tr style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; border-width: 1px 0px 0px; border-right-style: initial; border-bottom-style: initial; border-left-style: initial; border-right-color: initial; border-bottom-color: initial; border-left-color: initial; border-image: initial; border-top-style: solid; border-top-color: rgb(221, 221, 221); background-color: rgb(255, 255, 255); overflow-wrap: break-word;"><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">.tex</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">tex/plain/<em style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; font-style: italic; overflow-wrap: break-word;">packagename</em></td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">Plain TeX macro files</td></tr><tr style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; border-width: 1px 0px 0px; border-right-style: initial; border-bottom-style: initial; border-left-style: initial; border-right-color: initial; border-bottom-color: initial; border-left-color: initial; border-image: initial; border-top-style: solid; border-top-color: rgb(221, 221, 221); background-color: rgb(247, 247, 247); overflow-wrap: break-word;"><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">.tfm</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">fonts/tfm/<em style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; font-style: italic; overflow-wrap: break-word;">foundry</em>/<em style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; font-style: italic; overflow-wrap: break-word;">typeface</em></td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">TeX Font Metrics for METAFONT and Type 1 fonts</td></tr><tr style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; border-width: 1px 0px 0px; border-right-style: initial; border-bottom-style: initial; border-left-style: initial; border-right-color: initial; border-bottom-color: initial; border-left-color: initial; border-image: initial; border-top-style: solid; border-top-color: rgb(221, 221, 221); background-color: rgb(255, 255, 255); overflow-wrap: break-word;"><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">.ttf</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">fonts/truetype/<em style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; font-style: italic; overflow-wrap: break-word;">foundry</em>/<em style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; font-style: italic; overflow-wrap: break-word;">typeface</em></td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">TrueType font</td></tr><tr style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; border-width: 1px 0px 0px; border-right-style: initial; border-bottom-style: initial; border-left-style: initial; border-right-color: initial; border-bottom-color: initial; border-left-color: initial; border-image: initial; border-top-style: solid; border-top-color: rgb(221, 221, 221); background-color: rgb(247, 247, 247); overflow-wrap: break-word;"><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">.vf</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">fonts/vf/<em style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; font-style: italic; overflow-wrap: break-word;">foundry</em>/<em style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; font-style: italic; overflow-wrap: break-word;">typeface</em></td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">TeX virtual fonts</td></tr><tr style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; border-width: 1px 0px 0px; border-right-style: initial; border-bottom-style: initial; border-left-style: initial; border-right-color: initial; border-bottom-color: initial; border-left-color: initial; border-image: initial; border-top-style: solid; border-top-color: rgb(221, 221, 221); background-color: rgb(255, 255, 255); overflow-wrap: break-word;"><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">others</td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">tex/latex/<em style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 0px; font-style: italic; overflow-wrap: break-word;">packagename</em></td><td style="box-sizing: border-box; outline: 0px; margin: 0px; padding: 8px; font-weight: normal; overflow-wrap: break-word; border: 1px solid rgb(170, 170, 170); font-size: 14px; color: rgb(79, 79, 79); line-height: 22px; text-align: left;">other types of file unless instructed otherwise</td></tr></tbody></table>

（d）**更新索引：**最后更新Latex发行版的索引文件，以便Latex发行版能找到新安装的宏包。不同的发行版使用了不同的索引器：

-   teTeX, TeX Live, fpTeX：texhash.  
    
-   web2c: mktexlsr  
    
-   MacTeX: MacTeX appears to do this for you.
-   MikTeX: initexmf --update-fndb；或者使用GUI，即Start -> All Programs -> MikTex -> Settings(admin)下第一个tab，点击“Refresh FNDB”按钮即可。  
    

```
Media will be written to ./media\. You can change this behavior with the --media_dir flag.
C:\Users\admin\Documents\Tridu33\!Py\!3b1b-video\manim\manimlib\mobject\svg\svg_mobject.py:125: UserWarning: g3-45 not recognized
  warnings.warn("%s not recognized" % ref)
C:\Users\admin\Documents\Tridu33\!Py\!3b1b-video\manim\manimlib\mobject\svg\svg_mobject.py:125: UserWarning: g2-135 not recognized
  warnings.warn("%s not recognized" % ref)
C:\Users\admin\Documents\Tridu33\!Py\!3b1b-video\manim\manimlib\mobject\svg\svg_mobject.py:125: UserWarning: g1-87 not recognized
  warnings.warn("%s not recognized" % ref)
C:\Users\admin\Documents\Tridu33\!Py\!3b1b-video\manim\manimlib\mobject\svg\svg_mobject.py:125: UserWarning: g0-38 not recognized
  warnings.warn("%s not recognized" % ref)

```

# （e）www.tug.org/fonts/fontinstall.html
**更新字体映射图：**如果一个宏包还顺带安装了一些字体，还应该更新字体的映射。initexmf --edit-config-file updmap详细方法参详[这里](http://www.tug.org/fonts/fontinstall.html)。
MIKTEX
首先，编辑映射配置文件updmap.cfg，如下所示。在DOS /命令提示符窗口中，运行：
initexmf --edit-config-file updmap
您需要在记事本等文本编辑器中编辑它。
其次，将这一行添加到updmap.cfg并保存：
Map newfont.map

三，返回DOS提示符，运行：
initexmf --mkmaps
（忽略任何错误消息。）


https://blog.csdn.net/memray/article/details/45248259
安装宏包教程

C:\Users\admin>tex testfont
This is TeX, Version 3.14159265 (MiKTeX 2.9.7050 64-bit)

("C:/Users/admin/AppData/Local/Programs/MiKTeX 2.9/tex/plain/knuth-lib/testfont
.tex"
Name of the font to test = unisong4e
Now type a test command (\help for help):)
*\help

\init switches to another font;
\end or \bye finishes the run;
\table prints the font layout in tabular format;
\text prints a sample text, assuming TeX text font conventions;
\sample combines \table and \text;
\mixture mixes a background character with a series of others;
\alternation interleaves a background character with a series;
\alphabet prints all lowercase letters within a given background;
\ALPHABET prints all uppercase letters within a given background;
\series prints a series of letters within a given background;
\lowers prints a comprehensive test of lowercase;
\uppers prints a comprehensive test of uppercase;
\digits prints a comprehensive test of numerals;
\math prints a comprehensive test of TeX math italic;
\names prints a text that mixes upper and lower case;
\punct prints a punctuation test;
\bigtest combines many of the above routines;
\help repeats this message;
and you can use ordinary TeX commands (e.g., to \input a file).
*...

*\ table

*\bye
[1]
Output written on testfont.dvi (1 page, 312 bytes).
Transcript written on testfont.log.









https://talkingphysics.wordpress.com/2019/01/08/getting-started-animating-with-manim-and-python-3-7/




用法：manim.py [-h] [-p] [-w] [-s] [-l] [-m] [--high_quality] [-g] [-i] [-f]
                
[-t] [-q] [-a] [-o FILE_NAME] [-n START_AT_ANIMATION_NUMBER]
                
[-r RESOLUTION] [-c COLOR] [--sound] [--leave_progress_bars]
                
[--media_dir MEDIA_DIR]
                
[--video_dir VIDEO_DIR | 
--video_output_dir VIDEO_OUTPUT_DIR]
                
[--tex_dir TEX_DIR] [--livestream] [ -  to-twitch]
                
[--with-key TWITCH_KEY]
                
[file] [scene_names [scene_names ...]]


位置参数：
  
保存场景的python代码的文件的文件路径
  
scene_names要查看的Scene类的名称


可选参数：
  
-h， -  help显示此帮助消息并退出
  
-p， -  preview一旦完成，自动打开保存的文件
  
-w， -  write_to_movie将场景渲染为影片文件
  
-s， -  save_last_frame
                        
保存最后一帧
  
-l， -  low_quality以低质量渲染（以便更快地渲染）
  
-m， -  medium_quality以中等质量渲染
  
--high_quality以高品质渲染
  
-g， -  save_pngs将每个帧保存为png
  
-i， -  save_as_gif将视频另存为gif
  
-f， -  show_file_in_finder
                        
在finder中显示输出文件
  
-t， -  transarent向具有Alpha通道的电影文件渲染
  
-q， -  quiet
  
-a， -  write_all写入文件中的所有场景
  
-o FILE_NAME， -  file_name FILE_NAME
                        
指定输出文件的名称，ifit应该是
                        
不同于场景类名
  
-n START_AT_ANIMATION_NUMBER， -  START_at_animation_number START_AT_ANIMATION_NUMBER
                        
不是从第一个动画开始渲染，而是从
                        
另一个，由其索引指定。
如果你通过两个
                        
逗号分隔值，例如
“3,6”，它将结束
                        
渲染第二个值
  
-r RESOLUTION， - 分辨率解决方案
                        
分辨率，作为“高度，宽度”传递
  
-c COLOR， -  color COLOR
                        
背景颜色
  
--sound播放成功/失败声音
  
--leave_progress_bars
                        
在终端中显示进度条
  
--media_dir MEDIA_DIR
                        
目录写媒体
  
--video_dir VIDEO_DIR
                        
用于编写视频文件树的目录
  
--video_output_dir VIDEO_OUTPUT_DIR
                        
目录写视频
  
--tex_dir TEX_DIR目录写tex
  
--livestream以流模式运行
  
 - 抽搐流到抽搐
  
--with-key TWITCH_KEY
                        
用于抽搐的流键












python -m manim manim_tutorial_P37-sumiao.py Waving -pl
Media will be written to ./media\. You can change this behavior with the --media_dir flag.

File ready at C:\Users\admin\Documents\Tridu33\!Py\!3b1b-video\manim\media\videos\manim_tutorial_P37-sumiao\480p15\Waving.mp4

Played 4 animations


# 教程manim





https://blog.csdn.net/YinShiJiaW/article/details/94409981













