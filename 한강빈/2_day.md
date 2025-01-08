# 판다스(Pandas)
판다스(Pandas)는 파이썬 데이터 분석 라이브러리 중 하나로, 데이터 조작, 정제, 분석, 시각화 등을 위한 다양한 기능을 제공한다.
<br><br>
시리즈(Series)와 데이터프레임(DataFrame)이라는 자료형을 이용하여 데이터를 처리한다.

## 판다스 설치 코드

```javascript
pip install pandas
```

## 판다스 데이터 객체

### DataFrame

DataFrame 객체는 행과 열로 이루어진 2차원 데이터를 다루기 위한 객체다.
<br>
열은 각각의 변수를 나타내고, 행은 각각의 관측치를 나타낸다.
<br><br>
DataFrame 객체는 여러 가지 방법으로 생성할 수 있다.

> 생성 예시

```javascript
# 리스트를 사용하여 DataFrame 객체 생성
import pandas as pd

data = [['A', 1], ['B', 2], ['C', 3]]
df = pd.DataFrame(data, columns=['c1', 'c2'])
print(df)
# 출력 결과
#     c1    c2
# 0    A     1
# 1    B     2
# 2    C     3

# 딕셔너리를 사용하여 DataFrame 객체 생성
data = {'c1': ['A', 'B', 'C'], 'c2': [1, 2, 3]}
df = pd.DataFrame(data)
print(df)
# 출력 결과
#     c1    c2
# 0    A     1
# 1    B     2
# 2    C     3

# CSV 파일을 사용하여 DataFrame 객체 생성
df = pd.read_csv('data.csv')
print(df)
```

<br>

> 행/열 선택

DataFrame 객체에서는 열이나 행을 선택하여 데이터를 조회할 수 있다.

```javascript
# 열 선택하기
df['c1']
df[['c1', 'c2']]

# 행 선택하기
df.loc[0]
df.loc[[0, 1, 2]]
```

<br>

> 데이터 조작

DataFrame 객체에서는 데이터를 추가, 삭제, 수정하는 등 다양한 조작을 수행할 수 있다.

```javascript
# 열 추가하기
df['c3'] = [4, 5, 6]

# 열 삭제하기
df.drop('c3', axis=1, inplace=True)

# 행 추가하기
df.loc[3] = ['D', 4, 5]

# 행 삭제하기
df.drop(3, inplace=True)

# 열 이름 변경하기
df.rename(columns={'c1': 'new_c1'}, inplace=True)
```

### Series

Series 객체는 인덱스와 값으로 이루어진 1차원 데이터를 다루기 위한 객체다.
<br><br>
Series 객체는 DataFrame 객체에서 열을 선택하여 추출할 수 있다.

> 생성 예시

```javascript
import pandas as pd

data = [95, 90, 85, 90]
grade = ['1학년', '2학년', '3학년', '4학년']
score = pd.Series(data, index = grade)
print(score)
# 출력    결과
# 1학년    95
# 2학년    90
# 3학년    85
# 4힉년    90
# dtype: int64
```