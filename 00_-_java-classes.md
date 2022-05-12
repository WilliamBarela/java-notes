# Java Classes

## Declaring classes
- objects encapsulate data, operations, and user semantics
- all members of the class are in the brackets
- class is always capitalized
- source file name is normally required to have the same name as the class.

```java
class Flight {
  int passengers;
  int seats;

  Flight() {
    seats = 150;
    passengers = 0;
  }

  void add1Passenger() {
    if(passengers < seats)
      passengers += 1;
  }
}
```

## Class members
- *fields* store object state (i.e., the data of the class)
- *methods* are executable code which can:
  + manipulate the state of the object
  + perform operations related to the class
- *constructor* executable code which sets the initial state
  + has the same name of the class

## Working with objects

```Java
// make a reference to a flight object:
Flight nycToLv;
// make the instance
nycToLv = new Flight();

// The same as above, but just one line
// which declares the reference and the instance at the same time
Flight flight1 = new Flight();
Flight flight2 = new Flight();

flight2.add1Passenger();
```

## Creating an array of classes

```java
// make an array of four references to the location of the Flights 
Flights[] flights = new Flights[4];

// still have to instantiate the objects
flights[0] = new Flight();
flights[1] = new Flight();
flights[2] = new Flight();
flights[3] = new Flight();

// or:
for(Flight flight : flights) {
  flight = new Flight();
}
```

## Encapsulation and access modifiers

### Access modifiers

| MODIFIER | VISIBILITY                                    | USABLE ON CLASSES | USABLE ON MEMBERS |
| none     | only within its own package (package private) |        Y          |        Y          |
| public   | Everywhere                                    |        Y          |        Y          |
| private  | only within the declaring class               |        N\*        |        Y          |

\* in nested classes, classes could be private

```java
// Flight.java
public class Flight {
  int passengers;
  int seats
   
  Flight {...}
  
  void add1Passengers(){...}
}


// Main.java

Flight flight1;
```

```java
// Flight.java
public class Flight {
  private int passengers;
  private int seats
   
  public Flight {...}
  
  public void add1Passengers() {
    if (passengers < seats)
      passengers += 1;
    else
      handleTooMany()
  }

  private void handleTooMany() {
    System.out.println("Too many");
  }
}


// Main.java

Flight flight1 = new Flight();
```

### notes:
- marking a class public is not sufficient to allow instances to be declared
  + constructor *must* be marked as public as well
  + i.e., you will not be able to use `new Klass()` before declaring the constructor `public`.
- note that a private method can be used by a public method

## Special References

### this
- reference to the current object
  + useful for reducing ambiguity
  + allow an object to pass itself as a parameter

### null
- represents an uncreated object
  + can be assigned to any reference variable

## Field encapsulation (accessor and mutator methods)

- accessor
  + getters
  + normally name method `getMethodName`

- mutator
  + setters
  + normally name method `setMethodName`

```java
class Flight {
  private int seats;

  public int getSeats() {
    return seats;
  }

  public void setSeats(int seats) {
    this.seats = seats;
  }
}

Flight slcToNyc = new Flight();
slcToNyc.setSeats(200);
System.out.println(slcToNyc.getSeats());
// 200
```
