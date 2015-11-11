# scala-repl

Test setup and instructions for various Scala REPL tests.

## Test java packages

``javac JavaTest.java`` 
``jar cf java-test.jar JavaTest.class`` 
``scala -cp java-test.jar``

``scala> JavaTest.getString``
``res0: String = test string``

``scala> val a: Option[Long] = Option(JavaTest.getLongNull)``
``java.lang.NullPointerException``
``  at scala.Predef$.Long2long(Predef.scala:358)``
``  ... 33 elided``

``scala> val a: Option[Long] = Option(JavaTest.getLongNull).map(_.longValue)``
``a: Option[Long] = None``
