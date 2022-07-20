[TOC]

# 함수

내부구조를 몰라도 편리하게 사용할 수 있게 지정해 놓은 것

ex) len() / sum() / average

---

---

## 함수기초

---

### 함수

- 특정한 기능을 하는 코드의 조각, 필요시에 호출하여 사용

- 함수 기본구조
  
  1. 선언(생성) / 호출(사용)
     
     - **def** 키워드 활용
     
     - ```python
       #생성
       def function_name(parameter):
           #정의 
           return returning_value
       #생성
       def add(x, y):
           return x + y
       ```
  
  2. 입력(input)
     
     - Parameter : 함수 선언 def function(Parameter)
     
     - Argument : 함수 호출, 넣어주는 값 function(Argument)
       
       Argument가 호출 되었을때 Parameter 전달/호출
       
       - Positional Arguments(위치)
         
         ```python
         def add(x, y) :
             return x + y
         add(2, 3) #선언 시 지정한 위치대로 들어가는 것
         ```
       
       - Keyword Arguments()
         
         ```python
         def add(x, y) :
             return x + y
         add(x, y=5) #y = 5 라고 지정, 처음 인자가 x = 2 다음 인자가 5로 들어오면 error
         #Keyword Arguments는 순서에 혼란을 준다
         ```
       
       - Default Arguments Values
         
         ```python
         def add(x, y=0): #y에 기본값 설정
             return x + y
         add(2) #2 + 0 출
         ```
       
       - 
  
  3. 문서화(Docstring)
  
  4. 범위(Scope)
  
  5. 결과값(Output)

---

##### 가변인자(*)

시퀀스를 풀어 헤치는 연산자

- 튜플이나 리스트를 언패킹할 때 사용

- *를 활용하여 가변 인자를 만들수 있음
  
  ```python
  def som_all(*numbers):
      result = 0
      for number in numbers:
          result += number
      return result
  
  print(sum_all(1, 2, 3)) # 6
  print(sum_all(1, 2, 3, 4, 5, 6)) # 21
  ```

##### 가변 키워드 인자(**kwargs)

- 키워드 인자를 몇개나 받을지 모르는 함수 정의

- 딕셔너리로 묶여 처리됨.

---

##### 패킹 / 언패킹

###### 패킹

- 여러개의 데이터를 묶어서 변수에 할당
  
  numbers = (1, 2, 3, 4, 5) #패
  
  ```python
  numbers = (1, 2, 3, 4, 5) #패킹
  #1 a, b, c, d, e, f = numbers / Error 언패킹시 갯수를 통일시켜줘야  
  #2 a, b, *rest = numbers
  #3 a, *rest, e = numbers
  ```

###### 언패킹

- 시퀀스 속의 요소들을 여러개의 변수에 나누어 할당

---

##### print와 return의 차이점

- print를 사용하면 함수가 호출 될 때마다 값 출력
  
  - 바로 확인 할 수 있게 테스트 용으로 많이 사용

- 데이터 처리할 때는 return값을 써주자!!

##### return 두 개 이상의 값 반환(여러개의 값을 하나의 값으로 만들어서)

- 반환값을 튜플로 묶어서 사용

```python
return x - y, x * y
```

---

## 함수 응용

#### 내장함수

- 파이썬에 기본적으로 포함된 함수

- 자동적으로 설치되어 있음
  
  ##### map(function, iterable)
  
  ##### filter(function, iterable)
  
  ##### zip(*iterable)
  
  - 여러개의 리스트를 세로로 묶는다.
  
  ##### lambda
  
  ##### 재귀함수
  
  - 자기 자신을 호출하는 함수
  
  - ex) !(팩토리얼) : f(4) = 4 * f(3) / f(3) = 3 * f(2) / f(2) = 2 * f(1) / f(1) = 1
  
  - base case에 도달할 때까지 함수 호출
    
    ```python
    def factorial(n):
        if n == 0 or n == 1 :
            return 1
        else:
            return n * factorial(n-1)
    print(factorial(4))
    ```

#### 외장함수

- **import**를 통해 외부 라이브러리에서 가져옴

- 파이썬 내부 아닌 다른 개발자가 만들어서 제공

#### 사용자 정의 함수

- 사용자가 직접 만드는 함수

- def

## 함수의 결과값(Output)

## 합수의 입력(Input)

---

## Python의 함수의 범위(Scope)

### global scope

- global variable : global scope에 정의된 변수

### local scope

- local variable : local scope에 정의된 변수

```python
def func():
    a = 20 # a = 20은 func 함수 안에서만 존재
    print('local', a) # local 20 
func()
print('global', a) # a = not define 나오지 않는다. 함수 종료 후 수명 종료.
```

##### [LEGB Rule] 탐색 순서

- Local scope -> Enclosed scope -> Global scope -> Built-in-scope 
  
  - 하단 함수 에서 상단 함수에 접근은 가능하나 수정은 불가능함

```python
a = 0
b = 1
def enclose():
    a = 10
    c = 3
    def local(c):
        print(a, b, c) # 10 1 300
    local(300)
    print(a, b, c) # 10 1 3
enclosed()
print(a, b) # 0 1
```

### global 문 생성

global을 써주면 함수 바깥에서도 사용이 가능하다. 함수 바깥의 변수도 사용 가능.

```python
a = 10
def func1():
    global a #global로 함수 바깥의 a에 영향을 준다.
    a = 3

print(a) #10
func1()
print(a) #3
```

### nonlocal

```python
x = 0
def func1():
    x = 1
    def func2():
        nonlocal x
        x = 2
    funu2()
    print(y)
```
