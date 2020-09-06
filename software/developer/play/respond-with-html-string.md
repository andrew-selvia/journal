# Respond with HTML String

If you attempt to respond to a request with a string containing HTML content, you may be surprised to see the browser render it as raw text. In order for the browser to render the string as HTML as you intend, refer to [this StackOverflow answer](https://stackoverflow.com/a/21723170/6073927). In short, you must add `.as("text/html")` like this:

```scala
Ok("<p>hello world</p>").as("text/html")
```
