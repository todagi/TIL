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


```python

def exception_test():
    print("[1] Can you add 2 and '2' in python? ")
    print("[2] Try it~! ", 2+ '2')  # 예외 발생
    print("[3] It's not possible to add integer and string together. ")


exception_test()

```

```python
def exception_test2():
    print("[1] Can you add 2 and '2' in python? ")

    try:
        print("[2] Try it~! ", 2 + '2')  # TypeError 발생
    except TypeError:
        print("[2] I got TypeError! ")  # 에러 메시지 출력

    print("[3] It's not possible to add integer and string together. ")


exception_test2()
```


```python
def exception_test3():
    print("[1] Can you add 2 and '2' in python? ")
    
    try:
        print("[2] Try it~! ", 2+'2')     # TypeError 발생
    except TypeError as err:
        print("[2] TypeError: {}".format(err))    # 에러 메시지 출력
    
    
    print("[3] It's not possible to add integer and string together. ")
    
exception_test3()
```

```python
import traceback 

# 처음에 보았던 트레이스백 메시지와 함께 나타낸 함수
def exception_test4():
    print("[1] Can you add 2 and '2' in python? ")
    
    try:
        print("[2] Try it~! ", 2+'2')     # TypeError 발생
    except TypeError:
        print("[2] I got TypeError! Check below! ")    # 에러 메시지 출력
        traceback.print_exc()                          # 트레이스백 메시지 출력
    
    print("[3] It's not possible to add integer and string together. ")
    
exception_test4()
```

```python
def exception_test3():
    print("[1] Can you add 2 and '2' in python? ")

    try:
        print("[2] Try it~! ", 2 + '2')  # TypeError 발생
    except TypeError as err:
        print("[2] TypeError: {}".format(err))  # 에러 메시지 출력

    print("[3] It's not possible to add integer and string together. ")

finally:
    print("마지막")


exception_test3()

```
