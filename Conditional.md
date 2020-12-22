## 조건문
### if 문
> if ~ elif ~ else 로 작성한다.
```python
score = 85

if score >= 90:
    print('Grade A')
elif (score >= 80):
    print('Grade B')
else:
    print('Grade C')
```
### 비교 연산자
```python
# java or kotlin 과 동일
==
!=
>
<
>=
<= 
```

### 논리 연산자
```python
X and Y
X or Y
not X
```

### 파이썬 연산자
> 여러 개의 데이터를 담는 자료형(리스트, 튜플, 문자열, 사전)
> 안에 어떠한 값이 존재하는지 확인하는 연산자이다.
```python
X in (리스트, 튜플, 문자열, 사전)
X not in (리스트, 튜플, 문자열, 사전)
```
#### pass
```python
if true:
    pass
else:
    print('no pass')

print('Done')

-> Done
```

#### 표현식
```python
if true: pass
else: print('no pass')

print('Done')

-> Done
```
```python
result = "Grade A" if score >= 90 else  "Grade B"
```

```python
array = [1, 2, 2, 2, 3, 4, 5, 5]
remove_set = [2, 5]

result = [i for i in array if i not in remove_set]

print(result)

-> [1, 3, 4]
```
