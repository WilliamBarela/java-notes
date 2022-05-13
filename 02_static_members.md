# Static Members
Basically the equivalent of a class method in Ruby.

## static fields
allPassengers allows you to count all passengers across all instances of the Flight class

```java
public class Flight {
  private int passengers, seats = 150;
  // STATIC FIELD EXAMPLE:
  private static int allPassengers;

  public void add1Passenger() {
    if(passengers < seats) {
      passengers += 1;
      allPassengers += 1;
    }
  }
}
```

## static methods
Static methods can only access other static members.
They cannot access instance members

```java
public class Flight {
  private int passengers, seats = 150;
  // STATIC FIELD EXAMPLE:
  private static int allPassengers;

  public void add1Passenger() {
    if(passengers < seats) {
      passengers += 1;
      allPassengers += 1;
    }
  }

  // STATIC METHOD EXAMPLE:
  public static int getAllPassengers() {
    return allPassengers
  }

  // ANOTHER EXAMPLE OF A STATIC METHOD
  public static void resetAllPassengers() {
    allPassengers = 0;
  }
}
```

```java
// how you can use the static method:
Flight.resetAllPassengers()
```

## static imports

### WITHOUT THE STATIC IMPORT
```java
Flight.resetAllPassengers();

laxToSlc.add1Passenger();
laxToSlc.add1Passenger();

Flight dfwToNyc = new Flight();
dfwToNyc.add1Passenger();

System.out.println(Flight.getAllPassengers();
```

### WITH THE STATIC IMPORT
```java
import static com.pluralsight.flightapp.Flight.resetAllPassengers;
import static com.pluralsight.flightapp.Flight.getAllPassengers;

resetAllPassengers();

laxToSlc.add1Passenger();
laxToSlc.add1Passenger();

Flight dfwToNyc = new Flight();
dfwToNyc.add1Passenger();

System.out.println(getAllPassengers();
```

### CAN ALSO IMPORT ALL STATIC METHODS WITH A SPLAT (*)
```java
import static com.pluralsight.flightapp.Flight.*;

resetAllPassengers();

Flight laxToDfw = new FLight();
laxToDfw.add1Passenger();

getAllPassengers();
```

## static initialization block

```java
public class Flight {
  private int passengers, seats = 150;
  private static int allPassengers, maxPassengersPerFlight;

  static {
    AdminService admin = new AdminService();
    admin.connect();

    maxPassengersPerFlight = admin.isRestricted() ?
                             admin.getMaxFlightPassengers() :
                             Integer.MAX_VALUE;
    admin.close();
  }

  public void add1Passenger() {
    if(passengers < seats && passengers < maxPassengersPerFlight) {
      passengers += 1;
      allPassengers += 1;
    }
  }
}
```
