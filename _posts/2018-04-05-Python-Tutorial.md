---
title: Python Tutorial
description: 
categories: 
tags: Python
---

![Python Tutoral](https://www.freelancinggig.com/blog/wp-content/uploads/2017/12/Python-Tutorial.png)

# Python 특징

- 프로그래머 친화적 언어 - 사용하기 쉽다.
- 표현적 언어 - 코드를 더 쉽게 이해할 수 있다.
- 인터프리트 언어 - 한줄씩 실행하여 디버깅하는 것이 쉽다.

## jupyter notebook 

주피터 노트북 (Jupyter Notebook)은 머신러닝과 데이터 사이언스에서 많이 사용되는 툴이다. 웹 브라우저에서 파이썬 코드를 라인 별로 실행하고 마크다운을 지원한다.  

설치 `pip install Jupyter`  
실행 `jupyter notebook`

## String

길이 알아보기, 원하는 길이만큼 출력하기.

```python
string = "Hello World"
len(string) # 11
string[0:5] # Hello
string[:5]
string[6:11] # World
string[6:]
```

문자열을 리스트로 나누기.

```python
string = "Hello, World, Soovin, Jeemyeong"
string.split(", ") # ['Hello', 'World', 'Soovin', 'Jeemyeong']
```

 %s 포맷 코드. 문자열 포맷 코드는 어떤 형태의 값이든 변환해 넣을 수 있다.

```python
"I have %s apples" % 3 # 'I have 3 apples'
"rate is %s" % 3.234 # 'rate is 3.234'
```

## String 숫자, 알파벳 판별

isdigit() : 숫자로만 구성되있는지 확인해주는 함수  
isalpha() : 문자로만 구성되있는지 확인해주는 함수

```python
    str = '123'
    str.isdigit() # True
    str = 'abc'
    str.isalpha() # True
```

## List

리스트에 추가하기, 제거하기.

```python
say_hi = ["Hello", "Hi"]
say_hi.append("HEHE")
say_hi # ["Hello", "Hi", "HEHE"]
say_hi.pop() # 숫자를 넣으면 인덱스에 해당하는 값을 제거한다. 없는 경우는 마지막 값을 뺀다.
say_hi # ["Hello", "Hi"]
```

리스트 안에 리스트 넣기.  
안에 있는 리스트(say_hi)에 값을 추가하게 되면, 리스트 자체가 바뀌기 때문에 두번째 say_hi 리스트에도 'Yo'가 추가된다.

```python
nested_ary = [say_hi, say_hi]
nested_ary[0].append("Yo")
nested_ary # [['Hello', 'Hi', 'Yo'], ['Hello', 'Hi', 'Yo']]
```

리스트 원하는 길이만큼 출력, 문자열로 합치기.

```python
ary_list = ['Hello', 'World', 'Soovin', 'Jeemyeong']
ary_list[1:3] # ['World', 'Soovin']
", ".join(ary_list) # "Hello, World, Soovin, Jeemyeong"
```

정렬. sort()는 void함수이기 때문에 리스트를 출력하지 않는다.

```python
ary_list.sort() # None (void 함수)
ary_list # ['Hello', 'Jeemyeong', 'Soovin', 'World']
```

sorted(리스트)는 리스트를 바로 출력한다.

```python
ary_list = ['Hello', 'World', 'Soovin', 'Jeemyeong']
sorted(ary_list) # ['Hello', 'Jeemyeong', 'Soovin', 'World']
```

sorted에 reverse를 하게 되면 반대로 정렬이 된다.  
`key=lambda x: len(x)`를 이용하면, 길이 순서대로 정렬된다.

```python
sorted(ary_list, reverse=True) # ['World', 'Soovin', 'Jeemyeong', 'Hello']
sorted(ary_list, key=lambda x: len(x)) # ['Hello', 'World', 'Soovin', 'Jeemyeong']
```

## Dictionary

HashMap과 같이, 각각의 요소는 Key : Value 형태로 이루어져 있고 쉼표(,) 로 구분되어 있다.  
(※ Key에는 변하지 않는 값을 사용하고, Value에는 변하는 값과 변하지 않는 값 모두 사용할 수 있다.)

```python
dic = {
  "Hello": "World",
  "Jeemyeong": {
    "Soovin": 3
  }
}
dic["Jeemyeong"]["Soovin"] # 3
# dic.add(4) # AttributeError: 'dict' object has no attribute 'add'

추가, 삭제하기.

# HashMap
# dic = dict()
dic = {}
dic["Soovin"] = "Jeemyeong" # {'Soovin': 'Jeemyeong'}
dic[1] = 2 # {'Soovin': 'Jeemyeong', 1: 2}
del dic[1] # {'Soovin': 'Jeemyeong'}
```

해당 Key가 딕셔너리 안에 있는지 조사하기(in)

```python
a = {'name':'pey', 'phone':'0119993323', 'birth': '1118'}
'name' in a # True
'email' in a #False
```

## Set

중복을 허용하지 않는다.  
순서가 없다(Unordered).
a = {} 와 같이, 값이 없을경우에는 딕셔너리로 인식하게 된다.

```python
s1 = set() # 값이 비어있는 집합 자료형
s1 = [1, 2, 3]
print(set(s1))   # {1, 2, 3}
s2 = set("Hello")
print(s2)   # {'H', 'o', 'e', 'l'}
```

### 인덱싱

set 자료형에 저장된 값을 인덱싱으로 접근하려면 다음과 같이 리스트나 튜플로 변환한 후 해야 한다.

```python
s1 = set(s1)
l1 = list(s1)
print(l1)   # [1, 2, 3]
print(l1[0])   # 1
t1 = tuple(s1)
print(t1)   # (1, 2, 3)
print(t1[0])   # 1
```

### 집합

set 자료형이 정말 유용하게 사용되는 경우는 다음과 같이 교집합, 합집합, 차집합을 구할 때이다.

```python
s1 = {1, 2, 3, 4, 5, 6}
s2 = {4, 5, 6, 7, 8, 9}

print('교집합', s1 & s2)   # {4, 5, 6}
print('합집합', s1 | s2)   # {1, 2, 3, 4, 5, 6, 7, 8, 9}
print('차집합', s1 - s2)   # {1, 2, 3}
print('합집합-교집합', s1 ^ s2)   # {1, 2, 3, 7, 8, 9}
```

### 추가

```python
s1 = {1, 2, 3}
s1.update([4, 5, 6])    # 여러 개 업데이트
s1.add(4)   # 1개 추가
print(s1)   # {1, 2, 3, 4, 5, 6}
```

### 제거

```python
s1.remove(2)
print(s1)   # {1, 3, 4, 5, 6}
```

## If

```python
if False:
    print("Hello")
else:
    print("World")

c = True
# if c == True:
if c is True:
    c # True

a = 1 if 9 % 5 == 4 else 2 # 1
a = 1 if 9 % 5 == 3 else 2 # 2
```

## While

```python
cnt = 0
# while(cnt < 10) {}
while cnt < 10:
    cnt += 1
    cnt # cnt가 1씩 증가한다.
```

## For

```python
# for(int i = 0; i < 10; i++)
for i in range(10):
    i # 0부터 9까지 순서대로 증가한다.

# for(int i = 5; i < 10; i++)
for i in range(5, 10):
    i # 5부터 9까지 순서대로 증가한다.

# for(int i = 1; i < 10; i += 2)
for i in range(1, 10, 2):
    i # 1부터 9까지 2씩 증가한다.

for i in range(10):
    if i % 3 == 0:
        continue
    i # 1,2,4,5,7,8 이 순서대로 실행된다.
```

list에 for문을 통해 원소를 넣는다.

```python
ary_list = [1, 3, 5, 7, 9]
for i in ary_list:
    i # ary_list의 원소들이 하나씩 할당된다.

for_in_ary = [x for x in range(10)]
for_in_ary # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

for_in_ary = [2*x for x in range(10)]
for_in_ary # [0, 2, 4, 6, 8, 10, 12, 14, 16, 18]

for_in_ary = [2*x if x%2 == 1 else x for x in range(10)]
for_in_ary # [0, 2, 2, 6, 4, 10, 6, 14, 8, 18]

for_in_ary = [x for x in ['Hello', 'World', 'Soovin', 'Jeemyeong']]
for_in_ary # ['Hello', 'World', 'Soovin', 'Jeemyeong']
```

## Float

```python
float_num = float(3)
float_num # 3.0

float_num = 3/1
float_num # 3.0

float_num = int(3.0)
float_num # 3

str(3) + "3" # "33"
int("3") + 3 # 6
# 3 + "3" # TypeError: unsupported operand type(s) for +: 'int' and 'str'

# input_str = input()
# type(input_str) # <class 'str'>

# input_int = int(input())
# type(input_int) # <class 'int'>

# input_str_ary = [input() for x in range(3)]

# input_int_ary = [int(input()) for x in range(3)]
```

## Def

파이썬에서 함수를 정의할 때는 def 문을 사용한다.  
입력을 할때 input()대신 sys.stdin.readline()을 이용하면 더 효율적으로 시간을 줄일 수 있다.

```python
# def LI(): return [int(x) for x in sys.stdin.readline().split()]
import sys
def LI():
    # return [int(x) for x in input().split()]
    return [int(x) for x in sys.stdin.readline().split()]

# input_int_ary = LI()
# print(input_int_ary) # "1 2 3" => [1, 2, 3]
```

문자와 숫자를 곱하게 되면, 그 숫자만큼 문자가 반복된다.

```python
a = 3 * 4
a # 12
b = "3" * 4
b # "3333"

def mult(x, y):
    return x * y

mult(3, 4) # 12
mult(3, "4") # "444"
# mult("3", "4") # TypeError: can't multiply sequence by non-int of type 'str'
```

## Min, Max

내장함수인 min, max를 이용하여 최소값, 최대값을 구할 수 있다.  
또한 lambda를 이용하여 길이 중에서 최소값을 찾을 수 있다.

```python
min([1,2,3,4,5]) # 1
max([1,2,3,4,5]) # 5
min(["ab", "a", "abc"], key=lambda x:len(x)) # "a"
```

## Math

math를 import하여 제곱을 구할 때는 pow(), 제곱근을 구할 때는 sqrt()를 사용한다.  
float형에서 int형으로 바꾸면서 소수점 밑을 버릴 수 있다.

```python
import math

3**2 # 9
math.pow(3, 2) # 9.0
math.sqrt(9) # 3.0

3 == 3.0 # True
int(3.9) # 3
```

## pass, continue 차이점

pass는 그냥 아무것도 하지 않는다의 의미로 쓴다. 즉 수행할 코드가 없음을 명시적으로 표현할 뿐이다. continue는 강제로 다음 루프를 돌리게 한다.

```python
for i in [1,2,3]:
    print i
    if i:
        pass
        print "pass"
# 1
# pass
# 2
# pass
# 3
# pass

for i in [1,2,3]:
    print i
    if i:
        continue
        print "continue"
# 1
# 2
# 3
```
