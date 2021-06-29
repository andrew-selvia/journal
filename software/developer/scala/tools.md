# Tools

This document collects tools in the Scala ecosystem.

* [Polynote](https://polynote.org): A Scala-compatible notebook similar to Jupyter
    * [*Scala tooling in 2019*](https://geirsson.com/2019.html#polynote) has a section on Polynote that highlights some of its advantages over Jupyter notebooks including: Scala-Python interoperability, self-contained dependency management, and rich code editing
    * A full introduction to the tool was presented at [Scale by the Bay 2019](https://www.youtube.com/watch?v=QplRowWRNuQ)
    * Netflix also wrote [a blog post](https://netflixtechblog.com/open-sourcing-polynote-an-ide-inspired-polyglot-notebook-7f929d3f447) about Polynote when they open-sourced it
* [Scala Steward](https://github.com/scala-steward-org/scala-steward): Automatically keeps dependencies up-to-date by creating pull requests (PRs) against your repo
    * The official Scala blog encourages the use of Scala Steward in [*Keep Your Projects Up-to-date with Scala Steward*](https://www.scala-lang.org/blog/2019/07/10/announcing-scala-steward.html)
    * [FAQ](https://github.com/scala-steward-org/scala-steward/blob/master/docs/faq.md)
    * You can even run it on-premise (i.e. for your company's internal projects) as described in [Running Scala Steward On-premise](https://engineering.avast.io/running-scala-steward-on-premise/)
    * If you want to automatically merge the PRs created by Scala Steward, you can investigate [Mergify](https://mergify.io).

## References

* [Scala tooling in 2019](https://geirsson.com/2019.html)
