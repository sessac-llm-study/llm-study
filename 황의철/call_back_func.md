## 콜백 함수 

- 콜백함수란?
    - 다른 함수에 인자로 전달되는 함수 
    - 쉽게 설명해서 역순으로 함수가 실행되는 로직 
    - 더 쉽게 함수가 2번 호출되는 방법임 


```python
def greeting(name):
    return "안녕, " + name

def farewell(name):
    return name + ", 안녕히 가세요."

def handle_user(name, callback):
    print(callback(name))

handle_user("영희", greeting)  # 출력: 안녕, 영희
handle_user("철수", farewell)  # 출력: 철수, 안녕히 가세요.
```

예시에서 `handle_user` 함수는 이름과 콜백 함수를 인자로 받음 

이 함수는 주어진 콜백 함수에 이름을 인자로 전달해서, 호출하고 그 결과를 출력함 

이렇게 콜백 함수를 사용해서, `handle_user` 함수는 다양한 상황에서 유연하게 대응할 수 있음 

----

## 이게 왜 필요하냐?

왜 필요하긴 ㅋㅋ

`filter`, `map`, `reduce` 등이 이 콜백 기반으로 움직이거든 

3.7 버전 이후로는 `reduce`는 내장함수에서 제외되어,`functools` 에서 `import` 해야합니다. 

`filter` 
```python
# 짝수만 필터링하는 예제
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
even_numbers = filter(lambda x: x % 2 == 0, numbers)
print(list(even_numbers))  # 출력: [2, 4, 6, 8, 10]
```


`map` 
```python
# 각 요소를 제곱하는 예제
numbers = [1, 2, 3, 4, 5]
squared_numbers = map(lambda x: x ** 2, numbers)
print(list(squared_numbers))  # 출력: [1, 4, 9, 16, 25]
```

`reduce` 

```python
# 모든 요소의 합을 계산하는 예제
from functools import reduce

numbers = [1, 2, 3, 4, 5]
sum_of_numbers = reduce(lambda x, y: x + y, numbers)
print(sum_of_numbers)  # 출력: 15

```