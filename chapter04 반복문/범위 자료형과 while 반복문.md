# 범위(range)
리스트, 딕셔너리 외에 for 반복문과 함께 많이 사용되는 자료형. 정수로 이루어진 범위를 만들 때는 range()함수 사용.  
```
>>> a = range(5)    # 매개변수에 숫자 1개 넣기
>>> a
range(0, 5)
>>> list(range(5))
[0, 1, 2, 3, 4]
>>> list(range(0, 5))
[0, 1, 2, 3, 4]
>>> list(range(5, 10))
[5, 6, 7, 8, 9]
>>> list(range(0, 10, 2))    # 0부터 2씩 증가하면서 (10-1)까지 정수 범위
[0, 2, 4, 6, 8]
```
```
>>> n = 10
>>> a = range(0, int(n/2))    # 실수를 정수로 바꾸는 방법보다
>>> list(a)
[0, 1, 2, 3, 4]
>>> a = range(0, n//2)        # 정수 나누기 연산자를 더 많이 사용
>>> list(a)
[0, 1, 2, 3, 4]
```

# for 반복문: 범위
```
# for 반복문, 범위 조합
for i in range(5):
  print(str(i) + "= 반복 변수")
print()

for i in range(5, 10):
  print(str(i) + "= 반복 변수")
print()

for i in range(0, 10, 3):
  print(str(i) + "= 반복 변수")
print()

# 실행 결과
# 0 = 반복 변수
# 1 = 반복 변수
# 2 = 반복 변수
# 3 = 반복 변수
# 4 = 반복 변수
#
# 5 = 반복 변수
# 6 = 반복 변수
# 7 = 반복 변수
# 8 = 반복 변수
# 9 = 반복 변수
#
# 0 = 반복 변수
# 3 = 반복 변수
# 6 = 반복 변수
# 9 = 반복 변수
```
# for 반복문: 리스트
몇 번째 반복일지 알아야 할 경우 가장 쉬운 방법이 범위를 조합해서 사용하는 것.
```
# 리스트 선언
array = [273, 32, 103, 57, 52]

# 리스트에 반복문을 적용
for i in range(len(array)):
  # 출력
  print("{}번째 반복: {}".format(i, array[i])
```
가장 기본적이고, 많이 사용하는 형태. 리스트와 반복문 조합은 조금 더 편한 형식으로 사용 가능.
# for 반복문: 반대로 반복
변수가 큰 숫자에서 작은 숫자로 반복문을 적용하는 경우 역반복문임.
## range() 함수의 매개변수를 3개로 하여 사용
```
# 역반복문
for i in range(4, 0-1, -1):
  # 출력
  print("현재 반복 변수: {}".format(i))
```
중간에 0-1은 0까지 코드 반복함을 강조
## reversed()
```
# 역반복문
for i in reversed(range(5)):
  # 출력
  print("현재 반복 변수: {}".format(i))
```
reversed() 함수를 적용하면 [0, 1, 2, 3, 4]라는 형태의 범위가 [4, 3, 2, 1, 0]으로 뒤집어짐. 주의 사항이 많은 함수.
# 중첩 반복문으로 피라미드 만들기
```
output = ""

for i in range(1, 10):
  for j in range(0, i):
    output += "*"
  output += "\n"

print(output)
```
```
output = ""

for i in range(1, 15):
  for j in range(14, i, -1):
    output += ' '
  for k in range(0, 2 * i -1):
    output += '*'
  output += '\n'

print(output)
```
실무에서 이만큼 어려운 반복문을 그다지 많이 사용하지는 않음.
```
output = ""

for i in range(1, 10):
  output += ("*" * i)
  output += "\n"

print(output)
```

# while 반복문
리스트 또는 딕셔너리 내부의 요소를 모두 순회하는 경우, 특정 횟수만큼 반복하는 경우에는 for 반복문을 많이 사용하지만 그 외에도 범용적으로 사용 가능한 while 반복문이 있음.
```
while 불 표현식:
  문장
```
Ctrl + C 를 눌러 강제 종료 가능.

## while 반복문 사용
```
# 반복 변수를 기반으로 반복
i = 0
while i < 10:
  print("{}번째 반복입니다.".format(i))
  i += 1
```
for 반복문을 많이 사용하는 상황 외에는 대부분 while 반복문 사용. 대표적으로 무한 반복이 있음. 스스로 코드를 입력해보며 while 반복문이 나을지 for 반복문이 나을지 직접 느끼는 것이 중요.

## while 반복문: 상태 기반 반복
리스트의 remove() 함수는 리스트 내부에서 해당하는 값을 하나만 제거, while 반복문을 활용하면 여러개 제거 가능.
```
# 변수 선언
list_test = [1, 2, 1, 2]
value = 2

# list_test 내부에 value가 있다면 반복
while value in list_test:
  list_test.remove(value)

# 출력
print(list_test)
```

## while 반복문: 시간 기반 반복
시간을 기반으로 반복하려면 유닉스 타임이라는 개념을 알아야 하는데 유닉스 타임(Unix Time)이란 세계 표준시(UTC)로 1970년 1월 1일 0시 0분 0초를 기준으로 몇 초가 지났는지 정수로 나타낸 것. while 반복문을 조합하면 특정 시간동안 프로그램 정지 가능
```
# 시간과 관련된 기능을 가져옴
import time

# 변수 선언
number = 0

# 5초 동안 반복
target_tick = time.time() + 5
while time.time() < target_tick:
  number += 1

# 출력
print("5초 동안 {}번 반복했습니다.".format(number))
```
컴퓨터의 성능과 상황에 따라 반복횟수는 계속 달라짐. 이를 활용하여 5초 동안 다른 사용자의 응답 대기 가능. 통신할 때 자주 사용하는 코드이므로 시간 기반으로 조건을 걸 때는 while 반복문 활용 가능.

## while 반복문: break 키워드/continue 키워드
break 키워드는 반복문을 벗어날 때 사용하는 키워드. 무한 반복문의 내부에서 벗어날 때 많이 사용.
```
# 변수 선언.
i = 0

# 무한 반복
while True:
  # 몇 번째 반복인지 출력
  print("{}번째 반복문입니다.".format(i))
  i = i + 1
  # 반복 종료
  input_text = input("> 종료하시겠습니까?(y/n): ")
  if input_text in ["y", "Y"]:
    print("반복을 종료합니다.")
    break
```
continue 키워드는 현재 반복을 생략하고, 다음 반복으로 넘어갈 때 사용하는 키워드.
```
# 변수 선언
numbers = [5, 15, 6, 20, 7, 25]

# 반복
for number in numbers:
  # number가 10보다 작으면 다음 반복으로 넘어감
  if number < 10:
    continue
  # 출력
  print(number)
```

```
