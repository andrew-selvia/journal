# Convert Between List and Tuple

Imagine you have an array of values which are sequenced appropriately for use as the parameter list to a function. Rather than explicitly placing the item at each index into the parameter list, wouldn't it be nice to just pass the array itself in as the parameter list? If you've ever encountered a situation like this, you are likely aware that it's not quite so simple. This document aims to centralize some tips for deciding what to do. For additional details, refer to [this helpful guide](https://www.lorrin.org/blog/2011/10/04/scalas-missing-splat-operator/).

The key things you need to know are:

* To pass a list into a parameter list that ends with a variadic parameter, use the splat operator (`:_*`):
  ```scala
  def sum(integers: Int*) = (0 /: integers) (_ + _)
  val parameters = List(1, 2, 3, 4)
  sum(parameters:_*)
  ```
* To pass a tuple into a fixed-arity parameter list, use `tupled`:
  ```scala
  def multiply(x: Int, y: Double) = x * y
  val parameters = (6, 7.0)
  multiply _ tupled parameters
  ```
* To pass a list into a fixed-arity parameter list, you need to use shapeless as shown in [this Stack Overflow answer](https://stackoverflow.com/a/14727987/6073927):
  ```scala
  import shapeless._
  import syntax.std.traversable._
  val integers = List(1, 2, 3)
  val integersHList = integers.toHList[Int::Int::Int::HNil]
  val integersTuple = integersHList.get.tupled
  ```
  
## Shapeless

For a relatively gentle introduction on how to use Shapeless, refer to [this article](https://jto.github.io/articles/getting-started-with-shapeless/). Additional details can be found in [its official documentation](https://github.com/milessabin/shapeless/wiki/Feature-overview:-shapeless-2.0.0). The following list highlights some strategies which have proven useful in the past:

* [Operate on tuples as you do with standard `List`s](https://github.com/milessabin/shapeless/wiki/Feature-overview:-shapeless-2.0.0#hlist-style-operations-on-standard-scala-tuples)
