## DATE: 221216
---
## index
- [상수형 데이터 타입](#상수형-데이터-타입)
- [형변환](#형변환)
- [명시적 형변환](#명시적-형변환)
- [연산자 우선순위](#연산자-우선순위)
- [비교와 bollean](#비교와-bollean)
- [배열](#배열)

### 상수형 데이터 타입

- JAVA 에서 정수는 int 실수는 double 를 기본으로 채택

    ```JAVA
        float a = 2.2; // err
        float a = 2.2F; // flaot 타입을 명시 해야한다
        double a = 2.2; // 또는 double 사용

        long b = 214783648 // 정수 범위를 넘어가는 수를 정수로 표현하였기 때문에 에러 발생
        long b = 214783648L // long 타입을 명시해줌으로 에러 해결
    ```

### 형변환

- 자동 형 변환
    - 값의 유실이 될 수 있는 경우 형 변환 불가

    ```JAVA
        double a = 2.2F; // double 형이 float 형 보다 더 큰 수를 표현하여 자동 형 변환
        float a = 2.2; /* float 형이 double 형 보다 표현 가능한 수가 적어 
                        변환시 데이터 유실이 있을 수 있기 때문에 자동 형 변환 불가 */
        int a = 3.4; /* 실수 3.4 가 정수 3으로 변환 시 
                        데이터 유실 되기 때문에 자동 형 변환 불가 */
    ```

### 명시적 형변환

- 데이터 타입을 명시 함으로 써 유실되는 데이터가 있더라도 명시한 데이터 타입으로 강제 변환을 해준다.

```JAVA
    int a = 2.2 /* 변수의 데이터 int 가 double 보다  표현 가능한 데이터가 적어
    자동 형 변환이 되지 않는다. */
    int a = (int)2.2; /* int 타입을 명시 함으로 써 0.2 데이터를 잃은 채 int 2 라는 데이터로
    강제 변환하여 저장 */
```

### 연산자 우선순위

<img src="../PIC/JAVA 연산자 우선순위.png">

### 비교와 Bollean

- 문자열 비교함수 equals

```JAVA
    String a = "Hello world";
    String b = new String("Hello world");

    System.out.println(a == b);      // false
    System.out.println(a.equals(b)); // true
```

### 배열

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

