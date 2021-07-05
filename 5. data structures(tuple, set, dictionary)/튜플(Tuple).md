### 튜플(Tuple)

* 리스트와 유사한 __집합적 자료형__이지만 리스트와 달리 _원소 변경 불가_

* _추가, 수정, 삭제 모두 안 됨_

* 소괄호() 사용

  ```python
  튜플 = (값1, 값2, … , 값n)
  colors = ("red", "green", "blue")
  numbers = (1, 2, 3, 4, 5 )
  
  # 각 원소는 인덱스(index)로 구분 (0부터 시작)
  # 원소 변경 시 에러 발생
  ```

  

* 튜플 만들기

  ```python
  t1 = (1,2,3)
  print(t1)
  
  list1 = [1,2,3,t1]
  print(list1)
  
  list1[3] = 10
  print(list1)
  
  t2 = 4,5,6  # 괄호 없어도 튜플로 생성됨
  print(t2)   # (4, 5, 6) 으로 자동으로 괄호가 생기면서 튜플로 인식
  
  t3 = t1,(7,8,9)  # 튜플 내 다른 튜플도 포함 가능
  print(t3)
  
  t4 = [1,2],[3,4]  # 괄호는 없지만 콤마로 연결되어 있으니 튜플 만들어짐
  # 리스트로 튜플 생성할 수 있음
  print(t4)
  
  t4_1 = 3,   # 하나의 원소를 갖는 튜플로 생성 /  t4_1 = (3)
  print(t4_1)
  print(type(t4_1))
  
  t5 = tuple([5,6,7,8])   # 리스트를 튜플로 형변환 한 것!!!
  print(t5)      # (5,6,7,8)
  print(type(t5))
  
  # t6 = tuple(3)   # TypeError: 'int' object is not iterable
  # 정수를 튜플로 변환하는 것은 안 됨. 집합형태가 아니라서.
  # print(t6)
  
  ```

  

*  튜플을 리스트로 변환

  ```python
  # (1,2,3) -> [1,2,3]
  t1 = (1,2,3)
  to_list1 = list(t1)
  print(to_list1) # [1, 2, 3]
  
  # 리스트로 형변환이 되었어도 튜플 내 튜플 원소들은 그대로 튜플로 유지됨
  t2 = ((1,2,3),(7,8,9))
  to_list2 = list(t3)
  print(to_list2) # [(1, 2, 3), (7, 8, 9)]
  ```

* 리스트를 튜플로 변환

  ```python
  list=[1,2,3]
  to_list = tuple(list)
  print(to_list)  # (1,2,3) / 튜플 형태로 형변환 일어남
  ```

  