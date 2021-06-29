# Fix Unknown Artifact Warning in IntelliJ IDEA

Have you ever been frustrated by "Unknown Artifact" warnings underneath dependencies in a build.sbt file when browsing it in IntelliJ IDEA? You're not alone. Succinctly, this warning is a result of IntelliJ IDEA not being able to resolve dependencies from the Coursier cache. Since recent versions of SBT utilize Coursier by default, you must explicitly inform IntelliJ IDEA to **not** use it in order to remove the warnings in IntelliJ IDEA. For more information, refer to [this Stack Overflow answer](https://stackoverflow.com/a/58456468/6073927).
