## try-except

try 블록에서 에러 발생하면 except블록의 코드가 실행되는 구조

```python
try:
	실행할 코드
except:
	예외가 발생할 때 실행할 코드
```

- **ZeroDivisionError** : 0으로 숫자를 나눌 때 발생하는 에러
    
    ```python
    try:
    	num = 10 / 0
    except ZeroDivisionError:
    	print("0으로 나눌 수 없습니다!")
    ```
    
- **IndexError** : 리스트나 튜플에서 잘못된 인덱스에 접근하려 할 때 발생하는 에러
    
    ```python
    try:
    	a = [1, 2, 3]
        print(a[4])
    except IndexError:
    	print("잘못된 인덱스입니다. 인덱스 범위 내에 있는지 확인하세요.")
    ```
    
- **KeyError** : 딕셔너리에 존재하지 않는 키에 접근하려 할 때 발생
    
    ```python
    try:
    	data = {'apple': 5000, 'banana': 4000}
        print(data['tomato'])
    except KeyError:
    	print("키가 존재하지 않습니다! 딕셔너리에 키가 있는지 확인하세요.")
    ```
    
- **FileNotFoundError** : 존재하지 않는 파일을 열려고 할 때 발생하는 에러
    
    ```python
    try:
    	f = open('data.csv')
    except FileNotFoundError:
    	print("파일을 찾을 수 없습니다. 파일 경로가 올바른지 확인하세요.")
    ```