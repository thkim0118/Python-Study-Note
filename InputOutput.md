## 입출력
### 입력
#### input()
> 데이터의 개수가 주어지고 여러 개의 데이터를 공백을 기준으로 입력받을 때.
* list(map(int, input().split())) 
  * input() : 한 줄의 문자열을 입력
  * split() : 공백으로 나눈 리스트로 바꿈
  * map() : 해당 리스트의 모든 원소에 int() 함수를 적용
  * list() : 결과를 list로 반환
```python
n = int(input())

data = list(map(int, input().split()))

data.sort(reverse = True)
print(data)
```
  
> 공백을 기준으로 입력을 받을 때
```python
n, m, k = map(int, input().split())

print(n, m, k)
```
#### sys
> input() 보다 동작 속도가 빠른 sys 라이브러리.\
> 엔터가 줄 바꿈 기호로 입력되는데\
> __rstript()__ 함수를 실행하여야 해당 기호가 제거된다. 
```python
import sys

data = sys.stdin.readline().rstrip()

print(data)
```

### 출력
#### print()
> print 후 자동으로 줄 바꿈이 이루어진다.\
> , 를 이용해 매개변수를 구분하고 띄어쓰기로 구분되어 출력된다.
```python
a = 1
b = 2

print(a, b)
print(a)
print(b)

-> 1 2
   1
   2
```
> + 로 출력할 경우 변수를 문자열로 바꾸어 출력해야한다.
> , 로 구분이 가능하다.
> python3.6 이상 버전부터 f-string 문법을 사용할 수 있다.
```python
result = 500

print("Result is " + str(result) + ".")
print("Result is", str(result) + ".")
print(f"Result is {result}.")

-> Result is 500.
```
