# Simple Polyrhythm Charts

Referencing the simple polyrhythm representation from[this Adam Neely lecture]( https://youtu.be/JiNKlhspdKg?t=911).


What we'll do here is create a Python representation based on Adam Neely's algorithm for representing polyrhythms

Pen and Paper Method
1. Draw X rows of Y numbers
2. Circle every X numbers


For example, a 3 against 5 polyrhythm
X = 3
Y = 5
1. Draw 3 rows of 5 numbers:

```
1  2  3  4  5
1  2  3  4  5
1  2  3  4  5
```

2. Circle every 3 numbers

```
|1|  2  3  |4|  5
 1  |2|  3  4  |5|
 1  2  |3|  4  5
```

3. To express this polyrhythm
* instrument X will sound on every number in the pipes: |n|
* instrument Y will sound on every 1
