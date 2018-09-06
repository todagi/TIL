## day 4

============================================================================

making 'fibo.py' : 피보나치 수열

```python

def fib(n):
    '''
    n까지의 피보나치 수열 출력하는 함수
    : param n : integer
    : return : None
    '''
    a, b = 0 , 1
    while b < n:
        print(b, end = ' ')
        a, b = b, a + b

    print()

def fib2(n):
    '''
    n까지의 피보나치 수열 반환하는 함수
    : param n : integer
    : return : List
    '''
    result = []
    a, b = 0, 1
    while b < n:
        result.append(b)
        a, b = b, a+b
    return result
    
```

모듈 불러오기

```python

import fibo
fibo.fib(100)


1 1 2 3 5 8 13 21 34 55 89 
```

```python
import fibo as f
f.fib(50)

1 1 2 3 5 8 13 21 34 
```
