# JUnit Notes (shitty ahh)

## Boilerplate code for JUnit runner Class

```
Result result = JUnitCore.runClasses(whatever_your_class_name.class);
for(Failure failure : result.getFailures()){
    System.out.println(failure.toString());
}
System.out.println(result.wasSuccessful());
```

## A few JUnit Assertion Methods:
> assertTrue(Test)
>
> assertFalse(Test)
>
> asssertEquals(expected, actual)
>
> assertSame(expected, actual)
>
> assertNotSame(expected, actual)
>
> assertNull(value)
>
> assertNotNull(value)
>
> fail() -> causes the current test to fail immediately

**Fun fact, each method can also display a string to be displayed if it fails**
```
assertEquals("message", expected, actual)
```

## Test with a timeout
```
@Test (tiemout = 5000)
public void name() {...}
```
The above method will be considered a failure if it doesn't finish running within 5000 ms

## Test for exceptions
```
@Test (expected = ExceptionType.class)
public void name() {...}
```

For Example
```
@Test (expected = ArrayIndexOutOfBoundsException.class)
public void testBadIndex(){
    ArrayIntList list = new ArrayIntList();
    list.get(4)     // should fail
}
```

## Setup and Teardown
Basically, piece of code which needs to run before every test, or at the begining of the class code.

It can be used to initialise variables, blah blah blah.
- Code to be runned before every test
```
@Before
public void name() {...}
@After
public void name() {...}
```

- Code to be runned before the entire test class runs
```
@BeforeClass
public void name() {...}
@AfterClass
public void name() {...}
```