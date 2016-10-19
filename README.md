# Java Test Timer

Measures elapsed time between two points in an execution path.

## Usage with JUnit4

```java    
private Timer timer;

@BeforeClass
public void beforeAll() {
    timer = new Timer();
}

@AfterClass
public static void afterAll() {
  timer.dumpTimings();
}

@Test
public void junitTestMethod() {
    timer.startTimer();
    // test method body
    timer.stopTimer();
}
```

See the test cases in the project for more usage examples.

The ```dumpTimings()``` method writes the collected timings to the ```PrintStream``` specified on the Timer constructor ```Timer(PrintStream ps)``` or, by default, to ```System.out```. It produces output that looks like this:

```
------------------------------------------------------------
Timings for java8.sandbox.functions.FunctionsTest

addition_inline_Integers.........................................         608,900 ns
differenceOfSquares_class........................................         585,781 ns
differenceOfSquares_inline.......................................         282,575 ns
differenceOfSquares_utility......................................         523,390 ns
exponentiation...................................................         616,010 ns
increment_class_Integer..........................................         559,687 ns
increment_inline_Integer.........................................         418,412 ns
increment_utility_Integer........................................       1,038,834 ns

------------------------------------------------------------
Timings for java8.sandbox.predicate.CatalogSearchTest

itFindsEntriesByManufacturer_preJava8............................         479,167 ns
itFindsEntriesByManufacturer_usingPredicate......................         385,123 ns
itFindsEntriesByManufacturer_usingStreamsAndFilter...............         752,981 ns
itFindsEntriesByTextInDescription_preJava8.......................         404,558 ns
itFindsEntriesByTextInDescription_usingPredicate.................         955,732 ns
itFindsEntriesByTextInDescription_usingStreamsAndFilter..........      19,235,177 ns
itSortsResultsByProductName_preJava8.............................         640,303 ns
itSortsResultsByProductName_usingLambda..........................       3,517,193 ns
itSortsResultsByProductName_usingStreams.........................       3,141,018 ns
itSortsResultsByProductName_usingStreamsAndAnonymousInnerClass...         781,979 ns
```



