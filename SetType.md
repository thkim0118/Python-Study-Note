## 집합 자료형
### 집합 자료형이란
* 집합은 기본적으로 리스트 혹은 문자열을 이용해서 만들 수 있는데, 아래와 같은 특징이 있다.
  * 중복을 허용하지 않는다.
  * 순서가 없다.
* 키가 존재하지 않고, 값 데이터만 담는다.
* 데이터가 존재하는지 검사하는 연산의 시간 복잡도는 O(1)
```python
# 집합 자료형 초기화 1
data = set([1, 1, 2, 3, 4, 5, 5])
print(data) -> {1, 2, 3, 4, 5}

# 집합 자료형 초기화 2
data = {1, 1, 2, 3, 4, 5, 5}
print(data) -> {1, 2, 3, 4, 5}
```
</br>

### 집합 자료형의 연산
* 합집합 : |
* 교집합 : &
* 차집합 : -
```python
a = set([1, 2, 3, 4, 5])
b = set([3, 4, 5, 6, 7])

# 합집합
print(a | b) -> {1, 2, 3, 4, 5, 6, 7}

# 교집합
print(a & b) -> {3, 4, 5}

# 차집합
print(a - b) -> {1, 2}
```
</br>

### 집합 자료형 관련 함수
* add() : 값 추가 - O(1)
* update() : 여러 개의 값을 한꺼번에 추가
* remove() : 특정 값 제거 - O(1)
```python
data = set([1, 2, 3])
print(data) -> {1, 2, 3}

# 값 추가
data.add(4)
print(data) -> {1, 2, 3, 4}

# 여러 개 값 추가
data.update([5, 6])
print(data) -> {1, 2, 3, 4, 5, 6}

# 값 제거
data.remove(3)
print(data) -> {1,2, 4, 5, 6}
```
