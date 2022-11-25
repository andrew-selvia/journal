# Plugins

## Popular Plugins

If you are searching for interesting plugins, refer to [this article](https://tech.malliina.com/useful-sbt-plugins) for some suggestions. The list below also collects some popular ones:

* [sbt-native-packager](https://github.com/sbt/sbt-native-packager): Build application packages in native formats; for instance, you can package a command-line interface (CLI) as an executable program
* [sbt-assembly](https://github.com/sbt/sbt-assembly): Deploy fat JARs
* [sbt-docker](https://github.com/marcuslonnberg/sbt-docker): Create Docker images directly from sbt
* [scalafmt](https://scalameta.org/scalafmt/): Code formatter for Scala
* [mdoc](https://scalameta.org/mdoc/): Typechecked markdown documentation for Scala
* [sbt-buildinfo](https://github.com/sbt/sbt-buildinfo): Generates a Scala object with SBT build parameters so you can use them in your code

## Create a Plugin

If you are planning to create your own SBT plugin, refer to the following resources:

* [Plugins](https://www.scala-sbt.org/1.x/docs/Plugins.html)
* [Plugins Best Practices](https://www.scala-sbt.org/1.x/docs/Plugins-Best-Practices.html)
* [Tasks](https://www.scala-sbt.org/1.x/docs/Tasks.html)
* [How to Build and Deploy a Simple SBT Plugin](https://codewithstyle.info/how-to-build-a-simple-sbt-plugin/)
* [SBT Plugin – How to make it, debug it, improve it?](https://leobenkel.com/2018/11/make-sbt-plugin/)
* [Building and testing sbt plugins](https://timushev.com/posts/2020/04/25/building-and-testing-sbt-plugins/)

If you plan to have your SBT plugin call a shell script internally, refer to [this Stack Overflow answer](https://stackoverflow.com/a/12875270/6073927). Remember that your plugin will be imported into client projects as a jar file, therefore task definitions in your plugin won't be able to simply call the shell script directly. Instead, your plugin should store the shell script in `src/main/resources`. By storing it there, it will be accessible on the resource path of the client project at runtime. Your plugin can define a task to copy the contents of the resource, write them to a temporary file (perhaps the client project's `target` directory), make it executable, and finally run the script (refer to [*Execute Shell Commands from Scala Code*](../scala/execute-shell-commands-from-scala-code.md)).
