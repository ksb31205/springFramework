# Table of contents

- [JavaScript 기본 문법](#JavaScript-기본-문법)
  - [변수](#변수)
  - [연산자](#연산자)
  - [자료형](#자료형)
  - [조건문](#조건문)
  - [반복문](#반복문)
  - [예외 처리문](#예외-처리문)
  - [Promises](#Promises-★★★★★)
  - [문자열 처리](#문자열-처리)
  - [함수](#함수)

- [DOM(Document Object Model)](#DOM(Document-Object-Model))
  - [DOM이란?](#DOM이란?)
  - [관련 함수들](#관련-함수들)

<br/>

---



# JavaScript 기본 문법

- ### 변수

  - 변수는 var, let, const 등의 키워드로 선언 가능

    ```javascript
    var a = 2;
    var a = "aaa";
    var a = 'aaa';
    var a = true;
    var a = [];
    var a = {};
    var a = undefined;
    ```

  <br/>

- ### 연산자

  - #### 삼항연산자

    - 간단한 비교와 값 할당은 삼항연산자를 사용

      ```javascript
      const data = 11;
      const result = (data > 10) ? "ok" : "fail";
      console.log(result);
      ```

      <br/>

  - #### 비교연산자

    - `==`와 `===`이 있음

    - `==`로 인한 다양한 오류 상황이 있기 때문에, 비교할 때는 `==`보다는 `===`을 사용

    - `==`sms 

      ex) 오류 상황 예시

      ```javascript
      0 == false;			// true
      "" == false;		// true
      null == false;		// false
      0 == "0";			// true
      0 === "0";			// false
      null == undefined;	// true
      ```

      <br/>

- ### 자료형

  - 자바스크립트의 자료형에는 다양한 것이 존재함

    ```javascript
    undefined, null, boolean, number, string, object, function, array, Date, RegExp
    ```

  - 자료형은 선언할 때가 아닌, 실행 타임에 따라 결정됨
  - 자료형을 체크하는 또렷한 방법은 없음. 정확히는 **toString.call** 을 이용해서 그 결과를 매칭하곤 하는데, 문자 및 숫자와 같은 기본 자료형은 **typeof** 키워드를 사용하여 체크함
  - 배열의 경우 자료형을 체크하는 **isArray** 함수가 표준으로 존재함. 단, 브라우저 지원 범위를 살펴보고 사용해야 함

  <br/>

- ### 조건문

  - #### if....else문

    ```javascript
    if (condition_1) {
      // statement_1;
    } else if (condition_2) {
      // statement_2;
    } else if (condition_n) {
      // statement_n;
    } else {
      // statement_last;
    } 
    ```

  - #### 거짓으로 취급하는 값

    ```javascript
    false, undefined, null, 0, NaN, ""
    ```

  - #### switch문

    ```javascript
    switch (expression) {
      case label_1:
        // statements_1
        break;
      case label_2:
        // statements_2
        break;
        ...
      default:
        // statements_def
        break;
    }
    ```

  <br/>

- ### 반복문

  - #### for문

    ```javascript
    for([초기문]; [조건문]; [증감문]) {
    	// statements;
    }
    
    for(variable in object)	// 인덱스를 다룸
        // statements;
        
    for(variable of object)	// 값을 다룸
        // statements;
    ```

  - do...while문

  - while문

    <br/>

- ### 예외 처리문

  - #### throw, try...catch, finally문

    ```javascript
    try {
      throw "myException" // generates an exception
    }
    catch (e) {
      // statements to handle any exceptions
      logMyErrors(e) // pass exception object to error handler
    } finally {
        console.log("finish");
    }
    ```

  <br/>

- ### Promises ★★★★★

  - ECMAScript2015를 시작하면서, 자바스크립트는 지연된 흐름과 비동기식의 연산을 제어할 수 있게 하는 [`Promise`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Promise) 객체에 대한 지원을 얻게 되었음

  <br/>

  - #### Promise 상태의 종류

    - *pending* : 초기상태, fulfilled 되거나 rejected 되지 않음
    - *fulfilled* : 연산 수행 성공
    - *rejected* : 연산 수행 실패
    - *settled* : Promise 가 fulfilled 이거나 rejected 이지만 pending 은 아님

    <br/>

    ![img](https://mdn.mozillademos.org/files/8633/promises.png)
  
  - 강의 링크
    
    - https://joshua1988.github.io/web-development/javascript/promise-for-beginners/

<br/>

- ### 문자열 처리

  - 문자와 문자열은 같은 자료형으로, 모두 문자열임

    ```javascript
    typeof "abc";
    typeof "a";
    typeof 'a';
    
    "ab:cd".split(":");
    "ab:cd".replace(":", "$");
    "  abcde  ".trim();
    ```

<br/>

- ### 함수

  - JavaScript에서 별도의 return문을 작성하지 않는다면 함수의 기본 반환값은 **undefined**임

    ```javascript
    function foo() {
    	// statements;
    }
    ```

  - #### 함수표현식

    - 어떤 코드 안에서 함수 기본선언식 또는 함수표현식 둘 중 하나만 정해서 사용하는 것이 좋음

    ```javascript
    var foo = function() {
    	// statements;
    }
    ```

  - #### arguments 객체

    - 함수가 실행되었을 때 그 안에 생성되는 특별한 지역변수

    ```javascript
    function foo() {
    	console.log(arguments);
    }
    
    foo(1, 2, 3);
    ```

  - #### arrow 함수

    ```javascript
    function getName(name) {
       return "Kim " + name ;
    }
    
    //위 함수는 아래 arrow함수와 같다.
    var getName = (name) => "Kim " + name;
    ```

  - #### 콜백 함수

    - 함수 내에서 어떤 특정한 시점에 호출되는 함수

    - 어떤 이벤트에 의해 호출되는 함수

    - 다른 함수의 인자로서 이용되는 함수

    - 비동기 처리 : 특정 코드의 연산이 끝날 때까지 멈춰있지 않고 다음 코드를 먼저 실행하는 JavaScript의 특성

    - ##### 일반적인 함수

      ```javascript
      function plus(a, b) {
      	var sum = a + b;
      		return sum;
      }
      
      function print(result) {
      	console.log(result);
      }
      
      print(plus(1,2));
      ```

    - ##### 콜백 함수

      ```javascript
      function plus(a, b, callback) {
      	var sum = a + b;
      	callback(sum);
      }
      
      plus(1, 2, function(result) {
      	console.log(result);
      })
      ```

      ex)

      ```javascript
      function run() {
          console.log("start");
          setTimeout(function() {
              var msg = "hello codesquad";
              console.log(msg);  //이 메시지는 즉시 실행되지 않습니다.
          }, 1000);
          console.log("end");
      }
      
      run();
      ```

      ```
      start
      end
      hello codesquad
      ```

      

    - #### 콜백 함수를 쓰는 이유

      - 함수의 과정이 끝나기 전에 다음 프로세스를 진행해야 하는 경우가 있을 때, 해당 함수의 과정이 끝날 때까지 모든 작업이 멈춰버리는 현상이 발생할 수 있기 때문
      
        <br/>
    
    - #### 기본적인 콜백 함수들
    
      - setInterval : 특정 동작을 반복적으로 수행하기 위해 쓰임
      - setTimeout : 특정 동작을 다른 동작이 끝난 후 처리하기 위해 쓰임

<br/>

---



# DOM(Document Object Model)

<br/>

![img](https://cphinf.pstatic.net/mooc/20180126_280/1516956194218XFPk5_PNG/2-2-2_Dom_tree.png)

<br/>

- ### DOM이란?

  - HTML 코드를 트리 형태로 구성한 것
  - 웹브라우저에서는 HTML 코드를 DOM이라는 객체 형태의 모델로 저장함
  - 텍스트 파일로 만들어져 있는 웹 문서를 브라우저에 렌더링하려면 웹 문서를 브라우저가 이해할 수 있는 구조로 메모리에 올려야 한다. 브라우저의 렌더링 엔진은 웹 문서를 로드한 후, 파싱하여 웹 문서를 브라우저가 이해할 수 있는 구조로 구성하여 메모리에 적재하는데 이를 DOM이라 한다.
  - 웹브라우저에서는 다양한 DOM API를 제공함

<br/>

- ### 관련 함수들

  - **getElementById()**

    - id를 통해 값을 찾는 함수. 문서 내에 주어진 ID가 없으면 null을 반환
    - 찾으려는 id는 대소문자를 구분하며, 문서 내에서 유일해야 함

    ```html
    <html>
    <head>
      <title>getElementById 예제</title>
    </head>
    <body>
      <p id="para">어떤 글</p>
      <button onclick="changeColor('blue');">blue</button>
      <button onclick="changeColor('red');">red</button>
    </body>
    </html>
    ```

    ```javascript
    function changeColor(newColor) {
      var elem = document.getElementById('para');
      elem.style.color = newColor;
    }
    ```

  - **getElementsByName()**

  - **getElementsByTagName()**

  - **getElementsByClassName()**

    ※ 위 세 함수들은 값을 배열로 반환함

  - **element.querySelector()**

    - CSS 스타일의 선택자를 통해 값을 찾아내는 함수

      ex1)

      ```html
      <div id="app"></div>
      ```

      ```javascript
      document.getElementById("app")
      document.querySelector("#app")
      ```

      ex2)

      ```html
      <div class="container"></div>
      ```

      ```javascript
      document.getElementsByClassName("container")
      document.querySelector(".container")
      ```

  - 기타 함수들
    - `document.createElement(name)`
    - `parentNode.appendChild(node)`
    - `element.innerHTML`
    - `element.style.left`
    - `element.setAttribute`
    - `element.getAttribute`
    - `element.addEventListener`
    - `window.content`
    - `window.onload`
    - `window.dump`
    - `window.scrollTo`

<br/>

# Events

- ### Event란?

  - 키보드 또는 마우스 등을 통하는 특정 행위
  - 화면 크기 조절, 버튼 클릭, 마우스 스크롤 등

<br/>

- ### 자주 쓰이는 Event 목록

  | 이벤트    | 설명                                     |
  | --------- | ---------------------------------------- |
  | change    | 변동이 있을 때 발생                      |
  | click     | 클릭 시 발생                             |
  | focus     | 포커스를 얻었을 때 발생                  |
  | keydown   | 키를 눌렀을 때 발생                      |
  | keyup     | 키에서 손을 뗐을 때 발생                 |
  | load      | 로드가 완료되었을 때 발생                |
  | mousedown | 마우스를 클릭했을 때 발생                |
  | mouseout  | 마우스가 특정 객체 밖으로 나갔을 때 발생 |
  | mouseover | 마우스가 특정 객체 위로 올려졌을 때 발생 |
  | mousemove | 마우스가 움직였을 때 발생                |
  | mouseup   | 마우스에서 손을 뗐을 때 발생             |
  | select    | option 태그 등에서 선택을 했을 때 발생   |

  <br/>

- ### Event 등록 방법

  ```javascript
  // 방법 1
  var el = document.getElementById("myId");
  el.addEventListener("click", btnAlert);
  
  function btnAlert() {
  	alert("메세지");
  }
  ```

  ```javascript
  // 방법 2
  var el = document.getElementById("myId");
  el.addEventListener(function(){
  	alert("메세지");
  })
  
  ```

  

# Ajax(Asynchronous Javascript And Xml)

- ### Ajax란?

  - JavaScript의 라이브러리 중 하나. "비동기식 자바스크립트와 xml"의 약자
  - JavaScript를 사용한 비동기 통신, 클라이언트와 서버 간에 XML 데이터를 주고받는 기술
  - 브라우저 새로고침 없이 서버로부터 데이터를 받아와 보여주는 기술
  - 브라우저가 가지고 있는 XMLHttpRequest 객체를 이용해서 전체 페이지를 새로 고치지 않고도 페이지의 일부만을 위한 데이터를 로드하는 기법
  - 원래는 웹페이지의 일부 내용을 갱신하기 위해서라도 페이지 전체를 갱신해야 했는데, ajax를 사용하면 JSON이나 XML의 형태로 필요한 데이터만 받아 갱신하기 때문에 그만큼 자원과 시간을 아낄 수 있음

  #### ※ 기본 실행 코드

  ```javascript
  function ajax(data) {
   var oReq = new XMLHttpRequest();
   oReq.addEventListener("load", function() {
     console.log(this.responseText);
   });    
   oReq.open("GET", "http://www.example.org/getData?data=data"); //parameter를 붙여서 보낼수있음. 
   oReq.send();
  }
  ```

  <br/>



# JSP(Java Server Page)

- ### JSP란?

  - 동적 웹페이지를 만드는데 사용되는 자바의 표준 웹프로그래밍 기술

  - 겉보기에는 HTML 문서와 비슷하나, 내부적인 실행은 Servlet으로 변환되어 돌아감

  - HTML 문서 안에 자바 코드가 삽입되는 구조

    <br/>

  #### ※ 예제 코드

  - JSP 예제

      ```jsp
      <%@ page language="java" contentType="text/html; charset=UTF-8"
          pageEncoding="UTF-8"%>
      <!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
      <html>
      <head>
      <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
      <title>sum10</title>
      </head>
      <body>

      <% 
          int total = 0;
          for(int i = 1; i <= 10; i++){
              total = total + i;
          }
      %>

      1부터 10까지의 합 : <%=total %>

      </body>
      </html>
      ```
  - JSP가 Servlet으로 변환된 것
  
    ```java
    ​```java
        public void _jspInit() {
        }
    
          public void _jspDestroy() {
        }
    
          public void _jspService(final javax.servlet.http.HttpServletRequest request, final javax.servlet.http.HttpServletResponse response)
            throws java.io.IOException, javax.servlet.ServletException {
    
          .....
    
            try {
            .....
    
              out.write("\n");
              out.write("<!DOCTYPE html PUBLIC \"-//W3C//DTD HTML 4.01 Transitional//EN\" \"http://www.w3.org/TR/html4/loose.dtd\">\n");
              out.write("<html>\n");
              out.write("<head>\n");
              out.write("<meta http-equiv=\"Content-Type\" content=\"text/html; charset=UTF-8\">\n");
              out.write("<title>sum10</title>\n");
              out.write("</head>\n");
              out.write("<body>\n");
            out.write("\n");
    
          int total = 0;
          for(int i = 1; i <= 10; i++){
              total = total + i;
        }
    
              out.write("\n");
              out.write("\n");
              out.write("1부터 10까지의 합 : ");
              out.print(total );
              out.write("\n");
              out.write("\n");
              out.write("</body>\n");
              out.write("</html>");
            } catch (java.lang.Throwable t) {
              .....
              }
            } finally {
              _jspxFactory.releasePageContext(_jspx_page_context);
            }
          }
    ```
  
  <br/>
  
- ### JSP 실행 순서

  - 브라우저가 웹서버에 JSP에 대한 요청 정보를 전달한다.

  - 브라우저가 요청한 JSP가 최초로 요청했을 경우만

    - JSP로 작성된 코드가 서블릿으로 코드로 변환한다. (java 파일 생성)
    - 서블릿 코드를 컴파일해서 실행가능한 bytecode로 변환한다. (class 파일 생성)
    - 서블릿 클래스를 로딩하고 인스턴스를 생성한다.

  - 서블릿이 실행되어 요청을 처리하고 응답 정보를 생성한다.

    <br/>

  ##### ※ JSP Lifecycle 예제

  ```jsp
  <%@ page language="java" contentType="text/html; charset=UTF-8"
      pageEncoding="UTF-8"%>
  <!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
  <html>
  <head>
  <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
  <title>Insert title here</title>
  </head>
  <body>
  hello
  <%
  	System.out.println("_jspService()");
  %>
  
  <%!
  public void jspInit() {
  	System.out.println("jspInit()!");
  }
  
  public void jspDestroy() {
  	System.out.println("jspDestroy()");
  }
  %>
  
  </body>
  </html>
  ```

  <br/>

- ### JSP 기초 문법

  - #### JSP 전용 태그

    - 서블릿 생성 시 특정 자바 코드로 바뀌는 태그

      |    명칭    |                     문법                     |                          설명                          |
      | :--------: | :------------------------------------------: | :----------------------------------------------------: |
      | 스크립트릿 |                   <%    %>                   |                    자바 코드를 기술                    |
      | 익스프레션 |                  <%=    %>                   | 변수 또는 메소드의 결과값 등 화면에 출력할 내용을 기술 |
      |   지시자   | <%@ [지시자] [속성]="값" [속성]="값" ...  %> | 웹컨테이너가 JSP 페이지를 처리할 때 필요한 정보를 기술 |
      |   선언부   |                   <%!   %>                   |                  변수나 메서드를 선언                  |
      |    주석    |                 <%--   --%>                  |                          주석                          |

      <br/>

    - ##### 주석의 영향 및 범위

      - JSP 주석 : Servlet으로 변환 시 사라짐
      - JAVA 주석 : Servlet으로 변환 시 유지, 이 Servlet이 HTML로 변환 시 사라짐

      <br/>

    - ##### 지시자의 종류

      - page : JSP 페이지와 관련된 속성을 정의할 때 사용

        ```jsp
        <%@ page contentType="text/html;charset=UTF-8" language="java" pageEncoding="UTF-8" %>
        ```

        ```java
        response.setContentType("text/html;charset=UTF-8") // 위 JSP 코드가 이렇게 변환됨
        ```

      - include : 주어진 파일을 현재 페이지에 삽입하고자 할 때 사용

        ```jsp
        <%@ include file="file_url"%>
        ```

      - taglib : 태그 라이브러리를 선언할 때 사용

        ```jsp
        <%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>
        ```

      <br/>

  - ### JSP 내장 객체

    - JSP가 Servlet으로 변환될 때 자동으로 추가되는 Java 객체로써, JSP 프로그래밍을 좀 더 편하게 해주는 용도로 사용됨

      | 내장 객체   | 자바 클래스                            | 주요 역할                                                    |
      | ----------- | -------------------------------------- | ------------------------------------------------------------ |
      | request     | javax.servlet.http.HttpServletRequest  | HTML Form 요소 선택 값과 같은 사용자 입력 정보를 읽어올 때 사용 |
      | response    | javax.servlet.http.HttlServletResponse | 사용자 요청에 대한 응답을 처리할 때 사용                     |
      | pageContext | javax.servlet.jsp.PageContext          | 현재 JSP 실행에 대한 context 정보를 참조하기 위해 사용       |
      | session     | javax.servlet.http.HttpSession         | 클라이언트 세션 정보를 처리하기 위해 사용                    |
      | application | javax.servlet.ServletContext           | 웹서버의 애플리케이션 처리와 관련된 정보를 참조하기 위해 사용 |
      | out         | javax.servlet.jsp.JspWriter            | 사용자에게 전달하기 위한 output 스트림을 처리하기 위해 사용  |
      | config      | javax.servlet.ServletConfig            | 현재 JSP에 대한 초기화 환경을 처리하기 위해 사용             |
      | page        | javax.servlet.Http.JspPage             | 현재 JSP 페이지에 대한 클래스 정보                           |
      | exception   | javax.lang.Throwable                   | 예외 처리를 위해 사용                                        |

      <br/>

  - ### 리다이렉트(Redirect)

    - HTTP 프로토콜로 정해진 규칙

    - 서버가 클라이언트로부터 요청을 받았을 때, 클라이언트에게 특정 URL로 이동하라고 요청하는 것

    - 작동 순서

      - 서버는 클라이언트에게 HTTP 상태코드 302로 응답하는데 이때 헤더 내 Location 값에 이동할 URL을 추가함
      - 클라이언트는 리다이렉션 응답을 받게 되면 헤더(Location)에 포함된 URL로 재요청을 보냄
      - 이때 브라우저의 주소창은 새 URL로 바뀜

    - 서블릿이나 JSP는 리다이렉트하기 위해 HttpServletResponse 클래스의 sendRedirect() 메소드를 사용함

      <br/>

    ※ 예제

    - redirect01.jsp, redirect02.jsp 파일을 작성

    - 웹 브라우저가 redirect01.jsp을 요청 (즉, `localhostl:8080/.../.../redirect01.jsp` 로 접속)

    - redirect01은 redirect02.jsp로 리다이렉팅하는 로직이 실행되도록 함

      ```jsp
      <!-- redirect01.jsp -->
      <%@ page language="java" contentType="text/html; charset=UTF-8"
          pageEncoding="UTF-8"%>
      <%
          response.sendRedirect("redirect02.jsp");
      %>
      ```

      ```jsp
      <!-- redirect02.jsp -->
      <%@ page language="java" contentType="text/html; charset=UTF-8"
          pageEncoding="UTF-8"%>
      <!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
      <html>
      <head>
      <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
      <title>Insert title here</title>
      </head>
      <body>
      redirect된 페이지 입니다.
      </body>
      </html>
      ```

  <br/>

  - ### 포워드(Forward)

    - 클라이언트가 Servlet1로 어떤 요청을 보냈을 때, Servlet1이 그 요청의 일부분만 처리 한 후 남은 요청을 Servlet2로 넘겨주는 것

    - Servlet2는 이 나머지를 마저 처리한 다음에 응답을 만들어서 클라이언트한테 보냄

      <br/>

    - ##### 작동 순서

      - 웹 브라우저에서 Servlet1에게 요청을 보냄

      - Servlet1은 요청을 처리한 후, 그 결과를 HttpServletRequest에 저장

      - Servlet1은 결과가 저장된 HttpServletRequest와 응답을 위한 HttpServletResponse를 같은 웹 어플리케이션 안에 있는 Servlet2에게 전송(forward)

      - Servlet2는 Servlet1으로 부터 받은 HttpServletRequest와 HttpServletResponse를 이용하여 요청을 처리한 후 웹 브라우저에게 결과를 전송

        <br/>

    - ##### 포워드와 리다이렉트의 차이점

      ![image](https://user-images.githubusercontent.com/53200166/94514812-20c61a80-025d-11eb-88fa-cdd77921502e.png)

      - 포워드
        - Servlet1는 클라이언트의 요청을 일부 수행한 후 Servlet2에 남은 요청을 넘겨줌
        - 모든 작업이 끝난 후 클라이언트가 앞으로 요청할 곳은 Servlet1, 즉 **URL이 바뀌지 않음**
        - 클라이언트이 **요청이 단 한 번** (redirect01.jsp 요청) 이므로 `request` 객체와 `response` 객체는 한 번 만들어짐

      ![image](https://user-images.githubusercontent.com/53200166/94514824-258ace80-025d-11eb-913a-f83a554fa29d.png)

      - 리다이렉트

        - Servlet1은 해당 요청을 모두 수행한 후 앞으로는 Servlet2로 요청하라고 알려줌

        - 모든 작업이 끝난 후 클라이언트가 앞으로 요청할 곳은 Servlet2, 즉 **URL이 바뀜**

        - 클라이언트의 **요청이 두 번** 이므로 (redirect01.jsp 요청 -> redirect02.jsp 요청)  `request` 객체와 `response` 객체는 두 번 만들어짐

          <br/>

      ※ 예시

      - 포워드
        - 고객이 고객센터로 상담원에게 123번으로 전화를 건다.
        - 상담원은 해당 문의사항에 대해 잘 알지 못해서 옆의 다른 상담원에게 해당 문의사항에 대해 답을 얻는다.
        - 상담원은 고객에게 문의사항을 처리해준다.
      - 리다이렉트
        - 고객이 고객센터로 상담원에게 123번으로 전화를 건다.
        - 상담원은 고객에게 다음과 같이 이야기한다. "고객님 해당 문의사항은 124번으로 다시 문의 해주시겠어요?"
        - 고객은 다시 124번으로 문의해서 일을 처리한다.

    <br/>

    ※ 예제

    ```java
    // FrontServlet.java
    
    package examples;
    
    import java.io.IOException;
    
    import javax.servlet.RequestDispatcher;
    import javax.servlet.ServletException;
    import javax.servlet.annotation.WebServlet;
    import javax.servlet.http.HttpServlet;
    import javax.servlet.http.HttpServletRequest;
    import javax.servlet.http.HttpServletResponse;
    
    /**
     * Servlet implementation class FrontServlet
     */
    @WebServlet("/front")
    public class FrontServlet extends HttpServlet {
        private static final long serialVersionUID = 1L;
           
        /**
         * @see HttpServlet#HttpServlet()
         */
        public FrontServlet() {
            super();
            // TODO Auto-generated constructor stub
        }
    
        /**
         * @see HttpServlet#service(HttpServletRequest request, HttpServletResponse response)
         */
        protected void service(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
                
                int diceValue = (int)(Math.random() * 6) + 1; 
                request.setAttribute("dice", diceValue);
                
                RequestDispatcher requestDispatehcer = request.getRequestDispatcher("/next");
                requestDispatehcer.forward(request, response);
        }
    
    }
    ```

    ```java
    // NextServlet.java
    
    package examples;
    
    import java.io.IOException;
    import java.io.PrintWriter;
    import java.util.Enumeration;
    
    import javax.servlet.ServletException;
    import javax.servlet.annotation.WebServlet;
    import javax.servlet.http.HttpServlet;
    import javax.servlet.http.HttpServletRequest;
    import javax.servlet.http.HttpServletResponse;
    
    /**
     * Servlet implementation class ForwardServlet
     */
    @WebServlet("/forward")
    public class ForwardServlet extends HttpServlet {
        private static final long serialVersionUID = 1L;
           
        /**
         * @see HttpServlet#HttpServlet()
         */
        public ForwardServlet() {
            super();
            // TODO Auto-generated constructor stub
        }
    
        /**
         * @see HttpServlet#service(HttpServletRequest request, HttpServletResponse response)
         */
        protected void service(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
            response.setContentType("text/html");
            PrintWriter out = response.getWriter();
            out.println("<html>");
            out.println("<head><title>form</title></head>");
            out.println("<body>");
    
            int dice = (Integer)request.getAttribute("dice");
            out.println("dice : " + dice);
            for(int i = 0; i < dice; i++) {
                out.print("<br>hello");
            }
            out.println("</body>");
            out.println("</html>");
        }
    
    }
    ```

    

