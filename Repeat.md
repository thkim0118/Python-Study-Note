## 반복문
### while
```python
i = 1
result = 0

while i <= 9:
    if i % 2 == 1:
        result += i
    i += 1

print(result)

-> 25
```
### for문
```python
result = 0

for i in range(1, 10):
  result += i

print(result)

-> 45
```
```python
score = [90, 85, 77, 65, 97]
cheating_list = {2, 4}

for i in range(5):
  if i + 1 in cheating_list:
    continue
  if score[i] >= 80:
    print(i + 1, "번 학생은 합격입니다.")
    
-> 1 번 학생은 합격입니다.
   5 번 학생은 합격입니다.
```
```python
for i in range(2, 10):
  for j in range(1, 10):
    print(i, "X", j, "=", i * j)
  print()
  
-> 9x9 단 반복문...
```
