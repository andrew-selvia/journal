# Configure Memory

When you need to deploy your Play app into a production environment, you may be faced with memory constraints. Assuming you're using `sbt-native-packager` to build your app into a jar or Docker image, you can [configure the JVM to use a specific amount of memory](https://www.scala-sbt.org/sbt-native-packager/archetypes/java_app/customize.html#via-build-sbt). You can also [specify these JVM flags at the command-line](https://www.playframework.com/documentation/2.8.x/ProductionConfiguration#JVM-configuration).
