## 함수
### 다른 언어와 다른 파이썬의 특징
> 매개변수의 호출 위치가 달라도 상관없다.
```python
def add(a, b):
  print('Result : ', a + b)

add(b = 4, a = 20)

-> Result : 24
```
> global 키워드로 함수 바깥의 변수를 참조 가능
```python
a = 0

def func():
  global a
  a += 1

for i in range(10):
  func()

print(a)

-> 10
```
> 람다 표현식
```python
def add(a, b):
  print('Result : ', a + b)

print((lambda a, b: a + b)(3, 7))
```
