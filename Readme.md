## 데이터베이스 학습 레파지토리


### 데이터베이스 정의
조직체의 응용 시스템들이 **공유**해서 사용하는 운영 데이터들이 **구조적**으로 **통합**된 모임을 데이터베이스라 한다

**키워드**  
- 공유 (일부는 공유되는 데이터) 
- 통합 (운영 데이터들을 통합해서 저장)
- 구조적 (관계적 또는 객체지향 데이터 모델)

데이터베이스는 대규모 데이터 저장소로서 여러 부서에 속하는 여러 사용자에 의해 동시에 사용된다  


### 수업 챕터별 정리

#### [1. 데이터베이스 시스템 ](./ch1/Readme.md)
#### [2. 관계 데이터 모델과 제약조건 ](./ch2/Readme.md)
#### [4.관계 대수와 SQL ](./ch4/Readme.md)
 
### 수업을 통해 배울 수 있었던것

데이터베이스 시스템 개요 
- 스키마와 상태의 차이 (intension,extention)
- 시스템 카탈로그
- DBMS(Database management system) 개요 
- 컴퓨터 시스템에서 DBMS 의 위치 
- 데이터베이스 시스템의 요구사항 

DBMS 언어 
- 데이터 정의어(DDL : Data Definition Language) 
- 데이터 조작어(DML : Data Manuplation Language) 
- 데이터 제어어(DCL: Data Control Language) 

DBMS 사용자 분류
- 데이터베이스 관리자 (DBA: Database Administrator)   
- 응용 프로그래머 
- 최종 사용자 (end user)
- 데이터베이스 설계자
- 오퍼레이터 

관계 데이터 모델의 개념  
- 도메인(domain)
- 차수(degree) 와 카디날리티 (cadinality)
- 스키마(relation schema) 
- 릴레이션 인스턴스(relation instance)  
- 릴레이션 개념
- 릴레이션의 키(super key,candidate key,primary key,alternate key,foreign key) 들의 특징
  
무결성 제약조건
- 데이터 무결성(data integrity) 
- 도메인 제약조건(domain constraint) 
- 기본 키와 엔티티 무결성 제약조건(entity integrity constraint)  
- 외래 키와 참조 무결성 제약조건(referential integrity constraint)  
- 무결성 제약조건의 유지방법 
- 참조 무결성 제약조건을 만족시키기 위해 DBMS가 제공하는 옵션 