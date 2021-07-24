# Convert a JsValue to a String

If you have a value of type `JsValue`, you can convert to a trimmed `String` with:

```scala
Json.stringify(jsValue)
```

Alternatively, you can convert it to a pretty-printable representation with:

```scala
Json.prettyPrint(jsValue)
```

For additional details, refer to [the documentation](https://www.playframework.com/documentation/2.8.x/ScalaJson#Using-String-utilities).
