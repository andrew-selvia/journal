# Get Started

[Play](https://www.playframework.com) is a web framework with deep roots in the Scala ecosystem. It is built to be fast by leveraging Akka at its foundation. To get started, refer to [*Getting Started with Play Framework*](https://www.playframework.com/getting-started), [the Play Framework Tutorial](https://dvirf1.github.io/play-tutorial/), the [documentation](https://www.playframework.com/documentation/2.8.x/Home), and the [official tutorials](https://www.playframework.com/documentation/2.8.x/Tutorials). Once you're ready to begin coding, you should start with a template project like [play-scala-seed.g8](https://github.com/playframework/play-scala-seed.g8).

## Documentation

* [*Anatomy of a Play Application*](https://www.playframework.com/documentation/2.8.x/Anatomy)
* [Play samples](https://github.com/playframework/play-samples)
* [*Working with Public Assets](https://www.playframework.com/documentation/2.8.x/AssetsOverview)
* [StackOverflow: How to Serve Static Assets](https://stackoverflow.com/a/30569848/6073927)
* [*HTTP Routing*](https://www.playframework.com/documentation/2.8.x/ScalaRouting)

## Deploy

Once you are ready to deploy your app, you should be aware of a few changes you will need to make in order for your app to work properly.

### Allowed Hosts Filter

Play allows you to configure hosts which can reach your service. While developing locally, you will likely not be accepting traffic from any external IP addresses. Once deployed, though, you will find that Play will fail unless you have specified which IP addresses can reach your service. For more information, refer to [the documentation](https://www.playframework.com/documentation/2.8.x/AllowedHostsFilter).
