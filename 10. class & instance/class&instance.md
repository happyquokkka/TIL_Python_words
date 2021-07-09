## 객체 지향 프로그래밍(Object oriented programming)

* 객체 지향 프로그래밍에서는 모든 데이터를 객체(object)로 취급
  * __객체가 바로 프로그래밍의 중심__
* 객체(object)란 실생활에서 우리가 인식할 수 있는 사물(ex 사람, 자동차, 핸드폰 등)
* 이러한 객체의 __상태(state)__ 와 __행동(behavior)__ 을 구체화하는 형태의 프로그래밍을 의미함
* 이 때 객체를 만들어내기 위한 설계도와 같은 개념이 __클래스(Class)__





### 클래스(Class)

* 실세계의 것(사물)을 모델링하여 __속성(attribute)__ 와 __동작(method)__ 를 갖는 데이터 타입
  * Python에서의 string(문자열), int(정수), list(리스트), dict(딕셔너리) 등 모두 클래스로 존재함
    * ex) 학생이라는 클래스(class) 생성 → 학생을 나타내는 속성(attribute)과 학생이 행하는 행동(behavior)을 함께 정의할 수 있음
  * ∴ 다루고자 하는 __데이터(변수)__ 와 데이터를 다루는 __연산(함수)__ 를 하나로 캡슐화(encapsulation)하여 클래스로 표현
* 모델링에서 중요시하는 속성에 따라 _클래스의 속성과 행동이 각각 달라짐_
* 클래스의 예시
  * 차(car) : 설계도
  * 필드(field)
    * car.modelName
    * car.modelYear
    * car.color
    * car.maxSpeed
  * 메소드(method)
    * car.accelerate()
    * car.brake



### 클래스 선언

* 클래스 선언하기

  * 객체를 생성하기 위해서는 객체의 모체가 되는 클래스를 미리 선언해야 함

    ```python
    # class 클래스명 :
    	# 클래스 생성자
    	# 클래스 속성
    	# 클래스 메서드
        
    class Rectangle :
        count = 0  # 클래스 글로벌 속성
        
        def __init__(self, width, height) :  # 클래스 생성자
            self.width = width
            self.height = height
            Rectangle.count += 1
        
        def calcArea(self) :  # 클래스 메서드
            area = self.width * self.height
            return area
    ```

    

    

### 인스턴스(instance)

* 내 차(myCar) : 설계도에 의해 생산된 차량
* 친구 차(friendCar) : 설계도에 의해 생산된 또 다른 차량

![](C:\Users\LG Gram\Desktop/0005.jpg)



* 클래스를 사용 : 해당 클래스 타입의 _객체(object)_ 를 선언

* 클래스로부터 객체를 선언하는 과정 : 클래스의 __인스턴스화__

  * 선언된 해당 클래스 타입의 객체 = 인스턴스(instance)

    * 즉, 인스턴스란 메모리에 할당된 객체를 의미함

      `lis = list((3,5,7,9))  # lis 변수는 인스턴스 변수`

  * 하나의 클래스로부터 여러 개의 인스턴스 생성 가능

    ​	   `lis1 = list((1,2,3,4))`

  * 생성된 인스턴스는 독립된 메모리 공간에 저장된 _자신만의 필드_ 를 가질 수 있음

    ​       `lis.append(3)`



### 인스턴스 생성(Object  생성)

```python
객체명 = class명()  # 생성자 함수 호출
객체명 = class명(인수1, 인수2, ...)
list1 = list()
list2 = list([1,2,3])

# 클래스 정의
# name, age 2개의 속성을 정의 ㅡ 생성자 파라미터로 기본값 저장
class person :
    # 생성자 함수
    def __init__(self,name,age=10) :    # age는 기본값이 주어져 있음
        # self는 파라미터 대신 함수 내부에서만 사용하고. person 클래스 자체를 가리킴. 따라서 파라미터가 없는 상태임
        self.name = name
        self.age = age
        print(self, 'is generated')
    # 클래스 메서드 : sleep() ㅡ xxx는 잠을 잡니다 출력
    def sleep(self) :
        print('self :', self)
        print(self.name,'은 잠을 잡니다.')
        
# 객체 인스턴스 생성 및 사용
a = person('Aaron',20)
b = person('Bob',30)
print(a)
print(b)
a.sleep()
b.sleep()


# 클래스2 정의
# width, height 2개의 속성을 정의 ㅡ 기본값을 저장
class Rectangle :
    # 생성자 함수
    def __init__(self, width, height) :
        self.width = width
        self.height = height
    # 클래스 메서드 : calcArea() ㅡ 넓이를 계산해 반환
    def calcArea(self):
        area = self.width * self.height
        return area

# 객체 인스턴스 생성 및 사용
r_1 = Rectangle(10,30)
r_2 = Rectangle(3.5, 2.1)

print('면적 r_1 :', r_1.calcArea())
print('면적 r_2 :', r_2.calcArea())

```



