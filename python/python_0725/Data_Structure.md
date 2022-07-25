# 0725 데이터구조

데이터 구조 활용

데이터구조.메서드()

- 메서드 : 함수의 연장선

```python
List.append(10) #List에 10을 더한다
String.split() #문자열을 공백으로 쪼갠다
```

**공식문서의 표기법 : 선택적으로 써도 되고 안써도 되는 구문은 []로 표현**

id(변수명) # 메모리 주소 확인

# 시퀀스형 자료형

## 문자열(변경 불가능 : immutable)

- **str타입**

```python
a = 'hello'
a = 'name' 
#a를 변경한 것이 아니라 a에 hello의 메모리 주소를 할당하던 것을 name의 메모리 주소를 할당하는 것으로 바꿔준것
```

---

```python
'''조회 / 탐색 / 판별'''
s.find(x) #x의 첫번째 위치를 반환. 없으면 -1 반환 -> 진행
s.index(x) #x의 첫번째 위치를 반환. 없으면 *오류*발생 -> 종료
s.isalpha() #알파벳 판별 (한국어도 포함)
s.isupper() #대문자인가?
s.islower() #소문자인가?
s.istitle() #타이틀인가?
```

### 조회/탐색/판별

### 조회/탐색(find / index)

```python
'''find
- x가 처음 나오는 위치를 반환해준다.
- 문장에 x가 없을 경우 -1을 반환해준다
- 오류가 발생하지 않는다
'''
print('apple'.find('p')) # 1 처음 p 위치를 반환해준다
print('universe'.find('verse')) #3
print('banana'.finc('c')) # -1 없으면 -1을 반환

'''index
- x가 처음 나오는 위치를 반환해준다.
- 문장에 x가 없을 경우 *오류*가 발생한다
'''
print('apple'.index('p')) # 1
print('apple'.index('k')) # Error!

```

### 문자열검증(isalpha / isupper / islower / istitle)

```python
'''isalpha 알파벳인가?'''
print('*'.isalpha()) #False
print('가나다'.isalpha()) #True
print('ab'.isalpha()) #True

'''isupper 대문자인가?'''
print('Ub'.isupper()) #False
print('USB'.isupper()) #True

'''islower 소문자인가?'''
print('Hi'.islower()) #False
print('hi'.islower()) #True

'''istitle 각 단어의 시작이 대문자인가?'''
print('Hi, I\'M a Girl'.istitle()) #False a가 소문자라서
print('Hi, I\'M A Girl'.istitle()) #True
```

### 숫자판별( isdecimal < isdigit < isnumeric )

- 숫자 판별 메서드
    - isnumeric으로 갈수록 숫자로 판단하는 범위가 넓어짐
    - isdecimal
        - 숫자처럼 생긴것만!
    - isnumeric
        - 로마자까지도 가능

---

```python
'''변경 : 주소 값이 바뀜. 변경된 새로운 값을 넣어주는 것이므로!'''
s.replace(old, new[, count]) #old를 new로 바꿔준다
s.strip([chars])
s.split(sep=None, maxsplit=-1)
'separator'.join([iterable])
s.capitalize() # 문자열의 첫 번째 글자만 대문자로
s.title() # 띄어쓰기 기준으로 각 단어의 앞글자를 대문자로 나머지는 소문자로
s.upper() # 전부 대문자로 변환
s.lower() # 전부 소문자로 변환
s.swapcase() # 대문자를 소문자로, 소문자를 대문자로 변환
```

### 변경(replace / strip / split / join)

```python
'''replace'''
print('woowoowow'.replace('o', 'a')) # waawaawaw o를 전부 a로 변경
print('waawoowow'.replace('o', 'a', 2)) # waawaawaw o를 앞에서부터 2개만 a로 변경

'''strip : 지정한 문자열, 공백 제거'''
print('    와!     '.strip()) # '와!' 공백제거
print('    와!     '.lstrip()) # '와!     ' 왼쪽공백제거
print('    와!     '.rstrip()) # '    와!' 오른쪽공백제거
print('    와!!'.rstrip('!')) # '    와' 오른쪽 !제거

'''split'''
print('a, b, c'.split('_')) # ['a, b, c']
print('a, b, c'.split(',')) # ['a', ' b', ' c'] #,로 나눔 b와 c앞 공백포함

'''문자열.join'''
print('!!'.join('hello')) # 'h!!e!!l!!l!!o' '!!'에 문자열이 아닌게 들어오면 에러
```

### 변경(capitalize / title / upper / lower / swapcase)

```python
msg = 'Hello, I\'m a girl.'

# 첫글자만 대문자!
print(msg.capitalize()) # Hello, i'm a girl.
# 띄어쓰기 기준. 단어의 앞 대문자로!
print(msg.title()) # Hello, I'M A Girl.
# 전부 대문자로
print(msg.upper()) # HELLO, I'M A GIRL.
# 전부 소문자로
print(msg.lower()) # hello, i'm a girl.
# 대문자는 소문자로, 소문자는 대문자로
print(msg.swapcase()) #hELLO, i'M A GIRL.
```

