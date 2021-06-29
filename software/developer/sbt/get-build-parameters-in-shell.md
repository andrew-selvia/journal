# Get Build Parameters in Shell

If you ever want to retrieve the name, version, or some other build parameter from a `build.sbt` file, you can use a command similar to this:

```shell
sbt -Dsbt.supershell=false -error "print version"
```

For more information on this technique, refer to [this article](https://alvinalexander.com/source-code/how-print-sbt-project-version-number-command-line/).
