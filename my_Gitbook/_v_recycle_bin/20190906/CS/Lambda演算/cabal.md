# cabal



https://wiki.haskell.org/Cabal-Install

```



# make a new directory for my project
$ mkdir my-project && cd my-project

# initialize my sandbox
$ cabal sandbox init
...

# create the .cabal file
$ cabal init
...

# cabal init would have created a Main.hs like below
$ cat Main.hs
module Main where

main = putStrLn "Hello World!"

# now, you can immediately run \`cabal install\`
$ cabal install
...

# this produces an executable that you can immediately run
$ ./.cabal-sandbox/bin/my-project
Hello World!
$

```














