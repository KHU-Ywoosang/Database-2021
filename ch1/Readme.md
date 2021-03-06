
## 1.1 데이터베이스 시스템 개요


### 데이터베이스 스키마 : 전체적인 데이터베이스 구조  
- 자주 변경되지 않는다
- 데이터베이스의 모든 가능한 상태를 미리 정의한것이다
- 내포(intension) 라고 부른다

`DEPARTMENT(DEPTNO, DEPTNAME, FLOOR)` 

### 데이터베이스 상태 : 특정 시점의 데이터베이스 내용

- 시간이 지남에 따라 계속해서 바뀐다
- 외연(extention) 이라고 부른다

|DEPTNO|DEPTNAME|FLOOR|
|------|---|---|
|1|영업|5|
|2|기획|4|
|3|개발|10|

### 시스템 카탈로그

데이터베이스는 시스템 카탈로그(또는 데이터 사전)와 저장된 데이터베이스로
구분할 수 있다  

시스템 카탈로그(system catalog)는 저장된 데이터베이스의
스키마 정보를 유지한다

![image](https://user-images.githubusercontent.com/68385605/111860130-c8a8df00-8988-11eb-88f2-9de9e454c21e.png)

### DBMS(Database management system) 

데이터베이스 관리 시스템
- 소프트웨어 패키지  
- 데이터베이스 구조를 명시
- 효율적인 데이터 질의어를 지원
- 권한이 없는 사용자로부터 데이터를 안전하게 보호  
- 여러 사용자가 데이터베이스를 접근하는 것 제어 
- SQL은 여러 DBMS에서 제공되는 사실상의 표준 데이터베이스 언어 

### 컴퓨터 시스템에서 DBMS 의 위치

- 데이터베이스는 운영체제와 응용프로그램 사이에 위치한다 
- 데이터베이스는 디스크와 같은 `보조 기억 장치`에 저장된다
- DBMS 에서 원하는 정보를 찾기 위해서는 `보조 기억 장치`의 블록들을 `주기억 장치`로 읽어들어야한다
계산이나 비교 연산들을 수행하기 위해 `중앙 처리 장치(CPU)` 사용된다
- DBMS 자체도 `주기억 장치`에 적재되어 실행되어야 한다    

![image](https://user-images.githubusercontent.com/68385605/111860179-263d2b80-8989-11eb-9b1f-3563d2e87e0c.png)

![image](https://user-images.githubusercontent.com/68385605/111860315-14a85380-898a-11eb-8b42-8e3fb726fac1.png)

### 데이터베이스 시스템의 요구사항
- 프로그램-데이터 독립성 (프로그램에 영향을 주지 않으면서 데이터베이스 구조를 변경할 수 있다)
- 효율적인 데이터 접근 (사용자의 질의를 빠르게 수행할 수 있는 인덱스 등의 접근 경로를 DBMS가
자동적으로 선택하여 수행한다)
- 데이터에 대한 동시 접근
- 백업과 회복 (시스템이 고장 나면 데이터베이스를 고장 전의 일관된 상태로 회복시킨다)
- 중복을 줄이거나 제어하며 일관성 유지
- 데이터 무결성 (데이터 간의 복잡한 관계를 표현하며, 무결성 제약조건을 DBMS가
자동적으로 유지한다)
- 데이터 보안 (권한이 없는 사용자로부터 데이터베이스를 보호한다) 
- 쉬운 질의어
- 여러 사용자에게 적합한 다양한 사용자 인터페이스 

## 1.2 화일 시스템 vs DBMS 

### DBMS의 장점
- 중복성과 불일치가 감소된다
- 시스템을 개발하고 유지하는 비용이 감소된다
- 표준화를 시행하기가 용이하다
- 보안이 향상된다
- 무결성이 향상된다
- 조직체의 요구사항을 식별할 수 있다
- 다양한 유형의 고장으로부터 데이터베이스를 회복할 수 있디
- 데이터베이스의 공유와 동시 접근이 가능하다

### 기존 화일시스템 방식의 문제점

- 데이터에 대한 물리적 접근만 조정한다 (엔티티와 엔티티타입 관계등 논리적 설계 불가)
- 동일한 화일을 두 개 이상의 프로그램이 동시에 접근할수 없다
- 데이터가 비구조적이며, 중복성과 유지보수 비용이 높다
- 어떤 프로그램이 기록한 데이터는 다른 프로그램에서 읽을 수 없는 경우가 많다
- 데이터에 대한 접근은 미리 작성된 프로그램을 통해서만 가능하다
- 각 응용프로그램마다 화일이 따로 있으므로 데이터가 통합되어 있지 않다

### DBMS의 단점
- 추가적인 하드웨어 구입 비용이 들고, DBMS 자체의 구입 비용도 상당히
비쌈
- 직원들의 교육 비용도 많이 소요됨
- 비밀과 프라이버시 노출 등의 단점이 존재할 수 있음
- 초기의 투자 비용이 너무 클 때, 오버헤드가 너무 클 때, 응용이 단순하고
잘 정의되었으며 변경되지 않을 것으로 예상될 때, 엄격한 실시간 처리
요구사항이 있을 때, 데이터에 대한 다수 사용자의 접근이 필요하지 않을
때는 DBMS를 사용하지 않는 것이 바람직할 수 있음



## 1.3 DBMS 발전과정 

### 데이터 모델

- 데이터베이스의 구조를 기술하는데 사용되는 개념들의 집합 구조(데이터 타입과 관계)  
이 구조 위에서 동작하는 연산자들, 무결성 제약조건들  
- 사용자에게 내부 저장 방식의 세세한 사항은 숨기면서 데이터에 대한 직관적인 뷰 제공과 동시에 이들간의 매핑(사상) 제공  

### 데이터 모델의 분류

고수준 또는 개념적 데이터 모델(conceptual data model)
  * 엔티티-관계 데이터 모델(Entitiy-Relationship)  
표현(구현) 데이터 모델
  * 계층 데이터 모델(hierachical data model)
  * 네트워크 데이터 모델(network data model)
  * 관계 데이터 모델(relational data model)  
저수준 또는 물리적인 데이터 모델(physical data model)
  * 데이터베이스에 데이터가 어떻게 저장되는가를 기술
  * Unifying, ISAM, VSAM

```
계층 DBMS - 네트워크 DBMS ㅡ 관계 DBMS     -  객체 관계 DBMS 
                         └─ 객체지향 DBMS  
```         

관계형 DBMS : 데이터 베이스 테이블의 `키값(식별자)` 을 참조  
계층형 :  `포인터,링크`로 데이터 연결 

### 계층 DBMS 
1960년대 후반에 최초의 계층 DBMS가 등장(예: IBM사의 IMS)  
계층 데이터 모델은 네트워크 데이터 모델의 특별한 사례다  

장점 
- 어떤 유형의 응용에 대해서는 빠른 속도와 높은 효율성을 제공

단점 
- 어떻게 데이터를 접근하는가를 미리 응용 프로그램에 정의해야 함
- 데이터베이스가 생성될 때 각각의 관계를 명시적으로 정의해야 함
- 레코드들이 링크로 연결되어 있으므로 레코드 구조를 변경하기 어려움
- one-to-many 관계는 잘 처리하나 many-to-many 관계는 잘 처리할 수 없다

### 네트워크 DBMS 

1960년대 초에 Charles Bachman이 하니웰(Honeywell) 사에서 최초의
네트워크 DBMS인 IDS를 개발  
레코드들이 노드로, 레코드들 사이의 관계가 간선으로 표현되는 그래프를
기반으로 하는 네트워크 데이터 모델을 사용한다  
네트워크 DBMS에서도 레코드들이 링크로 연결되어 있으므로 레코드
구조를 변경하기 어렵다   

### 관계 DBMS 
1970년에 E.F. Codd가 IBM 연구소에서 관계 데이터 모델을 제안  
미국 IBM 연구소에서 진행된 System R과 캘리포니아 버클리대에서 진행된
Ingres 프로젝트

장점 
- 모델이 간단하여 이해하기 쉬움
- 사용자는 자신이 원하는 것(what)만 명시하고, 데이터가 어디에 있는지,
어떻게 접근해야 하는지는 DBMS가 결정

ex) 오라클, MS SQL Server, Sybase, DB2, Informix 등


### 객체 지향 DBMS 
1980년대 후반 들어 새로운 데이터 모델인 객체 지향 데이터 모델이 등장  
객체 지향 프로그래밍 패러다임을 기반으로 하는 데이터 모델  
장점
- 데이터와 프로그램을 그룹화하고, 복잡한 객체들을 이해하기 쉬우며,
유지와 변경이 용이하다

ex) ONTOS, OpenODB, GemStone, ObjectStore, Versant, O2 등


### 객체 관계 DBMS 
1990년대 후반에 관계 DBMS에 객체 지향 개념을 통합한 객체 관계 데이터
모델이 제안되었다
ex) 오라클, Informix Universal Server 등 

