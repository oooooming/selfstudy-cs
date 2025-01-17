
# 스프링 시큐리티로 로그인/로그아웃, 회원가입 구현하기

## 프로젝트 이해하기

<로그인>

1. /login 요청이 들어옴
   
2. UserViewController가 요청에 대한 분기 처리를 함 (*컨트롤러: 웹 애플리케이션에서 클라이언트의 요청을 받아 적절한 응답을 생성하는 역할; 요청 받기, 로직 분기 처리, 보안 처리)
   
3. WebSecurityConfig에 설정한 보안 관련 내용을 실행함
   
4. UserDetailsService를 실행 (*서비스: 비즈니스 로직 즉, 프로그램이 요구하는 핵심 기능 수행을 담당하는 역할; 사용자 정보 로드, 인증, 보안 설정)
   
5.요청을 성공하면, defaultSuccessUrl로 설정한 /articles로 리다이렉트하거나 csrf를 disable한다거나 등의 작업을 함
   
6. UserDetailsService에서 loadUserByUsername() 메서드를 실행하여 이메일로 유저를 찾고 반환함

<로그아웃>

1. /logout 요청이 오면 UserApiController 클래스에서 로그아웃 로직을 실행함

2. 로그아웃 로직이 SecurityContextLogoutHander에서 제공하는 logout() 메서드를 실행함

## 스프링 시큐리티

: 스프링 기반의 애플리케이션 보안(인증, 인가, 권한)을 담당하는 스프링 하위 프레임워크

*인증: 사용자의 신원을 입증하는 과정

*인가: 사이트의 특정 부분에 접근할 수 있는지 권한을 확인하는 과정

-> 인증과 인가 관련 코드를 아무런 도구의 도움 없이 작성하면 많은 시간이 필요한데 스프링 시큐리티를 사용한다면 아주 쉽게 처리할 수 있음

-스프링 시큐리티 특징: 애너테이션 설정이 매우 쉬움

-필터 기반으로 동작함

*UsernamePasswordAuthenticationFilter: 아이디와 패스워드가 넘어오면 인증 요청을 위임하는 인증 관리자 역할

*FilterSecurityInterceptor: 권한 부여 처리를 위임해 접근 제어 결정을 쉽게 하는 접근 결정 관리자 역할 

## 회원 도메인 만들기 

1. 회원 정보를 저장할 테이블을 만들고 도메인을 만든 다음 이 테이블과 연결할 회원 엔티티를 만듦

2. 회원 엔티티와 연결되어 데이터를 조회하게 해줄 리포지터리를 만듦

3. 스프링 시큐리티에서 사용자 정보를 가져오는 서비스를 만듦

4. 실제 인증 처리를 하는 시큐리티 설정 config 파일 작성

5. 사용자 정보 담고 있는 객체 작성 후 회원 정보를 추가하는 서비스 메서드 작성

6. 회원 가입 요청을 받으면 서비스 메서드를 사용하여 회원 정보를 저장하고 로그인 페이지로 이동시키는 회원 가입 컨트롤러 구현

7. 회원가입, 로그인 뷰 파일 연결 컨트롤러, 뷰 html 파일 작성

8. 로그아웃 메서드, 뷰 추가

9. 테스트를 위한 환경변수 추가 후 테스트!!

![image](https://github.com/user-attachments/assets/4c782f49-0815-4c35-acb4-17ae2f9aa28b)

![image](https://github.com/user-attachments/assets/a2d4ae9f-19a3-4d1f-ae82-c84c172c87f4)

![image](https://github.com/user-attachments/assets/748a195f-ad67-4737-a828-be2e34e3b232)

![image](https://github.com/user-attachments/assets/49f22e04-c6d0-4d4c-b781-1c4596f80524)

![image](https://github.com/user-attachments/assets/9cf6ec4d-6ade-4d4e-8ab9-758bcb1c7830)

![image](https://github.com/user-attachments/assets/c55aa8c1-1ead-4045-a716-ca3677d48561)
