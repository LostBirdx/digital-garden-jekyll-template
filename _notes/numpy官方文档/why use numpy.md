numpy is fast

simple example, consider the case of multiplying each element in a 1-D sequence with the corresponding element in another sequence of the same length

if we use list in Python:

```Python
c = []
for i in range(len(a)):
    c.append(a[i]*b[i])
```

or use C language
```c
for (i = 0; i < rows; i++): {
  c[i] = a[i]*b[i];
}
```

while in Numpy 

```Python
c = a * b
```

