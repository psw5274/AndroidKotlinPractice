* View
    * UI를 만드는데 사용되는 구성 요소
    * 화면에 보이는 모든 것은 뷰

* Widget
    * 사용자가 화면을 보면서 상호작용 하는 뷰
    * 모든 위젯은 View 클래스의 인스턴스이거나 View의 서브 클래스 인스턴스

* ViewGroup
    * 다른 뷰를 포함하고 배치하여 화면에 보여주지만 자신은 보이지 않는 뷰
    * 레이아웃

* View Hierarchy
    * 모든 뷰를 계층 구조로 표현한 것

* 위젯 속성
    * android:layout_width, layout_height
        * match_parent  : 부모 만큼의 크기를 가짐
        * wrap_content  : 자신의 컨텐츠에 필요한 크기가 됨
    * android:orientation
        * 자식을 vertical로 나타낼지 horizontal로 나타낼지 정함
    * android:text
        * 위젯 텍스트 설정

* 문자열 리소스
    * strings.xml 내에서 정적으로 문자열 리소스 선언
    * <string name="my_string">HELLO_WORLD</string>

* 레이아웃 xml -> 뷰 객체 생성
    * Activity.setContentView(layoutResID: Int)
    * 위 함수로 레이아웃을 inflate 하여 생성
        * inflate : 뷰 계층 구조에 따라 뷰들을 객체로 생성하는 것

* 리소스 ID
    * android:id="@+id/true_button"
    * text와는 다르게 id를 생성하기 때문에 +가 들어감

* 리스너
    * 안드로이드 앱은 event driven 으로 구동
    * 이벤트를 기다리는 것을 리스닝, 이러한 객체를 리스너
    * 리스너는 해당 이벤트의 '리스너 인터페이스'를 구현
        * Button 위젯의 setOnClickListener에 OnClickListener를 구현하여 등록
        * 보통 람다식을 통해 바로 등록한다
        ```kotlin
            Button.setOnClickListener { view: View ->
                // do something...
            }
        ```
      
    * SAM (Single Abstract Method) (functional interface)
        * 단일 추상 메소드
        * 하나의 추상 메소드를 갖는 인터페이스
        ```java
      
      public interface Callable<T> {
          public T call();
      }
      
      @FunctionalInterface
      public interface ArithmeticOperator {
          public int operate(int a, int b);
      }
        ```
        
    * SAM 변환
        * SAM 생성자는 컴파일러가 람다식을 자바의 functional interface로 자동으로 변환하게함
        * 인터페이스를 매개변수로 받는 함수에 대해 인터페이스 대신 함수를 전달할 수 있게 함
        (https://beomseok95.tistory.com/92)
        ```kotlin
        button.setOnClickListener({ v: View ->
            Unit
            // TODO
        })
        button.setOnClickListener {
            // TODO
        }
        ```
    