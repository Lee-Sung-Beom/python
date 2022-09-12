# 5. 논리 자료와 다양한 연산
5-1. 논리 값과 논리 연산
 - 논리 값인 True / False는 키워드로 제공되며, bool 클래스 타입
 - int( ) 함수에 의해 1, 0으로 반환
  ```py
  int(True)
  >>> (1)
  int(False)
  >>> (0)
  ```
 - 논리 연산
   - and / &: 두 항이 모두 참이어야 True 반환
   - or / | : 두 항이 모두 거짓이어야 False 반환
   - ^ : 두 항이 다르면 True 반환
   - not: 뒤에 위치한 논리 값을 반대 논리 값으로 전환
   - 우선 순위: 1. not 연산 - 2. and 연산 - 3. or 연산
  ```py
  # and / &
  True & True, True and True
  >>> (True, True)
  True & False, True and False
  >>> (False, False)
  # or / |
  True | True, True or True
  >>> (True, True)
  True | False, True or False
  >>> (True, True)
  False | True, False or True
  >>> (True, True)
  False | False, False or False
  >>> (False, False)
  # ^
  True ^ True
  >>> False
  True ^ False
  >>> True
  # not
  not True, not False
  >>> (False, True)
  ```

5-2. 관계 연산
 - 관계 연산을 통해 다음과 같은 값에 대한 연산 가능
   - 문자열의 경우 유니코드 값으로 비교

|연산자|의미|문자열에서의 사용|
|------|---|----------------|
|A > B|A가 B보다 크다|A가 B보다 사전상 뒤에 존재|
|A >= B|A가 B보다 크거나 같다|A가 B보다 사전상 뒤에 있거나 동일|
|A < B|A가 B보다 작다|A가 B보다 사전상 앞에 존재|
|A <= B|A가 B보다 작거나 같다|A가 B보다 사전상 앞에 있거나 동일|
|A ==B|A랑 B가 같다|A랑 B가 사전상 순서가 동일|
|A != B|A는 B와 다르다|A랑 B의 사전상 순서가 다름|

5-3. 멤버십 연산 in
 - 키워드 in은 멤버의 소속을 반환하며 결과는 True, False로 반환

|연산|의미|결과|
|---|----|-----|
|x in s|문자열 s에 부분 문자열 x가 포함|포함=True / 미포함 =False|
|x not in s|문자열 s에 부분 문자열 x가 미포함|미포함=True / 포함 = False|

5-4. 비트 논리 연산
 - 비트 연산: 정수로 저장된 메모리에서 비트와 비트의 연산
   - 논리곱: &
   - 논리합: |
   - 배타적 논리합: ^
 - 비트 연산은 일반 논리 연산과 동일한 의미로 계산
 - 비트 배타적 논리합의 특성을 사용해 암호화 가능
   - a ^ a == 0
   - a ^ 0 == a
   - a ^ 1 == ~a
   - a ^ b == b ^ a
   - (a ^ b) ^ c == a ^ (b ^ c)
   - (a ^ b) ^ b == a ^ (b ^ b) == a ^ 0 == a