# JAVA
> 이 글은 자문을 통해 작성되었습니다.
> 자문자 : [오시환](https://github.com/SHOM95)

> 출처
>
> MADE_BY: Sun Microsystems team led by James Gosling
>
> WHEN: 1991

## Java 의 핵심 특징
- 객체 지향 언어이다. (객체들끼리의 상호 작용에 의하여 프로그램이 구성됌)
- 호환성 갑: 모든 종류의 proecessor 에 대한 intermediate language (중간 언어) 인 Java byte-code 에 의하여 쉽고 작은 용량의 프로그램(자바 가상머신) 이 있다면 Java byte-code를 기계어로 변형 가능하다.
- application = 일반 프로그램.
  applet = html 과 비슷한 것. 인터넷상에서 여는것이 가능.
- 대소문자 구분
- 클래스 첫글자는 대문자로 / 변수, 메소드 첫글자는 소문자로
- 실행은 항상 main 메소드 ( main 함수 ) 를 찾아서 내부 내용을 순서대로 실행시킨다.
- 전역 변수가 없다.
- 포인터 개념이 없다. 대신 참조의 개념을 적극 활용한다.

## Compile 방식
- 자바는 우선적으로 모든 코드를 Java byte-code 로 코드를 한번에 컴파일 시킨다.
- 이 Java byte-code 를 자바가상머신이 main 함수 부분을 interpreter 방식으로 기계어로 변환시키며 실행한다.
- Class Loader 는 linker 와 같은 개념이다. 이를 통해 외부 클래스를 연결시킨다.
- 터미널를 활용한 컴파일
  - ` javac [file_name.java]`  : 컴파일 
  - `  java [file_name]`  : 실행 
  - ` javap`  : 디컴파일
- eclipse 의 경우 재생 버튼을 누르면 컴파일 및 실행이 된다.


## 자료형
자료형은 우리가 변수를 선언할 때 변수에 저장할 데이터의 종류를 결정해준다.

>  변수란 데이터를 저장하는 상자 같은 것이다.

- Java 의 자료형의 종류는 아래와 같다.

#### 1. primitive Types (기본자료형: 문자형, 숫자형, 논리형):

| 종류       | boolean | char | byte | short | int  | long | float | double |
| -------- | ------- | ---- | ---- | ----- | ---- | ---- | ----- | :----- |
| 크기(byte) | 1       | 2    | 1    | 2     | 4    | 8    | 4     | 8      |

- 기본 자료형은 메모리 크기가 다 정해져 있기 때문에 자동으로 메모리 공간을 확보해준다.

- 사용 예


```java
      int a; (초기화 안함)
      int b = 0; (초기화 함)
      int          a                =                    0          ;
  //  ---         ---              ---                  ---
//   자료형     변수명   오른쪽 값을 왼쪽에 저장한다.     정수형 값
```
#### 2. 참조 자료형: class, interface, 배열 등 (배열 또한 class type)

- class   =   객체를 생성하기 위한 설계도. C 의 구조체를 확장시킨 개념이다.

 (추가 설명은 아래에)

>   C의 구조체는 멤버 변수만을 갖지만, class 는 멤버 변수뿐만 아니라 멤버 함수도 갖는다.

- interface   =   객체를 생성할 수 없고, 상수와 추상메소드만을 쓸 수 있는 클래스(상속할수만 있음) (상속에 대한 설명은 아래에)

- 예시 

  ~~~java
  interface YejeHimdulda { // 타 인터페이스를 implement 할 수 있음.
  public abstract int itsHighNoon(int mokpyoNumber);
  }
  ~~~


- **추상 메소드**란 위와 같이 메소드 형태만을 적어 놓고 정의 부분은 쓰지 않은 메소드를 말한다. 상속시 반드시 이 메소드를 구현하도록 되어 있다.
- 일반적으로 class 를 생성시 클래스에 필히 포함되야 하는 메소드를 정해주기 위해 사용된다. 다른사람과 팀으로 협업할 때 좋은 기준이 된다.
- 배열    =   int[], char[] 등, 기본 자료형을 기초로 생성한다.
- 예를 들어 int[] 형 변수는 int 형 값 여러개를 나열하듯이 저장하고 있다.
- 참조 자료형의 경우 우리가 정의하는 것에 따라 메모리 크기가 다 달라지기 때문에 new 연산자를 통하여 메모리 공간을 코드에서 직접 확보해줘야한다. 선언 형태는 항상


 ```java
         Type     instance    =    new          Type('parameter');   // parameter = 매개변수
  //     ----     --------         ---          -----------------
  //    자료형   객체이름         new 연산자        생성자
 ```
 이런식으로 선언해준다.

> 이는 c++ 에서의 
>
> 	`포인터 = new 타입[(초기값)];`
>
> 과 사실상 거의 동일하다. 
>
> (밑에 생성자에 대해 설명되어 있다.) (참고: new 연산자란 메모리 할당용 연산자이다.)

- 사용 예:


```java
   public class Car {
        private int size;   // 멤버 변수 
        Car ( int size ){   // 생성자. Mutator 의 기능도 함께 함유.
            this.size = size;
        }
        public int getSize(){   // Accessor.
            return size;
        }
   }
```

 이와 같은 클래스가 정의 되어 있다고 하면, 메인 함수에서

```java
Car santafe = new Car(5); 
```

 라고 `size` 는 5이고 `santafe` 라는 이름을 가지고 있는 객체를 선언할 수 있다.
`Car santafe` 부분을 통하여 `santafe` 라는 인스턴스 (= 객체) 를 선언하고,
`= new Car(5);` 를 통하여 객체가 필요한 만큼의 공간을 적절히 확보하여 할당해준다. 또한 5 를 int 형 멤버변수 `size` 에 저장한다. 객체 선언과 동시에 멤버 변수 초기화를 같이 해준다고 보면 된다.



## Class 와 객체

1. 객체는 어떠한 성질을 가지고 있는 대상을 뜻한다.
2. Class 는 객체가 가질 성질을 정의하는 일종의 설계도이다.
```
일상에서 흔히 볼 수 있는 아무 대상이든지 다 객체이다. 예를 들어 샤프라는 객체는 특정 class 에 의하여 공장에서 형성이 
되고 (공장은 컴퓨터로 따지면 컴파일러의 기능 중 하나), 샤프심이라는 객체를 넣어 쓸 수 있는 기능을 가지고 있다. Java는
이러한 기능과 값을 가지고 있는 대상들(객체들)의 상호작용들을 일어난 순으로 실행시킨다. 즉, 우리가 코딩할 때 이 상호
작용의 순서를 정해나가는 것이라 할 수 있다.
```
객체의 구성요소는 모두 **클래스**에 의해 결정된다. 그렇다면 클래스의 구성요소가 될 수 있는 녀석들은 무엇이 있는가?

클래스에 기본적으로 다음 3가지 속성을 정의해 넣을 수 있다.

1. 멤버 변수 (값 저장 용도)
2. 메소드 (기능, 동작을 정의하는 용도)
3. 생성자 (*필수 포함 요소, 객체를 생성하는데 사용되는 특수한 메소드. return 이 없음)

위의 Car 클래스를 조금더 자세히 만들어 보고 main 함수에서 사용하면서 구조를 확인해보겠다.

```java
public class Car{

    private int size;   // 멤버 변수들
    private int speed;
    
    Car ( int size ){   // 생성자. Mutator 의 기능도 함께 함유.
        this.size = size;
        this.speed = 0;
    }
    public int getSize(){   
    // Accessor. Mutator 와 Accessor 에 대한 개념 설명은 아래에 있다.
        return size;
    }
    public void accel( int force ){
    // 자동차가 엑셀 밟으면 일어나는 기능을 간략화 한것.
        speed = speed + force;
    }

}
```

위와 같은 클래스가 정의 되어 있다고 했을 때, main 함수에서

```java
public static void main( char* argv[] ){
    Car car = new Car(10);

    for (int i = 0; i < 25; i++ ){  //25초 동안 엑셀 밟기
        car.accel(5);
    }
}
```
이런식으로 . 연산을 통하여 객체의 기능을 활용할 수 있다.

 *참고로 모든 클래스에는 반드시 하나 이상의 생성자가 있어야 한다.* 생성자를 정의하지 않았다고 해서 클래스에 생성자가 없는 것이 아니다. 모든 클래스는 생성자를 직접 정의하지 않았을 시에 기본 생성자를 이용하여 객체를 만들 수 있게 되있다.

위의 Car 클래스에 생성자가 없다고 가정해본다. 즉,

```java
	public class Car{
		// no ctor
	}
```
요렇게만 생겼다고 한다면,


```java
	 Car car = new Car();
     	         // -----
        	     // 기본 생성자
```

저런식으로 기본 생성자를 이용해서 정의할 수 있다.

## Accessor 와 Mutator 

위의 Car 클래스를 예시로 예시를 들어보겠다.

```java
Accessor:
    public void getSize(){
        return size;
    }
Mutator:
    public int setSize(){
        this.size = size;
    }
```
 위 예시에서 보는 것처럼, 특별한 개념이 있는게 아니라, 그냥 저런식으로 작동하는 getter 와 setter를 다른 용어로 Accessor, Mutator 라고 부른다.

## static 이란?

- static 의 사전 뜻
 
 " 정지하고 있는, 정적인, 움직임이 없는. "
- 프로그램에서 static 이 가지는 성질
  1. 정적 지속성
      static 으로 선언된 것은 일단 한번 생성이 되면 프로그램이 종료될 때까지 scope 에 영향을 받지 않고 항상 일정하다. (얘가 현재 구동되는 함수를 벗어나도 일정하다는 뜻이다. 다시 그 함수를 사용하면 전에 저장했던 값이 그대로 들어있다.)
  2. 유일성
      어떤 모듈 단위에서든지 static 객체는 단 한번만 생성된다.
  3. 내부 연결성
      전역 static 객체나 함수는 link 단계에서 외부 바인딩이 일어나지 않는다. (바인딩이란 변수나 함수에 속성을 결정짓는 것을 의미한다. 쉽게 말해 변수나 함수의 자료형, 범위, 값 등을 저장하는 과정을 말한다. 안드로이드의 `onBindViewHolder` 에서도 비슷한 의미이다.)

## Wrapper Class 와 primitive

 기본 자료형들을 class 화 시킨 것을 wrapper class 라고 한다. 예를 들어, int 자료형은 `Integer` 라는 클래스를 이용해서 변수를 만들 수 있다. 

 wrapper class 는 기본 자료형에 대하여 자주 쓰이는 기능들을 메소드화 시켜, 객체에 포함시키기 위해 만들어졌다. 또한, 기본 자료형으로 선언되는 기본 자료형 변수들을 객체화 시키기 위해서 사용하기도 한다. 

- Boxing, Unboxing

 기본 자료형을 wrapper class 화 시키는 것을 boxing 이라고 한다. 반대 과정을 unboxing 이라고 한다.

```java
    ex) Integer a = new Integer(5); //boxing
        Integer a = 5;  //auto boxing
        int b = a.intValue();   //unboxing
```
- Strings to Wrappers

 자료형 String 에서 wrapper class 로 형변환 가능하다.
```java
    ex) Integer.parseInt("42"); // Integer 형 42
```


## 상속 

 객체 지향의 핵심 개념 중 하나라고 하지만 정말 별거 없다. 상속하는 클래스는 부모 클래스, 상속 받은 클래스는 자식 클래스라 한다. 상속은 아래의 성질을 가지고 있다.

1.  한 클래스는 어떠한 클래스이든지 상속이 가능하며 상속 받을 수도 있다.
2.  한 클래스는 반드시 하나의 부모 클래스만을 갖는다. (다중 상속 불가능)
       즉, `public class Car extends A extends B{}`  이렇게 쓸 수 없다.


3. 한 클래스는 여러 자식 클래스를 가질 수 있다.
    즉, `public class Car{}` 이 있고, 상속받는 Hyundai 클래스와 Benz 클래스를 만들고 싶다면, 
   ```java
              public class Hyundai extends Car{}
              public class Benz extends Car{}
   ```
    이렇게 만들어도 된다는 뜻이다.

4. A라는 클래스가 B라는 클래스에게 상속을 받았다면, A 클래스로 형성한 객체는 B 클래스의 모든 성질을 갖고 있다. 여기에서 성질이란 멤버변수, 메소드들을 말한다. 
   단, private 이 붙어 있는 경우, 변수는 상속을 받으나 직접 접근이 불가능하며, 메소드는 상속되지 않는다.

5. 하위 클래스에서 `@Override` 를 통해 상위 클래스의 메소드를 재정의 할 수 있다.

6. 동일한 이름의 변수 혹은 동일한 형식의 메소드가 부모클래스와 자식클래스에 모두 존재하는 경우, 부모 클래스의 성질들은 가려진다.

7. 부모의 생성자는 자식에게 상속되지 않는다. 만일 부모 생성자의 성질을 가지고 오고 싶다면 super를 사용하여 생성자를 새로 생성해주면 된다.



## 접근 제어자와 static 
접근 제어자 기준

- `private`  : 외부 클래스에서의 접근이 불가능하다. (메소드, 변수 둘다 해당)
- `default`  : 접근 제어자에 아무것도 안쓴 상태로서, 동일 패키지 내의 클래스에서 접근 가능.
- `protected`  : 상속받은 클래스와 동일 패키지 클래스만 접근 가능.
- `public`  : 외부 클래스에서의 접근이 가능하다.

`static` 에 대하여 얘기를 해보자면, 기본적으로 static 이 붙으면 클래스 변수, 클래스 메소드 라고 한다. 왜냐하면 하나의 클래스 전체에서 공통된 메모리 주소로 공통된 값을 공유 하기 때문이다.

static 변수에 대한 작업을 하는 메소드는 무조건 static 이 붙어야 한다.  이와 달리 인스턴스 변수를 다루는 인스턴스 메소드의 경우 상황에 따라 변하는 값이 여러가지일 때 쓰는 것이 좋다.

참고로 인스턴스 메소드는 클래스에 대한 인스턴스를 생성해줘야만 사용 가능한 이유가 그 이름에 있다.

- static 메소드는 early-binding (컴파일시 연결)
- instance 메소드는 late-binding (실행시 연결)

late-binding 은 실행시에 클래스타입체크(RTTI) 를 통해서 결정되기 때문에 메소드를 찾을 때 시간이 더 오래걸린다. 

## Generics 와 Collection 과 Maps

**Generics** 란 `ArrayList<T>();` 에서 < > 의 기능 그 자체를 말한다. 저 꺽세 괄호 안에는 클래스 타입이 들어간다 (Object 형). < > 은 자료 종류가 무엇이든 간에 그 자료에 대하여 동일한 기능을 해주는 녀석을 정의할 때 사용된다. 예를 들어 `ArrayList<T>();` 의 경우, 배열과 매우 비슷한 놈인데 데이터로 들어갈 수 있는 데이터의 타입을 코딩할 때 < > 사이에 넣는 것만으로 결정할 수 있도록 해준다.

```java
ArrayList<Integer>();
ArrayList<String>();
ArrayList<Car>();
```
등, 서로 다른 자료형에 대하여 배열과 비슷하게 나열 형태로 해당 자료형의 데이터를 저장하는 기능을 수행한다.

**Collection** 과 **Maps** 는 Generics 를 활용하여 만들어진 자료를 그룹 형태로 묶어 저장하는 것들을 말한다. `ArrayList<T>();` 도 Collection 중 하나이다. Generics 를 활용하므로, 객체를 그룹 형태로 저장하는 것을 목적으로 만들어진 것들이라 할 수 있다. `ArrayList<T>();` 의 경우, Android 의 Recycler View 에서 필수 활용되므로 사용법을 잘 알아둘 필요가 있다.

 주의할 점은, 배열은 Collection 과 Maps 에 속해있지 않다. 배열은 int, char, float 같은 기본 자료형으로 정의된다. 기본 자료형만을 저장할 수 있는 배열은 참조 자료형인 클래스타입을 Generics 개념을 이용하여 만들어진  Collection 과 Maps 에 포함될 수 없다.




# ANDROID

## Recycler View

**Recycler View** 는 카톡 대화방이나 대화방리스트와 같이 데이터를 쭉 나열할 수 있는 기능을 가진 View 이다. 주로 `ArrayList<T>();` 를 사용하여 자료를 저장 및 나열을 한다.

- 구성요소:   (Adapter 와 LayoutManager 는 필수포함되야 recycler view 가 구동됨)
  1. Adapter  
     - ViewHolder  -   xml에서 만든 item 레이아웃(생긴형식)에 있는 뷰들을 자바 소스의 객체와 이어 모아 하나의 객체로 만들기 위한 클래스. 즉, 자바 소스에서 아이템 그 자체.
     - onCreateViewHolder  -   ViewHolder 의 객체를 생성해주는 함수. 데이터 저장을 하기 위한 아이템의 형태를 만들어 준다고 보면 된다.
     - onBindViewHolder    -   int position 번째 아이템에 들어갈 데이터를 저장해주는 함수.
  2. LayoutManager
      Recycler View 의 형태를 관리한다. 즉, 아이템들을 어떠한 형식으로 배치할지 결정해주는 녀석이다. 수평/수직/그리드 등, 다양한 형태의 배치가 가능하다.
  3. ItemDecoration
      각 아이템의 내용 양에 따른 크기 등 아이템을 꾸미는 작업을 한다.
  4. ItemAnimator 
      아이템에 특정 이벤트(추가, 삭제, 변경)가 발생할 때 보여줄 애니메이션을 관리한다.







> 이 자료는 이춘화 교수님의 OOP 자료와 구글 검색을 바탕으로 작성되었다.
> stackOverFlow 와 갓구글님께서는 모든 것을 알고 계신다네 ㅎㅎ.

> 주의: 삽질하면서 멘탈 으깨지다가 회복됬다가를 반복하게 될것임 (작성자포함 OTL).

> 갓구글로 떠납니다. (목표를 못찾겠다..)

> ctrl+space 짱짱. ctrl+space 짱짱. ctrl+space 짱짱.

# JAVA_notes

> 이 주석 아래로는 의식의 흐름 기법으로 정리한 것임.


#### 자바는 전역 변수가 없다! ( NO global variables instead, static variables!)

### 자바 
- 참조 자료형: class, interface, 배열
- 기본 자료형: char, byte, short, int, long, float, double, int, boolean (문자형, 숫자형, 논리형)


### JAVA 의 주요 정의들
- 객체의 정의: 변수들과 그와 관련된 메소드(method)들이 모여서 이룬 하나의 꾸러미. 객체는 클래스가 확장됨으로서 탄생한 변수의 확장인 녀석이다.
- 클래스의 정의: 클래스는 객체의 설계도.  클래스는 C의 구조체를 확장시킨 개념이다. 또한 자료형이다.
- 메소드의 정의: 기능
- 생성자의 정의: 인스턴스(=객체) 초기화 메소드
- new 연산자: 객체 동적할당 공간 생성 연산자.

### Accessor, Mutator

Accessor!

```java
public int getX(){
    return ~~;
}
```

Mutator!
```java
public void setX(int x){
    this.x = x;
}
```

this Parameter use ‘this’ 
trim() : erase white spaces

***

API란??

생성자에는 return 이 없다!!!

id 가 식별자.




### 접근 제어자 Static
- static method cannot refer to instance of the class (Cannot use ‘this’)
- Values of most data types require more than one byte of storage 
- A computer’s main memory can be thought of as a long list of memory locations of varying sizes.



### List

- 배열보다 강력한 List 이다. 우선 길이에 제한이 없고 (자동 동적할당), 모든 Class 에 대하여 List 를 사용할 수 있으니, 매우 효율적인 사용이 가능하다.

  ```java
  ArrayList or List<Class> = new List<>();
  ```



### Java & Pointer

- JAVA = no pointer : 참조를 사용하여 모든것을 조작함.  (객체 자체가 주소이면서 포인터인듯)




#ANDROID_notes

  생각해야 할 것

1. include layout vs fragment
   - include : 속한 activity 와 같은 생명 주기를 가지고 있음.
   - fragment : 독자적인 생명 주기를 가지고 있음.
2. 모든 res 파일은 대문자가 포함되선 안되고, 특수문자 역시 포함되면 안된다. 공백도 안된다.
3. button 의 OnClick 을 사용하는 방법은 3가지가 있다.
   - 버튼이 있는 xml 파일의 옵션에 OnClick 에 알맞는 method명 정의 후 해당 method 를 알맞는 액티비티에 구현 가능. (객체 사용 안함)
   - SetOnClickListener 인가? 를 implements 해줘서 사용하는 방법이 있다. 반드시 객체를 사용하게 된다.
   - 버튼 객체에 의한 setOnClickListener 를 이용하는 방법이 있다. 이것도 역시 객체를 사용한다.





##### 끝으로....

> 편집자 역 : 편집하다가 먼지가 되어 사라지겠다아아아아 뭐가이리 많아아아아
>
> [편집자1](https://github.com/PineApple777) : )
