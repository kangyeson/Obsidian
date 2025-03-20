파이썬은 임시변수를 생성할 필요없이 한 줄로 가능
```python
List = [3, 5]
List[0], List[1] = List[1], List[0]
# List = [5, 3]
```