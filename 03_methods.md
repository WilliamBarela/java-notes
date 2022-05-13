# Java Methods
  - follows naming convention of variables
  - allows a typed parameter list

## Declaring

```java
// return-type can be void when there is no return value
modifier return-type MethodName(typed-parameter-list) {
  statements
}

// example
static void doSomething() {
  System.out.println('does something');
}
```

## Calling

```java
doSomething();
```

## Parameters

```java
static void showSum(float x, float y, int count) {
  float sum = x + y;

  for(int i = 0; i < count; i++){
    System.out.println(sum);
  }
}

showSum(7.5, 1.4, 3);
```

## Exiting a method
  - end of method
  - return statement
  - error occurs (exception thrown)

```java
// example of how to return without specifying a value:
static void square(int num) {
  if (num = 0)
    return;
  
  System.out.println(num * num);

  return;
}
```

## Returning a value
  methods in Java can return:
    - primitive types
    - more complex types (such as arrays)

```java
static double calculateInterest(double amount, double rate, int years) {
  double interest = amount * rate * years;

  return interest;
}

double result = calculateInterest(100d, 0.05d, 10);

System.out.println(result); // 50.0
```

```java
// just like in other languages, you can return the calculation:

static double calculateInterest(double amount, double rate, int years) {
  return amount * rate * years;
}
```

```java
// returning an array
static double[] produceInterestHistory(double amount, double rate, int years) {
  double[] accumulatedInterest = new double[years]; // new double array of length years

  for(int yearIndex = 0; yearIndex < years; yearIndex++) {
    int year = yearIndex + 1;
    accumulatedInterest[yearIndex] = calculateInterest(amount, rate, year);
  }

  return accumulatedInterest;
}
```

## Command line args

```java
public static void Main(String[] args) {
  if(args.length < 1) {
    System.out.println("no args provided");
  else {
    for(String arg : args)
      System.out.println(arg);
  }
}
```

```bash
java com.application.example.Main Hello "William Barela"

# Hello
# William Barela
```

```java
// when getting args from the command line, they come in as String types
// so, conversion is necessary

// java com.application.example.Main f 120.0 15 
// args:
//  - arg[0] -> "f"
//  - arg[1] -> "120.0"
//  - arg[2] -> "15"

public static void Main(String[] args) {

  private static void readArgs(String[] args) {
    char code = args[0].charAt(0);
    double x = Double.parseDouble(args[1]);
    double y = Double.parseDouble(args[2]);

    if(code == "f") {
      return x + y;
    }
  }

}
```
