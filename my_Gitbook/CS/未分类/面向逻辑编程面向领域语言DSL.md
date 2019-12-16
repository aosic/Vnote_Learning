

作者：匿名用户  
链接：https://www.zhihu.com/question/34416029/answer/130195618  
来源：知乎  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。  
  

如果 Dan 老师的 The reasoned schemer 没时间看，要简单，就是 microKanren 了，[2013 Scheme Workshop paper](https://link.zhihu.com/?target=http%3A//minikanren.org/%23microKanrenPaper)

核心代码没几行： [microKanren/microKanren.scm at master · jasonhemann/microKanren · GitHub](https://link.zhihu.com/?target=https%3A//github.com/jasonhemann/microKanren/blob/master/microKanren.scm)

```scheme
(define (unify u v s)
  (let ((u (walk u s)) (v (walk v s)))
    (cond
      ((and (var? u) (var? v) (var=? u v)) s)
      ((var? u) (ext-s u v s))
      ((var? v) (ext-s v u s))
      ((and (pair? u) (pair? v))
       (let ((s (unify (car u) (car v) s)))
         (and s (unify (cdr u) (cdr v) s))))
      (else (and (eqv? u v) s)))))

```

  

如果没时间看 microKanren 的 paper 就想知道 unification 干什么的，那就看看 Kent 老师的TSPL的例子咯 [Extended Examples](https://link.zhihu.com/?target=http%3A//www.scheme.com/tspl4/examples.html%23g204)

多说2句， 要对 miniKanren 和 Prolog 做比较是非常狡猾了，它们有不同的设计哲学，做不同的 trade-off，严格来说是不同的语系，能怎么比? (SWI-Prolog vs core.logic ?)






miniKanren的实现不就是合一和回溯么，这有什么难理解的。而且不知道比Prolog丑到哪里去了 (逃

合一看 [Relational programming in miniKanren: Techniques, applications, and implementations](https://link.zhihu.com/?target=http%3A//gradworks.umi.com/33/80/3380156.html)  
回溯看 [Structure and Interpretation of Computer Programs](https://link.zhihu.com/?target=http%3A//mitpress.mit.edu/sicp/full-text/book/book-Z-H-28.html)  
优美的Prolog看 [Warren's Abstract Machine: A Tutorial Reconstruction](https://link.zhihu.com/?target=http%3A//wambook.sourceforge.net/)

  
  
作者：bhuztez  
链接：https://www.zhihu.com/question/34416029/answer/58588651  
来源：知乎  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
















































































































































