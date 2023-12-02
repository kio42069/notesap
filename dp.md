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
- When two or more objects act similar to each other so it's kinda annoying having different objects/interfaces for them
- So we create a bridge called adapter object

**Example**

Movable Interface
```
public interface Movable {
    public void move();
}
public class Car implements Movable {
    public void move() {
        System.out.println(“Car is moving”);
    }
}
public class Bike implements Movable {
    public void move() {
        System.out.println(“Bike is moving”);
    }
}
```
Flyable Interface
```
public interface Flyable {
    public void fly();
}
public class Airplane implements Flyable {
    public void fly() {
        System.out.println(“Airplane is flying”);
    }
}
public class Drone implements Flyable {
    public void fly() {
        System.out.println(“Drone is flying”);
}
```
Flyable Adapter Interface
```
public class FlyableAdapter implements Movable {
    Flyable type;
    public FlyableAdapter(Flyable type) {
        this.type = type;
    }
    public void move() {
        type.fly();
    }
}
```

Main code
```
public class Vehicle {
    public static void main(String[] args) {
        List<Movable> mylist = new ArrayList<Movable>();
        
        mylist.add(new Car());
        mylist.add(new Bike());
        mylist.add(new FlyableAdapter(new Airplane()));
        mylist.add(new (new Drone()));
        
        for(Movable obj: mylist) {
            obj.move();
        }
    }
}
```


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
