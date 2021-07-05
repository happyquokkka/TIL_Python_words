### 인수(argument)와 매개변수(parameter)

* 인수(인자) : argument

  * 함수에게 실제로 전달되는 값(호출할 때 전달되는 값)

    ```python
    print('hello') 
    # 'hello' = 인자
    ```

* 매개변수(parameter)

  * 함수를 호출할 때 전달되는 실제 값을 받아 저장하는 변수

  * 매개변수가 있는 함수 정의

    ```python
    def show_name(name) :
    	print(name)
    show_name('홍길동')
    ```

  * 디폴트 매개변수

    * 매개변수에 기본값 지정: 호출할 때 인수가 넘어오면 넘어온 인수를 사용하고, 그렇지 않으면 기본값으로 지정된 매개변수를 사용

      ```python
      def greet(name, msg = "안녕^^") :
      	# name 매개변수: 필수 매개변수로, 반드시 인수가 전달되어야 함
      	print(name + "," + msg)
      	# msg 매개변수는 인수가 전달되면 사용하고, 안 넘어오면 기본값 "안녕^^" 출력
      
      # 호출
      greet('홍길동', '잘 지내죠?')	# 모든 인수 전달
      greet('김철수')	# 두 번째 매개변수 msg는 디폴트 값으로 처리됨
      
      #### 디폴트 매개변수 사용시 주의사항
      # ※ 디폴트 매개변수는 무조건 매개변수 중 맨 마지막에 위치해야 함! ※ 그렇지 않으면 오류 발생
      def greet1(msg="안녕^^", name) :   
      # name 매개변수 : 필수 매개변수로 반드시 인수가 전달되어야 함
          print(name + "," + msg)      
          # msg 매개변수는 인수가 전달되면 사용, 안 넘어오면 기본값 안녕^^ 을 사용
      
      # greet1('이몽룡')   # SyntaxError: non-default argument follows default argument
      ```

      * 디폴트 매개변수를 2개 사용

        ```python
        def show_info(name,year=4,age=23) :
            print(name,year,age)
        
        show_info('홍길동')
        show_info('홍길동',3)
        show_info('홍길동',3,20)
        ```

        

* 가변 길이 매개변수  : 한 개의 매개변수로, 개수가 정해지지 않은 여러 개의 값을 전달 받을 때 사용하는 매개변수

  * 매개변수의 형태 : __*매개변수이름__

    ```python
    def show_players(*players) :
        print(players)
        print(type(players))  # <class 'tuple'> 가변길이 매개변수의 *args 형태는 튜플 형태로 전달된다
        for player in players :
            print(player, end='')
        print()
    
    show_players()  # 가변길이는 0 ~ 내가 넘기고 싶은 만큼을 의미!
    # show_players('손흥민','기성용')
    # show_players('박지성','손흥민','황의조')
    
    ```

  * keyword arguments : key=value  형태로 값을 전달 받음

    ```python
    def show_keywords(**kwargs) :   # 전달받을 때 인수가 dict 형태로 전달됨
        print(kwargs)
        print(type(kwargs))
    
    # 함수 호출
    show_keywords()     # 빈 딕셔너리가 전달된다
    show_keywords(a=3)
    show_keywords(id='sun',
                  name='kim',
                  phone='010-1234-1234')
    
    show_keywords(num=3,
                  val='kim',
                  str='abcdef')
    ```

    

