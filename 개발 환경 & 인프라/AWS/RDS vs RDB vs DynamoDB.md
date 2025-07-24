# RDB (Relational DataBase)
> 데이터를 테이블(행과 열) 구조로 저장
>- SQL을 사용하여 데이터를 조회/수정/삭제
>- JOIN, 정규화, 트랜잭션(ACID) 같은 특징이 있음
>- 예: MySQL, PostgreSQL, Oracle, SQL Server 등

</br>

# RDS (Relational Database Service)
> AWS에서 RDB를 쉽게 쓸 수 있도록 해주는 서비스
>- RDB를 직접 설치하지 않아도 AWS가 대신 관리해줌
>- 백업, 패치, 장애 복구, 스토리지 확장 등을 자동으로 해줌
>- 예: RDS for MySQL, RDS for PostgreSQL, RDS for Oracle

📌 쉽게 말하면:

> RDB = 자동차
>
>RDS = 그 자동차를 AWS에서 세차도 해주고, 기름도 넣어주는 서비스


<br>

# DynamoDB
> AWS의 NoSQL (비관계형) 데이터베이스 서비스
>- 테이블 구조이긴 하지만 JOIN이나 정규화 X
>- 키-값 기반, 매우 빠른 읽기/쓰기 처리
>- 자동 확장, 자동 백업, 서버 없음 (서버리스)
>- JSON 같은 유연한 형식도 저장 가능



### 요약
> RDB: 데이터 저장 방식의 개념 (SQL, 테이블 구조 등)
>
> RDS: AWS에서 RDB를 관리형으로 제공하는 서비스
>
> DynamoDB: AWS의 NoSQL 서비스 (관계형 아님)
