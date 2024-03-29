---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_What_is_this
title: "[Database] ORM"

# post specific
# if not specified, .name will be used from _data/owner.yml
author: 공지혁
# multiple category is not supported
category: Backend
# multiple tag entries are possible
tags: [Backend, DB]
# thumbnail image for post
img: "https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FdgejEm%2Fbtq8nsXjpYa%2Fwf9iTZD0G2gyrQRI4sQRRk%2Fimg.webp"
# disable comments on this page
#comments_disable: true

# publish date
date: 2022-11-28 10:04:30 +0900

# seo
# if not specified, date will be used.
#meta_modify_date: 2022-01-01 10:04:30 +0900
# check the meta_common_description in _data/lang/[language].yml
#meta_description: ""

# optional
# if you enabled image_viewer_posts you don't need to enable this. This is only if image_viewer_posts = false
#image_viewer_on: true
# if you enabled image_lazy_loader_posts you don't need to enable this. This is only if image_lazy_loader_posts = false
#image_lazy_loader_on: true
# exclude from on site search
#on_site_search_exclude: true
# exclude from search engines
#search_engine_exclude: true
# to disable this page, simply set published: false or delete this file
#published: false
---


# 영속성
- 데이터를 생성한 프로그램이 종료되더라도 사라지지 않는 데이터의 특성을 말합니다.
- 영속성을 가지지 않는 데이터는 단지 메모리에 존재하기 때문에 프로그램을 종료하면 모두 잃어버리게 됩니다.

## Object Persistance(영구적인 객체)
- 메모리 상의 데이터를 파일 시스템, 관계형  데이터베이스 혹은 객체 데이터베이스 등을 활용하여 영구적으러 저장하여 영속성을 부여합니다.
- 데이터를 데이터베이스에 저장하는 3가지 방법
    1) JDBC (Java에서 사용)
    2) Spring JDBC (Ex. JdbcTemplate)
    3) Persistence Framework (Ex. Hibernate, MyBatis)

## Persistence Layer
- 프로그램의 아키텍처에서, 데이터에 영속성을 부여해주는 계층을 말합니다.
- JDBC를 이용하여 직접 구현할 수 있지만 Persistence Framework를 이용한 개발이 많이 이루어집니다.

## Persistence Framework
- JDBC 프로그래밍의 복잡함이나 번거로움 없이 간단한 작업만으로 데이터베이스와 연동되는 시스템을 빠르게 개발할 수 있으며 안정적인 구동을 보장합니다.

# ORM
## Object-Relational Mapping
- 객체와 관계형 데이터베이스의 데이터를 자동으로 매핑해주는 것을 말합니다.
    - 객체지향 프로그래밍은 **클래스**를 사용하고, 관계형 데이터베이스는 **테이블**을 사용합니다.
    - 객체 모델과 관계형 모델 간에 불일치가 존재합니다.
    - ORM을 통해 객체 간의 관계를 바탕으로 SQL을 자동으로 생성하여 불일치를 해결해줍니다.
- 데이터베이스 데이터 <- 매핑 -> Object 필드
    - 객체를 통해 간접적으로 데이터베이스 데이터를 다룹니다.
- Persistant API라고도 부립니다.
    - Ex) JPA, Hibernate

## ORM의 장단점
### 장점
- 객체지향적인 코드로 인해 더 직관적이고, 비즈니스 로직에 더 집중할 수 있게 도와줍니다.
    - ORM을 이용하면 SQL 쿼리가 아닌 직관적인 코드로 데이터를 조작할 수 있어 개발자가 객체지향 프로그래밍하는데 집중할 수 있도록 도와줍니다.
    - 선언문, 할당 종료 같은 부수적인 코드가 없거나 급격히 줄어듭니다.
    - 각종 객체에 대한 코드를 별도로 작성하기 때문에 코드의 가독성을 올려줍니다.
    - SQL의 절차적이고 순차적인 접근이 아닌ㄴ 객체지향적인 접근으로 인해 생산성이 증가합니다.
- 재사용성 및 유지보수의 편리성이 증가합니다.
    - ORM은 독립적으로 작성되어있고, 해당 객체들을 재활용할 수 있습니다.
    - 이로인해 모델에서 가공된 데이터를 컨트롤로에 의해 뷰와 합쳐지는 형태로 디자인 패턴을 견고하게 다지는데 유리합니다.
    - 매핑정보가 명확하여 ERD를 보는 것에 대한 의존도를 낮출 수 있습니다.
- DBMS에 대한 종속성이 줄어듭니다.
    - 대부분 ORM 솔루션은 DB에 종속적이지 않습니다.
    - 종속적이지 않다는 것은 구현 방법 뿐만 아니라 많은 솔루션에서 자료형 타입까지 유효하다는 것입니다.
    - 개발자는 Object에  집중합으로써 극단적으로 DBMS를 교체하는 거대한 작업에도 비교적 적은 리스크와 시간이 소요됩니다.
    - 또한 자바에서 가공할 경우 equals, hashCode의 오버라이드 같은 자바의 기능을 이용할 수 있고, 간결하고 빠른 가공이 가능해집니다.
### 단점
- 완벽한 ORM으로만 서비스를 구현하기가 어렵습니다.
    - 사용하기 편하지만 설계는 매우 신중하게 해야합니다.
    - 프로젝트의 복잡성이 커질 경우 난이도 또한 올라갈 수 있습니다.
    - 잘못 구현된 경우에 속도 저하 및 심각할 경우 일관성이 무너지는 문제점이 생길 수 있습니다.
- 프로시저가 많은 시스템에서는 ORM의 객제 지향적인 장점을 활용하기 어렵습니다.
    - 이미 프로시저가 많은 시스템에서는 다시 객체로 바꿔야함, 그 과정에서 생산성 저하나 리스크가 많이 발생할 수 있습니다.

## Reference
https://velog.io/@dnjscksdn98/Database-ORM%EC%9D%B4%EB%9E%80
