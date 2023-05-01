## Index
---

- [기본 데이터 타입](#기본-데이터-타입)
- [상수형 데이터 타입](#상수형-데이터-타입)
- [형변환](#형변환)
- [명시적 형변환](#명시적-형변환)
- [연산자 우선순위](#연산자-우선순위)
- [비교와 bollean](#비교와-bollean)
- [배열](#배열)
- [for-each](#for-each)
- [public static void main (String[ ] args)](#public-static-void-main-string--args)
- [프로그램이 실행되는 동안 파라미터 입력받기](#프로그램이-실행되는-동안-파라미터-입력받기)

---

## 기본 데이터 타입

- 정수형 : byte, short, int, long
- 실수형 : float, double
- 문자 : char
- boolean : boolean
<br>

- 데이터 타입을 생성할 떄에 new 를 통해서 생성하는 것들은 기본 데이터 타입이 아닌 **참조형 데이터** 타입이라 부른다.
    - 기본 데이터 타입은 복제, 참조형 데이터 타입은 참조를 하기 때문에 참조 해온 데이터의 값을 바꾸면 오리지널 데이터 역시도 변경이 된다.
    - **복제** : 메모리 내의 데이터를 복사해서 나의 것을 갖는 것
    - **참조** : 데이터가 저장 된 위치의 메모리 주소만 건내 받는 것 ( 다른 인스턴스의 데이터에 접근 가능 )

## 상수형 데이터 타입

- JAVA 에서 정수는 int 실수는 double 를 기본으로 채택

    ```JAVA
        float a = 2.2;      // err
        float a = 2.2F;     // flaot 타입을 명시 해야한다
        double a = 2.2;     // 또는 double 사용

        long b = 214783648  // 정수 범위를 넘어가는 수를 정수로 표현하였기 때문에 에러 발생
        long b = 214783648L // long 타입을 명시해줌으로 에러 해결
    ```

## 형변환

- 자동 형 변환
    - 값의 유실이 될 수 있는 경우 형 변환 불가

    ```JAVA
        double a = 2.2F;    // double 형이 float 형 보다 더 큰 수를 표현하여 자동 형 변환
        float a = 2.2;      /* float 형이 double 형 보다 표현 가능한 수가 적어 
                                변환시 데이터 유실이 있을 수 있기 때문에 자동 형 변환 불가 */
        int a = 3.4;        /* 실수 3.4 가 정수 3으로 변환 시 
                                데이터 유실 되기 때문에 자동 형 변환 불가 */
    ```

## 명시적 형변환

- 데이터 타입을 명시 함으로 써 유실되는 데이터가 있더라도 명시한 데이터 타입으로 강제 변환을 해준다.

```JAVA
    int a = 2.2;        /* 변수의 데이터 int 가 double 보다  표현 가능한 데이터가 적어
                            자동 형 변환이 되지 않는다. */
    int a = (int)2.2;   /* int 타입을 명시 함으로 써 0.2 데이터를 잃은 채 int 2 라는 
                            데이터로 강제 변환하여 저장 */
```

## 연산자 우선순위

<img src="../../PIC/JAVA 기초/JAVA 연산자 우선순위.png">

## 비교와 Bollean

- 문자열 비교함수 equals

```JAVA
    String a = "Hello world";
    String b = new String("Hello world");

    System.out.println(a == b);      // false
    System.out.println(a.equals(b)); // true
```

## 배열

- 배열은 같은 데이터 타입끼리 묶는 것
- 다른 데이터 타입도 넣을 수 있는 Python 의 List 와는 다르다
- 문자열 배열 선언

```JAVA
    // 초기화
    String[] stringArray = { "a", "b", "c" };
    // stringArray[0] = "a"
    // stringArray[1] = "b"

    // 선언 후 데이터 추가
    String[] stringArray2 = new String[3];
    stringArray2[0] = "a";
    stringArray2[1] = "b";
```

- 배열의 크기
    - stringArray.length 를 실행 시 배열 안에 있는 데이터의 개수가 아닌 데이터를 담을 수 있는 배열 자체의 크기를 나타낸다

```JAVA
// 초기화
    String[] stringArray = new String[4];

    stringArray[0] = "a";
    System.out.println(stringArray.length); // 4

    stringArray[1] = "b";
    System.out.println(stringArray.length); // 4
     
    stringArray[2] = "c";
    System.out.println(stringArray.length); // 4

    stringArray[3] = "d";
    System.out.println(stringArray.length); // 4
```

## for-each

- 반복문을 통해 배열을 탐색 할 때에 더 간편하게 사용 할 수 있는 문법

``` JAVA
    String[] members = { "a", "b", "c" };
        for (String e : members) {
            System.out.println(e);
        }

    // a
    // b
    // c
```

## public static void main (String[ ] args)

- 함수명 **main** 은 약속된 이름의 함수로 JAVA를 실행하였을 때 시작점으로 main 을 찾아서 실행한다
<br/>

- **void** : return 값을 갖지 않는다
- **main( )** : 함수 이름은 main
- **String[ ] args** : main 함수의 파라미터로 변수명이 args 라는 문자열 배열을 입력 받는다

```JAVA
    public static void main(String[] args){
        System.out.println(args.length);    // 입력받은 파라미터( args ) 개수를 출력
    }
```

## 프로그램이 실행되는 동안 파라미터 입력받기

- Scanner 를 통해 실행 중인 프로그램이 키보드를 통해 파라미터가 입력 될 때까지 대기

```JAVA
    import java.util.Scanner;

    public class MyApp {
        public static void main(String[] args){
            Scanner sc = new Scanner(System.in);   // 입력 받을 Scanner 객체 생성
            int i = sc.nextInt();                  // 키보드로 값을 입력 할 때 까지 대기
            System.out.println("input: " + i);
            sc.close();
        }
}
```