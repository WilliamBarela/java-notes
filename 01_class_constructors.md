# Java Class Constructors

## class initial state

| byte, short, int, long | float, double | char     | boolean | reference type fields |
| 0                      | 0.0           | '\u0000' | false   | null                  |

### establishing initial state
- field initializers
- constructors
- initialization blocks

## field initializers

```java
public class Earth {
  long circumferenceInMiles = 24901;

  // long circumferenceInKms = (long)(circumferenceInMiles * 1.6d);
  long circumferenceInKms = Math.round(circumferenceInMiles * 1.6d);
}
```

circumferenceInMiles and circumferenceInKms are field initializers.

## constructors

- don't have return types
- must be named the same as the class
- if we don't provide a constructor, Java will provide one


```java
public class Passenger {
  private int checkedBags;
  private int freeBags;

  // getters and setters elided

  private double perBagFee;

  // Java would provide this:
  // public Passenger() {
  // }

}

// So that we can instantiate objects of this class:
Passenger passenger = new Passenger();
```

Java classes can have mutliple constructors
- each constructor has to have a uniq parameter list
  + constructors should differ in number of parameters
  + or differ in parameter data types

i.e., different signatures

### mutliple constructors example:

```java
public class Passenger {
  private int checkedBags;
  private int freeBags;

  // getters and setters elided

  private double perBagFee;

  public Passenger() { } 

  public Passenger(int freeBags) {
    this.freeBags = freeBags
  }
}

Passenger passenger = new Passenger(2);
```

The above code lets us instantiate new objects without passing any parameters (i.e. the `default constructor`).
However, we have also made a constructor which allows free bags to be set when instantiated.

## constructor chaining

```java
public class Passenger {
  // other members elided

  public Passenger() { } 

  public Passenger(int freeBags) {
    this(freeBags > 1 ? 25.0d : 50.0d);
    this.freeBags = freeBags
  }

  public Passenger(int freeBags, int checkedBags) {
    // this.freeBags = freeBags; instead of duplicating this, we can just call the previous constuctor
    this(freeBags);
    this.checkedBags = checkedBags;
  }

  public Passenger(double perBagFee) {
    this.perBagFee = perBagFee
  }
}

Passenger passenger = new Passenger(2);
```

## constructor visibility
You can prepend any constructor with an access modifier (e.g., private, etc.)

## initialization blocks

```java
public class Flight {
  private int passengers, int seats = 150;
  private int flightNumber;
  private char flightClass;
  private boolean[] isSeatAvailable = new boolean[seats];

  // this is an intialization block and it will run every time a new instance is instantiated
  // it also helps you to avoid this() in constructor chains
  {
    for(int i = 0; i < seats; i++) {
      isSeatAvailable[i] = true;
    }
  }
}
```

- intialization blocks do not replace a default constructor.
- you can have as many intialization blocks as you want
  + however, they will all run for sure
  + and they run in the order written

## Order of initial state setting:

1. field intializers
2. initialization blocks
3. constructors
