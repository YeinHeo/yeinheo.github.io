---
title: (Python)Permutations & Combinations 
categories: [dev]
comments: true
---

## Permutations(순열)
서로 다른 {\displaystyle n}n개의 원소에서 {\displaystyle r}r(≤{\displaystyle n}n)개를 뽑아 한 줄로 세우는 경우의 수이며, {\displaystyle n}nP{\displaystyle r}r로 나타낸다.
순열은 순서를 고려하기 때문에 같은 원소로 구성되었더라도 순서가 다르면 다른 집합으로 분류된다.

## Combinations(조합)
서로 다른 n개의 원소 중에서 순서에 상관없이 r개를 선택하는 경우의 수이며, {\displaystyle n}nC{\displaystyle r}r로 나타낸다.
조합은 순서를 고려하지 않기 때문에 순서가 다르더라도 같은 원소로 구성되었다면 같은 집합으로 분류된다.

파이썬에서는 순열과 조합을 쉽게 구할 수 있도록 `itertools` 모듈을 제공한다.
**itertools.permutations(iterable[, r])** : r-length tuples, all possible orderings, no repeated elements
**itertools.combinations(iterable, r)** : r-length tuples, in sorted order, no repeated elements


```ruby
from itertools import permutations
a = ['A', 'B', 'C']
b = list(permutations(a, 2)
print(b)

# .
```
