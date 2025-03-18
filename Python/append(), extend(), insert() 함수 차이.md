## 1. append()

array.append(x) 형태로 사용한다.

괄호() 안에 들어간 값을 array 맨 끝에 객체로 추가한다. 요소를 추가할 때는 객체로 추가하게 되는데, 입력한 값이 리스트와 같은 반복 가능한 [ierable](https://www.notion.so/Iterable-Iterator-1ad44dbcbb248035acd3e7e1dfb4b181?pvs=21) 자료형이더라도 객체로 저장한다.

```python
nums = [1,2,3]
nums.append(4) #[1,2,3,4]

# 리스트는 형태 그대로 하나의 객체로 추가됨.
nums.append([5,6]) #[1,2,3,4,[5,6]]
```

## 2. extend()

array.extend([iterable](https://www.notion.so/Iterable-Iterator-1ad44dbcbb248035acd3e7e1dfb4b181?pvs=21)) 형태로 사용한다.

append와 동일하게 요소를 array의 끝에 추가하지만 다른 점은 iterable 자료형만을 입력 받을 수 있다는 것이다.

iterable 자료형이 아닌 경우 TypeError가 발생한다.

```python
nums = [1,2,3]
nums.extend([4,5]) #[1,2,3,4,5]

a = [10]
nums.extend(a) #[1,2,3,4,5,10]
# a는 iterable자료형이 아닌 int형 10을 가진다면 에러발생
#하지만 이렇게 요소 하나만 추가한다면 append함수를 사용하는 것이 편리
```

## 3. insert()

array.insert(i, x) 형태로 사용한다.

array의 원하는 위치 i 앞에 추가할 값 x를 삽입할 수 있다.

i는 위치를 나타내는 인덱스 숫자를 입력한다. 음수를 입력하면 배열의 끝을 기준으로 처리된다. iterable 자료형도 추가 가능하다.

```python
nums = [1,2,3]
nums.insert(0, [10, 20]) # 0번째(맨앞에) 추가
# [10,20],1,2,3]

nums.insert(-1, 100) # 끝에서 1번째 전에 추가
# [10,20],1,2,100,3]
```

array의 끝에 추가하고 싶은 경우 len() 함수를 이용할 수 있다.