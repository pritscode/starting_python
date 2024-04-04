# 불 자료형 if 조건문
Boolean은 불린 또는 불리언이라는 발음으로 부름. 프로그래밍에서는 짧게 Bool이라고 쓰기도 함. 한국에서는 Boolean Algebra를 불 대수, Boolean Operator를 불 연산자로 부르는 것처럼 '불'이라고 많이 표기 불은 오직 True(참)와 False(거짓) 값만 가질 수 있음.

## 불 만들기: 비교 연산자
불은 **비교 연산자**를 통해 만들 수 있음.
|연산자|설명|
|:--:|:--:|
|==|같다|
|!=|다르다|
|<|작다|
|>|크다|
|<=|작거나 같다|
|>=|크거나 같다|

비교 연산자는 숫자 또는 문자열에 적용할 수 있음. 숫자의 대소 비교는 누구나 쉽게 할 수 있음.
```
>>> print(10 == 100)
False
>>> print(10 != 100)
True
>>> print(10 < 100)
True
```
파이썬은 문자열에도 비교 연산자를 적용할 수 있음. 한글은 사전 순서(가나다순)로 앞에 있는 것이 작은 값을 가짐. '가방'과 '하마'를 비교하면 사전 순서로 '가방'이 앞에 있으므로 '가방'이 '하마'보다 작은 값을 가짐.
```
>>> print("가방" == "가방")
True
>>> print("가방" < "하마")
True
```
## 불 연산하기: 논리 연산자
불끼리는 논리 연산자를 사용 가능.
|연산자|의미|설명|
|:--|:--|:--|
|not|아니다|불을 반대로 전환|
|and|그리고|피연산자 2개가 모두 참일 때 True를 출력하며, 그 외는 모두 False를 출력.|
|or|또는|피연산자 2개 중에 하나만 참이라도 True를 출력하며, 2개가 모두 거짓일 때만 False를 출력.|

> 단항 연산자: 피연산자가 1개 (부호 연산자 등.. -10, +10)  
> 이항 연산자: 피연산자가 2개 (대부분의 숫자 연산자 10+10, 10*10..)

### not 연산자
not 연산자는 단항 연산자로, 참과 거짓을 반대로 바꿀 때 사용. 실행하면 단순하게 True와 False가 서로 바뀜
```
>>> print(not True)
False
>>> print(not False)
True
```
일반적으로 비교 연산자로 불 자료형의 변수를 만들고, 여기에 not 연산자를 적용.  
```
x = 10
under_20 = x<20    # under_20 = (x<20)
print("under_20: ", under_20)
print("not under_20: ", not under_20)
```

### and 연산자와 or 연산자
not 연산자는 대부분 쉽게 이해, and 연산자와 or 연산자는 처음 본 사람들한테는 이해하기 힘든 연산자. 최종 결과를 확인하고 해당 내용은 차근차근 설명.  
and 연산자는 양쪽 변의 값이 모두 참일 때만 True를 결과로 나타냄.  
or 연산자는 둘 중 하나만 참이어도 True를 결과로 나타냄.

## if 조건문
파이썬에서 if 조건문은 조건에 따라 코드를 실행이나, 실행하지 않게 만들고 싶을 때 사용하는 구문. 코드의 실행 흐름을 변경한다는 뜻. 조건을 기반으로 실행의 흐름을 변경하는 것을 조금 어려운 용어로 조건분기라고 함.  
if 조건문의 기본적인 구조.
```
if 불 값이 나오는 표현식:
    불 값이 참일 때 실행할 문장
```
if 뒤에 있는 불 값이 거짓인 경우에는 들여쓰기 된 명령문이 있다고 하더라도 아무것도 실행되지 않음.  
```
# 입력을 받음
number = input("정수 입력> ")
number = input(number)

# 양수 조건
if number > 0:
  print("양수입니다")

# 음수 조건
if number < 0:
  print("음수입니다")

# 0 조건
if number == 0:
  print("0입니다")
```

