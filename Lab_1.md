# Lab 1 - Python introduction


### Exercise 0 - Example
Assign the number 31 to a new variable, q. Write an expression that raises q to the 4th power 


```python
# Your answer here
q = 31
q**4
```




    923521



### Exercise 1
Create arbitrary list, tuple and dictionary and print them


```python
# Your answer here
list = ['apple', 'banana', 2 , True]
print (list)

tuple = ('apple', 'banana', 2 , True)
print (tuple)

dict = {'fruits': ['apple','banana'],
         2: 'number of fruits'}
print (dict)
```

    ['apple', 'banana', 2, True]
    ('apple', 'banana', 2, True)
    {'fruits': ['apple', 'banana'], 2: 'number of fruits'}
    

### Exercise 2
Print the next elements of array s: 10th, from 10 to 20, all elements more than 0 


```python
import numpy as np
s = np.random.normal(0,1,100)

# Your answer here
print (s[9], s[9:19])
for i in range(100):
    if s[i]>0:
        print(s[i])

```

    0.12813514022479228 [ 0.12813514 -0.73914508  0.79007137 -0.41041264 -2.13009615 -1.42825942
      1.11964007  0.58860658 -0.07026195 -0.02424442]
    1.037794643064071
    0.8674620877915491
    0.8409924580216183
    2.4307224542632633
    0.5310609606733514
    0.12813514022479228
    0.7900713723122585
    1.1196400655531689
    0.5886065791159726
    0.03759014682465444
    1.2566493298884063
    0.45596989291973183
    2.0003239075293178
    0.14098339760291656
    0.03186575361189712
    0.9525447665633103
    0.36957239499301575
    1.0228231901698972
    0.12873628325166447
    0.6537923827699269
    1.150264758938887
    0.06606616523448566
    0.43783910315542923
    0.13893079291574323
    0.5076270102407207
    1.0652086608383649
    0.03040977961260979
    0.8755861273585637
    0.5904152324431646
    1.168371773378425
    1.3488041680877827
    0.2070777796515862
    0.2919410166291119
    1.3335692422129541
    1.7322407329873064
    1.2701679539609234
    2.8415609556950114
    0.33925260972638227
    1.2983935940096418
    2.7590899947181695
    0.406600634554257
    0.8783772825152832
    1.1345043258447525
    0.30991623543788405
    0.5520057811188462
    1.4312770610979748
    2.932500369319298
    0.7959423187145577
    1.0258288852613848
    

### Exercise 3
Make a function `pow` that raised base `number` to a fixed power `power`. If `power >= 50` print message "power is too big" and return `-1`


```python
# Your answer here
def pow(x, y):
    if y >= 50:
        print ('power is too big')
        return -1
    if y == 0:
        return 1
    if y >= 1:
        return x * pow (x, y-1)
print(pow(4, 52))
print (pow(4,3))



```

    power is too big
    -1
    64
    

### Exercise 4
Make a function `above(x,n)` which returns all elements `x > n`. By default `x = 10`. Use numpy arrays


```python
import numpy as np
# Your answer here
def above(n, x = 10):
    new_arr = []
    for y in n:
        if y < x:
            new_arr.append(y)
    return new_arr
above([34,21,6,5])

```




    [6, 5]



### Exercise 5
Write a function `my_ifelse(x, exp, n)` which test array `x` with expression `exp` to number `n`. For instance, `my_ifelse(x,'>=',10)` returns all elements of array `x` which greater or equal 10. `exp` can be `<`, `>`, `<=`, `>=`, `==`. If `exp` dont match these expression array `x` is retured


```python
import numpy as np
# Your answer here
def my_ifelse(x, exp, n):
    new_arr = []
    if exp == "<":
        for y in x:
            if y< n:
                new_arr.append(y)
    elif exp == ">":
        for y in x:
            if  y > n:
                new_arr.append(y)
    elif exp == "<=":
        for y in x:
            if y <= n:
                new_arr.append(y)
    elif exp == ">=":
        for y in x:
            if y >= n:
                new_arr.append(y) 
    elif exp == "==":
        for y in x:
            if y == n:
                new_arr.append(y)
    else :
        new_arr = x
    return new_arr
my_ifelse([1,9,12],">",8)


```




    [9, 12]



### Exercise 6
Make a function called `counter` that takes a string input_string and returns a dictionary of letter counts.


```python
# Your answer here
def counter(input_string):
    letters = {}
    input_string = list(input_string)
    for letter in input_string:
        if letter in letters:
            letters[letter]+=1
        else:
            letters[letter]=1
    return letters
counter ('bananas')

            

```




    {'b': 1, 'a': 3, 'n': 2, 's': 1}



### Exercise 7
From the function `counter` make function `counter_sorted` with second boolean argumens `reverse` that returns sorted letter counts. Order depends of the `reverse` argument. By default `reverse = False`


```python
# Your answer here
def counter(input_string):
    letters = {}
    input_string = list(input_string)
    for letter in input_string:
        if letter in letters:
            letters[letter]+=1
        else:
            letters[letter]=1
    return letters
counter ('bananas')
import operator
def counter_sorted(input_string, reverse = False):
    if reverse:
        return dict(sorted(counter(input_string).items(), key=operator.itemgetter(1),reverse=True))
    else:
        return dict(sorted(counter(input_string).items(), key=lambda item: item[1]))
print(counter_sorted('bananas', True))
print(counter_sorted('bananas'))
```

    {'a': 3, 'n': 2, 'b': 1, 's': 1}
    {'b': 1, 's': 1, 'n': 2, 'a': 3}
    


```python

```
