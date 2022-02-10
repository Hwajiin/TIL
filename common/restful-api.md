# RESTful API

## 👀 참조 링크

📎 <a href="https://gmlwjd9405.github.io/2018/09/21/rest-and-restful.html" target="_blank">RESTful API 개념이 잘 정리된 사이트</a>

📎 <a href="https://docs.github.com/en/rest/overview/resources-in-the-rest-api" target="_blank">깃허브 REST API Docs</a>

📎 <a href="https://developers.google.com/youtube/v3/getting-started" target="_blank">유튜브 Data API Docs</a>

---

## 🐾 목차

> [API](#1-apiapplication-programming-interface)  
> [RESTful API](#2-restful-api)  
> [REST의 구체적인 개념](#3-rest의-구체적인-개념)  
> [REST 구성 요소](#4-rest-구성-요소)  
> [RESTful System의 특징](#5-restful-system의-특징)  
> [REST의 장단점](#6-rest의-장단점)  
> [REST API 설계 기본 규칙](#7-rest-api-설계-기본-규칙)  
> [REST API 설계 규칙](#8-rest-api-설계-규칙)  
> [더 공부할 사항](#9-더-공부할-사항)

---

## 1. API(Application Programming Interface)

API는 쉽게 말해,
프로그램들(컴퓨터의 소프트웨어 등)이 간편하게 상호작용할 수 있도록 도와주는 매개체라고 할 수 있다

여기서 주로 이야기하고자 하는 API는 클라이언트-서버 통신의 관점에서 쓰여진 것이다

## 2. RESTful API

- REST: _자원(Resource)의 이름으로 자원의 상태(정보)를 주고받는 모든 것_

  - 여기서 자원이란 해당 소프트웨어가 관리하는 모든 것을 의미한다(예: 이미지, 비디오, 데이터 등)

- RESTful: *API를 디자인하는 가이드라인의 개념*으로 보면 이해하기 쉬울 것 같다

  - Representational State Transfer

  - 자원으로의 접근과 전달을 위해 설계될 API의 디자인 가이드 라인

- RESTful API: _REST를 준수하여 설계된 API_
  - HTTP Method를 통해, 자원을 기준으로 API를 디자인하는 것

## 3. REST의 구체적인 개념

HTTP URI(Uniform Resource Identifier)를 통해 Resource를 명시하고,  
HTTP Method로 해당 자원에 대한 CRUD Operation을 적용하는 것을 의미

- REST는 자원 기반의 구조(ROA, Resource Oriented Architecture) 설계의 중심에 Resource가 있고 HTTP Method를 통해 Resource를 처리하도록 설계된 아키텍쳐를 의미

## 4. REST 구성 요소

### 1) Resource: URI

- 서버에 존재하는 모든 자원은 고유한 ID를 보유하고 있다
- 클라이언트에서 서버의 자원에 접근하기 위해서는 URI를 지정하여 요청을 보내야 한다

### 2) Actions: HTTP Method

- 자원에 어떤한 요청을 할지를 HTTP Method를 통해 나타낸다
- CRUD: Create Read Update Delete

### 3) Representational of Resource: 표현

- 클라이언트가 자원에 대한 요청을 보내면 서버는 적절한 응답해야한다
- 자원에 관해 JSON, XML, RSS, TEXT 등의 형식으로 응답할 수 있다

## 5. RESTful System의 특징

### 1) Client-Server 구조

- 자원을 요청하는 쪽은 Client, 요청에 응답하는 쪽은 Server

### 2) Stateless

- HTTP 프로토콜은 무상태 프로토콜이기 때문에 REST 역시 무상태성을 갖는다
- 서버는 요청을 각각 개별적으로 인식한다
- 클라이언트의 context를 서버에 저장하지 않는다

### 3) 캐시 처리 가능

- HTTP 프로토콜을 그대로 사용하기 때문에 인프라를 그대로 사용할 수 있다

### 4) Layered System(계층화)

- 클라이언트는 REST API Server만 호출한다
- 서버는 다중 계층으로 구성될 수 있다

### 5) Code-On-Demand(Optional)

- 서버로부터 스크립트를 받아서 실행한다

### 6) Uniform Interface(일관성)

- URI로 지정한 Resource에 대한 조작을 통일되고 한정적인 인터페이스로 수행한다

## 6. REST의 장단점

### 1) 장점

- HTTP 프로토콜의 인프라를 그대로 사용 가능하다
- HTTP 표준 프로토콜을 따르는 모든 플랫폼에서 활용 가능하다
- 클라이언트와 서버의 역할을 명확하게 분리한다
- 일관적인 서비스를 디자인할 수 있도록 돕는다

### 2) 단점

- 사용할 수 있는 메소드에 한계가 있다
- 표준이 정해지지 않았다
- 구형 브라우저가 아직 지원해주지 못하는 부분이 존재한다

## 7. REST API 설계 기본 규칙

도큐먼트 : 객체 인스턴스나 데이터베이스 레코드와 유사한 개념  
컬렉션 : 서버에서 관리하는 디렉터리라는 리소스  
스토어 : 클라이언트에서 관리하는 리소스 저장소

### 1) URI는 정보의 자원을 포함해야 한다

- 자원은 동사보다는 명사를, 대문자보다는 소문자
- 도큐먼트 이름은 단수 명사
- 컬렉션과 스토어으 이름은 복수 명사

### 2) 자원에 관한 행위는 HTTP Method로 표현한다

- URI에 HTTP Method가 들어가서는 안된다
- URI에 동사 표현이 들어가서는 안된다
- 경로 부분 중 변하는 부분은 고유한 값으로 표현한다

## 8. REST API 설계 규칙

- / 구분자는 계층 관계를 나타낸다
- URI의 마지막에는 슬래쉬를 사용하지 않아도 된다
- 하이픈은 가독성을 높이지만 언더스코어는 사용하지 않는 것이 좋다
- URI는 소문자로 작성한다
- 파일확장자는 URI에 포함하지 않는다

---

## 9. 더 공부할 사항

- [ ] graphQL과 REST API
- [ ] HTTP Method에 관한 자세한 내용
