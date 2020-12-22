## 주요 라이브러리
### 내장 함수
> 별도의 import 명령어 없이 바로 사용할 수 있다.

* __sum__
  * 리스트와 같은 iterable 객체가 입력.
```python
sum([1, 2, 3, 4, 5]) -> 15
```

* __min__
  * 파라미터 2개 이상 들어왔을 때 가장 작은 값을 반환
```python
min(9, 7, 5, 1, 10) -> 1
```

* __max__
  * 파라미터 2개 이상 들어왔을 때 가장 큰 값을 반환
```python
max(9, 7, 5, 1, 10) -> 10
```
* __eval__
  * 수학 수식이 문자열 형식으로 들어오면 해당 수식을 계산한 결과를 반환
```python
eval("3 - 5 * (1 + 2)") -> -12
```

* __sorted__
  * iterable 객체가 들어왔을 때 정렬된 결과를 반환
  * key : 정렬 기준을 명시
  * reverse : 결과를 뒤집을지 설정
```python
sorted([9, 7, 5, 1, 10]) -> [1, 5, 7, 9, 10]

sorted([9, 7, 5, 1, 10], reverse = True) -> [10, 9, 7, 5, 1]

# 2번째 원소를 기준으로 내림차순으로 정렬.
print(sorted([('Eng', 100), ('Kor', 50), ('Ger', 28), ('Fra', 40)], key = lambda x: x[1], reverse = True))
-> [('Eng', 100), ('Kor', 50), ('Fra', 40), ('Ger', 28)]
```
> 리스트와 같은 iterable 객체는 sort() 함수를 기본으로 내장하고있다.
```python
data = [9, 7, 5, 1, 10]
data.sort()
print(data) -> [1, 5, 7, 9, 10]
```

### itertools
> 반복되는 데이터 처리 기능을 포함하는 라이브러리

* **permutations**
  * 리스트와 같은 iterable 객체에서 r 개의 데이터를 뽑아 일렬로 나열하는 모든 경우(순열)을 계산해준다.
  * 클래스이므로 객체 초기화 이후에는 리스트 자료형으로 변환하여 사용한다.
```python
# 리스트['a', 'b', 'c'] 에서 3개(r=3)를 뽑아 나열하는 모든 경우를 출력하는 예시
from itertools import permutations

data = ['a', 'b', 'c']

result = list(permutations(data, 3))

print(result)
->
[('a', 'b', 'c'), ('a', 'c', 'b'), ('b', 'a', 'c'), ('b', 'c', 'a'), ('c', 'a', 'b'), ('c', 'b', 'a')]
```

* **combinations**
  * 리스트와 같은 iterable 객체에서 r 개의 데이터를 뽑아 순서를 고려하지 않고 나열하는 모든 경우(조합)를 계산한다.
  * 클래스이므로 객체 초기화 이후에는 리스트 자료형으로 변환하여 사용한다.
```python
# 리스트['a', 'b', 'c'] 에서 2개(r=2)를 뽑아 순서에 상관없이 나열하는 모든 경우를 출력하는 예시
from itertools import combinations

data = ['a', 'b', 'c']

result = list(combinations(data, 2))

print(result)
->[('a', 'b'), ('a', 'c'), ('b', 'c')]
```

* **product**
  * iterable 객체에서 r 개의 데이터를 뽑아 일렬로 나열하는 모든 경우(순열)를 계산한다.
  * 원소를 중복하여 뽑는다.
  * 객체를 초기화할 때, 뽑고자 하는 데이터의 수를 repeat 속성값으로 넣어준다.
  * 클래스이므로 객체 초기화 이후에는 리스트 자료형으로 변환하여 사용한다.
```python
# 리스트['a', 'b', 'c'] 에서 중복을 포함하여 2개(r=2)를 뽑아 나열하는 모든 경우를 출력하는 예시
from itertools import combinations

data = ['a', 'b', 'c']

result = list(combinations(data, 2))

print(result)
-> [('a', 'a'), ('a', 'b'), ('a', 'c'), ('b', 'a'), ('b', 'b'), ('b', 'c'), ('c', 'a'), ('c', 'b'), ('c', 'c')]
```

* **combinations_with_replacement**
  * 리스트와 같은 iterable 객체에서 r 개의 데이터를 뽑아 순서를 고려하지 않고 나열하는 모든 경우(조합)의 수를 계산한다.
  * 원소를 중복해서 뽑는다.
  * 클래스이므로 객체 초기화 이후에는 리스트 자료형으로 변환하여 사용해야 한다.
```python
# 리스트['a', 'b', 'c'] 에서 중복을 포함하여 2개(r=2)를 뽑아 순서에 상관없이 나열하는 모든 경우를 출력하는 예시
from itertools import combinations_with_replacement

data = ['a', 'b', 'c']

result = list(combinations_with_replacement(data, 2))

print(result)


-> [('a', 'a'), ('a', 'b'), ('a', 'c'), ('b', 'b'), ('b', 'c'), ('c', 'c')]
```

