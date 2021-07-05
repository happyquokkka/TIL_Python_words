### 딕셔너리(dictionary)

* 키(key)와 값(value)의 한 쌍(item)을 요소로 갖는 자료형

  ```python
  dict = {키1:값1, 키2:값2, ...}
  ```

* 딕셔너리의 특징

  * 순서가 없음
    * ∴	인덱스로 접근 불가
  * 중괄호{} 사용
  * key를 통해서만 접근 가능
    * key는 숫자와 문자 모두 가능
  * key:value 의 한 쌍을 item 이라고 한다
    * 쉼표(,)로 아이템을 구분함



* 딕셔너리 만들기

  ```python
  d = {1:'a'}
  print(d)
  print(type(d))
  ```

  

* item 추가하기

  ```python
  d[2] = 'b'  # d라는 딕셔너리 변수에 value가 'b'인 원소 하나 추가한다
  # ※ 주의 : 2는 인덱스가 아닌 key를 의미!!!!!! ※
  print(d)    # {1: 'a', 2: 'b'}
  
  # 세 번째 아이템 추가
  # key는 문자도 가능
  d['test'] = 'valueTest'  # test는 key의 이름, valueTest는 value
  print(d)
  
  member = {'name':'홍길동', 'phone':'1234-1234', 'birth':'10/15'}
  
  # item 추가 : address : 서울
  member['address'] = '서울'    # address라는 key에 서울이라는 value 추가
  print(member)
  
  # 길면 여러 줄로 입력해도 됨
  naver = {
      'name':'naver',
      'url':'www.naver.com',
      'userid':'nv',
      'password':'1234'
  }
  print(naver)
  ```

  

* 딕셔너리 필수 함수

  * 딕셔너리.keys()	: key만 추출해서 리스트로 반환

  * 딕셔너리.values()  : value만 추출해서 리스트로 반환

  * 딕셔너리.items()   : (key:value)의 튜플을 추출해서 리스트로 반환

    ```python
    print(naver.keys())     # key를 리스트 형태로 반환 ㅡ 형변환 필요
    print(naver.values())   # value를 리스트 형태로 반환 ㅡ 형변환 필요
    print(naver.items())    # (key:value) 의 튜플 형태로 리스트 반환 ㅡ 형변환 필요
    
    # 출력 결과
    # dict_keys(['name', 'url', 'userid', 'password'])
    # dict_values(['naver', 'www.naver.com', 'nv', '1234'])
    # dict_items([('name', 'naver'), ('url', 'www.naver.com'), ('userid', 'nv'), ('password', '1234')])
    
    print(type(naver.keys()))     # <class 'dict_keys'>
    print(type(naver.values()))   # <class 'dict_values'>
    print(type(naver.items()))    # <class 'dict_items'>
    
    # 따라서 추출한 결과들은 리스트 형태로 반환시켜 사용해야 함!!!
    
    # 리스트로 변환: list() 함수 사용
    to_list = list(naver.keys())
    print(to_list)
    print(type(to_list))
    
    # 튜플로 변환: tuple() 함수 사용
    to_tuple = tuple(naver.keys())
    print(to_tuple)
    print(type(to_tuple))
    ```

    

* 딕셔너리 내 특정 item의 value 참조 : key 사용

  ```python
  member = {'name':'홍길동', 'phone':'1234-1234', 'birth':'10/15'}
  print(member['name'])   # key를 참조하여 해당 키에 들어있는 value 참조하여 출력
  ```

  

* 딕셔너리 내 key, value, item 출력 방법

  ```python
  for key in naver.keys() :   # dict_keys(['name', 'url', 'userid', 'password'] ㅡ in 연산자로 바로 접근 가능
      print(key)
  
  # value값 출력
  for value in naver.values() :   # dict_values(['naver', 'www.naver.com', 'nv', '1234'])
      print(value)
  
  # item 출력
  for item in naver.items() :     # dict_items([('name', 'naver'), ('url', 'www.naver.com'), ('userid', 'nv'), ('password', '1234')])
      print(item)     # 튜플 형태로 각각 출력된다
  ```

  

* key값으로  value 찾기

  ```python
  # 딕셔너리변수[key] 이용한 접근 / 딕셔너리변수.get(key) 이용한 접근 모두 가능
  print(naver["userid"])
  print(naver.get("password"))
  
  # 존재하지 않는 경우
  # print(naver['link'])    # KeyError: 'link'
  print(naver.get('link')) # none 값 반환
  print(naver.get('link','없음'))
  ```



* if문에서 get() 함수 사용

  ```python
  insert_key = 'link'
  if naver.get(insert_key) is None :  # none이라고 첫 글자를 대문자로 쓰지 않으면 오류남!
      print(insert_key + '에 대한 data가 없습니다')
  ```



* 존재 여부만 확인: in/not in 연산자 활용

  ```python
  print('link' in naver)      # 있음? 없어
  print('link' not in naver)  # 없음? 있어
  ```

  

