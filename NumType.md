## 수 자료형
### 실수형 표현 방식

```python
# 유효숫자e^지수 = 유효숫자 x 10^지수
a = 2e9
print(a) -> 2000000000.0

a = 65.11e1
print(a) -> 651.1

a = 6642e-3
print(a) -> 6.642
```

> 컴퓨터는 실수를 정확히 표현하지 못한다.\
> 실수형은 4바이트 혹은 8바이트의 고정된 메모리를 할당하여 실수 정보를 표현하는 정확도에 한계를 가진다.\
> Ex. 2진수로 0.9를 정확하게 표현할 수 있는 방법이 없다.
```python
a = 0.3 + 0.9
print(a) -> 0.8999999999999999

if a == 0.9:
  print(True)
else:
  print(False)

-> False
```

> 실수형 데이터를 비교할 때 소수점 특정 자릿수를 반올림하는 round() 함수를 이용한다.\
> round(123.456, 2) -> 123.46\
> round(123.456) -> 123
```python
print(round(123.456, 2)) -> 123.46

print(round(123.456)) -> 123
```

### 연산
> python 에서는 (/)는 실수형으로 처리한다.
```python
a = 7
b = 3

print(a / b) -> 2.3333333333333335

print(a % b) -> 1

print(a // b) -> 3

# 거듭제곱
print(a ** b) -> 343
```

### 리스트
> python 의 리스트 자료형은 내부적으로 연결 리스트 자료구조이다.
```python
# 선언
a = [1, 2, 3, 4, 5, 6, 7, 8, 9]
print(a) -> [1, 2, 3, 4, 5, 6, 7, 8, 9]

# 접근
print(a[4]) -> 5

# 빈 리스트 선언 1
a = list()
print(a) -> []

# 빈 리스트 선언 2
a = []
print(a) -> []

# 크기가 N이고, 모든 값이 0인 1차원 리스트 초기화
n = 10
a = [0] * n
print(a) -> [0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
```

### 리스트의 인덱싱과 슬라이싱
> 인덱싱 : 인덱스값을 입력하여 리스트이 특정한 원소에 접근하는 것\
> 파이썬의 인덱스 값은 양의 정수, 음의 정수 모두 사용 가능\
> 음의 정수를 넣으면 원소를 거꾸로 탐색한다.
```python
a = [1, 2, 3, 4, 5, 6, 7, 8, 9]
print(a[-1]) -> 9

print(a[-3]) -> 7

a[3] = 7
print(a) -> a = [1, 2, 3, 7, 5, 6, 7, 8, 9]
```
> 리스트에서 연속적인 위치를 갖는 원소들을 가져와야 할 때는 슬라이싱을 이용한다.\
> 대괄호 안에 콜론(:)을 넣어서 시작 인덱스와 (끝 인덱스 -1)을 설정한다.\
```python
a = [1, 2, 3, 4, 5, 6, 7, 8, 9]

# 두 번째 원소부터 다섯 번째 원소까지
print(a[1 : 5]) -> [2, 3, 4, 5]
```

### 리스트 컴프리헨션
```python
# 0부터 19까지의 수 중에서 홀수만 포함하는 리스트
array = [i for i in range(20) if i % 2 == 1]

print(array) -> [1, 3, 5, 7, 9, 11, 13, 15, 17, 19]

# 1부터 9까지의 수의 제곱 값을 포함하는 리스트
array = [i * i for i in range(1, 10)]

print(array) -> [1, 4, 9, 16, 25, 36, 49, 64, 81]

# N X M 크기의 2차원 리스트 초기화
n = 3
m = 4
array = [[0] * m for _ in range(n)]

# 특정 크기의 2차원 리스트를 초기화할 때는 반드시 리스트 컴프리헨션을 이용해야한다.
# N X M 크기의 2차원 리스트 초기화(잘못된 방법)
n = 3
m = 4
array = [[0] * m] * n
print(array) -> [[0, 0, 0, 0], [0, 0, 0, 0], [0, 0, 0, 0]]

array[1][1] = 5
print(array) -> [[0, 5, 0, 0], [0, 5, 0, 0], [0, 5, 0, 0]]
# 내부적으로 포함된 3개의 리스트가 모두 동일한 객체에 대한 3개의 레퍼런스로 인식된다.
```

