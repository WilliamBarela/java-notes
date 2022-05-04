# Strings in Java

## String class
- Strings in Java are UTF-16
- char types are in single quotes
- string literals are in double quotes

```Java
char letter = 'a';
String letters = "abc";
```

values can be concatenated with:

```java
// +
// +=

String firstName = "William";
String lastName = "Barela";

String fullName = firstName + " " + lastName;

String greeting = "Hello";
greeting += fullName + ". Good to see you";
```

## String equality

```java
package com.pluralsight.organized;

public class Main {
    public static void main(String[] args){
        String word0 = "I love ";
        word0 += "Java";
        String word1 = "I ";
        word1 += "love Java";
        String word2 = word0;

        System.out.println(word0); // I love Java
        System.out.println(word1); // I love Java
        System.out.println(word2); // I love Java
        System.out.println(word0 == word1); // false
        System.out.println(word0 == word2); // true
        System.out.println(word0.equals(word1)); //true
    }
}
```

`myString.intern();`

## String methods

```java
String myString = "a random string";

// LENGTH
myString.length(); // 15

// CREATE NEW STRINGS FROM EXISTING
myString.concat(" of characters"); // "a random string of characters"
myString.replace("r", "w"); // " a wandom stwing"
myString.toUpperCase(); // "A RANDOM STRING"
myString.toLowerCase();
myString.trim();
myString.split()
```

## String conversions

```java
int iVal = 100;
String sVal = String.valueOf(iVal); // "100"
```

## StringBuilder class

Since strings in Java are immutable, the StringBuilder class allows for a more efficient way of joining strings.

```java
package com.pluralsight.organized;

public class Main {
    public static void main(String[] args){
        String location = "Florida";
        int flightNumber = 175;

        StringBuilder sb = new StringBuilder(); // you can pass the final length of the string as an arg if you know it to be more efficient

        sb.append("I flew to ");
        sb.append(location);
        sb.append(" on Flight #");
        sb.append(flightNumber);

        String message = sb.toString(); // I flew to Florida on Flight #175
        System.out.println(message);

        String time = "9:00 am";
        int pos = sb.indexOf(" on");
        sb.insert(pos, " at ");
        sb.insert(pos + 4, time);

        message = sb.toString();
        System.out.println(message); // I flew to Florida at 9:00 am on Flight #175
    }
}```