* 생성자함수 :  `__init__(self)`

  * 생성자, 클래스 인스턴스가 생성될 때 호출됨

    * `rect1 = Rectangle()`  이 코드가 실행될 시 호출
    * `self` 인자는 항상 첫 번째에 오며, 자기 자신을 가리킴
    * 이름이 꼭 `self`일 필요는 없지만, 관례적으로 사용함

  * 생성자 함수에서는 해당 클래스가 다루는 데이터를 정의함

    * 이 데이터를 __멤버 변수(member variable)__ 또는 __속성(attribute)__ 라고 함

      

* 메서드(method) 정의

  * __멤버 함수__ 라고도 하며, 해당 클래스의 객체(object)에서만 호출 가능함

  * 메서드는 객체 레벨에서 호출되며, 해당 객체의 속성에 대한 연산을 진행함

  * `{obj}.{method}()` 형태로 호출됨

  * 함수 정의와 같으므로 필요 시 정의해서 사용

    * 메서드의 종류
      * __클래스 메서드__(Class method - static method)  ㅡ @staticmethod 사용
        * 클래스 레벨로 호출되기 때문에 _클래스 멤버 변수만_ 변경 가능
      * __객체(인스턴스) 메서드__(Instance method - 일반 메서드)
        * 객체 레벨로 호출되기 때문에, 해당 메서드를 호출한 객체에만 영향을 미침

    ```python
    # 클래스 메서드 : @staticmethod 키워드 사용
    # 클래스명.메서드 -> 접근 (객체 인스턴스를 만들지 않음)
    # 생성자 함수가 없으면 파이썬이 내부적으로 만들어 줌
    
    class Math :
        @staticmethod
        def add(a,b) :
            return a+b
    
        @staticmethod
        def multiply(a,b) :
            return a*b
    
    
    # 클래스 메서드 사용
    print('클래스 메서드로 접근 :', Math.add(10,20))
    print('클래스 메서드로 접근 :', Math.multiply(10,20))
    
    #
    m_obj = Math()
    print('객체(인스턴스) 메서드로 접근 :', m_obj.add(3,4))
    print('객체(인스턴스) 메서드로 접근 :', m_obj.multiply(3,4))
    ```

    

### Class Inheritance(상속)

* 기존에 정의해 둔 클래스의 기능을 그대로 물려받을 수 있

* 기존 클래스에 일부 기능을 추가하거나, 변경하여 새로운 클래스를 정의함

* 코드를 재사용할 수 있음

* 상속 받고자하는 대상인 기존 클래스는 __Parent/ Super / Base Class__ 라고 부름

  * 상속 받는 새로운 클래스는 __Child/ Sub/ Derived Class__ 라고 부름

    

* 메소드 오버라이드 (Method override)

  * 부모 클래스의 메서드를 재정의(override)
  * _하위 클래스(자식 클래스)의 인스턴스로 호출 시,_  재정의된 메서드가 호출됨

  ```python
  # 07_class_inheritance.py
  
  # super/부모/base 클래스
  class person :
      # 생성자 함수
      def __init__(self,name,age) :
          self.name = name
          self.age = age
  
      def eat(self, food) :
          print('{}은 {}를 먹습니다.'.format(self.name, food))
  
      def sleep(self, minute) :
          print('{}은 {}분 동안 잡니다'.format(self.name,minute))
  
      def work(self, minute) :
          print('{}은 {}분 동안 일합니다'.format(self.name,minute))
  
  # 상속 : class 클래스명(부모클래스명)
  
  # child 클래스 생성(Student, Employee)
  class Student(person) :   # student 클래스는 person이라는 클래스를 상속받는다
      def __init__(self,name,age):    # 생성자 함수 따로 만들기
          self.name = name
          self.age = age
  
  # 하위 클래스에서 부모 큻래스가 갖고 있는 함수(메서드)를 재정의 하는 것 = 메서드 오버라이드(method override)
      def work(self, minute) :
          print('{}은 {}분 동안 강의를 듣습니다'.format(self.name, minute))
  
  class Employee(person) :
      def __init__(self,name,age):    # 생성자 함수 따로 만들기
          self.name = name
          self.age = age
  
  bob = Employee('Bob', 25)
  bob.eat('BBQ')
  bob.sleep(30)
  bob.work(60)
  
  lee = Student('Lee',19)
  lee.eat('NOODLE')
  lee.sleep(60)
  lee.work(30)
  ```

  