### 리스트 관련 기타 메서드
<table class="tg">
<thead>
  <tr>
    <th >메서드명</th>
    <th >사용법</th>
    <th >설명</th>
    <th >시간 복잡도</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td >append()</td>
    <td >변수명.append()</td>
    <td >리스트에 원소를 하나 삽입할 때 사용한다.</td>
    <td >O(1)</td>
  </tr>
    <td rowspan=2>sort()</td>
    <td >변수명.sort()</td>
    <td >기본 정렬 기능으로 오름차순으로 정렬한다.</td>
    <td rowspan=2>O(NlogN)</td>
  </tr>
  <tr>
    <td >변수명.sort(reverse = True)</td>
    <td >내림차순으로 정렬한다.</td>
  </tr>
  <tr>
    <td >reverse()</td>
    <td >변수명.reverse()</td>
    <td >리스트의 원소의 순서를 모두 뒤집어 놓는다.</td>
    <td >O(N)</td>
  </tr>
  <tr>
    <td >insert()</td>
    <td >변수명.insert(a, b)</br>a = 삽입할 위치 인덱스</br>b = 삽입할 값</td>
    <td >특정한 인덱스 위치에 원소를 삽입할 때 사용한다.</td>
    <td >O(N)</td>
  </tr>
  <tr>
    <td >count()</td>
    <td >변수명.count(특정 값)</td>
    <td >리스트에서 특정한 값을 가지는 데이터의 개수를 셀 때 사용한다.</td>
    <td >O(N)</td>
  </tr>
  <tr>
    <td >remove()</td>
    <td >변수명.remove(특정 값)</td>
    <td >특정한 값을 갖는 원소를 제거하는데, 값을 가진 원소가 여러 개면 하나만 제거한다.</td>
    <td >O(N)</td>
  </tr>
</tbody>
</table>

> insert(), remove() 함수는 시간 복잡도가 O(N) 이므로 유의해서 사용해야한다.
```python
a = [1, 4, 3]
print("기본 리스트 : ", a) -> 기본 리스트 : [1, 4, 3]

# 리스트에 원소 삽입
a.append(2)
print("삽입 : ", a) -> 삽입 : [1, 4, 3, 2]

# 오름차순 정렬
a.sort()
print("오름차순 정렬 : ", a) -> 오름차순 정렬 : [1, 2, 3, 4]

# 내림차순 정렬
a.sort(reverse = True)
print("내림차순 정렬 : ", a) -> 내림차순 정렬 : [4, 3, 2, 1]

# 리스트 원소 뒤집기
a.reverse()
print("원소 뒤집기 : ", a) -> 원소 뒤집기 : [1, 2, 3, 4]

# 특정 인덱스에 데이터 추가
a.insert(2, 3)
print("인덱스 2에 3 추가 : ", a) -> 인덱스 2에 3 추가 : [1, 2, 3, 3, 4]

# 특정 값인 데이터 개수 세기
print("값이 3인 데이터 개수 : ", a.count(3)) -> 값이 3인 데이터 개수 : 2

# 특정 값 데이터 삭제
a.remove(1)
print("값이 1인 데이터 삭제 : ", a) -> 값이 1인 데이터 삭제 : [2, 3, 3, 4]
```

> 특정한 값의 원소를 모두 제거하는 방법
```python
a = [1, 2, 3, 4, 5, 5, 5]
remove_set = {3, 5}

# remove_set 에 포함되지 않은 값만을 저장
result = [i for i in a if i not in remove_set]
print(result) -> [1, 2, 4]
```