> 들여쓰기(indent)  
> 들여쓰기는 코드 앞에 '띄어쓰기 4번', '띄어쓰기 2번', '탭'과 같은 것을 의미. 파이썬 개발에서는 일반적으로 '띄어쓰기 4번'을 많이 사용.  
> 코드를 입력할 때 띄어쓰기를 4개 입력할 필요 없이 파이썬 IDLE 에디터나 비주얼 스튜디오 코드 등의 개발 전용 에디터에서는 소프트탭(soft tab)이라는 tab키를 누르면 자동으로 띄어쓰기 4개를 넣어주는 기능 존재. 들여쓰기 제거는 shift+tab. 여러 줄 들여쓰기도 여러 줄을 선택하고 tab키 누르기. 들여쓰기 제거도 마찬가지.

### 짝수와 홀수 구분
```
# 입력을 받음.
number = input("정수 입력> ")

# 마지막 자리 숫자를 추출.
last_character = number[-1]

# 숫자로 변환하기
last_number = int(last_character)

# 짝수 확인
if last_number == 0 \
  or last_number == 2 \
  or last_number == 4 \
  or last_number == 6 \
  or last_number == 8:
  print("짝수입니다")

# 홀수 확인
if last_number == 1 \
  or last_number == 3 \
  or last_number == 5 \
  or last_number == 7 \
  or last_number == 9:
  print("홀수입니다")
```
```
# 입력을 받습니다.
number = input("정수 입력> ")
last_character = number[-1]

# 짝수 조건
if last_character in "02468":
  print("짝수입니다")

# 홀수 조건
if last_character in "13579":
  print("홀수입니다")
```
```
# 입력을 받음.
number = input("정수 입력> ")
number = int(number)

# 짝수 조건
if number % 2 == 0:
  print("짝수입니다")

# 홀수 조건
if number % 2 == 1:
  print("홀수입니다")
```

## 날짜/시간 활용
시간을 조건으로 구분하여 오전인지 오후인지 출력하는 조건문 사용 프로그램.
```
# 날짜/시간과 관련된 기능을 가져옴.
import datetime

# 현재 날짜/시간을 구함.
now = datetime.datetime.now()

# 출력.
print(now.year, "년")
print(now.month, "월")
print(now.day, "일")
print(now.hour, "시")
print(now.minute, "분")
print(now.second, "초")

# 실행 결과
# 2024 년
# 4 월
# 3 일
# 19 시
# 3 분
# 14 초
```
모듈이라는 기능을 활용해서 datetime이라는 기능을 가져 옴. 현재 시각을 기반으로 하고 있기 때문에 결과는 실행할 때마다 다르게 나타남.
format() 함수를 활용하면 날짜를 한눈에 볼 수 있게 출력.
```
# 날짜/시간과 관련된 기능을 가져옴.
import datetime

# 현재 날짜/시간을 구함.
now = datetime.datetime.now()

# 출력.
print("{}년 {}월 {}일 {}시 {}분 {}초".format(
        now.year,
        now.month,
        now.day,
        now.hour,
        now.minute,
        now.second
))
```
> 파이썬에서 월 출력  
> 월을 0~11까지로 출력함. 문자열의 첫번째 글자를 0번째라고 세었던 것처럼 프로그래밍 언어의 규칙을 지키기 위한 목적.  
> 파이썬은 사람이 이해하기 쉬운 형태로 현재 월을 출력.

```
# 날짜/시간과 관련된 기능
import datetime

# 현재 날짜/시간을 구함.
now = datetime.datetime.now()

# 오전 구분
if now.hour < 12:
  print("현재 시각은 {}시로 오전입니다.".format(now.hour))

# 오후 구분
if now.hour >= 12:
  print("현재 시각은 {}시로 오후입니다.".format(now.hour))
```
```
# 날짜/시간과 관련된 기능
import datetime

# 현재 날짜/시간을 구함.
now = datetime.datetime.now()

# 봄 구분
if 3 <= now.month <= 5:
  print("이변 달은 {}월로 봄입니다.".format(now.month))

# 여름 구분
if 6 <= now.month <= 8:
  print("이변 달은 {}월로 여름입니다.".format(now.month))

# 가을 구분
if 9 <= now.month <= 11:
  print("이변 달은 {}월로 가을입니다.".format(now.month))

# 겨울 구분
if now.month == 12 or 1 <= now.month <= 2:
  print("이변 달은 {}월로 겨울입니다.".format(now.month))
```
