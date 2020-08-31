---
title: (Python)Permutations & Combinations 
categories: [dev]
comments: true
---

## Permutations(순열)
서로 다른 n개의 원소에서 r(≤n)개를 뽑아 한 줄로 세우는 경우의 수이며, nPr로 나타낸다.  
순열은 순서를 고려하기 때문에 같은 원소로 구성되었더라도 순서가 다르면 다른 집합으로 분류된다.

## Combinations(조합)
서로 다른 n개의 원소 중에서 순서에 상관없이 r(≤n)개를 선택하는 경우의 수이며, nCr로 나타낸다.  
조합은 순서를 고려하지 않기 때문에 순서가 다르더라도 같은 원소로 구성되었다면 같은 집합으로 분류된다.

`itertools`  
파이썬에서는 순열과 조합을 쉽게 구할 수 있도록 **itertools** 모듈을 제공한다.  

**itertools.permutations(iterable[, r])** : r-length tuples, all possible orderings, no repeated elements  

```python
from itertools import permutations
a = ['A', 'B', 'C']
b = list(permutations(a, 2))
print(b)

# [('A', 'B'), ('A', 'C'), ('B', 'A'), ('B', 'C'), ('C', 'A'), ('C', 'B')]
```

**itertools.combinations(iterable, r)** : r-length tuples, in sorted order, no repeated elements  

```python
from itertools import combinations
a = ['A', 'B', 'C']
b = list(combinations(a, 2))
print(b)

# [('A', 'B'), ('A', 'C'), ('B', 'C')]
```

**itertools.product(p, q, … [repeat=1])** : cartesian product, equivalent to a nested for-loop

```python
from itertools import product
a = ['A', 'B', 'C']
b = list(product(a, repeat=2))
print(b)

# [('A', 'A'), ('A', 'B'), ('A', 'C'), ('B', 'A'), ('B', 'B'), ('B', 'C'), ('C', 'A'), ('C', 'B'), ('C', 'C')]
```

**itertools.combinations_with_replacement(p, r)** : r-length tuples, in sorted order, with repeated elements

```python
from itertools import combinations_with_replacement
a = ['A', 'B', 'C']
b = list(combinations_with_replacement(a, 2))
print(b)

# [('A', 'A'), ('A', 'B'), ('A', 'C'), ('B', 'B'), ('B', 'C'), ('C', 'C')]
```

+ 추가로 `**join**`을 사용하게 되면 집합의 원소를 하나의 문자열로 사용할 수 있다.
```python
from itertools import combinations_with_replacement
a = ['A', 'B', 'C']
b = list(map(''.join, combinations_with_replacement(a, 2)))
print(b)

# ['AA', 'AB', 'AC', 'BB', 'BC', 'CC']
```
