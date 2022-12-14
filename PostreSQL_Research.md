<h1 style="text-align:center">PostgreSQL Research</h1>

<div style="text-align:right">1891059 안 민재</div>

### DB 

데이터베이스는 통합되어 관리되는 데이터의 집합체를 의미합니다. 데이터가 중복되는 것을 방지하고

자료를 구조화하여, 효율적인 데이터의 처리가 가능하도록 해줍니다.



__특징__

1. 사용자의 쿼리(질의)에 즉각적인 처리와 응답이 이루어집니다.

2. 생성, 수정, 삭제를 통하여 항상 데이터가 최신 상태로 유지하게 합니다.

3. 사용자들이 원하는 데이터를 동시에 공유할 수 있습니다.

4. 사용자가 원하는 데이터를 주소가 아닌 내용에 따라 참조할 수 있습니다.

5. 응용프로그램과 데이터베이스는 독립되어 있으므로, 데이터의 논리적 구조와 응용프로그램은

   별개로 동작됩니다.



### DBMS 

데이터베이스는 응용 프로그램과는 다른 별도의 서로 다른 어플리케이션이 서로 통신하는 데 사용되는

소프웨어인 미들웨어 일종인 데이터베이스 관리 시스템, DBMS 에 의해 관리됩니다.



### SQL

SQL 은 Structed Query Language 의 약자로 데이터베이스에서 정의, 조작, 제어하기 위해 사용하는 

언어입니다. SQL 은 목적에 맞게 세 가지로 구분할 수 있습니다.

<table>
<tr style="background-color:lightgray"><td>속성</td><td>설명</td><td>주요 명령어</td></tr> <tr><td>DDL(Data Definition Language)</td><td>데이터베이스나 테이블 등을 생성, 삭제하거나 그 구조를 변경하기 위한 명령어 </td><td>CREATE, ALTER, DROP</td></tr>
<tr><td>DML(Data Manipulation Language)</td><td>데이터베이스에 저장된 데이터를 처리하거나 조회, 검색하기 위한 명령어</td><td>INSERT, UPDATE, DELETE, SELECT 등</td></tr>
 <tr><td>DCL(Data Control Language)</td><td>데이터베이스에 저장된 데이터를 관리하기 위하여 데이터의 보안성 및 무결성 등을 제어하기 위한 명령어</td><td>GRANT, REVOKE 등</td></tr>
</table>



### RDBMS

관계형 데이터베이스는 현재 가장 많이 사용되고 있는 데이터베이스의 한 종류입니다.

관계형 데이터베이스는 테이블로 이루어져 있으며, 테이블은 키와 값의 관계를 나타냅니다.

이와 같이 데이터의 종속성을 관계로 표현하는 것이 관계형 데이터베이스의 특징입니다.

테이블은 이름을 가지며, 행과 열 그리고 거기에 대응하는 값을 가집니다.



__특징__

1. 데이터의 분류, 정렬, 탐색 속도가 빠릅니다.

2. 긴 사용 역사로 인해 신뢰성이 높고, 어떤 상황에서도 데이터의 무결성을 보장합니다.

   *데이터 무결성은 데이터의 정확성, 일관성, 유효성이 유지되는 것을 의미합니다. 정확성은*

   *중복이나 누락이 없는 상태를 말하며, 일관성은 원인과 결과의 의미가 연속적으로 보장되어*

   *변한지 않는 상태를 뜻합니다.*

3. 기존에 작성된 스키마를 수정하기가 어렵습니다.

   *스키마는 데이터베이스에서 자료의 구조, 자료의 표현 방법, 자료 간의 관계를 형식 언어로 정의한*

   *구조를 말합니다.* *한마디로 테이블을 디자인하기 위한 청사진이라고 할 수 있습니다.*

4. 데이터베이스의 부하를 분석하는 것이 어렵습니다.



__관계__

테이블의 관계는 관계를 맺는 테이블의 수에 따라 다음과 같이 나눌 수 있습니다.

1. 일대일 관계 : 한 테이블의 하나의 데이터가 다른 테이블의 하나의 데이터에 연관된다.
2. 일대다 관계 : 한 테이블의 하나의 데이터가 다른 테이블의 여러 데이터와 연관된다.



__transaction__

하나의 논리적 작업 단위를 구성하는 일련의 연산들의 집합을 트랜잭션이라고 한다.

트랜잭션의 대표적 예로는 계좌 간의 자금 이체가 있는데 전체 작업이 정상적으로 완료되거나, 

정상적으로 처리될 수 없는 경우, 아무 것도 실행되지 않은 처음 상태로 되돌려져야 한다.

이러한 트랜잭션은 다양한 데이터 항목들을 접근하고 갱신하는 프로그램 수행의 단위가 된다.

트랜잭션은 ACID 라고 하는 아래 4가지 성질로 설명된다.



* Actomicity (원자성)

  DBMS 는 완료되지 않은 트랜잭션의 중간상태를 데이터베이스에 반영해서는 안 된다.

  즉, 트랜잭션의 모든 연산들이 정상적으로 수행 완료되거나 아니면 전혀 어떤 연산도 수행되지

  않은 상태를 보장해야한다.



