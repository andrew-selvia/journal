# View Dependency Tree

You can view the dependency tree for a project build with SBT 1.4.0 or later with this command:

```shell
sbt dependencyTree
```

For earlier versions, use this command instead:

```shell
sbt "inspect tree clean"
```

For additional details, refer to [this Stack Overflow question](https://stackoverflow.com/questions/25519926/how-to-see-dependency-tree-in-sbt/25520209).
