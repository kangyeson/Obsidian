- 컴프리헨션(Comprehension)은 파이썬에서 컬렉션(리스트, 집합, 딕셔너리 등)을 생성하기 위한 간결하고 표현적인 방법
- 반복문과 조건문을 결합하여 컬렉션을 생성하는 한 줄 짜리 표현식으로 작성

## 리스트 컴프리헨션

```python
[표현식 for 요소 in 반복 가능한 객체 if 조건문]
```

![](https://i.imgur.com/84NkpWR.png)

ex) 1부터 10까지의 제곱 값을 갖는 리스트 생성

```python
squares = [x**2 for x in range(1,11)]
print(squares)
# [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

ex) 문자열 리스트에서 길이가 5 이상인 단어만 선택

```python
words = ['apple', 'banana', 'cherry', 'date', 'elderberry']
long_words = [word for word in words if len(word) >= 5]
print(long_words) 
# ['apple', 'banana', 'cherry', 'elderberry']
```

ex) 리스트의 요소를 변환하여 새로운 리스트 생성

```python
numbers = [1, 2, 3, 4, 5]
double = [num * 2 for num in numbers]
print(double)
# [2, 4, 6, 8, 10]
```

- [리스트 컴프리헨션 활용한 코테 풀이](https://www.notion.so/1b544dbcbb24805f9c81d21d9da790cd?pvs=21)

## 집합 컴프리헨션

위 리스트 컴프리헨션 예제에서 [대괄호]를 {중괄호}로 바꿔 그대로 집합 컴프리헨션으로도 사용 가능.

**집합 컴프리헨션은 중복된 요소를 제거하고 유일한 값을 가지는 집합을 생성**

```python
{표현식 for 요소 in 반복 가능한 객체 if 조건문}
```

## 딕셔너리 컴프리헨션

```python
{키_표현식: 값_표현식 for 요소 in 반복 가능한 객체 if 조건문}
```

ex) 1부터 5까지의 숫자를 Key로 하고 제곱 값을 값으로 갖는 딕셔너리 생성

```python
squares = { x: x**2 for x in range(1,6)}
print(squares)
# {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

ex) 문자열 리스트의 각 단어의 길이를 Key로 하고 해당 단어를 Value로 갖는 딕셔너리 생성

```python
words = ['apple', 'banana', 'cherry', 'date']
word_lengths = { word: len(word) for word in words}
print(word_lengths)
# {'apple': 5, 'banana': 6, 'cherry': 6, 'date': 4}
```