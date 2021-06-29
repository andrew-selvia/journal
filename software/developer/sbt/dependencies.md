# Dependencies

[SBT dependencies](https://www.scala-sbt.org/1.x/docs/Library-Management.html#Dependencies) are defined by a `groupID`, `artifactID`, and `revision` as follows:
```scala
libraryDependencies += groupID % artifactID % revision
```

You may also encounter the `%%` syntax in a dependency definition. It is used to route to the correct SBT-built jar based on the project's Scala version. Java artifacts don't need to use `%%`, but Scala ones often do because they are not binary compatible. For more information, refer to [the documentation](https://www.scala-sbt.org/release/docs/Library-Dependencies.html#Getting+the+right+Scala+version+with).
