# cabal使用hackage上的包

本电脑全局安装位置：C:\Users\admin\AppData\Roaming\cabal\packages\hackage.haskell.org


本机hi  o全局文件位置：C:\Users\admin\AppData\Roaming\cabal\x86_64-windows-ghc-8.6.3

sandbox沙盒本地安装会不一样。

cabal v2-build就行




```

Packages GHC can use
    | 
Are registered with "ghc-pkg register"
    |
And (almost always) built with Cabal
    |
With build dependencies resolved by cabal-install
    |
From Hackage.


```


## 卸载

如果在sandbox外：

ghc-pkg unregister --force regex-compat-0.95.1

如果在一个[cabal sandbox](http://www.haskell.org/cabal/users-guide/installing-packages.html#developing-with-sandboxes)内：

cabal sandbox hc-pkg -- unregister attoparsec --force










cygwin效果


```


admin@Tridu /cygdrive/c/Users/admin/Desktop/!hush/flourierDraw_jpeg_svg/reanimation/reanimate-master
$ cabal install reanimate
Warning: The install command is a part of the legacy v1 style of cabal usage.

Please switch to using either the new project style and the new-install
command or the legacy v1-install alias as new-style projects will become the
default in the next version of cabal-install. Please file a bug if you cannot
replicate a working v1- use case with the new-style commands.

For more information, see: https://wiki.haskell.org/Cabal/NewBuild

Resolving dependencies...
Notice: installing into a sandbox located at
C:\Users\admin\Desktop\!hush\flourierDraw_jpeg_svg\reanimation\reanimate-master\.cabal-sandbox
Starting     MemoTrie-0.6.9
Starting     async-2.2.2
Starting     case-insensitive-1.2.1.0
Starting     ansi-terminal-0.9.1
Building     async-2.2.2
Building     MemoTrie-0.6.9
Building     case-insensitive-1.2.1.0
Building     ansi-terminal-0.9.1
Completed    case-insensitive-1.2.1.0
Starting     contravariant-1.5.2
Completed    MemoTrie-0.6.9
Starting     data-default-instances-containers-0.0.1
Completed    async-2.2.2
Starting     data-default-instances-dlist-0.0.1
Building     contravariant-1.5.2
Building     data-default-instances-containers-0.0.1
Building     data-default-instances-dlist-0.0.1
Completed    data-default-instances-containers-0.0.1
Downloading  data-default-instances-old-locale-0.0.1
Completed    data-default-instances-dlist-0.0.1
Starting     network-3.0.1.1
Completed    contravariant-1.5.2
Starting     parallel-3.2.2.0
Downloaded   data-default-instances-old-locale-0.0.1
Starting     data-default-instances-old-locale-0.0.1
Building     parallel-3.2.2.0
Building     data-default-instances-old-locale-0.0.1
Completed    ansi-terminal-0.9.1
Starting     primitive-0.7.0.0
Completed    data-default-instances-old-locale-0.0.1
Starting     random-1.1
Completed    parallel-3.2.2.0
Downloading  reflection-2.1.4
Building     primitive-0.7.0.0
Downloaded   reflection-2.1.4
Starting     reflection-2.1.4
Building     random-1.1
Building     reflection-2.1.4
Completed    random-1.1
Downloading  semigroups-0.18.5
Downloaded   semigroups-0.18.5
Starting     semigroups-0.18.5
Completed    reflection-2.1.4
Downloading  split-0.2.3.3
Downloaded   split-0.2.3.3
Starting     split-0.2.3.3
Completed    primitive-0.7.0.0
Downloading  tagged-0.8.6
Downloaded   tagged-0.8.6
Starting     tagged-0.8.6
Building     split-0.2.3.3
Building     semigroups-0.18.5
Building     tagged-0.8.6
Completed    semigroups-0.18.5
Downloading  th-abstraction-0.3.1.0
Completed    split-0.2.3.3
Downloading  transformers-compat-0.6.5
Downloaded   th-abstraction-0.3.1.0
Starting     th-abstraction-0.3.1.0
Downloaded   transformers-compat-0.6.5
Starting     transformers-compat-0.6.5
Building     th-abstraction-0.3.1.0
Completed    tagged-0.8.6
Downloading  unix-compat-0.5.2
Building     transformers-compat-0.6.5
Downloaded   unix-compat-0.5.2
Starting     unix-compat-0.5.2
Building     unix-compat-0.5.2
Completed    transformers-compat-0.6.5
Downloading  unordered-containers-0.2.10.0
Downloaded   unordered-containers-0.2.10.0
Starting     unordered-containers-0.2.10.0
Completed    th-abstraction-0.3.1.0
Downloading  void-0.7.3
Building     unordered-containers-0.2.10.0
Downloaded   void-0.7.3
Starting     void-0.7.3
Building     void-0.7.3
Completed    void-0.7.3
Downloading  xml-1.3.14
Completed    unix-compat-0.5.2
Downloading  zlib-0.6.2.1
Downloaded   xml-1.3.14
Starting     xml-1.3.14
Downloaded   zlib-0.6.2.1
Starting     zlib-0.6.2.1
Building     xml-1.3.14
Building     zlib-0.6.2.1
Completed    xml-1.3.14
Downloading  vector-space-0.16
Downloaded   vector-space-0.16
Starting     vector-space-0.16
Completed    unordered-containers-0.2.10.0
Downloading  ansi-wl-pprint-0.6.9
Building     vector-space-0.16
Downloaded   ansi-wl-pprint-0.6.9
Starting     ansi-wl-pprint-0.6.9
Building     ansi-wl-pprint-0.6.9
Completed    ansi-wl-pprint-0.6.9
Downloading  data-default-0.7.1.1
Downloaded   data-default-0.7.1.1
Starting     data-default-0.7.1.1
Completed    vector-space-0.16
Downloading  integration-0.2.1
Downloaded   integration-0.2.1
Starting     integration-0.2.1
Completed    zlib-0.6.2.1
Building     data-default-0.7.1.1
Starting     vector-0.12.0.3
Building     integration-0.2.1
Completed    data-default-0.7.1.1
Downloading  scientific-0.3.6.2
Downloaded   scientific-0.3.6.2
Starting     scientific-0.3.6.2
Building     vector-0.12.0.3
Completed    integration-0.2.1
Downloading  distributive-0.6
Downloaded   distributive-0.6
Starting     distributive-0.6
Building     scientific-0.3.6.2
Building     network-3.0.1.1
Completed    scientific-0.3.6.2
Downloading  transformers-base-0.4.5.2
Downloaded   transformers-base-0.4.5.2
Starting     transformers-base-0.4.5.2
Building     transformers-base-0.4.5.2
Building     distributive-0.6
Completed    transformers-base-0.4.5.2
Downloading  microlens-mtl-0.2.0.1
Completed    distributive-0.6
Downloading  exceptions-0.10.2
Downloaded   microlens-mtl-0.2.0.1
Starting     microlens-mtl-0.2.0.1
Downloaded   exceptions-0.10.2
Starting     exceptions-0.10.2
Building     microlens-mtl-0.2.0.1
Building     exceptions-0.10.2
Completed    microlens-mtl-0.2.0.1
Downloading  MonadRandom-0.5.1.1
Downloaded   MonadRandom-0.5.1.1
Starting     MonadRandom-0.5.1.1
Completed    exceptions-0.10.2
Downloading  microlens-th-0.4.3.2
Downloaded   microlens-th-0.4.3.2
Starting     microlens-th-0.4.3.2
Building     MonadRandom-0.5.1.1
Building     microlens-th-0.4.3.2
Completed    MonadRandom-0.5.1.1
Downloading  fsnotify-0.3.0.1
Downloaded   fsnotify-0.3.0.1
Starting     fsnotify-0.3.0.1
Completed    microlens-th-0.4.3.2
Downloading  svg-builder-0.1.1
Downloaded   svg-builder-0.1.1
Starting     svg-builder-0.1.1
Completed    network-3.0.1.1
Downloading  mfsolve-0.3.2.0
Building     fsnotify-0.3.0.1
Downloaded   mfsolve-0.3.2.0
Starting     mfsolve-0.3.2.0
Building     svg-builder-0.1.1
Building     mfsolve-0.3.2.0
Completed    fsnotify-0.3.0.1
Downloading  optparse-applicative-0.14.3.0
Downloaded   optparse-applicative-0.14.3.0
Starting     optparse-applicative-0.14.3.0
Completed    svg-builder-0.1.1
Downloading  bytes-0.15.5
Downloaded   bytes-0.15.5
Starting     bytes-0.15.5
Completed    mfsolve-0.3.2.0
Downloading  attoparsec-0.13.2.2
Building     optparse-applicative-0.14.3.0
Downloaded   attoparsec-0.13.2.2
Starting     attoparsec-0.13.2.2
Building     attoparsec-0.13.2.2
Building     bytes-0.15.5
Completed    optparse-applicative-0.14.3.0
Downloading  intervals-0.8.1
Downloaded   intervals-0.8.1
Starting     intervals-0.8.1
Completed    bytes-0.15.5
Downloading  comonad-5.0.5
Downloaded   comonad-5.0.5
Starting     comonad-5.0.5
Building     intervals-0.8.1
Building     comonad-5.0.5
Completed    vector-0.12.0.3
Downloading  palette-0.3.0.2
Completed    intervals-0.8.1
Downloading  streaming-commons-0.2.1.1
Downloaded   palette-0.3.0.2
Downloaded   streaming-commons-0.2.1.1
Starting     palette-0.3.0.2
Starting     streaming-commons-0.2.1.1
Building     palette-0.3.0.2
Building     streaming-commons-0.2.1.1
Completed    attoparsec-0.13.2.2
Downloading  matrix-0.3.6.1
Downloaded   matrix-0.3.6.1
Starting     matrix-0.3.6.1
Completed    comonad-5.0.5
Starting     matrices-0.5.0
Building     matrix-0.3.6.1
Building     matrices-0.5.0
Completed    palette-0.3.0.2
Starting     JuicyPixels-3.3.3.1
Building     JuicyPixels-3.3.3.1
Completed    streaming-commons-0.2.1.1
Downloading  bifunctors-5.5.4
Downloaded   bifunctors-5.5.4
Starting     bifunctors-5.5.4
Building     bifunctors-5.5.4
Completed    bifunctors-5.5.4
Downloading  websockets-0.12.5.3
Downloaded   websockets-0.12.5.3
Starting     websockets-0.12.5.3
Completed    matrix-0.3.6.1
Downloading  semigroupoids-5.3.2
Downloaded   semigroupoids-5.3.2
Starting     semigroupoids-5.3.2
Completed    matrices-0.5.0
Downloading  profunctors-5.4
Downloaded   profunctors-5.4
Starting     profunctors-5.4
Building     websockets-0.12.5.3
Building     profunctors-5.4
Building     semigroupoids-5.3.2
Completed    websockets-0.12.5.3
Downloading  cubicbezier-0.6.0.6
Downloaded   cubicbezier-0.6.0.6
Starting     cubicbezier-0.6.0.6
Completed    profunctors-5.4
Downloading  invariant-0.5.3
Downloaded   invariant-0.5.3
Starting     invariant-0.5.3
Building     cubicbezier-0.6.0.6
Building     invariant-0.5.3
Completed    semigroupoids-5.3.2
Downloading  monoid-extras-0.5
Downloaded   monoid-extras-0.5
Starting     monoid-extras-0.5
Completed    invariant-0.5.3
Downloading  free-5.1.1
Downloaded   free-5.1.1
Starting     free-5.1.1
Building     monoid-extras-0.5
Building     free-5.1.1
Completed    monoid-extras-0.5
Downloading  dual-tree-0.2.2
Downloaded   dual-tree-0.2.2
Starting     dual-tree-0.2.2
Building     dual-tree-0.2.2
Completed    dual-tree-0.2.2

Completed    free-5.1.1
Downloading  adjunctions-4.4
Downloaded   adjunctions-4.4
Starting     adjunctions-4.4
Building     adjunctions-4.4
Completed    cubicbezier-0.6.0.6

Completed    adjunctions-4.4
Downloading  kan-extensions-5.2
Downloaded   kan-extensions-5.2
Starting     kan-extensions-5.2
Building     kan-extensions-5.2
Completed    kan-extensions-5.2
Downloading  lens-4.17.1
Downloaded   lens-4.17.1
Starting     lens-4.17.1
Building     lens-4.17.1
Completed    JuicyPixels-3.3.3.1
Completed    lens-4.17.1
Downloading  linear-1.20.9
Downloaded   linear-1.20.9
Starting     linear-1.20.9
Building     linear-1.20.9
Completed    linear-1.20.9
Downloading  reanimate-svg-0.9.0.0
Downloading  force-layout-0.4.0.6
Downloaded   force-layout-0.4.0.6
Downloading  diagrams-core-1.4.1.1
Starting     force-layout-0.4.0.6
Downloaded   reanimate-svg-0.9.0.0
Downloading  active-0.2.0.13
Starting     reanimate-svg-0.9.0.0
Downloaded   diagrams-core-1.4.1.1
Downloaded   active-0.2.0.13
Starting     diagrams-core-1.4.1.1
Starting     active-0.2.0.13
Building     active-0.2.0.13
Building     force-layout-0.4.0.6
Building     diagrams-core-1.4.1.1
Building     reanimate-svg-0.9.0.0
Completed    force-layout-0.4.0.6
Completed    active-0.2.0.13
Completed    diagrams-core-1.4.1.1
Downloading  diagrams-lib-1.4.2.3
Downloaded   diagrams-lib-1.4.2.3
Starting     diagrams-lib-1.4.2.3
Building     diagrams-lib-1.4.2.3
Completed    reanimate-svg-0.9.0.0
Completed    diagrams-lib-1.4.2.3
Downloading  diagrams-svg-1.4.2
Downloading  diagrams-contrib-1.4.3
Downloaded   diagrams-svg-1.4.2
Starting     diagrams-svg-1.4.2
Downloaded   diagrams-contrib-1.4.3
Starting     diagrams-contrib-1.4.3
Building     diagrams-svg-1.4.2
Building     diagrams-contrib-1.4.3
Completed    diagrams-svg-1.4.2
Completed    diagrams-contrib-1.4.3
Downloading  diagrams-1.4
Downloaded   diagrams-1.4
Starting     diagrams-1.4
Building     diagrams-1.4
Completed    diagrams-1.4
Downloading  reanimate-0.1.5.0
Downloaded   reanimate-0.1.5.0
Starting     reanimate-0.1.5.0
Building     reanimate-0.1.5.0
Completed    reanimate-0.1.5.0






```




## 手动安装 

https://wiki.haskell.org/Cabal/How_to_install_a_Cabal_package

## cabal安装

https://wiki.haskell.org/Cabal-Install



cabal官网
https://www.haskell.org/cabal/users-guide/developing-packages.html#developing-packages

## stack安装

stack官网

https://docs.haskellstack.org/en/stable/GUIDE/


```






>stack --help
stack - The Haskell Tool Stack

Usage: stack [--help] [--version] [--numeric-version] [--hpack-numeric-version]
             [--docker*] [--nix*] ([--verbosity VERBOSITY] | [-v|--verbose] |
             [--silent]) [--[no-]time-in-log] [--stack-root STACK-ROOT]
             [--work-dir WORK-DIR] [--[no-]system-ghc] [--[no-]install-ghc]
             [--arch ARCH] [--ghc-variant VARIANT] [--ghc-build BUILD]
             [-j|--jobs JOBS] [--extra-include-dirs DIR] [--extra-lib-dirs DIR]
             [--with-gcc PATH-TO-GCC] [--with-hpack HPACK]
             [--[no-]skip-ghc-check] [--[no-]skip-msys] [--local-bin-path DIR]
             [--[no-]modify-code-page] [--[no-]allow-different-user]
             [--[no-]dump-logs] [--resolver RESOLVER] [--compiler COMPILER]
             [--[no-]terminal] [--color WHEN] [--terminal-width INT]
             [--stack-yaml STACK-YAML] COMMAND|FILE

Available options:
  --help                   Show this help text
  --version                Show version
  --numeric-version        Show only version number
  --hpack-numeric-version  Show only hpack's version number
  --docker*                Run 'stack --docker-help' for details
  --nix*                   Run 'stack --nix-help' for details
  --verbosity VERBOSITY    Verbosity: silent, error, warn, info, debug
  -v,--verbose             Enable verbose mode: verbosity level "debug"
  --silent                 Enable silent mode: verbosity level "silent"
  --[no-]time-in-log       Enable/disable inclusion of timings in logs, for the
                           purposes of using diff with logs
  --stack-root STACK-ROOT  Absolute path to the global stack root directory
                           (Overrides any STACK_ROOT environment variable)
  --work-dir WORK-DIR      Relative path of work directory (Overrides any
                           STACK_WORK environment variable, default is
                           '.stack-work')
  --[no-]system-ghc        Enable/disable using the system installed GHC (on the
                           PATH) if it is available and its version matches.
                           Disabled by default.
  --[no-]install-ghc       Enable/disable downloading and installing GHC if
                           necessary (can be done manually with stack setup)
  --arch ARCH              System architecture, e.g. i386, x86_64
  --ghc-variant VARIANT    Specialized GHC variant, e.g. integersimple
                           (incompatible with --system-ghc)
  --ghc-build BUILD        Specialized GHC build, e.g. 'gmp4' or 'standard'
                           (usually auto-detected)
  -j,--jobs JOBS           Number of concurrent jobs to run
  --extra-include-dirs DIR Extra directories to check for C header files
  --extra-lib-dirs DIR     Extra directories to check for libraries
  --with-gcc PATH-TO-GCC   Use gcc found at PATH-TO-GCC
  --with-hpack HPACK       Use HPACK executable (overrides bundled Hpack)
  --[no-]skip-ghc-check    Enable/disable skipping the GHC version and
                           architecture check
  --[no-]skip-msys         Enable/disable skipping the local MSYS installation
                           (Windows only)
  --local-bin-path DIR     Install binaries to DIR
  --[no-]modify-code-page  Enable/disable setting the codepage to support UTF-8
                           (Windows only)
  --[no-]allow-different-user
                           Enable/disable permission for users other than the
                           owner of the stack root directory to use a stack
                           installation (POSIX only)
  --[no-]dump-logs         Enable/disable dump the build output logs for local
                           packages to the console
  --resolver RESOLVER      Override resolver in project file
  --compiler COMPILER      Use the specified compiler
  --[no-]terminal          Enable/disable overriding terminal detection in the
                           case of running in a false terminal
  --color WHEN             Specify when to use color in output; WHEN is
                           'always', 'never', or 'auto'. On Windows versions
                           before Windows 10, for terminals that do not support
                           color codes, the default is 'never'; color may work
                           on terminals that support color codes
  --terminal-width INT     Specify the width of the terminal, used for
                           pretty-print messages
  --stack-yaml STACK-YAML  Override project stack.yaml file (overrides any
                           STACK_YAML environment variable)

Available commands:
  build                    Build the package(s) in this directory/configuration
  install                  Shortcut for 'build --copy-bins'
  uninstall                DEPRECATED: This command performs no actions, and is
                           present for documentation only
  test                     Shortcut for 'build --test'
  bench                    Shortcut for 'build --bench'
  haddock                  Shortcut for 'build --haddock'
  new                      Create a new project from a template. Run `stack
                           templates' to see available templates. Note: you can
                           also specify a local file or a remote URL as a
                           template.
  templates                List the templates available for `stack new'.
                           Templates are drawn from
                           https://github.com/commercialhaskell/stack-templates
                           Note: `stack new' can also accept a template from a
                           local file or a remote URL.
  init                     Create stack project config from cabal or hpack
                           package specifications
  solver                   Add missing extra-deps to stack project config
  setup                    Get the appropriate GHC for your project
  path                     Print out handy path information
  ls                       List command. (Supports snapshots and dependencies)
  unpack                   Unpack one or more packages locally
  update                   Update the package index
  upgrade                  Upgrade to the latest stack
  upload                   Upload a package to Hackage
  sdist                    Create source distribution tarballs
  dot                      Visualize your project's dependency graph using
                           Graphviz dot
  ghc                      Run ghc
  hoogle                   Run hoogle, the Haskell API search engine. Use 'stack
                           exec' syntax to pass Hoogle arguments, e.g. stack
                           hoogle -- --count=20
  exec                     Execute a command
  run                      Build and run an executable. Defaults to the first
                           available executable if none is provided as the first
                           argument.
  ghci                     Run ghci in the context of package(s) (experimental)
  repl                     Run ghci in the context of package(s) (experimental)
                           (alias for 'ghci')
  runghc                   Run runghc
  runhaskell               Run runghc (alias for 'runghc')
  script                   Run a Stack Script
  eval                     Evaluate some haskell code inline. Shortcut for
                           'stack exec ghc -- -e CODE'
  clean                    Clean the local packages
  list-dependencies        List the dependencies
  query                    Query general build information (experimental)
  ide                      IDE-specific commands
  docker                   Subcommands specific to Docker use
  config                   Subcommands specific to modifying stack.yaml files
  image                    Subcommands specific to imaging
  hpc                      Subcommands specific to Haskell Program Coverage

stack's documentation is available at https://docs.haskellstack.org/



```



stack
stack init --force
Looking for .cabal or package.yaml files to use to init the project.
Using cabal packages:
- .\

Selecting the best among 16 snapshots...

* Matches lts-14.3

Selected resolver: lts-14.3
Initialising configuration using resolver: lts-14.3
Total number of user packages considered: 1
Overwriting existing configuration file: stack.yaml
All done.





## stack/cabal
stack没有什么好多写的， 这就是一个自管理数据库的泥沙盒。和一般的虚拟环境不太一样的是，由一个用户管理其所有的全部环境，所以不会存在同一软件多次被安装而占用空间的问题，同时也可以使得多个工具可以共存。但是这个工具有一个问题，就是不太好清理，想清理得自己进目录下面来一删。而且删除时，也会影响到依赖数据库。

cabal是haskell本身所提供的，但这并不是一个传统意义上的包管理，准确来说，这不是一个管理工具，只是一个安装工具！是的，它只提供了install。想删除，也得自己进目录去删。同时update只是针对list，而不是packages。如果在全局安装的话，update后要人工进行一次reinstall。

所以不论二者那个，都不建议在全局安装库包。对于执行工具而言，开发工具直接使用stack会比较好。比如intero或ghc-mod。因为stack是全局管理唯一，再配合插件使用会相对优秀。自动初始化。

但对于hoogle一类工具而言，使用cabal安装会比较好。配合全局ghc进行使用。或者针对项目进行一次install

而cabal虽然也能使用sandbox，但这样一来得手动处理PATH目录，stack会自动将文件放至`~/.local/bin`中，当然这样带来的另外问题就是我们得需要安需install一次（但其实配合开发插件，一般这个过程会自动完成）。




https://vonfry.name/haskell-pkg-manager/

Haskell项目中，经常用到包管理工具，有些用cabal，stack， nix。这里对这三个工具做个简要的说明。

首先要明确的是cabal库，是一个haskell包集合的库，提供了不同的包以及不同的版本。cabal-install和stack均是前端基于cabal库使用的工具。

cabal-install是最早用的工具，用于haskell包的管理。提供了规范文件，来构建包，同时也提供了工具来进行包的下载安装cabal-install。

stack是一个可以替代cabal的工具，提供了更加便利的包管理，对于包的依赖，不同的版本，均提供了很好的支持。同时stack也支持不同的ghc发行版本管理。可以将不同的ghc发行版本来进行本地安装，通过配置文件，来进行选择。

stack通过提供沙盒机制，来进行隔离，从而使得不同版本应用之间不会冲突。

nix其实像stack，都是提供项目代码的包依赖，将这些依赖的包编译并且运行。但是stack要求依赖的包都是Haskell包，而nix是一个更加通用的包管理工具，可以是任何的包。它提供了一个库管理的通用方法，每一个库不同的版本，均有一个唯一的标识，这样可以做了多个包多个版本的管理。nixos就是原生包含了nix管理能力的linux的一个发型版本。
 ———————————————— 
版权声明：本文为CSDN博主「Hello编程世界」的原创文章，遵循CC 4.0 by-sa版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/gzjimzhou/article/details/83108347












## nix





























