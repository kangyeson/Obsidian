**Zip함수** :

반복 가능한(iterable) 객체를 인자로 받아 동일한 인덱스의 요소를 튜플 형태로 묶어주는 역할을 한다.

ex)

```python
list1 = [1, 2, 3]
list2 = ['a', 'b', 'c']
zipped = zip(list1, list2)
print(list(zipped)) #[(1, 'a'), (2, 'b'), (3, 'c')]
```

[https://docs.python.org/3/library/functions.html#zip](https://docs.python.org/3/library/functions.html#zip)

→ 공식 문서

### zip함수의 결과 다시 분리하기

zip형태를 *(asterisk)를 이용해 분리할 수 있다.

```python
list1 = [1, 2, 3]
list2 = ['a', 'b', 'c']
zipped = zip(list1, list2)

unzipped_list1, unzipped_list2 = zip(*zipped)
print(list(unzipped_list1))  # [1, 2, 3]
print(list(unzipped_list2))  # ['a', 'b', 'c']
```

### zip으로 두 리스트를 dict으로 변경

zip함수는 두 개의 리스트를 튜플로 묶어주는 기능이 있기 때문에, 이를 활용하여 두 리스트를 dictionary(key, value) 형태로 쉽게 바꿔줄 수 있다.

```python
keys = ['name', 'age', 'job']
values = ['Alice', 25, 'Engineer']

dictionary = dict(zip(keys, values))
print(dictionary)  # Output: {'name': 'Alice', 'age': 25, 'job': 'Engineer'}
```

### 여러 리스트를 동시에 순회하기

**for루프를 사용하여 리스트를 순회하면서 동일한 인덱스의 다른 요소를 참조해야 할 때**, zip함수를 사용하여 코드를 간결하게 만들 수 있다.

```python
names = ['Alice', 'Bob', 'Charlie']
ages = [25, 30, 35]

for name, age in zip(names, ages):
    print(f'{name} is {age} years old.')

# Output:
# Alice is 25 years old.
# Bob is 30 years old.
# Charlie is 35 years old.
```

[zip함수 응용 문제](https://www.notion.so/qr-code-1b844dbcbb2480ba946dfc8b1b9b4912?pvs=21)