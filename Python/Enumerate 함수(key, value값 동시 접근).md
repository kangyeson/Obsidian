- 순서가 있는 자료형(list, set, tuple, dictionary, string)의 인덱스(key)와 값(value)을 포함하여 리턴
- for문과 함께 자주 사용됨
- **인덱스(key)와 값(value)을 동시에 접근하면서 루프를 돌리고 싶을 때 사용**

**enumerate(순서가 있는 객체, start=0)**

- 원리

```python
sample = enumerate(sample)
next(sample) #(0, 7)
next(sample) #(1, 9)
```

enumerate로 감싼 변수를 next()를 통해 호출하면 인덱스(key)와 값(value)이 **튜플 형식으로 순서대로 반환되는 것**을 확인할 수 있다.

ex) enumerate로 key와 value값을 가지는 list추출 `fruits = ['orange', 'apple', 'pear', 'banana', 'kiwi', 'apple', 'banana']`

```python
print(fruits) 
#['orange', 'apple', 'pear', 'banana', 'kiwi', 'apple', 'banana']

print(list(enumerate(fruits))) 
#[(0, 'orange'), (1, 'apple'), (2, 'pear'), (3, 'banana'), (4, 'kiwi'), (5, 'apple'), (6, 'banana')]

# start로 시작 인덱스(key) 설정 가능
print(list(enumerate(fruits)), start=1)
#[(1, 'apple'), (2, 'pear'), (3, 'banana'), (4, 'kiwi'), (5, 'apple'), (6, 'banana')]
```

ex) for문과 함께 사용하는 경우

```python
# 인덱스와 값을 추출해 내기 위해 변수 2개를 선언하여 for문에 추가한다.
for key, value in enumerate(sample):
	print(key) # 인덱스 키값
	print(value) # 해당 인덱스의 값
	
# 결과
# 0 7
# 1 9
# 2 2
# 3 9
# 4 2
# 5 5

# start값을 지정할 경우
for key, value in enumerate(sample, start=2):
    print(key, value)
    
# 결과
# 2 7
# 3 9
# 4 2
# 5 9
# 6 2
# 7 5
```