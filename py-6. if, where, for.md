# 6. 조건과 반복문
6-1. if문
 - 조건인 논리표현식의 결과가 True이면 이후의 문장을 출력, False이면 실행하지 않음
   - 주의사항
     - 논리표현식 이후에는 콜론( : ) 사용
     - 콜론 이후의 문장은 들여쓰기
  ```py
  #if 문 구성
  if 논리표현식:
    문장
  
  #예시
  PM = 90
  if 81 < PM:
    print('마스크 착용')
  >>> '마스크 착용'
  ```

6-2. if else
 - if 논리표현식의 결과가 False일 경우 else: 블록 문장 출력
   - 주의사항
     - if문에서 논리표현식 결과가 True이면 논리표현식 콜론 이후 블록 실행
     - 논리표현식의 결과가 False이면 else: 이후의 블록 실행
  ```py
  #if else 문 구성
  if 논리표현식:
    True 결과 시 출력 문장
  else:
    False 결과 시 출력 문장
  
  #예시
  n = 3
  if n%2 == 0:
    print('%d 짝수' % n)
  else:
    print('%d 홀수' % n)
  >>> 3 홀수
  ```

6-3. if elif
 - 다중 택일 결정 구조인 if elif문은 여러 경로 중 하나를 선택하는 구문
 - 논리표현식의 결과가 False일 경우 elif의 논리표현식에서 검증
   - fasle 결과 시 다음 elif 문에서 검증
 - elif: 는 필요한 만큼 늘릴 수 있고 마지막 else는 생략 가능
  ```py
  #if elif 문 구성
  if 논리표현식1:
    논리표현식1이 True 일 경우 출력 문장
  elif 논리표현식2:
    논리표현식1이 False 이고 논리표현식2가 True 일 경우 출력 문장
  else:
    논리표현식1, 2 모두 False 일 경우 출력 문장

  #예시
  point = 82 #성적
  if 90 <= point:
    print('점수 {}, 성적 {}'.format(point, 'A'))
  elif 80 <= point:
    print('점수 {}, 성적 {}'.format(point, 'B'))
  elif 70 <= point:
    print('점수 {}, 성적 {}'.format(point, 'C'))
  else:
    print('점수 {}, 성적 {}'.format(point, 'D'))
  >>> 점수 82 성적 B
  ```

6-4. 조건의 중첩
 - 각 조건문 내에는 조건문의 사용이 가능하고 if 문에서의 중첩, else 문에서의 중첩이 모두 가능
  ```py
  category = int(input('원하는 음료 1.커피 2. 주스'))

  if category == 1:
    menu = int(input('1.아메리카노 2.카푸치노'))
    if menu == 1:
        print('1 아메리카노 주문')
    elif menu == 2:
        print('2 카푸치노 주문')
  else:
    menu = int(input('1.토마토주스 2.오렌지주스'))
    if menu == 1:
        print('1 토마토주스 주문')
    elif menu ==2:
        print('2 오렌지주스 주문')
  ```

6-5. for 문
 - for 문은 항목의 나열인 <시퀀스>의 구성요소가 순서대로 <변수>에 저장되어 반복 수행
   - 실행 흐름
     - 시퀀스의 값들이 순서대로 변수에 저장
     - 변수에 저장된 시퀀스 값으로 문장들 순차적 실행
     - 반복 몸체 문장들에서 변수 사용 가능
     - 저장된 하나의 시퀀스 값이 끝나면 그 다음 시퀀스 값을 사용해 문장 실행
     - 마지막 항목까지 실행 완료 후 else: 블록 실행 후 종료
  ```py
  #for문 구성
  for <변수> in <시퀀스>:
    반복 몸체 문장들

  #예시
  for s in 'python':
    print(s,ord(s)) #ord()는 문자의 코드 번호 출력
  else:
    print('반복 for문 완료')
  ```
 - range( ) 함수를 사용하여 정수의 범주로 시퀀스 표현 가능
   - 단, range( ) 함수 사용 시 0부터 순서대로 포함
  ```py
  for i in range(3):
    print(i, end = ' ')
  >>> 0 1 2
  ```

6-6. while 문
 - 논리표현식이 True이면 반복 몸체 문장들 실행 후 다시 논리표현식 검사 실행
 - 논리표현식이 False이면 바로 else: 이후 블록 실행 후 종료
  ```py
  #while문 구성
  while 논리표현식:
    논리표현식이 True 일 경우 반복 실행
  else:
    논리표현식이 False 일 경우 실행
  
  #예시
  n = 1
  while n <= 5:
    print(n, end = ' ')
    n += 1
  else:
    print('\n 반복 while 종료: n => %d' % n)
  >>> 1 2 3 4 5
      반복 while 종료: n => 6
  ```

6-8. break, continue의 반복 제어
 - 난수와 반복의 제어를 하기 위해 사용
 - random 모듈을 호출하여 .randint method 사용
   - 사용법
     - import random / random.randint(start, stop)
     - from random import randint / randint(start, stop)
  ```py
  import random #random 모듈 호출
  random.randint(1, 3) # .randint() method 사용
  >>> 1
  random.randint(1, 3)
  >>> 3
  #1~3 사이의 숫자 중 임의의 수 반환
  
  #예시
  import random
  for i in range(6):
    n = random.randint(1, 45)
    print(n, end = ' ')
  >>> 1 13 30 7 22
  #숫자의 순서와 상관없이 뽑힌 순서대로 반환
  ```
6-8-1. break
 - while문에서 논리표현식이 True라면 반복 몸체 문장들은 무한 반복(indefinite loop)
 - break문은 for, while문에서 else: 블록을 실행하지 않고 반복을 무조건 종료
 - break문으로 종료되면 else: 부분 실행하지 않음
  ```py
  #난수의 반복에서의 break
  from random import randint #난수 생성을 위한 모듈 호출
  LUCKY= 7
  while True: #while문 내 반복 몸체 문장의 결과가 참일 경우, 반복 실행
    n = randint(1, 9) #1 ~ 9 사이의 난수 생성
    if n == LUCKY:
        print('당첨 %d' % n)
        break #생성된 난수가 LUCKY와 동일하다면 즉시 종료
    else:
        print('실패 %d, %d 나올때까지' % (n, LUCKY))
  else:
    print('여기는 실행되지 않습니다.')
  ```

6-8-2. continue
 - for, while문에서 조건에 맞는 경우 continue 이후의 문장을 출력하지 않고 반복 진행
  ```py
  for s in 'python':
    if s in 'aeiou':
        continue
    print(s, end = ' ')
  else:
    print()
  >>> p y t h n