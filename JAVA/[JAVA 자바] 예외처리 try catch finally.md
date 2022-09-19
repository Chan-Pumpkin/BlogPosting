![CatchMe](https://user-images.githubusercontent.com/62877858/191021433-1109e5bb-6ead-4fd2-8dda-f57bab5ced7f.png)

## **try문**

-   예외 발생할 가능성이 있는 코드 문장을 try문 안에 넣는다.
-   try 블록 내에서 예외가 발생하면 해당 예외가 연결된 예외 처리기에 의해 처리가 된다.
-   예외 처리기를 try문과 연결하려면, try문 뒤에 catch문을 작성해줘야 함.

```
try {
    //code
}
//catch and finally blocks . . .
```

## [](https://github.com/Chan-Pumpkin/Tech_TIL/edit/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_2_try,catch,finally.md#catch%EB%AC%B8)**catch문**

-   try문 바로 뒤에 하나 이상의 catch문을 제공하여 예외 처리기를 try문과 연결할 수 있다.
-   어떠한 코드도 try문의 끝과 첫 번째 catch문의 시작 사이에 있을 수 없다.
-   처리기가 처리할 수 있는 예외 유형을 선언하며, Throwable클래스로부터 상속하는 클래스의 이름이어야 함.
-   예외 처리기는 오류 메시지를 인쇄하거나 프로그램을 중지하는 것 이상의 작업을 수행할 수 있습니다.

```
try {

} catch (ExceptionType name) {

} catch (ExceptionType name) {

}
```

### [](https://github.com/Chan-Pumpkin/Tech_TIL/edit/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_2_try,catch,finally.md#%EC%98%88%EC%8B%9C)**예시**

```
try {

} catch (IndexOutOfBoundsException e) {
    System.err.println("IndexOutOfBoundsException: " + e.getMessage());
} catch (IOException e) {
    System.err.println("Caught IOException: " + e.getMessage());
}
```

## [](https://github.com/Chan-Pumpkin/Tech_TIL/edit/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_2_try,catch,finally.md#printstacktrace-getmessage)**printStackTrace(), getMessage()**

### **[](https://github.com/Chan-Pumpkin/Tech_TIL/edit/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_2_try,catch,finally.md#printstacktrace)printStackTrace()**

예외발생 당시의 호출스택(Call Stack)에 있었던 메서드의 정보와 예외 메시지를 화면에 출력한다.

### [](https://github.com/Chan-Pumpkin/Tech_TIL/edit/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_2_try,catch,finally.md#getmessage)**getMessage()**

발생한 예외클래스의 인스턴스에 저장된 메시지를 얻을 수 있음.

## [](https://github.com/Chan-Pumpkin/Tech_TIL/edit/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_2_try,catch,finally.md#%EB%A9%80%ED%8B%B0-catch-%EB%B8%94%EB%9F%AD)**멀티 catch 블럭**

JAVA SE 7이상에서 하나의 catch문이 둘 이상의 예외 유형을 처리할 수 있다.

-   vertical bar | 로 각 예외 유형을 구분함.
-   vertical bar | 로 연결할 수 있는 예외 클래스의 개수에는 제한이 없다.

```
catch (IOException|SQLException ex) {
    logger.log(ex);
    throw ex;
}
```

## [](https://github.com/Chan-Pumpkin/Tech_TIL/edit/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_2_try,catch,finally.md#%EB%A9%80%ED%8B%B0-catch-%EB%B8%94%EB%9F%AD-%EC%A3%BC%EC%9D%98%EC%82%AC%ED%95%AD)**멀티 catch 블럭 주의사항**

멀티 catch블럭 | 을 예외 클래스가 조상과 자손의 관계가 있는 예외를 연결하면 컴파일 예러가 발생함.

두 예외 클래스가 조상과 자손의 관계라면, 조상 클래스만 써주는 것이 맞다.

```
try{
	...
} catch(ParentException | childException e) { //에러 발생
	...
}
```

## **finally 블럭**

> try 또는 catch 문이 실행되는 동안 JVM이 종료되면, finally문은 실행되지 않을 수 있다.  
> 출처 : oracle 공식문서

-   항상 try문이 종료될 때 실행됨.
-   예외가 발생한 경우 try→catch→finally 순으로 실행됨.
-   예외가 발생하지 않은 경우 try→finally의 순으로 실행됨.

### [](https://github.com/Chan-Pumpkin/Tech_TIL/blob/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_2_try,catch,finally.md#try-finally)**try->finally**

예외가 발생하지 않아서, catch를 지나지 않아서 바로 finally로 간다.

```
public class testExceptionClass {
    public static void main(String[] args) {
        try {
            System.out.println("Try");
        } catch(Exception e) {
            System.out.println("Catch");
        } finally {
            System.out.println("Finally");
        }
    }
}
```

### [](https://github.com/Chan-Pumpkin/Tech_TIL/blob/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_2_try,catch,finally.md#try-catch-finally)**try->catch->finally**

try문안에서 throw new Exception(); 로 강제로 예외를 발생시켰기 때문에, catch문에 갔다가 finally로 간다.

```
public class testExceptionClass {
    public static void main(String[] args) {
        try {
            System.out.println("Try");
            throw new Exception();
        } catch(Exception e) {
            System.out.println("Catch");
        } finally {
            System.out.println("Finally");
        }
    }
}
```

## [](https://github.com/Chan-Pumpkin/Tech_TIL/blob/master/Java/%EC%9E%90%EB%B0%94%EC%9D%98%EC%A0%95%EC%84%9D/8_2_try,catch,finally.md#%EC%B0%B8%EA%B3%A0)**참고**

-   오라클 공식문서 [https://docs.oracle.com/javase/tutorial/essential/exceptions/index.html](https://docs.oracle.com/javase/tutorial/essential/exceptions/index.html)
-   자바의 정석 3rd Edition
