### 리스트(List)

* 자료구조의 일종으로, __동일한 이름을 갖는 원소들의 연속 저장 영역__ → _집합적 자료형_

* 대괄호 사용

  ```python
  변수명 = [값1, 값2, 값3, ...]
  인덱스 = 리스트의 원소 개수 -1
  	ex) scores = [34, 56, 78, 89]
  	    scores[0] = 34
  ```

* 리스트의 크기는 가변적

* 다양한 종류의 데이터를 하나의 리스트 안에 저장할 수 있음



* 단일 자료형 리스트

  ```py
  ints = [1,2,3,4,5]
  floats = [1.1,2.2,3.3,4.4,5.5]
  names = ['홍길동', '이몽룡', '성춘향']
  ```

  

* 복합 자료형 리스트

  ```
  mix = [1, 5.0, '김철수']
  ```

  * 리스트 안에 리스트를 포함할 수 있음

    ```py3
    numbers = [100,200,300,[10,20,30]]
    ```

    

* 리스트 반환

  * 리스트 이름으로 접근 → 리스트 형태로 반환함

    ```python
    print(ints)
    print(floats)
    print(names)
    ```

  * 원소별 접근

    ```python
    for name in names :
        print(name)
        print(type(name))
    ```

* 리스트 각각의 값을 원소에 저장

  ```python
  nums = [1,2,3]
  # 리스트 nums의 원소값 각각을 a, b, c 변수에 저장하시오
  # a = nums[0]
  # b = nums[1]
  # c = nums[2]
  ```



* 리스트 특징

  ```python
  nums1 = [10,20,30]
  # a1, b1 = nums1  # ValueError : too many values to unpack (expected 2)
  # 왼쪽 변수의 개수가 오른족 리스트 원소의 개수보다 작으면 안된다
  # a1, b1 = 10, 20, 30
  
  a1, b1, c1, d1 = nums1
  # print(a1,b1,c1,d1) # ValueError: not enough values to unpack (expected 4, got 3)
  # 왼쪽 변수의 개수가 오른쪽 리스트 원소의 개수보다 많아도 안 됨
  ```

  

* 리스트 연산

  * 리스트 합치기(결합) : + 연산자 사용

    ```python
    a = [1,2,3]
    b = [4,5,6]
    c = a + b # a 리스트와 b 리스트를 결합해서 하나의 리스트 생성
    print(c)
    ```

  * 리스트 곱하기(반복) : * 연산자 사용

    ```python
    a = [1,2,3]
    b = [4,5,6]
    d = a * 3 # [1,2,3,1,2,3,1,2,3]
    # a 리스트의 원소들을 3번 반복해서 원소를 생성 => 하나의 리스트 반환
    print(d)
    ```

  * 리스트 내용 변경 : 인덱싱 접근, 슬라이싱 접근 모두 가능

    ```python
    a = [1,2,3]
    a[2] = 30
    print(a) # [1,2,30]
    
    a[0:2] = [10,20] # [1,2,30] -> [10,20,30]
    # a[0],a[1]=[10,20] / 바꿀 원소가 두 개이므로 0번, 1번에 각각 들어갔음!
    print(a)
    ```

    * 인덱싱을 통해 원소의 값 변경

      ```
      b = [4,5,6]
      b[0] = [1,2,3,4]    # 리스트를 한 원소값으로 주면 하위 리스트로 생성
      print(b)
      ```

      

* 빈 리스트 값 저장 : 내용 삭제됨

  ```python
  c = [1,2,3,4,5,6]
  c[1:3] = [] # 빈 리스트는 생략(삭제)해 버림
  print(c)    # [1,4,5,6]  => 1번부터 2번 원소를 삭제
  
  ## 문자열과 다르게 리스트는 부분 원소값 변경이 가능하다
  ```

  

* 리스트 변수 복사

  * 얕은 복사 (shallow copy)

    ```python
    a = [1,2,3]
    # 리스트 [1,2,3]을 메모리 어딘가 저장하고 저장되어 있는 주소를 a가 갖고 있다
    
    # a 리스트의 값을 b 변수에 복사하시오. (저장하시오)
    # 얕은 복사 : 원본을 변경하면 복사본 내용도 변경
    b = a
    # a가 갖고 있는 저장 주소를 b에게 저장하는 것임!
    
    print(a)
    print(b)
    
    b[0] = 100
    print(a)
    print(b)
    # b[0] 원소값을 변경했는데 a[0] 원소값도 변경
    ```

  * 깊은 복사 (deep copy)

    : list() 함수 또는 deepcopy()  함수를 사용해서 리스트의 복사본을 새로 생성해서 반환

     복사본 리스트 원소의 값을 변경해도 원본 리스트 원소의 값은 변경되지 않음

    ```python
    scores = [1,2,3,4,5]
    values = list(scores)
    print(scores)
    print(values)
    
    values[0] = 100
    
    # scores는 변경되지 않고 values만 변경됨
    print('scores :', scores)
    print('values :', values)   # values : [100, 2, 3, 4, 5]
    
    # deepcopy() 함수 : 깊은 복사
    # copy 모듈을 import 해야함
    
    import copy
    
    a = ['a','b','c']
    b = copy.deepcopy(a)  # a를 복사해서 b에 할당
    
    print('b 리스트 수정 전')
    print(a)
    print(b)
    
    b[0] = 1
    
    print('b 리스트 수정 후')
    print(a)
    print(b)
    ```

    