## 리스트(변경 가능)

- 어떠한 자료형도 저장 가능(리스트 안에 리스트까지도 가능)

### 값 추가(append / insert / extend)

- x의 값을 리스트의 마지막에 추가해준다.

```python
list_cafe = ['starbucks', 'coffeebean', 'ediyacoffee']

'''append'''
list_cafe.append('banapresso')

'''insert'''
list_cafe.insert(2, 'hollys coffee') #2의 위치에 추가
# 숫자가 리스트보다 클경우 맨 뒤에
list_cafe.insert(10000, 'twosome place') 

'''extend'''
list_cafe.extend(['coffee']) # 'coffee
list_cafe.extend('cup') # 'c', 'u', 'p'
```

### 값 삭제(remove / pop / clear)

- x의 값을 리스트의 마지막에 추가해준다.

```python
list_number = [1, 3, 100, 4201]

'''remove 특정 값 제거. 그 값이 없으면 error'''
list_number.remove('hi') #Error hi가 없음
list_number.remove(1) [3, 100, 4201]

'''pop : 마지막 항목 제거하고 값을 따로 빼준다'''
list.pop = list_number.pop() #list_pop = 4201 / list_number = [3, 100]

'''clear : '''
print(list_number.clear) # []
```

### 탐색 / 정렬

- x의 값을 리스트의 마지막에 추가해준다.

```python
list_number = [1, 1, 1, 4, 2, 1, 1, 2, 3, 4]

'''count(x)'''
list_number.count(1) #5 / 1의 갯수 출력 

'''sort() / sorted(new_list_number)'''
list_number.sort() #원본 list_number가 정렬됨
#list_number의 정렬값을 new_list_number에 저장함
list_number.sorted(new_list_number) #

'''reverse() : 순서를 반대로. 정렬X'''
numbers = [5, 2, 1, 19]
reverse_numbers = numbers.reverse()
print(reverse_numbers) # [19, 1, 2, 5]
```

## 튜플(변경 불가능 : immutable)

- 값 변경 불가능

```python
a = (1, 2, 3, 5, 1)
a[0] = 5 #Error 값 바꿀 수 없음.
```

```python
day_name = ('월', '화', '수', '목', '금')
print(type(day_name))
print(day_name[-3]) # 수
print(day_name * 2) # ('월', '화', '수', '목', '금', '월', '화', '수', '목', '금')
day_name += False, True # ('월', '화', '수', '목', '금', False, True)
```

## 연산자

- 멤버십 연산자 **in / not in**

```python
print('apple' in 'a') #True a가 apple에 있는가?
print('a' in 'apple') #False
print('a' not in 'melon') #True a가 melon에 없는가?
```

- 시퀀스형 연산자
    - 반복연산자(*)

```python
day_name = ('월', '화', '수', '목', '금')
print(type(day_name))
print(day_name[-3]) # 수
print(day_name * 2) # ('월', '화', '수', '목', '금', '월', '화', '수', '목', '금')
day_name += False, True # ('월', '화', '수', '목', '금', False, True)
```

# 비시퀀스형 자료형

## 셋(Set) : 중복X

```python
s.copy() : 셋의 얕은 복사본을 반환
s.add(x) : 셋에 s가 없다면 추가
s.pop() : 랜덤항목 반환, 제거. 셋이 비어 있을경우 **Error**
s.remove(x) : x를 셋에서 삭제. 셋에 x가 없을경우 **Error**
s.discard(x) : x를 셋에서 삭제. Error발생 X
s.update(t) : t는 셋. s에 없는 항목을 t에서 추가.
s.clear() : 모든항목 제거
s.isdisjoint(t) : 셋s와 셋t가 하나도 겹치지 않으면 True
s.issubset(t) : 셋 s가 셋t에 포함되어 있으면 True
s.issuperset(t)
```

### 추가(add / update)

```python
a = {'사과', '바나나', '수박'}

'''add'''
a.add('딸기') # a에 딸기 추가. 순서는 랜덤.
print(a) # {'사과', '바나나', '수박', '딸기'}

'''update'''
a.update(['바나나', '참외', '메론']) #a와 비교하여 없는 거 추가
print(a) # {'사과', '바나나', '수박', '딸기', '참외', '메론'}
```

### 삭제(remove / discard / pop / clear)

```python
a = {'사과', '바나나', '수박', '복숭아'}

'''remove'''
a.remove('사과')
print(a) # {'바나나', '수박', '복숭아'}
a.remove('딸기')
print(a) # *Error* 발생. 딸기가 없기 때문에

'''discard'''
a.discard('딸기') #Error 없음. 해당 항목 없으면 그냥 넘어감.
print(a) # {'바나나', '수박', '복숭아'} 

'''pop'''
pop_a = a.pop() #제거된 것 pop_a에 할당.
print(a) # 바나나, 수박, 복숭아 중 하나 랜덤 제거. 

'''clear'''
a.clear() # 전체 항목 삭제
print(a) # set()
```

