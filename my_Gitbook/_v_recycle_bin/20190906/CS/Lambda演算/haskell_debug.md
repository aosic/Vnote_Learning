# haskell_debug

技巧BVM脑力虚拟机

https://www.jianshu.com/p/57523e147480

```haskell
import Debug.Trace

funct :: Integer -> [Integer] -> Bool 
funct a list = trace (show list) $ funct (a + 1) (a : list)



```




https://blog.csdn.net/cenfan327/article/details/42496137



https://en.wikibooks.org/wiki/Haskell/Debugging


# debug


https://github.com/ndmitchell/debug








https://wiki.haskell.org/Debugging







