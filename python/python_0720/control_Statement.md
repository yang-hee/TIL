[TOC]

# 제어문(Control Statement)

---

## Ⅰ. 조건문

참/거짓을 판단할 수 있는 조건식과 함께 사용

### 조건문의 기본 형식(if ~ else)

```python
if 조건 == True :
    #조건이 참일 때 실행합니다
else :
    #조건이 거짓일 때 실행합니다.    
```

#### 조건문을 이용한 홀수/짝수 판별하기

```python
#홀수/짝수 여부
num = int(input())
if num % 2 == 1 :
    print('홀수입니다')
else :
    print('짝수입니다')
```

### 복수조건문(if ~ elif ~ else)

#### 복수 조건문 이용하여 미세먼지 상황 출력

```python
dust = 80 #미세먼지 농도
if dust > 150:
    print('매우 나쁨')
elif dust > 80:
    print('나쁨')
elif dust > 30:
    print('보통')
else:
    print('좋음')
print('미세먼지 확인 완)
```

- if부터 else까지 순차적으로 비교하면서 해당하지 않는부분 제거함.
  
  - if가 false이면 150보다 크지 않다고 생각함.

### 중첩조건문

- 조건문은 다른 조건문에 중첩 가능하다.

- 들여쓰기

#### 중첩조건문 사용하여 미세먼지 출력

```python
dust = 80 #미세먼지 농도
if dust > 150:
    print('매우 나쁨')
    if dust > 300:
        print('실외 활동을 자제하세요')
elif dust > 80:
    print('나쁨')
elif dust > 30:
    print('보통')
elif dust > 0:
    print('좋음')
else :
    print('값이 잘못 되었습니다.')                
```

### 조건 표현식

- 조건표현식(삼항연산자)
  
  ```python
  true인 경우 값 if 조건 else false인 경우 값
  ```
  
  - 조건이 True인 경우 왼쪽 값, False인 경우 오른쪽 값이 나온다

- ```python
  #num이 정수일 때 절댓값을 저장하기 위한 코드
  value = num if num >= 0 else -num 
  ```

--- 

## Ⅱ. 반복문

특정 조건을 만족할 때 까지 같은 동작을 반복하고 싶을 때 사용

### 

### 1. while문

조건식이 참인 경우를 반복실행. <mark>종료조건</mark>까지 코드 반복!!

무한루프에 주의할 것. 종료조건 확인!

```python
while 조건:
    #조건이 참인 동안코드 반복
```

```python
a = 0
while a < 5:
    print(a)
    a += 1 #반복 시 a값 증가. 반복문을 종료하기 위한 조건. a = a + 1 과 같다. 
print('끝')
```

- 복합연산자 : 연산과 할당을 합쳐놓은 것 ex) +=, -= ...

### 

### 2. for문

별도의 종료 조건이 필요 없음. 

```python
for 변수명 in iterable:
        # iterable을 순회하는 동안 코드실행
```

- iterable (순회 할 수 있는 자료형)
  
  - string, list, dict, tuple, range, set 등.
    
    - dict 순회시에는 기본적으로 key값을 순회한다. 
  
  - 순회형 함수(range, enumerate)
  
  #### for문을 사용한 코드 예시

```python
fruits = ['apple', 'mango', 'banana']
for fruit in fruits:
    print(fruit)
print('끝')
'''
apple
mango
banana
끝
'''
```

```python
#딕셔너리 grades의 key와 value값 출력하는 for문
grades = {'john' : 80, 'eric' : 90}
for student.grade in grades.items() :
    print(student, grades[student])
'''
john 80
eric 90
'''
```

```python
#enumerate 함수
members = ['민수', '영희', '철수']
enumerate(members)
print(list(enumerate(members))) #[(0, '민수'), (1, '영희'), (2, '철]
```

```python
# 1~3의 세제곱 리스트 만들
cubic_list = [] #리스 생성
for number in range(1, 4):
    cubic_list.append(number ** 3)
print(cubic_list) # [1, 8, 27]

#List Comprehension
```

```python
# 1~3의 세제곱 딕셔너리 만들기
cubic_dict = {} #딕셔너리 생성
for number in range(1, 4):
    cubic_dict[number] = number ** 3
print(cubic_dict) # {1: 1,2: 8,3: 27]


#Dict Comprehension
```

### 반복문제어

#### break

- 반복문 종료

#### continue

- continue 이후의 코드 스킵. 다음 반복 수행.

#### for-else

- 반복을 온전히 끝까지 한다음에 else문 실행.

#### pass

- 아무것도 하지 않음.

- 문법적으로 필요하지만, 할 것이 없을때 사용.

---