* 리스트 관련 함수 정리

  * len() : 내장함수, 리스트의 길이를 반환

    ```python
    a = [1,2,3,3,4]
    
    # len()
    # 내장함수
    # 리스트의 길이 반환
    print('전체 원소의 개수: ', len(a)) # 5 = 리스트 a의 원소의 개수
    ```

  * count() : 메소드, 리스트 내의 특정 요소의 개수 셈

    ```python
    a = [1,2,3,3,4]
    print('원소 3의 개수: ', a.count(3)) # 2
    ```

  * append() : 리스트의 끝에 새로운 요소 추가

    ```python
    # 리스트.append(새로추가할요소)
    a = [1,2,3,4]
    a.append(5) # a 리스트 마지막 요소로 5를 추가하고 a에 저장 (원본을 바꾼다!)
    print(a)    # [1,2,3,4,5]
    
    a.append([6,7]) # a 리스트 마지막에 하위 리스트 추가
    print(a)    # [1, 2, 3, 4, 5, [6, 7]]
    
    # a.append(8,9) # 원소를 2개 추가하면 에러남 - TypeError: list.append() takes exactly one argument
    # append는 무조건 하나의 값만 추가할 수 있음
    
    # 빈 리스트 생성하고 요소를 나중에 추가하고 싶을 때
    values = []
    values.append(10)
    values.append(20)
    values.append(30)   # [10,20,30]
    print(values)
    ```

  * insert() : 리스트의 특정 위치에 요소 삽입

    ```python
    # insert(위치, 값) : 리스트 특정 위치에 요소 삽입
    nums = [1,2,3,4,5]
    nums.insert(1,200)  # 두 번째 위치에 삽입(인덱스 값 1번에 삽입 - 기존 인덱스 1번 이상부터는 뒤로 밀림)
    print(nums)     # [1, 200, 2, 3, 4, 5]
    
    nums.insert(-1,'홍길동') # 마지막 원소 바로 전에 삽입 [1, 200, 2, 3, 4, '홍길동', 5]
    print(nums)
    
    # insert 함수를 이용해서 리스트 맨 뒤에 삽입 - append 를 활용하는 것이 일반적
    nums.insert(len(nums),12.3)
    print(nums)
    
    nums.insert(len(nums)-1, [10,20]) # 삽입되는 위치는? 마지막 원소 앞에 하위 리스트 삽입
    print(nums)     # [1, 200, 2, 3, 4, '홍길동', 5, [10, 20], 12.3]
    ```

  * remove() : 리스트에서 값에 해당되는 요소를 제거

    ```python
    # 리스트.remove(값)
    # 동일한 값이 여러 개 있는 경우 첫 번째 값만 제거
    
    n = [1,2,3,3,4,5,4,3]
    n.remove(4)     # 첫 번째로 존재하는 4만 제거하고 원본에도 반영됨
    print(n)        # [1, 2, 3, 3, 5, 4, 3]
    
    # n 리스트에서 원소값이 3인 원소를 모두 제거하시오.
    # 3의 개수를 확인해야 함
    count = n.count(3)  # ㄷ개 들어 있음
    print(count)
    
    for i in range(count) :
        n.remove(3)
        print('3 삭제', n)
    
    print(n)
    ```

  * pop() : 값을 반환하고 삭제

    ```python
    # 리스트.pop()
    # 리스트의 마지막 요소를 반환하고 삭제
    # 리스트.pop(인덱스값)
    # 인덱스 위치에 있는 요소를 반환하고 삭제
    
    x = ['a','b','c','d']
    y = x.pop()     # 'd'
    print(y)    # 반환된 마지막 요소 = d
    print(x)    # d 삭제된 나머지 요소만 확인 ['a', 'b', 'c']
    
    # x에 남아 있는 요소 3개를 pop
    # 계속 pop 실행해서 더 이상 요소가 없으면 빈 리스트로 남게 됨
    x.pop()  # ['a', 'b']
    x.pop()  # ['a']
    x.pop()  # []
    print(x)  # [] / 리스트인 변수는 유지하나 빈 리스트로 반환
    
    # x가 빈 리스트인 경우 에러 발생
    # x.pop() # IndexError: pop from empty list 오류 발생
    
    # pop(인덱스) : 인덱스 위치에 있는 요소 반환하고 삭제
    heroes = ['슈퍼맨', '스파이더맨', '헐크', '아이언맨', '배트맨']
    tmp = heroes.pop(2)  # 세번째 : 헐크 삭제
    print('삭제된 값 :', tmp)
    print('삭제 후 리스트',heroes)
    ```

  * extend() : 리스트를 확장하는 기능/ 이전 리스트에 원소를 추가하여 확장된 리스트로 변화하고, 원본 리스트 변경됨

    ```python
    a = [1,2,3]
    a.extend([4,5])
    print('a리스트:', a)
    
    b = [1,2,3]
    b.append([4,5])
    print('b리스트', b)
    # extend는 원소가 추가되면서 리스트가 확장됨 - 하나의 리스트
    # append 와 insert 는 추가된 원소가 리스트면 하위 리스트로 추가됨 - 리스트 안의 리스트
    
    c = [1,2,3]
    c.insert(len(c),[4,5])
    print('c리스트:',c)
    
    print('---------------------------') ; print()
    ```

  * sort() / reverse() / sorted()  : 원소의 정렬과 관계되는 함수

    ```python
    # sort() : 리스트 정렬, 원본 리스트 변경
    scores = [90,78,81,64,89] ; print()
    scores.sort()   # 기본 : 오름차순 정렬
    print(scores)   # [64, 78, 81, 89, 90]
    
    scores = [90,78,81,64,89] ; print()
    scores.sort(reverse=True)   # 내림차순 정렬
    print(scores)
    
    scores = [90,78,81,64,89] ; print()
    scores.reverse() # 원소의 위치를 역순으로 변경(정렬이 아니라 위치값만 변경하는 것임)
    print(scores)   # [89, 64, 81, 78, 90]
    
    print('---------------------------') ; print()
    
    ## 문자의 정렬 - 대문자 < 소문자, A~Z, a~z
    char = ['b','A','d','C']
    char.sort()   # 오름차순 정렬
    print(char)
    
    char = ['b','A','d','C']
    char.sort(reverse=True)   # 내림차순 정렬 - ['d', 'b', 'C', 'A']
    print(char)
    
    print('---------------------------') ; print()
    
    # 대소문자 구별 없이 알파벳 순으로 정렬하고 싶을 때
    # key = str.lower
    char = ['b','A','d','C']
    char.sort(key=str.lower)  # sort의 옵션으로 key=str.lower 부여
    print(char)
    
    # 대소문자 구별없이 내림차순 정렬 하고 싶을 때
    char = ['b','A','d','C']
    char.sort(key=str.lower,reverse=True)
    print(char)
    
    print('---------------------------') ; print()
    
    # 문자열은 어떻게 정렬?
    ids = ['SKY','Blue','red','eBook','GREEN']
    ids.sort()  # 오름차순 정렬 ㅡ 첫 문자 기준으로 정렬함
    print(ids)  # ['Blue', 'GREEN', 'SKY', 'eBook', 'red']
    
    # 대소문자 구별 없이 정렬
    ids = ['SKY','Blue','red','eBook','GREEN']
    ids.sort(key=str.lower)  # 대소문자 구별 없이 알파벳 순 정렬
    print(ids)
    
    print('---------------------------') ; print()
    
    # sorted() : 원본을 유지하면서 정렬된 새로운 리스트를 반환함
    a = [3,5,2,1,4]
    b = sorted(a)
    print('a:',a)
    print('b:',b)
    ```

  * index() : 리스트 안에서 원소의 위치 값을 반환

    ```python
    # 리스트.index(값)
    a = [1,2,3,4,5,5]
    print(a.index(3))  # 값 3은 2번 인덱스에 있음
    print(a.index(5))  # 값 5는 4번 인덱스에 있음/ 첫 번째 만나는 원소의 위치값을 반환
    # print(a.index(10)) # ValueError: 10 is not in list  리스트 안에서 못 찾았음
    ```

  * mix() / max() : 리스트 내 최소값/최댓값을 가지는 원소 반환

    ```python
    n = [100,7,-2,99,30]
    char = ['c','a','D','A','b']
    n_char = [1,300,'a','D',-2]
    
    print(min(n))
    print(max(n))
    
    print(min(char))     # A (대문자 에이)
    print(max(char))     # c (소문자 씨)
    
    
    # 복합 자료형인 경우 max 함수나 min 함수는 사용할 수 없음
    
    # print(min(n_char))  # TypeError: '<' not supported between instances of 'str' and 'int'
    # print(max(n_char))  # TypeError: '<' not supported between instances of 'str' and 'int'
    ```

  * in/not in : 포함여부 판단 후  True 나 False 값으로 반환

    ```python
    num = [1,2,3,4,5]
    result = 2 in num   # 2가 있니?
    print(result)   # True
    
    result = 2 not in num   # 2가 없니?
    print(result)   # False
    ```

  * 리스트 일치 검사 : 비교 연산자를 사용해서 2개의 리스트 비교

    ```python
    # 첫 번째 요소부터 비교 시작
    # 첫 번재 요소의 비교에서 결과가 False 면 더 이상 비교하지 않고 첫 번째 요소가 동일하면 두 번째 요소를 비교하는 방식
    # 리스트 안에 모든 요소 비교 결과가 True 면 전체 결과 : True
    
    list1 = [1,2,3]
    list2 = [1,2,3]
    print(list1 == list2)
    
    list1 = [5,2,3]
    list2 = [1,2,3]
    print(list1 >= list2)
    ```

    