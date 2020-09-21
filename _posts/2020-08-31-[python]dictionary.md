---
title: (Python)Dictionary 
categories: [python]
comments: true
---

## Dictionary(딕셔너리)
딕셔너리는 키(key)와 값(value)으로 이루어진 집합으로, 해쉬테이블 구조를 가지고 있다.
키(key)는 immutable(값을 변경할 수 없는)만 가능하고, 값(value)은 immutable과 mutable 모두 가능하다. 즉, 키(key)로 리스트(list) 또는 딕셔너리(dict)가 올 수 없다.

### 딕셔너리 선언
```python
a = {}
b = dict()

print(type(a))  # <class 'dict'>
print(type(b))  # <class 'dict'>
```

### 딕셔너리 접근
순서가 없기 때문에 인덱스로 접근하는 것이 불가능하고, 키로 접근할 수 있다
```python
# {key1 : value1, key2 : value2, key3 : value3, ...}

n = {1: 'A', 2: 'B', 3: 'C'}

print(n[0])  # KeyError
print(n[1])  # 'A'

n[2] = 'D'
print(n)  # {1: 'A', 2: 'D', 3: 'C'}
```

### 추가, 삭제
```python
n = {1: 'A', 2: 'B', 3: 'C'}

n[5] = 'E' # 추가
print(n)  # {1: 'A', 2: 'B', 3: 'C', 5: 'E'}

del n[1] # 삭제
print(n)  # {2: 'B', 3: 'C', 5: 'E'}
```

### 키(key), 값(value) 뽑아내기
```python
n = {'red': 100, 'yellow': 120, 'green': 160, 'blue': 200}
  
print(n.keys())  # dict_keys(['red', 'yellow', 'green', 'blue'])
print(n.values())  # dict_values([100, 120, 160, 200])
print(n.items())  # dict_items([('red', 100), ('yellow', 120), ('green', 160), ('blue', 200)])
```  

- for문을 사용하여 출력하기  

```python
# key 값 출력
n = {'red': 100, 'yellow': 120, 'green': 160, 'blue': 200}  
  
for i in n:  
    print(i)

# red
# yellow
# green
# blue
```

```python
# value값 출력
n = {'red': 100, 'yellow': 120, 'green': 160, 'blue': 200}  
  
for i in n.values():  
    print(i)

# 100
# 120
# 160
# 200
```

### 딕셔너리 key의 존재 여부
```python
n = {'red': 100, 'yellow': 120, 'green': 160, 'blue': 200}  
  
print('red' in n)  # True
print('orange' in n)  # False
```

### 딕셔너리의 변환
아래와 같이 key와 value의 값을 리스트나 튜플에서 딕셔너리로 변환해줄 수 있다.
```python
n = [['red', 100], ['yellow', 120], ['green', 160]]  
  
print(dict(n))  # {'red': 100, 'yellow': 120, 'green': 160}
```

### 딕셔너리 복사
shallow copy
```python
a = {'red': 100, 'yellow': 120, 'green': [160, 190]}  
  
b = a.copy()  
b['green'].append(200)  
  
print(a)  # {'red': 100, 'yellow': 120, 'green': [160, 190, 200]}
print(b)  # {'red': 100, 'yellow': 120, 'green': [160, 190, 200]}
```

deep copy
```python
import copy  
  
a = {'red': 100, 'yellow': 120, 'green': [160, 190]}  
  
b = copy.deepcopy(a)  
b['green'].append(200)  

print(a)  # {'red': 100, 'yellow': 120, 'green': [160, 190]}
print(b)  # {'red': 100, 'yellow': 120, 'green': [160, 190, 200]}
```

### 딕셔너리 정렬

#### 1. 키(key)를 기준으로 딕셔너리를 정렬하는 방법

- 키를 기준으로 오름차순 정렬  

```python
a = {"red": 20, "yellow": 40, "blue": 50, "green": 70}  
  
b = sorted(a.keys())  
print(b)   # ['blue', 'green', 'red', 'yellow']
  
c = sorted(a.items())  
print(c)   # [('blue', 50), ('green', 70), ('red', 20), ('yellow', 40)]
```

```python
# lambda 함수 사용

a = {"red": 20, "yellow": 40, "blue": 50, "green": 70}  
  
b = sorted(a.items(), key = lambda x: x[0])  
print(b) 

# [('blue', 50), ('green', 70), ('red', 20), ('yellow', 40)]
```

- 키를 기준으로 내림차순 정렬

  내림차순으로 정렬하려면 reverse=True 옵션을 추가하면 된다.

```python
a = {"red": 20, "yellow": 40, "blue": 50, "green": 70}  
  
b = sorted(a.keys(), reverse=True)  
print(b)   # ['yellow', 'red', 'green', 'blue']  
  
c = sorted(a.items(), reverse=True)  
print(c)   # [('yellow', 40), ('red', 20), ('green', 70), ('blue', 50)]  
```

```python
# lambda 함수 사용

a = {"red": 20, "yellow": 40, "blue": 50, "green": 70}  
  
b = sorted(a.items(), key = lambda x: x[0], reverse=True)  
print(b)

# [('yellow', 40), ('red', 20), ('green', 70), ('blue', 50)]
```

#### 2. 값(value)을 기준으로 딕셔너리를 정렬하는 방법

- 값을 기준으로 오름차순 정렬 

```python
# lambda 함수 이용

a = {"red": 20, "yellow": 40, "blue": 50, "green": 70}  
  
b = sorted(a.items(), key=lambda x: x[1])  
print(b)

[('red', 20), ('yellow', 40), ('blue', 50), ('green', 70)]
``` 

- 값을 기준으로 내림차순 정렬

  내림차순으로 정렬하려면 reverse=True 옵션을 추가하면 된다.

```python
# lambda 함수 이용

a = {"red": 20, "yellow": 40, "blue": 50, "green": 70}  
  
b = sorted(a.items(), key=lambda x: x[1], reverse=True)  
print(b)

# [('green', 70), ('blue', 50), ('yellow', 40), ('red', 20)]
```

> 활용
```python

a = {"red": 20, "yellow": 40, "blue": 50, "green": 70}  
  
b = sorted(a.items(), key=lambda x: len(x[0]), reverse=True)  
  
for key, value in b:  
    print(key, ":", value)
    
# yellow : 40
# green : 70
# blue : 50
# red : 20
```
