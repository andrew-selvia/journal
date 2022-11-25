## sbt-buildinfo

[sbt-buildinfo](https://github.com/sbt/sbt-buildinfo) is a SBT plugin which dynamically generates a Scala object containing build parameters from the `build.sbt` file so you can use them in your code without statically defining them in multiple places. In other words, sbt-buildinfo allows your project to adhere to the don't-repeat-yourself (DRY) principle. An example use case would be if your application has an endpoint (if it's a service) or subcommand (if it's a CLI) that communicates the application's version. [This Stack Overflow answer](https://stackoverflow.com/a/48782896/6073927) provides additional context.

If you plan to write your code in IntelliJ IDEA, you **must** take care to inform the IDE about this dynamically-generated file; [this pull request](https://github.com/sbt/sbt-buildinfo/pull/75) demonstrates how to do that. Basically, you need to add a build setting named `buildInfoUsePackageAsPath` and set it to `true`. For example:

```sbt
lazy val root = (project in file("."))
  .enablePlugins(BuildInfoPlugin, JavaAppPackaging)
  .settings(
    buildInfoKeys := Seq[BuildInfoKey](name, version),
    buildInfoPackage := rootPackage,
    buildInfoUsePackageAsPath := true
  )
```
