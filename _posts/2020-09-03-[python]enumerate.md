---
title: (Python)Enumerate 
categories: [python]
comments: true
---

## Enumerate 함수
파이썬에서 enumerate 함수는 리스트, 튜플, 문자열 등 순서가 있는 자료형을 입력받아 인덱스 값을 포함하는 enumerate 객체를 돌려준다.

```python
a = ["yellow", "blue", "green"]
for index, value in enumerate(a):
	print(index, value)

# 0 yellow
# 1 blue
# 2 green
```

```python
a = ["yellow", "blue", "green"]
for i in enumerate(a):
	print(i)

# (0, 'yellow')
# (1, 'blue')
# (2, 'green')
```

```python
a = ["yellow", "blue", "green"]  
for index, value in enumerate(a):  
    print("{}번째 값은 {}".format(index, value))
    
# 0번째 값은 yellow
# 1번째 값은 blue
# 2번째 값은 green
```
