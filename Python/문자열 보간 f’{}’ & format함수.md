## 문자열 앞에 f 붙이고 중괄호에 함수&변수를 넣어 formatting

```python
a, b = map(int, input().strip().split(' '))
print(f'{str(a)} + {str(b)} = {(a + b)}')
```

## 문자열 format()함수

```python
print('두 개의 숫자는 {}과 {}이다.'.format(10,20))
# 두 개의 숫자는 10과 20이다.

print('두 개의 숫자는 { }과 { }이다.'.format(10,20))
# 중괄호{}안에 빈 칸이 포함되면 에러 발생
```