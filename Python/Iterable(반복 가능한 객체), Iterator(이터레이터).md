# [Iterable]

: 반복 가능한 객체

반복 가능함은 객체를 구성하는 요소가 여러 개이면서, 이 요소들을 **한 번에 하나씩** 꺼낼 수 있다는 것을 의미한다.

→ 객체의 모든 요소를 미리 메모리에 저장할 필요가 없어진다.

실행마다 다음 요소에 해당하는 값만 새로 추가해주면 되기 때문.

→ 메모리 절약됨

## 파이썬에서 기본적으로 사용할 수 있는 Iterable

- List
- Tuple (Read Only List)
- 문자열
- Dictionary (key-value 자료형)
- Set (집합 개념, 중복 허용X, 순서X)
- File

## Iterable한 객체를 argument(전달인자)로 받는 함수 종류

- **all(x)** : 모두 참이면 True, 하나라도 거짓이면 False

```python
x = [1,2,3,4]
all(x) #True
x = [0,1,2,3]
all(x) #False
```

- **any(x)** : 하나라도 참이면 True, 모두 거짓이면 False

```python
x = [1,2,3,4]
all(x) #True
x = [0,""]
all(x) #False
```

- **filter (function, iterable)** : 첫 번째 함수에서 참인 것만 리턴

```python
def positive(x):
	return x > 0

print(list(filter(positive, [1, -2, 3, -4, 5, -6])))
# [1, 3, 5]
```

- **map (function, iterable)** : 자료형의 각 요소가 함수f에 의해 수행된 결과를 묶어서 리턴

```python
def two_times(x) : return x*2
list(map(two_times, [1,2,3,4,5]))
# [2,4,6,8,10]

list(map(lambda x : x+1, [1,2,3,4,5]))
# [2,3,4,5,6]
```

- **max (iterable), min (iterable)** : 최대값, 최솟값 리턴
- **Sorted (iterable)** : 입력값을 정렬한 후 그 결과를 리스트로 리턴하는 함수
- **tuple (iterable)** : 튜플 형태로 바꾸어 리턴하는 함수 (만약 튜플이 입력되면 그대로 리턴

```python
tuple("abc") #('a','b','c')
tuple([1,2,3]) #(1,2,3)
tuple((1,2,3)) #(1,2,3)
```

- __zip (iterable_)_* : 동일한 개수로 이루어진 자료형을 튜플 형태로 묶어주는 기능을 하는 함수

```python
list(zip([1,2,3], [4,5,6])) #[(1,4), (2,5), (3,6)]
list(zip("abc","def")) #[('a','d'), ('b','e'), ('c','f')]
```

## Iterable 객체의 특성

객체가 반복 가능해지려면 내부에 **iter** 메소드가 있어야 한다.

따라서 **hashattr**과 같은 함수를 사용해서 객체의 iterable 여부를 확인할 수 있다.

**hashattr(확인할 객체, “**iter**”)** # 있다면 해당 객체는 iterable

```python
from typing import Iterable

print(isinstance([1,2,3], iterable)) #True
print(isinstance('abcd', Iterable)) #True
print(isinstance({1:'cal', 2:'jun'}, Iterable)) #True
print(isinstance((5,6,7), Iterable)) #True
print(isinstance(set([5,6,7]), Iterable)) #True
```

### 따라서 내부에 **iter** 메서드만 선언해준다면 모두 Iterable 객체로 인식하게 된다.

```python
class Temp:
	def __init(self):
		pass
	def __iter__(self, start, end):
		pass
		
print(isinstance(Temp(), Iterable)) #True
```

→ 아무 내용도 의미도 없는 ‘Temp’ Calss에 **iter** 메서드를 선언하니 Iterable 객체로 인식된다.

## Iterator = iter(iterable)

**Iterator**는 Itreable 객체에서 __iter__메서드를 통해 생성되는 객체이다.

![](https://i.imgur.com/NkkesxL.png)


- 상태가 존재하기 때문에 한 번 순회하면 재사용할 수 없다.
- 내부에 존재하는 **__next__메서드**를 통해 다음 값을 하나씩 차례대로 반환한다.
- 마지막 원소까지 접근하여, 더 이상 반환할 수 있는 값이 없다면 StopIteration 에러를 반환하며 순회를 종료한다.

## Iterable과 Iterator의 차이

1. Iterabl은 순회 당하는 객체, Iterator는 순회를 주관하는 객체
2. Iterable은 재사용 가능, Iterator는 재사용 불가

```python
list_a = [1,2,3,4] #Iterable 객체, for문에서 몇번을 사용하든 재사용 가능

#list_a에서 __iter__ 메서드를 통해 iterator_a를 생성
iterator_a = list_a.__iter__()
for i in iterator_a:
	print(i, end='') # 결과값 : 1 2 3 4
# -> iterator_a는 다른 for문에서 상태가 없는 상태. 다시 선언하지 않는 이상 재사용 불가	
```

## iterator(이터레이터) 예시

대표적으로 우리가 많이 활용하는 이터레이터로는 for문이 있다.

![](https://i.imgur.com/GnPUKNc.png)
