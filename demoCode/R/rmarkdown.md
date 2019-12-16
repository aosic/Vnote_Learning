# rmarkdown






https://rmarkdown.rstudio.com/lesson-2.html

运行时render，R Markdown将.Rmd文件提供给knitr https://yihui.name/knitr/ ⧉，该文件将执行所有代码块并创建一个新的markdown（.md）文档，其中包括代码及其输出。

然后，由knitr生成的markdown文件由负责创建最终格式的pandoc processed处理。

这听起来可能很复杂，但是R Markdown通过将上述所有处理封装到一个render函数中使其变得非常简单。



R包
r-pkgs.had.co.nz/description.html




