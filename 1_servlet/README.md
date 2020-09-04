# Table of contents

- [First project for studying about servlet](#First-project-for-studying-about-servlet)
  - [IntelliJ](#IntelliJ)
  - [Eclipse](#Eclipse)

- [기본적인 서블릿 작성 방법](#기본적인-서블릿-작성-방법)
    - [서블릿이란?](#서블릿이란?)
    - [기본적인 메서드들](#기본적인-메서드들)
  - [서블릿 라이프사이클](#서블릿-라이프사이클)
    - [서블릿 수행 과정](#서블릿-수행-과정)
    - [서블릿 라이프사이클 관련 메서드들](#서블릿-라이프사이클-관련-메서드들)
    - [service(...) 메서드의 특징](#service(...)-메서드의-특징)
  - [요청 및 응답 정보 출력하기](#요청-및-응답-정보-출력하기)
    - [Header 정보 출력하기](#Header-정보-출력하기)
    - [URL 파라미터 출력하기](#URL-파라미터-출력하기)
    - [URI, URL, PATH, Remote Host 출력하기](#URI,-URL,-PATH,-Remote-Host-출력하기)

<br/>

---



# First project for studying about servlet

- ### IntelliJ

  - ##### Make a project

    ![image](https://user-images.githubusercontent.com/70624367/92197829-d0ea7280-eead-11ea-9316-02e4536408d5.png)

    ![image](https://user-images.githubusercontent.com/70624367/92197838-d5169000-eead-11ea-8b67-e0b71528a7a0.png)

    ![image](https://user-images.githubusercontent.com/70624367/92197844-d8118080-eead-11ea-82fc-1ad0739af7e2.png)

    ![image](https://user-images.githubusercontent.com/70624367/92197849-db0c7100-eead-11ea-9483-46e26cb7cb55.png)

    

  - ##### Configuration Settings

    ![image](https://user-images.githubusercontent.com/70624367/92197866-e364ac00-eead-11ea-9968-3c125d2b098f.png)

    ![image](https://user-images.githubusercontent.com/70624367/92197870-e52e6f80-eead-11ea-8c97-e95dbaa1e87a.png)

    ![image](https://user-images.githubusercontent.com/70624367/92197874-e790c980-eead-11ea-9d41-8a665db5ce25.png)

    ![image](https://user-images.githubusercontent.com/70624367/92197882-ed86aa80-eead-11ea-9ec8-39aee0ca207c.png)

    ![image](https://user-images.githubusercontent.com/70624367/92197944-08f1b580-eeae-11ea-9920-05f4a95897c6.png)

    ![image](https://user-images.githubusercontent.com/70624367/92197951-0b540f80-eeae-11ea-9c64-0fde35563cff.png)

    ![image](https://user-images.githubusercontent.com/70624367/92197956-0e4f0000-eeae-11ea-8308-6da95121cedb.png)

    

  - ##### Make a servlet

    ![image](https://user-images.githubusercontent.com/70624367/92197857-de076180-eead-11ea-9451-96060117ce7a.png)

    ![image](https://user-images.githubusercontent.com/70624367/92197862-e1025200-eead-11ea-9276-1e05fb01677a.png)

    

- ### Eclipse

  - ##### Make a project

    ![image](https://user-images.githubusercontent.com/70624367/92198575-aef1ef80-eeaf-11ea-8297-acb4d3741249.png)

    ![image](https://user-images.githubusercontent.com/70624367/92198581-b1544980-eeaf-11ea-9f1c-7f5348d2adc2.png)

    ![image](https://user-images.githubusercontent.com/70624367/92198584-b2857680-eeaf-11ea-8038-df550e716469.png)

    ![image](https://user-images.githubusercontent.com/70624367/92198587-b3b6a380-eeaf-11ea-97fd-ceb7b61bfac2.png)

    ![image](https://user-images.githubusercontent.com/70624367/92198591-b4e7d080-eeaf-11ea-8e3c-3de5916ea9b8.png)

    

  - ##### Make a servlet

    ![image](https://user-images.githubusercontent.com/70624367/92198594-b6b19400-eeaf-11ea-9378-e614af7bab10.png)

    ![image](https://user-images.githubusercontent.com/70624367/92198595-b7e2c100-eeaf-11ea-8c37-f2cb9566fe49.png)

    ![image](https://user-images.githubusercontent.com/70624367/92198600-ba451b00-eeaf-11ea-9420-98943f733ac4.png)

<br/>

---



# 기본적인 서블릿 작성 방법

- ### 서블릿이란?

  - 자바를 사용하여 웹을 만들기 위해 필요한 기술
  - 클라이언트의 요청에 따라 동적으로 응답 결과를 만들어내는 것

<br/>

- ### 기본적인 메서드들

    - ### doGet(...)

      - 요청이 들어왔을 때 일(응답)을 처리해주는 메서드. 클라이언트가 요청하면, 서버는
        - 요청을 받아내는 객체 `HttpServletRequest`와
        - 응답을 하기위한 객체 `HttpServletResponse`를 자동으로 만들어 냄

    <br/>

    - ### response.setContentType(…)

      - 웹브라우저가 서버로부터 응답을 받았을 때, 응답으로 받은 데이터의 형태가 무엇인지 알려주는 메서드

      - 한글이 읽히지 않는 문제를 해결하기 위해 끝에 `charset=utf-8`을 넣음

    <br/>

    - ### PrintWriter out = response.getWriter();

      - 응답으로서 데이터를 전송해주는 통로 역할

    <br/>

    - ### out.println(...) or out.print(...)

      - 데이터 전송

<br/>

# 서블릿 라이프사이클

![image](https://user-images.githubusercontent.com/70624367/92199728-ea41ed80-eeb2-11ea-97b1-5e67ae78db81.png)

<br/>

- ### 서블릿 수행 과정

  - 해당 URL로 클라이언트가 서버에게 요청
  - 서버는 해당 URL을 받아서 URL mapping 값을 확인
    - 서블릿 실행 규칙
      - IntelliJ : `http://localhost:8080/{아티펙트이름}/{URL Mapping값}`
      - Eclipse : `http://localhost:8080/{프로젝트이름}/{URL Mapping값}`
    - 해당 클래스가 메모리에 존재하는지 확인
    - 메모리에 존재하지 않는다면 클래스 객체를 생성하여 메모리에 적재
      - 서블릿은 서버에 서블릿 객체를 단 한 개 만듦
    - 서블릿 객체를 생성하고 초기화하는 작업은 비용이 많이 들기 때문에, 별도의 제거 작업이 있지 않는 한 이미 생성된 서블릿 객체는 메모리에 남아있음

<br/>

- ### 서블릿 라이프사이클 관련 메서드들

  - #### 생성자

    - 서블릿 객체가 메모리에 적재될 때 수행

  - #### init(…)

    - 서블릿 초기화 작업. 프로그램이 시작될 때 수행

  - #### service(…)

    - 클라이언트(웹브라우저)의 요청 처리 작업.
    - 클라이언트로부터 요청된 객체가 메모리에 있다면 수행
    - 요청이 들어왔을 때 응답해야하는 모든 내용은 이 메서드에 구현하는 것이 좋음

  - #### destroy(…)

    - 메모리에 적재되어 있던 서블릿 객체가 메모리에서 제거될 때 수행
    - WAS가 종료되거나, 웹페이지가 새롭게 갱신될 경우 수행

<br/>

- ### service(...) 메서드의 특징

  - 내가 **service()** 메서드를 오버라이드하여 새로 작성하지 않았다면, 서블릿의 부모인 **HttpServlet** 클래스의 **service()** 메서드가 실행됨

  - #### HttpServlet 클래스의 service() 메서드의 구현 형식

    - 템플릿 메서드 패턴으로 구현되어 있음
    - 클라이언트의 요청이 **GET**일 경우 자신이 가지고 있는 **doGet(…)** 메서드를 호출
    - 클라이언트의 요청이 **POST**일 경우 자신이 가지고 있는 **doPost(…)** 메서드를 호출
    - 따라서 **service()** 메서드를 작성하지 않고 **doGet(…)** 또는 **doPost(…)**만 작성(오버라이드)하여 실행한다면, **HttpServlet** 클래스의 **service()** 메서드가 알아서 내가 작성한 **doGet(…)** 또는 **doPost(…)**를 호출하는 것

<br/>

---



# 요청 및 응답 정보 출력하기

- ### Header 정보 출력하기

    - 클라이언트가 서버에게 요청할 때 함께 보내는 요청 정보 출력
      
        ```java
        Enumeration<String> headerNames = request.getHeaderNames();
        
        while(headerNames.hasMoreElements()) {
            String headerName = headerNames.nextElement();
            String headerValue = request.getHeader(headerName);
            out.println(headerName + " : " + headerValue + " <br> ");
        }
        ```
        
          <br/>

- ### URL 파라미터 출력하기

    - 형식 : `http://localhost:8080/{프로젝트이름}/{URL Mapping값}?{파라미터1}={값}&{파라미터2}={값}&...`

    - #### 요청과 함께 들어온 파라미터값 출력하기

      - 아래 예시는 클라이언트가 **http://localhost:8080/firstweb/param?name=kim&age=5** 를 통해 웹페이지에 접속하였을 때 전달받는 파라미터들을 출력하는 코드

          ```java
          String name = request.getParameter("name");
          String age = request.getParameter("age");
          
          PrintWriter out = response.getWriter();
          out.println("name : " + name + "<br>");
          out.println("age : " +age + "<br>");
          ```

      <br/>

- ### URI, URL, PATH, Remote Host 출력하기

  ~~~java
  ```java
  String uri = request.getRequestURI();
  StringBuffer url = request.getRequestURL();
  String contentPath = request.getContextPath();
  String remoteAddr = request.getRemoteAddr();
  
  out.println("uri : " + uri + "<br>");
  out.println("url : " + url + "<br>");
  out.println("contentPath : " + contentPath + "<br>");
  out.println("remoteAddr : " + remoteAddr + "<br>");
  ```    
  ~~~