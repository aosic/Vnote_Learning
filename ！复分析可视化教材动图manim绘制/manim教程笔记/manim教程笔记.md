[TOC]






------------------------------------

Grant Sanderson
3b1b
# manim教程笔记


物理大佬教学
https://talkingphysics.wordpress.com/2019/01/08/getting-started-animating-with-manim-and-python-3-7/

官方教程
https://www.eulertour.com/learn/manim/getting_started/index.html

github仓库
https://github.com/3b1b/manim#using-manim

外文教程很多，github源码就是最好的教程，已经有很多包在github一搜就有，本地目录：!manim_help
所有旧版文件通通把$big_ol_pile_of_manim_imports$更换成为

```python

# -*- coding: utf-8 -*-
'''
>File Name      :MyPractise.py

'''

from manimlib.imports import *
```



鹏程万里Tony写的：

[https://github.com/Tony031218/manim-projects](https://github.com/Tony031218/manim-projects)

cigar666写的内容：

https://www.bilibili.com/video/av42621196/
常见问题记录1
https://blog.csdn.net/bababi/article/details/84640840
第一阶段性总结

https://blog.csdn.net/YinShiJiaW/article/details/94409981

第二阶段性总结
https://blog.csdn.net/YinShiJiaW/article/details/95393683
https://www.bilibili.com/video/av52591210

工程结构理解
https://blog.csdn.net/YinShiJiaW/article/details/93586984

Bilibli的教程



https://www.bilibili.com/read/cv2539928?from=articleDetail  （1）

https://www.bilibili.com/read/cv2579540   教程latex，文字贴图（2）

https://www.bilibili.com/read/cv2650778/ 牛逼（3）





```python

python -m manim example_scenes.py SquareToCircle -pl
python -m manim example_scenes.py OpeningManimExample -pl


```

texlive-fonts-extra 字体包
texlive-science 数学物理计算机科学的包

中文









# help






```python
python -m manim example_scenes.py SquareToCircle -pl
```

命令中，python解析器，manim.py以脚本方式执行的python文件，example_scenes.py用户文件名，SquareToCircle 是用户文件里的类名，表示执行该命令，还有很多参数api，下面介绍：

[^_^]:
    注释 (`>>`).
    
程序执行流程：主程序入口manim.py进入manimlib.main()

[//]: #(python文件有一个内置属性，__name__，如果它是一个被执行的脚本文件，那么它的值就会变成"__main__"，否则就是自身文件名，我们知道程序的入口只能有一个，python也不例外，解释器会寻找到__name__的值为"__main__"的文件并将它当作唯一脚本来执行)


根目录文件命令以及对应功能，正在调试进行中的文件名称为$demo.py$


帮助

``` python
python -m  manim --help
usage: manim.py [-h] [-p] [-w] [-s] [-l] [-m] [--high_quality] [-g] [-i] [-f]
                [-t] [-q] [-a] [-o FILE_NAME] [-n START_AT_ANIMATION_NUMBER从动画编号开始]
                [-r 分辨率RESOLUTION] [-c COLOR] [--sound] [--leave_progress_bars]
                [--media_dir MEDIA_DIR]
                [--video_dir VIDEO_DIR | --video_output_dir VIDEO_OUTPUT_DIR]
                [--tex_dir TEX_DIR] [--livestream] [--to-twitch]
                [--with-key TWITCH_KEY]
                [file] [scene_names [scene_names ...]]

positional arguments:
  file                  path to file holding the python code for the scene包含场景的python代码的文件的路径
  scene_names           Name of the Scene class you want to see您要查看的Scene类的名称

optional arguments:
  -h, --help            show this help message and exit
  -p, --preview         Automatically open the saved file once its done完成后自动打开预览保存的文件

  -w, --write_to_movie  Render the scene as a movie file将场景渲染为电影文件
  -s, --save_last_frame 保存最后一帧Save the last frame
  -l, --low_quality     Render at a low quality (for faster rendering)快低质量渲染
  -m, --medium_quality  Render at a medium quality 中质量
  --high_quality        Render at a high quality 高质量
  -g, --save_pngs       Save each frame as a png 每帧保存png
  -i, --save_as_gif     Save the video as gif 视频保存为gif
  -f, --show_file_in_finder    Show the output file in finder 在finder中显示输出文件
  -t, --transparent     Render to a movie file with an alpha channel使用Alpha通道渲染到电影文件
  -q, --quiet
  -a, --write_all       Write all the scenes from a file写一个文件中所有场景
  -o FILE_NAME, --file_name FILE_NAME
                        Specify the name of the output file, ifit should be different from the scene class name指定输出文件的名称（如果它与场景类名称不同）
  -n START_AT_ANIMATION_NUMBER, --start_at_animation_number START_AT_ANIMATION_NUMBER
Start rendering not from the first animation, but from another, specified by its index. If you passin two comma separated values, e.g. "3,6", it will end the rendering at the second value不从第一个动画开始渲染，而是从其索引指定的另一个动画开始渲染。如果您传入两个逗号分隔的值，例如“ 3,6”，它将在第二个值处结束渲染
  -r RESOLUTION, --resolution RESOLUTION
                        Resolution, passed as "height,width"分辨率，“高度，宽度”传递
  -c COLOR, --color COLOR
                        Background color背景色
  --sound               Play a success/failure sound成功失败显示声音
  --leave_progress_bars
                        Leave progress bars displayed in terminal保持进度条显示在终端中
  --media_dir MEDIA_DIR
                        directory to write media写入多媒体路径
  --video_dir VIDEO_DIR
                        directory to write file tree for video写入视频文件树的目录
  --video_output_dir VIDEO_OUTPUT_DIR
                        directory to write video 编写视频的目录
  --tex_dir TEX_DIR     directory to write tex 写写入text路径
  --livestream          Run in streaming mode流模式
  --to-twitch           Stream to twitch
  --with-key TWITCH_KEY
                        Stream key for twitch

```
第一个和第二个命令行参数是必须给出的（哪个文件里哪个模块），而且必须要按顺序（可以区分的参数不用按照顺序，不可以区分的要按照顺序），之后都是可选参数。再往下面就是对获取到的命令行参数的提取，最后是对这些参数的使用，我们最终把这个包含参数的args对象返回出去给外部使用。



config.py命令行参数解析

```python 




def parse_cli():
    try:
        parser = argparse.ArgumentParser()
        module_location = parser.add_mutually_exclusive_group()
        module_location.add_argument(
            "file",
            nargs="?",
            help="path to file holding the python code for the scene源py代码路径",
        )
        parser.add_argument(
            "scene_names",
            nargs="*",
            help="Name of the Scene class you want to see场景类想看到的",
        )
        parser.add_argument(
            "-p", "--preview",
            action="store_true",
            help="Automatically open the saved file once its done一旦完成自动打开保存的文件",
        ),
        parser.add_argument(
            "-w", "--write_to_movie",
            action="store_true",
            help="Render the scene as a movie file写视频文件",
        ),
        parser.add_argument(
            "-s", "--save_last_frame",
            action="store_true",
            help="Save the last frame保存最后一帧",
        ),
        parser.add_argument(
            "-l", "--low_quality",
            action="store_true",
            help="Render at a low quality (for faster rendering)低质量渲染",
        ),
        parser.add_argument(
            "-m", "--medium_quality",
            action="store_true",
            help="Render at a medium quality中等质量渲染",
        ),
        parser.add_argument(
            "--high_quality",
            action="store_true",
            help="Render at a high quality高品质渲染高质量渲染",
        ),
        parser.add_argument(
            "-g", "--save_pngs",
            action="store_true",
            help="Save each frame as a png每帧保存图片Png",
        ),
        parser.add_argument(
            "-i", "--save_as_gif",
            action="store_true",
            help="Save the video as gif视频保存gif",
        ),
        parser.add_argument(
            "-f", "--show_file_in_finder",
            action="store_true",
            help="在finder中显示输出文件Show the output file in finder",
        ),
        parser.add_argument(
            "-t", "--transparent",
            action="store_true",
            help="Render to a movie file with an alpha channel使用Alpha通道渲染到电影文件",
        ),
        parser.add_argument(
            "-q", "--quiet",
            action="store_true",
            help="",
        ),
        parser.add_argument(
            "-a", "--write_all",
            action="store_true",
            help="Write all the scenes from a file写文件中所有视频",
        ),
        parser.add_argument(
            "-o", "--file_name",
            help="Specify the name of the output file, if"
                 "it should be different from the scene class name输出文件命名",
        )
        parser.add_argument(
            "-n", "--start_at_animation_number",
            help="Start rendering not from the first animation, but"
                 "from another, specified by its index.  If you pass"
                 "in two comma separated values, e.g. \"3,6\", it will end"
                 "the rendering at the second value从第三帧到第六帧",
        )
        parser.add_argument(
            "-r", "--resolution",
            help="Resolution, passed as \"height,width\"分辨率",
        )
        parser.add_argument(
            "-c", "--color",
            help="Background color背景色,eg:#ffffff",
        )
        parser.add_argument(
            "--sound",
            action="store_true",
            help="Play a success/failure sound",
        )
        parser.add_argument(
            "--leave_progress_bars",
            action="store_true",
            help="Leave progress bars displayed in terminal保持进度条显示在终端中",
        )
        parser.add_argument(
            "--media_dir",
            help="directory to write media多媒体目录",
        )
        video_group = parser.add_mutually_exclusive_group()
        video_group.add_argument(
            "--video_dir",
            help="directory to write file tree for video",
        )
        video_group.add_argument(
            "--video_output_dir",
            help="directory to write video写视频目录",
        )
        parser.add_argument(
            "--tex_dir",
            help="directory to write tex写latex文件目录",
        )

        # For live streaming
        module_location.add_argument(
            "--livestream",
            action="store_true",
            help="Run in streaming mode",
        )
        parser.add_argument(
            "--to-twitch",
            action="store_true",
            help="Stream to twitch",
        )
        parser.add_argument(
            "--with-key",
            dest="twitch_key",
            help="Stream key for twitch",
        )
        args = parser.parse_args()

        if args.file is None and not args.livestream:
            parser.print_help()
            sys.exit(2)
        if args.to_twitch and not args.livestream:
            print("You must run in streaming mode in order to stream to twitch")
            sys.exit(2)
        if args.to_twitch and args.twitch_key is None:
            print("Specify the twitch stream key with --with-key用--with-key指定切换视频流制作键")
            sys.exit(2)
        return args
    except argparse.ArgumentError as err:
        print(str(err))
        sys.exit(2)



```
渲染命令选项

```python 
# To watch one of these scenes, run the following:
# python -m manim example_scenes.py SquareToCircle -pl
# python -m 打开manim.py入口文件里面的AquareToCircle类
# Use the flat -l for a faster rendering at a lower低质量快速渲染看
# quality.
# Use -s to skip to the end and just save the final frame调到保存最后一帧
# Use the -p to have the animation (or image, if -s was used) pop up once done.完成后，使用-p自动弹出动画（或图像，如果使用-s的话）。
# Use -n <number> to skip ahead to the n'th animation of a scene.跳到第n帧动画场景
# Use -r <number> to specify a resolution (for example, -r 1080 for a 1920x1080分辨率 video)

```




# Manim[Constants](https://www.eulertour.com/learn/manim/constants.html#manim-constants "固定到该标题")

该`constants.py`下`manimlib/`包含了设置和运行manim过程中使用的变量。此处未记录某些变量，因为它们仅由manim内部使用。

## [Index](https://www.eulertour.com/learn/manim/constants.html#directories "固定到该标题")

> MEDIA_DIR
> 
> 如果未通过标志指定创建目录`VIDEO_DIR`和`TEX_DIR`创建目录。
> 
> VIDEO_DIR
> 
> 用于存储Manim渲染的场景。场景渲染完成后，它将存储在下`VIDEO_DIR/module_name/scene_name/quality/scene_name.mp4`。`MEDIA_DIR`默认情况下创建。
> 
> TEX_DIR
> 
> Latex编写的文件存储在这里。它还充当缓存，这样就不必在每次需要Latex时都重写文件。

如果这些目录不存在，则创建它们。

## [latex](https://www.eulertour.com/learn/manim/constants.html#tex "固定到该标题")

> TEX\_USE\_CTEX
> 
> 布尔值。如果需要使用中文排版，请将其更改为True。
> 
> TEX\_TEXT\_TO_REPLACE
> 
> manim在生成tex文件时使用的占位符文本
> 
> TEMPLATE\_TEX\_FILE
> 
> 默认情况下`manimlib/tex_template.tex`使用。如果`TEX_USE_CTEX`设置为True，则`manimlib/ctex_template.tex`使用。

## [数字常量](https://www.eulertour.com/learn/manim/constants.html#numerical-constants "固定到该标题")

> PI
> 
> 别名 `numpy.pi`
> 
> AU
> 
> PI * 2
> 
> DEGREES
> 
> TAU / 360

## [相机配置](https://www.eulertour.com/learn/manim/constants.html#camera-configuration "固定到该标题")

渲染设置预设

> PRODUCTION\_QUALITY\_CAMERA_CONFIG
> 
> 2560x1440 @ 60fps＃渲染场景时的默认设置
> 
> HIGH\_QUALITY\_CAMERA_CONFIG
> 
> 1920x1080 @ 60帧/秒 ＃在传递`-h`or `--high_quality`标志时使用。
> 
> MEDIUM\_QUALITY\_CAMERA_CONFIG
> 
> 1280x720 @ 30fps。＃在 传递`-m`or `--medium_quality`标志时使用。
> 
> LOW\_QUALITY\_CAMERA_CONFIG
> 
> 854x480 @ 15fps。＃在传递`-l`or `--low_quality`标志时使用。

## [坐标](https://www.eulertour.com/learn/manim/constants.html#coordinates "固定到该标题")

用于2d / 3d动画和放置：

```python
ORIGIN
UP
DOWN
RIGHT
LEFT
IN # 3d camera only, away from camera
OUT # 3d camera only, close to camera

UL = UP + LEFT # diagonal abbreviations. You can use either one
UR = UP + RIGHT
DL = DOWN + LEFT
DR = DOWN + RIGHT

TOP
BOTTOM
LEFT_SIDE
RIGHT_SIDE
```

## [颜色](https://www.eulertour.com/learn/manim/constants.html#colors "固定到该标题")

> COLOR_MAP
> 
> 预定义的颜色图
> 
> 调色板
> 
> 从COLOR_MAP派生的彩色十六进制字符串列表





































































































































































































































