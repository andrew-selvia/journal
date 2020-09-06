# Return a File Stored in Google Cloud Storage via a Play Application

The [Google Cloud Storage (GCS) Alpakka connector](https://doc.akka.io/docs/alpakka/current/google-cloud-storage.html) streamlines the process of interacting with the GCS API for Scala applications. [Alpakka](https://doc.akka.io/docs/alpakka/current/index.html) is built atop [Akka Streams](https://doc.akka.io/docs/akka/current/stream/index.html) to expose stream-aware interfaces to many popular APIs. The GCS connector handles authentication and API interaction so your app can remain focused on its core business logic.

While the documentation provides a good start, complete integration with Play requires a bit more care. Here are a few things to keep in mind:

* The HOCON definition of `privateKey` seems to only work as a single-line string, despite the documentation [defining it as a multi-line string](https://github.com/akka/alpakka/blob/5dab46011b5b66e8a6c3499d0d617e6721c70888/google-cloud-storage/src/test/resources/application.conf#L12-L28). Obviously, this could easily be the result of user error.
* As of the time of this writing, explicit dependencies on version 10.1.12 of `akka-http` & `akka-http-spray-json` must be declared to work with Play version 2.8.2.
* You will need to inject an actor system & declare an implicit materializer into the controller, for instance like this:

    ```scala
    @Singleton
    class YourController @Inject()
    (val controllerComponents: ControllerComponents, actorSystem: ActorSystem)
    (implicit materializer: Materializer = SystemMaterializer(actorSystem).materializer)
    extends BaseController {}
    ```
* If the controller's action was previously synchronous, you will need to modify it to be asynchronous to account for the streaming nature of `GCStorage.download`; specifically, it should become `Action.async`.
* The return type of `GCStorage.download` is difficult to navigate for those new to Akka Streams. The following is one way to map it to an `Ok` response in Play:

    ```scala
    GCStorage
            .download("my-bucket", fileName)
            .map(
              _
                .map(
                  _
                    .map(_.utf8String)
                    .fold("")(_ + _)
                    .map(Ok(_))
                    .map(_.as("text/html"))
                    .runWith(Sink.head))
                .get)
            .runWith(Sink.head)
            .flatten
    ```

For more details on how to use Akka Streams, refer to the [Streams Quickstart Guide](https://doc.akka.io/docs/akka/current/stream/stream-quickstart.html).