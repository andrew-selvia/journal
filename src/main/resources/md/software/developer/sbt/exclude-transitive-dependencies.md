# Exclude Transitive Dependencies

You can [exclude transitive dependencies](https://stackoverflow.com/questions/10958215/how-to-exclude-commons-logging-from-a-scala-sbt-slf4j-project) from a SBT project by using one of the following strategies.

If you want to exclude a specific transitive dependency, use `exclude`:

```scala
libraryDependencies += "organization" % "artifact" % "0.0.0" exclude("organization", "artifact")
```

If you want to exclude multiple transitive dependencies, use `excludeAll` instead:

```scala
excludeAll(ExclusionRule(organization = "organization"))
```
