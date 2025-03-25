
## 작성한 코드

```python
def solution(q, r, code):
    answer = [code[i] for i in range(len(code)) if i%q==r]
    return ''.join(answer)
```

- code의 index를 반복문으로 돌리며 index%q가 r인것만 찾아 저장

## 인상깊은 풀이

```python
def solution(q, r, code):
    return code[r::q]
```

- 문자열 code의 index를 q로 나누면 q-1까지의 나머지가 q간격으로 반복되니, target나머지가 곧 시작 index가 되고, 그걸 code의 끝까지 q간격으로 반환하는거나 다름없음.
- index = xq+r임을 알 수 있음. 우리가 필요한 인덱스는 \[0q+r, 1q+r, 2q+r... xq+r]임. 즉, \[r, q+r, 2q+r... xq+r]임을 알 수있고, r로 시작해서 q씩 커지는 index만 가져오면 됨.