### DBMS 의 데이터 모델에 따른 프로그래밍 분량
![image](https://user-images.githubusercontent.com/68385605/111862674-28f44c80-899a-11eb-9b63-0fc6c4286bcf.png)



## 1.4 DBMS 언어

### 데이터 정의어(DDL : Data Definition Language)
- 사용자는 데이터 정의어를 사용하여 데이터베이스 `스키마를 정의`
- 데이터 정의어로 명시된 문장이 입력되면 DBMS는 사용자가 정의한 스키마에 대한 명세를 시스템 카탈로그 또는 데이터 사전에 저장
- 데이터 정의어의 기본적인 기능
  * 데이터 구조를 생성 : CREATE TABLE
  * 데이터 구조의 변경 : ALTER TABLE
  * 데이터 구조의 삭제 : DROP TABLE
  * 데이터 접근을 위해 특정 애트리뷰트 위에 인덱스를 정의 : CREATE INDEX 

### 데이터 조작어(DML : Data Manuplation Language)
- 데이터 검색,수정,삽입,삭제
- 절차적 언어와 비절차적 언어로 나뉨
- SQL 은 대표적 비절차적 언어
- 대부분 데이터 조작어는 SUM,COUNT,AVG 와 같은 내장 함수들을 갖고 있음
- 데이터 조작어는 단말기에서 대화식으로 입력되어 수행되거나 JAVA 등 응용프로그램 내에서 사용됨
- 데이터 조작어의 기본적인 기능
  * 데이터의 검색 : SQL에서 SELECT 
  * 데이터의 수정 : SQL에서 UPDATE 
  * 데이터의 삭제 : SQL에서 DELETE 
  * 데이터의 삽입 : SQL에서 INSERT 


![image](https://user-images.githubusercontent.com/68385605/111862820-1b8b9200-899b-11eb-8ced-56e94719ed88.png)

 
![image](https://user-images.githubusercontent.com/68385605/111862924-aff5f480-899b-11eb-88d1-c3d15bd8b8ba.png)

### 데이터 제어어(DCL: Data Control Language)
- 사용자는 데이터 제어어를 사용하여 데이터베이스 트랜잭션을 명시하고
권한을 부여하거나 취소

## 1.5 DBMS 사용자

### 데이터베이스 관리자 (DBA: Database Administrator)  
- 조직의 여러 부분의 상이한 요구를 만족시키기 위해 일관성 있는 데이터베이스 스키마를 생성하고 유지
- 데이터베이스 관리자의 역할  
  * 데이터베이스 스키마 생성과 변경
  * 무결성 제약조건을 명시
  * 사용자 권한을 허용하거나 취소하고, 사용자 역할을 관리
  * 저장 구조와 접근방법(물리적 트랜젝션) 정의


  
### 응용 프로그래머
- 데이터베이스 위에서 특정 응용(고객관리,인사관리,재고관리 등) 이나 인터페이스 구현  
- 고급 프로그래밍 언어인 JAVA 등으로 응용 프로그램을 개발하면서
데이터베이스를 접근하는 부분은 내포된 데이터 조작어를 사용
- 이들이 작성한 프로그램은 최종 사용자들이 반복해서 수행하므로 `기작성
트랜잭션`(canned transaction)이라 부름

`기작성 트랜지션`: 사용자가 추가적으로 뭘 개발하거나 할 필요 없이 바로 쓸 수 있는것


### 최종 사용자 (end user)
- 질의하거나 갱신하거나 보고서를 생성하기 위해서 데이터베이스를 사용하는 사람이다
- 캐주얼 사용자와 기작전 트랜지션(canned transaction)을 주로 반복해서 수행하는 초보 사용자로 구분된다

### 데이터베이스 설계자
- ERWin 등의 CASE 도구들을 이용해 데이터베이스 설계를 담당
- 데이터베이스의 일관성을 위지하기 위해서 정규화를 수행

### 오퍼레이터
- DBMS가 운영되고 있는 컴퓨터 시스템과 전산실을 관리하는 사람

## 1.6 ANSI/SPARC 아키텍처와 데이터 독립성 


현재의 대부분의 상용 DBMS 구현에서 사용되는 일반적인 아키텍처는
1978년에 제안된 ANSI/SPARC 아키텍처이다  
ANSI/SPARC 아키텍처의 3단계  
- 외부 단계(external level): 각 사용자의 뷰
- 개념 단계(conceptual level): 사용자 공동체의 뷰
- 내부 단계(internal level): 물리적 또는 저장 뷰



각각의 DBMS 는 각각의 API 사용 => 표준 API 하나로 통함 (ODBC)
자바는 JDBC(java database connectivity) : 자바프로그램을 사용해서 DBMS 사용하는 프로그램을 사용할때 
DBMS 제품이 바뀌더라도 응용프로그램 바꾸지 않고 사용 가능 
bridge : 연결되지 않은 것을 연결시키는 역할 : DBAS 

DBMS A => ODBC
DBMS B => JDBC 
A 와 B 연결하고 싶으면 bridge 사용 
데이터가 한 쪽에서 다른쪽으로 가는 것을 허용
클라이언트-서버 데이터베이스 시스템
클라이언트-서버 환경에서 대표적인 응용프로그램의 예 : POS 기 웹 화면 

응용 논리 (2,3 계층 ) : application logic 또는 business logic 
편의점 갈 때 1+1 이벤트 같은것 : 프로그램 안에서 구현
항공기 예약 시스템 : 클라이언트 - 사용자 로그인, 알아보기 쉬운 형식으로 결과 출력
응용서버 : 새로운 예약받기,기존예약 취소
데이터베이스 서버 : 


3층모델 응용서버에만 프로그램~ 용이


내부단계 :조직체 전체 
외부단계 : 개별적 사용자의 뷰 