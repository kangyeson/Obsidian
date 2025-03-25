## find()

- 문자열.find(’찾는 문자or문자열’, 탐색 시작 위치, 탐색 끝 위치)
- 문자열에서만 사용 가능(리스트, 튜플, 딕셔너리 자료형에서 사용 시 에러 발생)
- **찾는 문자가 없는 경우 -1 반환**

```python
a = 'abcdab'
print(a.find('a')) # 0
print(a.find('c')) # 2
print(a.find('bcd')) # 1 => 문자열의 위치를 찾을 수도 있음
print(a.find('a', 2)) # 4 => 시작점만 지정한 경우
print(a.find('a', 2, 5)) # 4 => 시작점과 끝점을 지정한 경우
print(a.find('a', 2, 4)) # -1 => 끝점이 4인 경우 끝 범위가 3까지임을 알 수 있음 + 찾는 문자가 없는 경우 -1 반환
```

## index()

- 변수.find(’찾는 문자’, 탐색 시작 위치, 탐색 끝 위치)
- 문자열, 리스트, 튜플에서 사용 가능(딕셔너리 자료형에서 사용 시 에러 발생)
- 찾는 문자가 없는 경우 ValueError발생

```python
a = 'abcdab'
print(a.index('a')) # 0
print(a.index('c')) # 2
print(a.index('bcd')) # 1
print(a.index('a', 2)) # 4
print(a.index('a', 2, 5)) # 4
# print(a.index('a', 2, 4)) #찾는 문자가 존재하지 않아 에러 발생!!

# 리스트에서도 사용 가능
b = [1, 2, 3]
print(b.index(2)) # 1   

# 튜플에서도 사용 가능
c = ('a', 'b', 'c', 'd')
print(c.index('c')) # 2
```