### heapq
> Heap 기능
> 우선순위 큐 기능 구현에 주로 사용됨\
> 파이썬의 힙은 최소 힙(Min Heap)으로 구성되어 있으므로 단순히 원소를 힙에 전부 넣었다가 빼는 것만으로도 시간 복잡도 O(NlogN)에 오름차순 정렬이 완료된다.\
> 보통 최소 힙 자료구조의 최상단 원소는 항상 '가장 작은' 원소이기 때문이다.\
```python
import heapq

def heapsort(iterable):
  h = []
  result = []
  # 모든 원소를 차례대로 힙에 삽입
  for value in iterable:
    heapq.heappush(h, value)
  # 힙에 삽입된 모든 원소를 차례대로 꺼내어 담기
  for i in range(len(h)):
    result.append(heapq.heappop(h))
  return result

result = heapsort([1, 3, 5, 6 ,7, 2, 4, 5, 6, 7, 0])

print(result)
-> [0, 1, 2, 3, 4, 5, 5, 6, 6, 7, 7]
```
> 파이썬에서는 최대 힙(Max Heap)을 제공하지 않는다.\
> 따라서 최대 힙을 구현해야 할 때는 원소의 부호를 임시로 변경하는 방식을 사용한다.\
> 힙에 원소를 삽입하기 전에 잠시 부호를 반대로 바꾸었다가, 힙에서 원소를 꺼낸 뒤에 다시 원소의 부호를 바꾸면 된다.\
```python
# 최대 힙을 구하여 내림차순 힙 정렬 구현
import heapq

def heapsort(iterable):
  h = []
  result = []
  # 모든 원소를 차례대로 힙에 삽입
  for value in iterable:
    heapq.heappush(h, -value)
  # 힙에 삽입된 모든 원소를 차례대로 꺼내어 담기
  for i in range(len(h)):
    result.append(-heapq.heappop(h))
  return result

result = heapsort([1, 3, 5, 6 ,7, 2, 4, 5, 6, 7, 0])

print(result)
-> [7, 7, 6, 6, 5, 5, 4, 3, 2, 1, 0]
```

### bisect
> 이진 탐색을 위한 라이브러리\
> '정렬된 배열'에서 특정한 원소를 찾아야 할 때 매우 효과적으로 사용된다.\
> bisect_left(), bisect_right() 함수 들이 매우 중요하게 사용되며, 시간 복잡도 O(logN)에 동작한다.
* **bisect_left(a, x)**
  * 정렬된 순서를 유지하면서 리스트 a에 데이터 x를 삽입할 가장 왼쪽 인덱스를 찾는 메서드
* **bisect_right(a, x)**
  * 정렬된 순서를 유지하도록 리스트 a에 데이터 x를 삽입할 가장 오른쪽 인덱스를 찾는 메서드
```python
from bisect import bisect_left, bisect_right

a = [1, 2, 4, 4, 8]
x = 4

print(bisect_left(a, x)) -> 2
print(bisect_right(a, x)) -> 4
```
> bisect_left() 와 bisect_right() 함수는\
> '정렬된 리스트'에서 '값이 특정 범위에 속하는 원소의 개수'를 구하고자 할 때\
> 효과적으로 사용될 수 있다.\
```python
from bisect import bisect_left, bisect_right

# 값이 [left_value, right_value]인 데이터의 개수를 반환하는 함수
def count_by_range(a, left_value, right_value):
  right_index = bisect_right(a, right_value)
  left_index = bisect_left(a,left_value)
  return right_index - left_index

a = [1, 2, 3, 3, 3, 3, 4, 4, 8, 9, 10, 11, 11]

print(count_by_range(a, 3, 9)) -> 8

print(count_by_range(a, -1, 3)) -> 6
```

### collections
* **deque**
  * deque 를 사용해 큐를 구현한다.
  * 인덱싱, 슬라이싱 등의 기능을 사용할 수 없다.
  * 그러나 연속적으로 나열된 데이터의 시작 부분이나 끝부분에 데이터를 삽입하거나 삭제할 때는 시간 복잡도가 O(1)이므로 효과적으로 사용된다.
  * 스택이나 큐의 기능을 모두 포함한다.
  * 첫번째 원소 제거 : popleft(), 마지막 원소 제거 : pop()
  * 첫번째 인덱스에 원소 삽입 : appendleft(x), 마지막 인덱스에 원소 삽입 : append(x)
```python
from collections import deque

data = deque([2, 3, 4])
data.appendleft(1)
data.append(5)

print(data) -> deque([1, 2, 3, 4, 5])

print(list(data)) -> [1, 2, 3, 4, 5]
```
* **Counter**
  * Counter 는 등장 횟수를 세는 기능을 제공한다.
  * 리스트와 같은 iterable 이 주어졌을 때, 해당 객체 내부의 원소가 몇 번씩 등장했는지를 알려준다.
  * 원소별 등장 횟수를 세는 기능이 필요할 때 구현한다.
```python
from collections import Counter

counter = Counter(['red', 'blue', 'red', 'green', 'blue', 'blue'])

print(counter['blue']) -> 3
print(counter['green']) -> 1
# 사전 자료형으로 변환
print(dict(counter)) -> {'red': 2, 'blue': 3, 'green': 1}
```

### math
* 팩토리얼, 제곱근, 최대공약수 등을 계산해주는 기능을 포함하고있다.
#### **factorial(x)**
```python
import math

# 5 팩토리얼 출력
print(math.factorial(5))
```

#### **sqrt(x)**
```python
import math

# 7 의 제곱근 출력
print(math.sqrt(7))
```

#### **gcd(x, y)**
```python
import math

# 21 과 14 의 최대공약수 출력
print(math.gcd(21, 14))
```

#### **pi, e**
```python
import math

# 파이(pi) 자연상수(e)
print(math.pi)
print(math.e)
```
