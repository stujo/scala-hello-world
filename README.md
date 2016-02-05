Hello World in Scala
=================

#Getting Set Up

```
$ brew install scala
```

#``scala``

```
$ scala
Welcome to Scala version 2.11.7 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_25).
Type in expressions to have them evaluated.
Type :help for more information.

scala> :help
All commands can be abbreviated, e.g., :he instead of :help.
:edit <id>|<line>        edit history
:help [command]          print this summary or command-specific help
:history [num]           show the history (optional num is commands to show)
:h? <string>             search the history
:imports [name name ...] show import history, identifying sources of names
:implicits [-v]          show the implicits in scope
:javap <path|class>      disassemble a file or class name
:line <id>|<line>        place line(s) at the end of history
:load <path>             interpret lines in a file
:paste [-raw] [path]     enter paste mode or paste a file
:power                   enable power user mode
:quit                    exit the interpreter
:replay [options]        reset the repl and replay all previous commands
:require <path>          add a jar to the classpath
:reset [options]         reset the repl to its initial state, forgetting all session entries
:save <path>             save replayable session to a file
:sh <command line>       run a shell command (result is implicitly => List[String])
:settings <options>      update compiler options, if possible; see reset
:silent                  disable/enable automatic printing of results
:type [-v] <expr>        display the type of an expression without evaluating it
:kind [-v] <expr>        display the kind of expression's type
:warnings                show the suppressed warnings from the most recent line which had any

scala>  println("Hello, world!")
Hello, world!

scala> :quit
$
```

#``val`` vs ``var``

* ``val`` are immutable
```
scala> val i:Integer=3
i: Integer = 3

scala> i
res0: Integer = 3

scala> i = 5
<console>:11: error: reassignment to val
       i = 5
         ^
```

* ``var`` are mutable
```
scala> var i2 = 5
i2: Int = 5

scala> i2
res1: Int = 5

scala> i2 = 6
i2: Int = 6
```


# Functions

```
def max(x: Int, y: Int): Int = { if (x > y) x else y } 
```

```
scala> max(5,6)
res2: Int = 6

scala> max(6,5)
res3: Int = 6
```

* Function parameters are typed

```
scala> max("Hello","World")
<console>:12: error: type mismatch;
 found   : String("Hello")
 required: Int
       max("Hello","World")
           ^
<console>:12: error: type mismatch;
 found   : String("World")
 required: Int
       max("Hello","World")
                   ^
```

#``scala`` Files

* Filenames match object names

``HelloWorld.scala``:
```
object HelloWorld {
  def main(args: Array[String]): Unit = {
    println("Hello, world!")
  }
}
```

#Compiler

```
$ mkdir classes
$ scalac -d classes HelloWorld.scala
```
* Outputs Java ``.class`` files to the ``classes`` directory

#Runtime
* Uses classpath just like Java
```
$ scala -cp classes HelloWorld
Hello, world!
```

#Traits
* Something like modules in Ruby
* In this case ``App`` is the trait
* [The App trait can be used to quickly turn objects into executable programs](http://www.scala-lang.org/api/2.10.1/index.html#scala.App)
``HelloWorldApp.scala``
```
object HelloWorldApp extends App {
  println("Hello, world! (App)")
}
```

```
$ scalac -d classes HelloWorldApp.scala
$ scala -cp classes HelloWorldApp
Hello, world! (App)
```

#Resources
* [Programming in Scala, First Edition](http://www.artima.com/pins1ed/)
* [http://www.scala-lang.org/documentation/getting-started.html](http://www.scala-lang.org/documentation/getting-started.html)