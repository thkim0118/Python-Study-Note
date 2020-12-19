## 문자열 자료형
### 문자열 초기화
```python
data = 'Hello World'
print(data) -> Hello World

data = "Don't you know \"Python\"?"
print(data) -> Don't you know "Python"?
```
### 문자열 연산
```python
a = "Hello"
b = "World"

print(a + " " + b) -> "Hello World"

a = "String"
print(a * 3) -> StringStringString

# 파이썬의 문자열은 내부적으로 리스트와 같이 처리된다.
a = "ABCDEF"

print(a[2 : 4]) -> CD
```
