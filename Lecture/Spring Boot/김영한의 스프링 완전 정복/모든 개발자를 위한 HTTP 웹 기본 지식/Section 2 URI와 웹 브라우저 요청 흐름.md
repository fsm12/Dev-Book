# Section 2 URI와 웹 브라우저 요청 흐름
마지막 공부날짜 : 2024.04.02.

</br></br>

## URI, URL, URN
`URI(Uniform Resource Identifier)`는 `URL`과 `URN`을 모두 포함하는 용어로 자원의 위치(Locator)와 이름(Name)을 모두 포함한다. 

|분류|URL|URN|
|:--:|:--:|:--:|
|정의|자원이 있는 위치(Locator)를 지정|자원에 이름(Name)을 부여|
|가변|위치는 변할 수 있음|이름은 변하지 않음|
|사용|사용|이름만으로 실제 리소스를 찾을 수 있는 방법이 보편화 되어있지 않음|

![image](https://github.com/fsm12/Dev-Book/assets/74345771/145f62b5-8ee4-4574-ad56-db6935a8ee74)

![image](https://github.com/fsm12/Dev-Book/assets/74345771/573f05da-1b25-4597-a9a0-0a4e7a94bf3c)

</br></br>

## URL 분석
|Format|scheme://[userinfo@]host[:port][/port][/path][?query][#fragment]|
|:--:|:--:|
|Example|https://google.com/search?q=hello&hl=ko|

- **scheme**: 주로 프로토콜을 사용하며 어떤 방식으로 자원에 접근할 것인가 하는 규칙   
    *Ex: http, https, ftp, ...*
- **userinfo**: 사용자 정보를 포함해서 인증에 사용하는데 거의 사용하지 않는다.    
*Ex:  GitLab 접속시 사용자정보를 입력하거나, SSH 유저정보를 넣을때도 사용하고는 한다.* 
- **host**: 호스트명, 도메인명 또는 IP주소를 직접 사용할 수도 있다.    
- **port**: 접속 포트로 IP 가 컴퓨터의 논리적 주소라면, port는 컴퓨터에서 실행되는 앱의 주소라 할 수 있다. 생략도 가능하며 http는 80, https는 443생략한다.    
- **path**: 리소스 경로로 계층적 구조로 되어 있다.   
*[docs.spring.io/spring-framework/reference/index.html)*   
- **query(=query parameter, query string)** : key/value형태로 ?로 시작하며 &으로 추가가 가능하다.   
*?a=b&c=d*
- **fragment**: `html`내부 북마크 등에 사용되며 서버에 전송되는 정보가 아니다.

![image](https://github.com/fsm12/Dev-Book/assets/74345771/6f5c7d9a-fe07-4ae6-a9d5-c52b5852b4cb)

</br></br>

## 웹 브라우저 요청 흐름

참고 : [What happens when you type a URL in the browser and press enter?](https://medium.com/@maneesa/what-happens-when-you-type-an-url-in-the-browser-and-press-enter-bb0aa2449c1a)

[시나리오] `http://www.google.com` url을 요청하면?
1. www.google.com을 브라우저 주소창에 친다 
2. Browser는 캐싱된 DNS 기록들을 통해 www.google.com에 대응되는 IP 주소가 있는지 확인한다
3. 요청한 URL이 캐시에 없으면, ISP의 DNS 서버가 www.google.com을 호스팅하고 있는 서버의 IP 주소를 찾기 위해 DNS query를 날린다
4. Browser가 서버와 TCP connection을 한다
5. Browser가 웹 서버에 HTTP 요청을 한다.
6. 서버가 요청을 처리하고 response를 생성한다
7. 서버가 HTTP response를 보낸다
8. Browser가 HTML content를 보여준다

