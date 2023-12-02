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
