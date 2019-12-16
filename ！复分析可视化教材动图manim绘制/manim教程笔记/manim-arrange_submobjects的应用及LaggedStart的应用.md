# manim-arrange_submobjects的应用及LaggedStart的应用




————————————————
版权声明：本文为CSDN博主「wsx_9999」的原创文章，遵循 CC 4.0 BY-SA 版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/wsx_9999/article/details/102673351


这是example_scenes.py中的代码

```python
class example(Scene):
    def construct(self):
        title = TextMobject("This is some \\LaTeX")
        basel = TexMobject(
            "\\sum_{n=1}^\\infty "
            "\\frac{1}{n^2} = \\frac{\\pi^2}{6}"
        )
        VGroup(title, basel).arrange_submobjects(DOWN)
        self.play(
            Write(title),
            FadeInFrom(basel, UP),
        )
        self.wait()
        self.play(
            FadeOutAndShift(title,UP),
            LaggedStart(FadeOutAndShiftDown, basel),
        )
        self.wait()
```

重点关注VGroup的arrange_submobjects的应用：

```
  VGroup(title, basel).arrange_submobjects(DOWN)
```

以及LaggedStart的应用：

```
LaggedStart(FadeOutAndShiftDown, basel),
```

让我困惑的是，LaggedStart只能对FadeOutAndShiftDown起作用：

```
self.play(LaggedStart(FadeOutAndShift(title,UP))
```

对于FadeOutAndShift()会报错。
因此为了将LaggedStart()应用于FadeOutAndShift(title,UP)，我们可以仿造FadeOutAndShiftDown()，建立FadeOutAndShiftUp()。
打开manimlib\animation\creation.py
```

class FadeOutAndShift(FadeOut):
    CONFIG = {
        "direction": DOWN,
    }

    def __init__(self, mobject, direction=None, **kwargs):
        FadeOut.__init__(self, mobject, **kwargs)
        if direction is None:
            direction = self.direction
        self.target_mobject.shift(direction)


class FadeOutAndShiftDown(FadeOutAndShift):
    CONFIG = {
        "direction": DOWN,
    }
class FadeOutAndShiftUp(FadeOutAndShift):
    CONFIG = {
        "direction": UP,
    }
class FadeOutAndShiftLeft(FadeOutAndShift):
    CONFIG = {
        "direction": LEFT,
    }
class FadeOutAndShiftRight(FadeOutAndShift):
    CONFIG = {
        "direction": RIGHT,
    }

```
然后利用它们：
```

class example(Scene):
    def construct(self):
        title = TextMobject("This is some \\LaTeX")
        basel = TexMobject(
            "\\sum_{n=1}^\\infty "
            "\\frac{1}{n^2} = \\frac{\\pi^2}{6}"
        )
        VGroup(title, basel).arrange_submobjects(DOWN)
        self.play(
            Write(title),
            FadeInFrom(basel, UP),
        )
        self.wait()
        self.play(
            LaggedStart(FadeOutAndShiftUp,title),
            LaggedStart(FadeOutAndShiftDown, basel),
        )
        self.wait()




```


闪退效果做出来了。











































