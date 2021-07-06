* 내장함수(Built-in functions)

  * 파이썬에 이미 만들어져 내장되어 있는 함수들

  * 별도의 모듈을 import 하지 않아도 사용 가능함

  * 형식에 맞춰 함수 이름만 호출해서 사용

    ```python
    print()
    input()
    type()
    dir()
    abs()
    
    # 특정 객체를 통해 사용 가능한 함수(메서드)
    # 문자열.sort()
    # 문자열.split()
    # 리스트.insert()
    ```

    

  * 내장함수 VS 메서드

    * 내장함수

      * 함수 : 특정 기능을 수행하는 코드 집합

      * 내장함수 : 파이썬에 이미 만들어져 있는 함수들

        ```python
        print()
        len()
        # 사용법 : print(변수(객체)), len(리스트)
        print(names)
        ```

    * 메서드

      * 함수와 같은 코드 집합이지만 클래스의 멤버로 객체를 통해서만 사용 가능함

        ```python
        append()
        insert()
        remove()
        count()
        ...
        # 사용법 : 객체.메소드
        names.append()
        names.count()
        ```

        