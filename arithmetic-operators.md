# Arithmetic Operators

## Basic Operators:

### Multiplicative
```
*
/
%
```

### Additive

```
+
-
```

## Prefix and Postfix Operators:

### Postfix:
```
x++
x--
```

### Prefix:
```
++x
--x
```

## Compound Assignment Operators:

- apply right side value to left side
- store result in variable on left side

```
+=
-=
*=
/=
%=
```

***

### Example:
```java
int myValue = 50;
myValue -= 5;
System.out.println(myValue); // 45

int val0 = 100;

int val1 = 5;
int val2 = 10;

val0 /= val1 * val2;

// 1) val1 * val2 = 5 * 10 = 50
// 2) val0 / 50 = 100 / 50 = 2

System.out.println(val0); // 2
```

## Order of Operation

1. Postfix (x++, x--)
2. Prefix (++x, --x)
3. Multiplicative ( *, /, % )
4. Additive ( +, - )

---

## Type Conversion

### Implicit Conversion

compiler does the conversion for you.
widening conversions are performed automatically

```java
int anIntVal = 50;
long aLongVal = anIntVal;
```

### Explicit Conversion

you have to use the cast operator to convert
Can perform widening and narrowing conversions

```java
logn aLongVal = 50;
int anIntVal = (int) aLongVal;
```

`(int)` is the cast operator
`(short)`, etc.

`(short) (byteVal - longVal)`
