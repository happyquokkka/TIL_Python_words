### 예외처리 (exceptions)

* 에러 (error)

  * 문법적 오류나 실행 시간에 잘못된 메모리 접근 오류, 논리 오류, 사용자의 잘못된 입력 오류 등

  * 오류가 발생하면 프로그램이 중단되고 에러 메시지 출력됨

  * 발생되는 에러의 예 :

    * ZeroDivisionError : 0으로 나누었을 경우
    * FileNotFoundError : File을 못 찾았을 경우
    * IndexError : 리스트 등에서 인덱스가 잘못 되었을 때

    ```python
    print('--------- 에러 확인 ----------')
    
    # ZeroDivisionError : division by zero
    # print(10/0
    
    # TypeError
    # print("나이: " + 23 + "살")    # can only concatenate str (not "int") to str
    
    # NameError
    # print(b)    # name 'b' is not defined
    
    # ValueError
    c = 100
    # print('%d%' % c)    # incomplete format
    
    # SyntaxError
    # if x > 10   # invalid syntax
    #     print('홍길동')
    
    # IndexError
    # a = [1,2,3,4]
    # print(a[5])   # ist index out of range
    
    # UnboundLocalError
    # def add() :
    #     a = a+1       / local variable 'a' referenced before assignment
    # add()
    
    # ModuleNotFoundError
    # import mymodule     / No module named 'mymodule'
    
    # FileNotFoundError
    # f = open('exception.txt','r')   / [Errno 2] No such file or directory: 'exception.txt'
    
    # OSError : 파일 경로는 운영체제 권한이기 때문에 운영체제에서 나타난 에러
    # 경로명에 \ 사용하면 에러 ㅡ \\ 두 번 사용하면 에러가 나지 않음
    f = open('c:\PythonStudy\file_t2.txt','w')
    ```

    

    

* 예외처리 위계구조 (Exception Hierarchy)

  ![image-20210707001648300](C:\Users\LG Gram\AppData\Roaming\Typora\typora-user-images\image-20210707001648300.png)

  * 예외 처리 방법

    `try ... except` 문 사용

    * 예외 처리문 형식

      ```python
      try:
      	(예외 발생 가능) 문장
      except 예외 유형:
      	예외 처리 문장
      else:	# 생략 가능
      	예외 없을 때 수행 문장
      finally: # 생략 가능
      	예외 유무와 상관 없이 항상 실행되는 문장
          
      try :
           print(10/0) # 에러가 발생하면 무조건
           print('나이: ' + 23 + '살')
      except :        # 본 구문으로 포커스가 넘어옴
           print('오류발생')
      
      print('----- Exception 클래스 사용 -----')
      
      try :
           print(10/0) # 에러가 발생하면 무조건
           print('나이: ' + 23 + '살')
      except Exception:        # 본 구문으로 포커스가 넘어옴
           print('오류발생')
      
      # 에러 종류 명시
      try :
           print('나이: ' + 23 + '살')   # type 에러 발생 ㅡ 에러 발생 이후 문장을 실행하지 않음
           print(10/0)   # ZeroDivisionError 발생 ㅡ 바로 except 구문으로 넘어감
      
      except ZeroDivisionError:        # 0으로 나눈 논리 에러만 처리하겠다
           print('오류발생')
      
      # 숫자를 입력하지 않은 경우
      try :
           num = int(input('숫자를 입력하세요: '))
      except ValueError :
           print('숫자가 아닙니다')
      
      # 에러 종류 명시 : as 에러 메시지 변수
      try :
           num = int(input('숫자를 입력하세요: '))
      except ValueError as e:
           print('숫자가 아닙니다',e)
      
      ## 여러 개의 except 구문 생성 : 첫 번째 에러만 처리됨
      a = [1,2,3]
      
      try :
          # print(10/0)
          print(a[4])
          print(10/0)
      except ZeroDivisionError as e :
          print('0으로 나눌 수 없습니다')
      except indexError as e :
          print(e)
      
      #
      a = [1,2,3]
      
      try :
          # print(10/0)
          print(a[4])
          print(10/0)
      except (ZeroDivisionError, IndexError) as e :
          print('오류가 발생했습니다')
          
      # else 문 수행 ㅡ 예외가 발생하지 않은 경우
      
      try :
           num = int(input('숫자 입력: '))
      except ValueError :
           print('숫자가 아닙니다')
      else :  # 에러가 없는 경우에 실행
           print(num)
      
      # 오류 발생 시 아무것도 하지 않고 넘어가기
      
      try :
          num = int(input('숫자 입력: '))
      except ValueError :
          pass
      print('종료')
      
      ## finally 구문
      
      try :
          num = int(input('숫자 입력: '))
      except ValueError :
          print('숫자가 아닙니다')
      else :  # 에러가 없는 경우에 실행
          print(num)
      finally:
          print('종료')
      ```

      