# Design Patterns
## Singleton
- A class that has only one instance
- Creating another instance is strictly illegal

### How to make singleton!
- Make constructor private so that it can't be called from outside
- Declare a single private static instance of the class
- Write a getInstance() method [or smth like that] that allows read access but no new creationg access  

Example
```
public class RG{
    private static RG gen = null;

    public static RG getInstance(){
        if(gen == null){
            gen = new RG();
        }
        return gen;
    }
    private RG(){}
    ...
}
```
-----
## Flyweight
- a class that has only one instance for each unique state
- An assurance that no more than one instance of a class will have identical state
- Achieved by caching attempts to create object instances that already exist.

**Boilerplate Code : Implementing a Flyweight**

```
public class Flyweighted {
    private static Map<KeyType, Flyweighted> instances = new HashMap<KeyType, Flyweighted>();

    private Flyweighted(...) { ... }

    public static Flyweighted getInstance(KeyType key) {
        if (!instances.containsKey(key)) {
            instances.put(key, new Flyweighted(key));
        }
        return instances.get(key);
    }
}
```

**Fun fact! Strings in java are automatically handled as flyweights. Any two variables, if they have the same string stored, will point to the same string object instead of having two differernt objects**

-----
## Adapter
-----
## Strategy
-----




# **Next lecture**

## Facade
-----
## Template
-----
## Factory
-----
## Abstract Factory
-----
## Decorator
-----
## Composite
