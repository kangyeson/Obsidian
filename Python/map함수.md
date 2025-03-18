## [map]

리스트, 튜플 등 반복 가능한 [iterable자료형](https://www.notion.so/Iterable-Iterator-1ad44dbcbb248035acd3e7e1dfb4b181?pvs=21)을 입력받아, 해당 객체의 모든 요소에 대해 **(특정 함수or자료형 변환)**을 적용한 결과를 새로운 리스트로 반환하는 함수이다.

- **map(자료형&함수, iterable값)**

```python
def square(numbers):
    return numbers ** 2

numbers = [1,2,3,4,5]
squared = map(square, numbers) #함수에 numbers의 객체를 모두 적용
print(list(squared)) # [1, 4, 9, 16, 25]
```

- 여러 개의 리스트를 map함수에 적용하기

```python
numbers1 = [1, 2, 3, 4, 5]
numbers2 = [6, 7, 8, 9, 10]

#lambda함수 사용
squared = map(lambda x, y: x ** y, numbers1, numbers2)
print(list(squared)) # [1, 128, 6561, 262144, 9765625]

#단순 함수 사용
first_it = [1, 2, 3]
second_it = [4, 5, 6, 7]

list(map(pow, first_it, second_it)) # [1, 32, 729]
```

- filter 함수와 map 함수 함께 사용하기

```python
def is_positive(num):
    return num >= 1

num_list = [0,1,2,3,0]
list(map(str, filter(is_positive, num_list))) # ['1', '2', '3']
```