## [Join]

리스트에 담긴 값들에 특정 구분자를 준다거나 값들을 합쳐서 출력할 때 사용

**’구분자’.join(리스트)**

```python
# 구분자를 안 넣었을 경우
test = ['Q', 'W', 'E', 'R']
print(''.join(test)) # QWER

# 구분자를 '*'로 넣었을 경우
test = ['Q', 'W', 'E', 'R']
print('*'.join(test)) # Q*W*E*R

# 구분자를 줄바꿈으로 주어 반복문 없이 줄바꿈 상태로 출력 가능
test = ['Q', 'W', 'E', 'R']
print('\\n'.join(test)) 
"""
Q
W
E
R
"""

```