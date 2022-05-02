# Java Primative Data Types

## Integer Types

| Type  | Bits | Min                  | Max                 | Literal |
|-------|------|----------------------|---------------------|---------|
| byte  |    8 |                 -128 |                 127 |      0  |
| short |   16 |               -32768 |               32767 |      0  |
| int   |   32 |          -2147483648 |         -2147483647 |      0  |
| long  |   64 | -9223372036854775808 | 9223372036854775807 |      0L |

---

### examples:
```java
byte numLettersInEnglish = 26;
short feetInAMile = 5280;
int milesToSun = 92960000;
long milesInALightYear = 5879000000000L;
```

## Floating Point Types

| Type   | Bits | Min                     | Max                    | Literal        |
|--------|------|-------------------------|------------------------|----------------|
| float  |   32 | 1.4 x 10<sup>-45</sup>  | 3.4 x 10<sup>38</sup>  |          0.0f  |
| double |   64 | 4.9 x 10<sup>-324</sup> | 1.7 x 10<sup>308</sup> |   0.0 or 0.0d  |

---

### examples:
```java
float kilometersInAMarathon = 42.195f;
float absoluteZeroInCelcius = -273.15f;
double atomWidthInMeters = 0.0000000001d;
```

## Character Types

The character type allows you to store a single unicode character.
You can use the 4-digit hex unicode notation.

---

### examples:
```java
char regularU = 'U';
char accentedU = '\u00DA';
```

## Boolean Types

Boolean just like in any other programming language.

---

### examples:
```java
boolean iLoveJava = true;
```
