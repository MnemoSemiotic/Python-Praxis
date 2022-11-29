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



## An X against Y polyrhythm function

```python
def build_polyrhythm_table(x, y):
    lst = list(range(1, y+1)) * x

    output = f"""       {x} against {y}  \n\n"""

    for idx, num in enumerate(lst):
        if idx % x == 0:
            output += f" |{num}| "
        else:
            output += f"  {num}  "

        if num == y:
            output += "\n"

    
    return output


print(build_polyrhythm_table(x=3, y=5))
```

```
 |1|   2    3   |4|   5  
  1   |2|   3    4   |5| 
  1    2   |3|   4    5 
```


## Using numpy and pandas to show the count, and both instruments

```python
import numpy as np
import pandas as pd


def build_polyrhythm_table(x, y):
    lst = list(range(1, y+1)) * x

    title = f"""       {x} against {y}  \n"""

    beats = np.arange(1, x*y+1, 1, dtype=int)
    
    polyrhythm = []
    
    for idx, num in enumerate(lst):
        if idx % x == 0:
            polyrhythm.append(f"|{num}|")
        else:
            polyrhythm.append(f"{num}")

        # if num == y:
        #     output += "\n"

    
    return title, beats, np.array(polyrhythm)


title, beats, polyrhythm = build_polyrhythm_table(x=3, y=5)

print(title)
# print(np.reshape(polyrhythm, (3,5)))
beats_and_poly = np.vstack((beats, polyrhythm))

pd.DataFrame(beats_and_poly)
```

```
0 	1 	2 	3 	4 	5 	6 	7 	8 	9 	10 	11 	12 	13 	14
1 	|1| 	2 	3 	|4| 	5 	1 	|2| 	3 	4 	|5| 	1 	2 	|3| 	4 	5
```


## Cleaning up to get a clearer visual representation of the polyrhythm

```python
import numpy as np
import pandas as pd


def build_polyrhythm_table(x, y):
    lst = list(range(1, y+1)) * x

    title = f"""       {x} against {y}  \n"""
    
    
    x_list = []
    y_list = []
    
    
    for idx, num in enumerate(lst):
        if idx % x == 0:
            x_list.append(f"*")
        else:
            x_list.append(" ")
    
    for idx, num in enumerate(lst):
        if idx % y == 0:
            y_list.append(f"*")
        else:
            y_list.append(" ")
                          

    
    return title, np.vstack((np.array(x_list), np.array(y_list)))


title, polyrhythm = build_polyrhythm_table(x=3, y=5)

print(title)
# print(np.reshape(polyrhythm, (3,5)))

print(pd.DataFrame(polyrhythm))
```

```
       3 against 5  

  0  1  2  3  4  5  6  7  8  9  10 11 12 13 14
0  *        *        *        *        *      
1  *              *              *            
```

```
       2 against 5  

   0  1  2  3  4  5  6  7  8  9
0  *     *     *     *     *   
1  *              *            
```


```
       3 against 4  

  0  1  2  3  4  5  6  7  8  9  10 11
0  *        *        *        *      
1  *           *           *         
```