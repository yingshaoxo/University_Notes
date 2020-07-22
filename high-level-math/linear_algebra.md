# Linear algebra

## Import `numpy` firstly

```text
import numpy as np
```

## Matrix production

![](../.gitbook/assets/matrix-multiplication%20%281%29.png)

```text
>>> a = np.array([[2,3,0], [1,2,0]])
>>> b = np.array([[1,0], [0,2], [3,0]])
>>> np.dot(a,b)
array([[2, 6],
       [1, 4]])
```

## Determinant of an array \(数组的行列式\)

```text
>>> b = np.array([[1,-1,0], [4,-5,-3], [2,3,6]])
>>> np.linalg.det(b)
9.0000000000000018
```

