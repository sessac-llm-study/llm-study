## 1일차 

## 조건문

### 형식

```python
if A:  #조건 
	B #실행할 내용 #4칸 들여쓰기
```

### 예시

```python
age = 23
if age > 19:
	print('성인은 주류를 구매할 수 없습니다')		
```

```python
age = 18
if age <20:
	print('미성년자는 주류를 구매할 수 없습니다.')
```

```python
#20 미만인 수를 입력했을 때

age = int(input('나이가 어떻게 되세요?'))
if age <20: 
	print('미성년자는 주류를 구매할 수 없습니다.')
