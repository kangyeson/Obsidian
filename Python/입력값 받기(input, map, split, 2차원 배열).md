## 1. input

- 문자열 입력받기

```python
a = input()
print(a)
```

- 숫자 입력받기 : int() 사용하여 값 형 변환

```python
a = int(input())
print(a)
```

## 2. split

: 특정 문자를 기준으로 문자열을 나눈 뒤, 리스트 형태로 반환한다.

- **문자열.split(’구분자’, 분할횟수)**

```python
res = input().split(',', 3) #'a,b,c,d,e,f,g'
print(res) #['a', 'b', 'c', 'd,e,f,g']
```

- **문자열.split()** : split 함수에 아무런 파라미터를 넣지 않으면 기본적으로 공백을 기준으로 분리한다.

```python
res = input().split() #'a b c d e f g'
print(res) #['a', 'b', 'c', 'd', 'e', 'f', 'g']
```

- **문자열.split(’구분자’)** : 구분자를 기준으로 문자열을 모두 나눠준다.

```python
res = input.split(',') #'a,b,c,d,e,f,g'
print(res) #['a', 'b', 'c', 'd', 'e', 'f', 'g']
```

- 리스트 반환을 두 변수에 나누어 받을 수도 있다.

```python
x, y = input().split() #Coding Everyday!
print(x) #Coding
print(y) #Everyday!
```

## 3. [map](https://www.notion.so/map-1af44dbcbb248040ac20da7a2ba1f58d?pvs=21) + split

- **map(자료형or함수,** **iterable값)**

map함수와 split함수를 활용하여 다중으로 입력받을 수 있다.

```python
# split()함수의 특성을 활용하여 공백을 기준으로 나눠, 
# map함수를 통해 int형으로 여러 값을 쪼개서 입력받는 코드
a, b, c = map(int, input().split())
print(a, b, c) #1 10 100
```

```python
# 리스트로 형변환된 값을 받는 것도 가능
number_list = list(map(int, input().split()))
print(number_list) #[1, 10, 100]
```

## 4. 2차원 배열 입력받기

map함수와 split함수를 응용하여 이차원 배열도 입력받을 수 있다.

**1 0 0 0 
0 1 0 0 
0 0 1 0**

아래 코드에 위 input을 넣을 경우 아래와 같은 이차원 배열값을 출력할 수 있음.

\[\[1, 0, 0, 0], \[0, 1, 0, 0], \[0, 0, 1, 0]]
```python
word_map = []
for _ in range(8):
	word_map.append(list(map(int, input().split())))
print(word_map) # [[1, 0, 0, 0], [0, 1, 0, 0], [0, 0, 1, 0]]

word_map2 = [list(map(int, input().split())) for _ in range(8)]
print(word_map2) # [[1, 0, 0, 0], [0, 1, 0, 0], [0, 0, 1, 0]]
```