# Block Until a Future Completes

You can block until completion of a `Future` with a strategy like this:

```scala
import scala.concurrent.duration._
Await.result(future, 10.seconds).get
```

You can find other options in [this Stack Overflow thread](https://stackoverflow.com/a/25898559/6073927).
