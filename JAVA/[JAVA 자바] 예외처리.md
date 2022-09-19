# 에러 종류

### [](https://github.com/Chan-Pumpkin/Tech_TIL/blob/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_1_%EC%98%88%EC%99%B8%EC%B2%98%EB%A6%AC.md#%EC%BB%B4%ED%8C%8C%EC%9D%BC-%EC%97%90%EB%9F%AC)컴파일 에러

컴파일 시에 발생하는 에러

컴파일 에러 없이 성공적으로 마쳤어도, 실행도중에 발생할 수 있는 잠재적인 오류까지 검사할 수 없기 때문에 에러에 의해서 잘못된 결과를 얻거나 프로그램이 비정상적으로 종료될 수 있다.

### [](https://github.com/Chan-Pumpkin/Tech_TIL/blob/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_1_%EC%98%88%EC%99%B8%EC%B2%98%EB%A6%AC.md#%EB%9F%B0%ED%83%80%EC%9E%84-%EC%97%90%EB%9F%AC)런타임 에러

실행 시에 발생하는 에러

예를 들면, 실행 중 동작을 멈춘 상태로 오랜 시간을 지속하는 경우 또는 프로그램이 실행을 멈추고 종료되는 경우

### [](https://github.com/Chan-Pumpkin/Tech_TIL/blob/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_1_%EC%98%88%EC%99%B8%EC%B2%98%EB%A6%AC.md#%EB%85%BC%EB%A6%AC%EC%A0%81-%EC%97%90%EB%9F%AC)논리적 에러

실행은 되지만, 의도와 다르게 동작하는 것.

# [](https://github.com/Chan-Pumpkin/Tech_TIL/blob/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_1_%EC%98%88%EC%99%B8%EC%B2%98%EB%A6%AC.md#%EC%97%90%EB%9F%AC%EC%99%80-%EC%98%88%EC%99%B8-%EC%B0%A8%EC%9D%B4)에러와 예외 차이

### [](https://github.com/Chan-Pumpkin/Tech_TIL/blob/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_1_%EC%98%88%EC%99%B8%EC%B2%98%EB%A6%AC.md#%EC%97%90%EB%9F%AC-1)에러

프로그램 코드에 의해서 수습될 수 없는 심각한 오류

### [](https://github.com/Chan-Pumpkin/Tech_TIL/blob/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_1_%EC%98%88%EC%99%B8%EC%B2%98%EB%A6%AC.md#%EC%98%88%EC%99%B8)예외

프로그램 코드에 의해서 수습될 수 있는 다소 미약한 오류

적절한 코드를 미리 작성해 놓음으로서, 프로그램의 비정상적인 종료를 막을 수 있음.

# [](https://github.com/Chan-Pumpkin/Tech_TIL/blob/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_1_%EC%98%88%EC%99%B8%EC%B2%98%EB%A6%AC.md#%EC%98%88%EC%99%B8-%ED%81%B4%EB%9E%98%EC%8A%A4%EC%9D%98-%EA%B3%84%EC%B8%B5%EA%B5%AC%EC%A1%B0)예외 클래스의 계층구조

[##_Image|kage@3WtT1/btrMrw0wRr9/ABucaLKvfnPNwqDuknAICk/img.png|CDM|1.3|{"originWidth":346,"originHeight":243,"style":"alignCenter"}_##]

출처 : [https://docs.oracle.com/javase/tutorial/essential/exceptions/throwing.html](https://docs.oracle.com/javase/tutorial/essential/exceptions/throwing.html)

### [](https://github.com/Chan-Pumpkin/Tech_TIL/blob/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_1_%EC%98%88%EC%99%B8%EC%B2%98%EB%A6%AC.md#error-class)Error class

Java 가상 머신에서 동적 연결 실패 or 기타 하드 장애가 발생하면 가상 머신에서 Error 발생하며, 단순 프로그램은 일반적으로 catch하거나 throw 하지 않는다.

### [](https://github.com/Chan-Pumpkin/Tech_TIL/blob/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_1_%EC%98%88%EC%99%B8%EC%B2%98%EB%A6%AC.md#exception-class)Exception class

-   심각한 시스템 문제는 아님
-   주로 외부 영향으로 발생할 수 있는 것들로, 프로그램의 사용자들의 동작에 의해서 발생하는 경우가 많음.
-   FileNotFoundException, classNotFoundException, DataFormatException

### [](https://github.com/Chan-Pumpkin/Tech_TIL/blob/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_1_%EC%98%88%EC%99%B8%EC%B2%98%EB%A6%AC.md#runtimeexception-class)RuntimeException class

-   주로 개발자 실수에 의해서 발생될 수 있는 예외
-   ArrayIndexOutOfBoundException, NullPointerException, ClassCastException, ArithmeticException

## [](https://github.com/Chan-Pumpkin/Tech_TIL/blob/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_1_%EC%98%88%EC%99%B8%EC%B2%98%EB%A6%AC.md#%EC%98%88%EC%99%B8%EC%B2%98%EB%A6%AC)예외처리

### [](https://github.com/Chan-Pumpkin/Tech_TIL/blob/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_1_%EC%98%88%EC%99%B8%EC%B2%98%EB%A6%AC.md#%EC%A0%95%EC%9D%98)정의

프로그램 실행시 발생할 수 있는 예외에 대비한 코드를 미리 작성하는 것

### [](https://github.com/Chan-Pumpkin/Tech_TIL/blob/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_1_%EC%98%88%EC%99%B8%EC%B2%98%EB%A6%AC.md#%EB%AA%A9%EC%A0%81)목적

프로그램이 비정상 종료를 막고, 정상적인 실행 상태 유지

# [](https://github.com/Chan-Pumpkin/Tech_TIL/blob/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_1_%EC%98%88%EC%99%B8%EC%B2%98%EB%A6%AC.md#%EC%B0%B8%EA%B3%A0)참고

-   오라클 공식문서 : [https://docs.oracle.com/javase/tutorial/essential/exceptions/index.html](https://docs.oracle.com/javase/tutorial/essential/exceptions/index.html)
-   자바의 정석 3rd Edition
