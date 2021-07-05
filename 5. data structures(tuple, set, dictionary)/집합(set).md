### 집합(set)

* 수학의 집합, 중복되지 않는 항목들이 모인 것

  ```python
  set1 = {항목1, 항목2, ..., 항목n}
  ```

* 집합의 특징

  * 순서가 없음 : 입력되는 순서와 출력되는 순서가 다를 수 있음
  * 동일한 요소(값)가 중복될 수 없음
  * 인덱스 사용 불가
  * 이미 포함되어 있는 요소(값)를 변경할 수 없음
    * but 요소 추가 및 삭제 가능
  * 집합 안에 변경 가능한 항목(ex. 리스트)을 포함할 수 없음
    * but 튜플은 포함 가능 → 튜플은 변경 불가하기 때문에



* 집합 만들기 : 중괄호 {} 이용

  ```python
  s1 = {1,2,3,4,5}
  print(s1)
  print(type(s1))
  ```

* set() 함수로 집합 만들기

  ```python
  s2 = set([10,20,30])    # 리스트 -> set 형으로 형변환 하는 것이라 오류 발생하지 않음
  print(s2)
  print(type(s2)) # class 'set'
  
  s3 = set((100,200,300)) # 튜플 -> set 형으로 변환
  print(s3)
  print(type(s3))
  
  print('---------------------------------------')
  
  s4 = {1,2,3,3,4}  # 중복값을 set에 저장 - 에러 X
  print(s4)  # 저장할 때 중복값은 한 번만 저장함 {1,2,3,4}
  
  # {} 이용해서 리스트를 집합에 추가하면 에러 발생
  # s5 = {1,2,[3,4]}  # TypeError: unhashable type: 'list'
  # print(s5)
  
  # 인덱스 사용 불가
  # print(s4[0])  TypeError: 'set' object is not subscriptable
  ```

  

* 집합에 요소 추가

  * add() 함수 이용

    ```python
    s = {1,2,3}
    s.add(4)
    print(s)    # {1, 2, 3, 4}
    ```

  * update() 함수 이용 : 여러 개 추가 시 사용하고 여러 개이기 때문에 묶어서 넣어야 함

    ```python
    s.update([5,6])
    s.update((5,6))
    # s.update(5) 여러 개가 아니기 때문에 오류 발생
    print(s)
    ```



* 집합에 요소 제거

  ```python
  s.remove(3)
  print(s) # {1, 2, 4, 5, 6}
  s.discard(5)
  print(s)    # {1, 2, 4, 6}
  
  # 없는 요소 삭제 시
  # s.remove(10) # 에러 발생
  s.discard(10) # 에러 없음
  
  # 전체 요소 삭제
  s.clear()
  print(s)    # set() : 빈 집합입니다. 요소는 삭제되지만 집합 변수는 남음
  
  # 집합 삭제 ㅡ del 명령문 사용
  del s       # s 변수 완전 삭제
  # print(s)  # NameError
  ```



* 집합에 in/not in 연산자 사용 가능

  ```python
  s = {1,2,3,4}
  print(3 in s)   # True
  ```



* 집합 연산 : 연산자 처리 속도가 함수 처리 속도보다 빠름

  ```python
  A = {1,2,3}
  B = {3,4,5,6}
  
  # 합집합 -
  # a|b (역슬러시키 + shift)
  print(A|B)
  # a.union(b)
  print(A.union(B))
  
  # 교집합
  # a & b
  print(A&B)
  # a.intersection(b)
  print(A.intersection(B))
  
  # 차집합
  # a - b
  print(A-B)
  # a.difference(b)
  print(A.difference(B))
  ```

  

