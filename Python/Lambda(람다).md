```python
solution = lambda a, b, c: a+b+c if a!=b and b!=c and c!=a else ((a+b+c)*(a**2+b**2+c**2)*(a**3+b**3+c**3) if a==b and b==c else (a+b+c)*(a**2+b**2+c**2))
```