* Consistency(일관성)

  트랜잭션의 수행이 데이터베이스의 일관성을 보존해야한다. 즉, 성공적으로 수행된 트랜잭션은

  올바른 데이터만을 데이터베이스에 반영해야한다. 트랜잭션의 수행을 데이터베이스 상태변화로

  보았을 때, 트랜잭션 수행 전후의 데이터베이스 상태는 각각 일관성이 보장되는 서로 다른 상태가

  된다. 



* Isolation(독립성)

  여러 트랜잭션이 동시에 수행되더라도 각각의 트랜잭션은 다른 트랜잭션의 수행에 영향을 받지

  않고 독립적으로 수행되어야 한다. 즉, 한 트랜잭션의 중간 결과가 다른 트랜잭션에서는 파악할

  수 없어야 한다. 이런 성질이 보장되지 않으면 트랜잭션이 원 상태로 되돌아갈 수 없다. 이를

  보장할 수 있는 가장 쉬운 방법은 모든 트랜잭션을 순차적으로 수행하는 것이다. 하지만 

  병렬적 수행의 장점을 얻기 위해서 DBMS 는 병렬적으로 트랜잭션을 수행하며 일렬수행과

  같은 결과를 보장할 수 있는 방식을 제공하고 있다.



* Durability(지속성)

  트랜잭션이 성공적으로 완료되어 커밋되고 나면, 해당 트랜잭션에 의한 모든 변경은 향후에

  어떤 소프트웨어나 하드웨어 장애가 발생하더라도 보존되어야 한다.

  

### PostgreSQL

PostgreSQL 은 무료, 오픈소스 RDBMS 로 데이터베이스 계의 거장 Michael Stonebraker 가 시작한

Ingre(INteractive Graphics REtrieval System) 에서 파생된 프로젝트인 Postgres 는 Post-Ingres 의

줄임말인데 PostgreSQL 은 이 프로젝트에 SQL 을 지원하고 오픈소스가 되며 1997년에 공식적으로

출시되었다. BSD, MIT 라이선스와 같은 개방 라이선스와 유사한 고유 라이선스를 사용해 상용적인

사용과 수정을 허용하지만, 사용 중 발생하는 문제에 대해 법적 책임이 없음을 분명히 하고 있다.

PostgreSQL 의 로고는 코끼리인데 정확한 근원은 없으나 오픈소스화된 직후 한 사용자가 아가사

크리스트의 소설 '코끼리는 기억한다' 에서 착안해 제안한 것이 가장 유력한 이유이다.

이외에 코끼리가 크고 강하고 믿음직하며 기억력이 좋다는 점때문에 채택되었다는 설도 있다.



__특징__

1. 관계형 모델

   PostgreSQL 이 발생한 Postgre 프로젝트 연구의 목적 중 하나는 고수준을 확장 가능한 관계형

   DBMS 를 제작하는 것이었다. 따라서 PostgreSQL 은 관계형 DBMS 가 가지고 있는 거의 모든

   기능을 지원한다. 예시로 서술적인 질의어 사용, 동시성 제어, 트랜잭션 처리, 다중 사용자 기능

   들을 제공한다.



2. 고수준 확장성

   사용자 정의 오퍼레티어와 타입, 함수, 접근 메서드를 지원한다.



3. 객체지향

   PostgreSQL 은 상속, 객체와 같은 객체지향개념에서 볼 수 있는 여러 특징을 미흡하게나마 구현

   하고 있다. 이러한 특징으로 인해 ORDBMS(객체지향형 RDBMS) 라 칭해지기도 한다.



__개발 프로세스__

Postgre 의 개발 프로세스 모델은 한 마디로 '소수 주도의 커뮤니티 기반 오픈 소스 프로젝트' 라 할 수

있다. 소수의 관리자와 다양한 개발자 그리도 다수의 사용자가 프로젝트 구성원을 이루고 있으며, 

소수의 관리자 그룹은 다수의 사용자로부터 요청과 피드백을 수집하여 제품의 방향을 결정하고

최종 승인 및 배포를 시행한다. 



__현황, 동향__

PostgreSQL 을 사용하는 사람들은 대부분 개발자적인 성향을 가지고 있으며, 제품에 대한 애정도와

충성도가 높은 편이다. 프로젝트 페이지에 잘 정리된 매뉴얼, 문서와 몇 백종 이상의 관련 서적, 

매년 세계적으로 개최되는 관련 세미나와 컨퍼런스들이 그 근거로 볼 수 있으며, 이는 왕성한

커뮤니터 활동의 결과물이라고 볼 수 있겠다. 기능이나 성능적인 면에서 Oracle 에 비견할만하다는

벤치마크 자료도 종종 보이고 있으며, 최근 클라우드 분야에서 비용이나 라이선스 측면으로 부각되며

많은 클라우드 서비스 업체들이 PostgreSQL 을 사용하는 서비스를 제공하고 있다.

또한 MySQL 을 인수했던 Sun 이 2009년 Oracle 에 인수되며 좀 더 폐쇄적인 기업형 프로젝트 성향을

보이고 이에 해당 프로젝트에 참여했던 개발자들의 이탈이 발생함에 따라 PostgreSQL 의 사용률이

보다 증가할 수 있다는 전망이 보이고 있다. 이에 따라 PostgreSQL 오픈 소스 프로젝트 진영에서는

보다 나은 다양한 서비스 제공과 노력을 지속하고 있다.



