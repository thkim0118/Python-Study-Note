## 사전 자료형
### 사전자료형 이란.
* 키(Key)와 값(Value)의 쌍을 데이터로 가지는 자료형이다.
* 리스트나 튜플은 순차적으로 저장하지만, 
사전 자료형은 키-값 쌍을 데이터로 가진다는 점에서 원하는 
변경 불가능한 데이터를 키로 사용할 수 있다<sup>[[1]](#note_1)</sup>.
* 파이썬의 사전 자료형은 내부적으로 '해시 테이블'을 사용하므로 기본적으로 데이터의 검색 및 수정에 있어서 O(1)의 시간에 처리할 수 있다.
```python
data = dict()
data['사과'] = 'Apple'
data['바나나'] = 'Banana'
data['코코넛] = 'Coconut'

print(data) -> {'사과': 'Apple', '바나나': 'Banana', '코코넛': 'Coconut'}
```
</br>

* 사전 자료형에 특정한 원소가 있는지 검사할 때는 '원소 in 사전' 형태를 사용할 수 있다.
* 이는 리스트나 튜플에 대해서도 사용할 수 있는 문법이다<sup>[[2]](#note_1)</sup>.
```python
data = dict()
data['사과'] = 'Apple'
data['바나나'] = 'Banana'
data['코코넛] = 'Coconut'

if '사과' in data:
  print("'사과'를 키로 가지는 데이터가 존재합니다.") -> '사과'를 키로 가지는 데이터가 존재합니다.
```
</br>

### 사전 자료형 관련 함수
* 키와 값을 별도로 뽑아내기 위한 함수가 있다.
* 키 데이터만 뽑아서 리스트로 이용할 때는 keys().
* 값 데이터만 뽑아서 리스트로 이요할 때는 values().
```python
data = dict()
data['사과'] = 'Apple'
data['바나나'] = 'Banana'
data['코코넛] = 'Coconut'

# 키 데이터만 담은 리스트
key_list = data.keys()

# 값 데이터만 담은 리스트
value_list = data.values()
print(key_list) -> dict_keys(['사과', '바나나', '코코넛'])
print(value_list) -> dict_values(['Apple', 'Banana', 'Coconut'])
# 각 키에 따른 값을 하나씩 출력
for key in key_list:
  print(data[key]) 
  -> Apple
     Banana
     Coconut
```
---
### 주석
* <a name="note_1">[1] : </a>변경 불가능한 자료형이란 수 자료형, 문자열 자료형, 
튜플 자료형과 같이 한 번 초기화되면 변경이 불가능한 자료형을 의미한다. 
흔히 사용되지는 않지만, 튜플 자료형이 사전 자료형의 키로 사용되기도 한다.</br>
* <a name="note_1">[2] : </a>
파이썬에서 리스트, 문자열, 튜플 등 순차적인 정보를 담는 자료형을 iterable 자료형이라고 한다. 
in 문법은 이러한 자료형에 모두 사용이 가능하다.</br>