### 집합관련함수(isdisjoint / issubset / issuperset)

```python
a = {'사과', '바나나', '수박'}
b = {'포도', '망고'}
c = {'사과', '포도', '망고', '수박', '바나나'} 

'''isdisjoint : a와 b는 교집합, 서로소인가?'''
print(a.isdisjoint(b)) # True 겹치는게 하나도 없음.

'''a.issubset(b) : a는 b에 하위셋(포함되어 있는가)인가?'''
print(b.issubset(c)) # True b는 c에 포함되어 있음.

'''a.issuperset(b) : a는 b를 전부 포함하는가(상위셋인가?)?'''
print(a.issuperset(c)) # False c가 a의 superset임.
```

## 딕셔너리

```python
d.copy()
d.keys()
d.values()
d.items()
d.get(k)
d.get(k, v)
d.pop(k)
d.pop(k, v)
d.update()
d.clear() : 모든항목 제거
```

### 조회(get / update)

```python
dict_a = {'apple' : '사과',
				  'banana' : '바나나',
				  'watermelon' : '수박'}

'''get'''
#apple의 키 값인 사과 반환
print(dict_a.get('apple')) #사과
#pineapple의 키 값 반환
print(dict_a.get('pineapple')) #None 존재X, ErrorX
#default 값 0을 지정해줘서 값이 없어도 0 반환
print(dict_a.get('pineapple', 0)) # 0

```

### 삭제(pop)

```python
dict_a = {'apple' : '사과',
				  'banana' : '바나나',
				  'watermelon' : '수박'}

'''pop'''
data = dict_a.pop('banana') #제거된 것 pop_a에 할당.

print(a) # 바나나, 수박, 복숭아 중 하나 랜덤 제거. 

'''clear'''
dict_a.clear() # 전체 항목 삭제
print(a) # {}
```

### 추가(update)

```python
dict_a = {'apple' : '사',
				  'banana' : '바나나',
				  'watermelon' : '수박'}

'''update'''
dict_a.update(apple='사과') # 'apple'아님 ''빼고!
print(dict_a) # {'apple' : '사과', 'banana' : '바나나', 'watermelon' : '수박'}

```

### 집합관련함수(isdisjoint / issubset / issuperset)

```python
a = {'사과', '바나나', '수박'}
b = {'포도', '망고'}
c = {'사과', '포도', '망고', '수박', '바나나'} 

'''isdisjoint : a와 b는 교집합, 서로소인가?'''
print(a.isdisjoint(b)) # True 겹치는게 하나도 없음.

'''a.issubset(b) : a는 b에 하위셋(포함되어 있는가)인가?'''
print(b.issubset(c)) # True b는 c에 포함되어 있음.

'''a.issuperset(b) : a는 b를 전부 포함하는가(상위셋인가?)?'''
print(a.issuperset(c)) # False c가 a의 superset임.
```

## 얕은 복사(Shallow copy)

### 할당(대입연산자 ’=’)

```python
list_1 = [1, 2, 3]
copy_list = list_1 # list_1을 copy_list에 할당 **같은주소공유**

print(list_1, copy_list) # [1, 2, 3] [1, 2, 3]

copy_list[0] = 'hello'

# 같은 주소를 공유 하고 있기 때문에 하나의 항목을 바꾸면 둘 다 바뀜.
print(list_1, copy_list) # ['hello', 2, 3] ['hello', 2, 3]
```

- 얕은 복사 해결방법

```python
a = [1, 2, 3]
b = a[:] #Slice 연산자 이용하여 복제. 처음값부터 끝값까지 복제
b[0] = 5 
print(a, b) # [1, 2, 3] [5, 2, 3]
```

- 얕은 복사 해결방법 주의사항!!!!!!!!

```python
'''1차원 리스트에서만 가능!'''
a = [1, 2, ['a', 'b']
b = a[:] #Slice 연산자 이용하여 복제. 처음값부터 끝값까지 복제
b[2][0] = 0 
print(a, b) # [1, 2, [0, 'b']] [1, 2, [0, 'b']]
#리스트안의 리스트. 2차원 리스트에서는 똑같음.
```

## 깊은 복사(deepcopy)

- 얕은 복사 해결 가능

```python
import copy #deepcopy를 쓰기 위해 import 해줘야 함.

a = [1, 2, ['a', 'b']
b = copy.deepcopy(a)
b[2][0] = 0 
print(a, b) # [1, 2, ['a', 'b']] [1, 2, [0, 'b']]
```

python 사용Tip

```python
alt + shift + 방향키 : 한줄 복제
alt + 방향키 : 줄 변경
Ctrl +D : 원하는 단어 선택하고 누르면 같은 단어 전체 선택 변경
```