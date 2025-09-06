# AWS Glue 정리

## 1. 개요
- **AWS Glue**는 서버리스 데이터 통합 서비스.
- **기능**: 데이터 추출(Extract), 변환(Transform), 적재(Load) → ETL 파이프라인 구축.
- **주요 특징**:
  - 서버리스: 인프라 관리 필요 없음.
  - 다양한 소스 지원: Amazon S3, RDS, Redshift, DynamoDB 등.
  - 자동 스키마 추론, 데이터 카탈로그 생성 가능.
  * .csv, parquet 변환 적합

---

## 2. 주요 구성 요소
1. **Glue Data Catalog**
   - 메타데이터 저장소 (테이블 정의, 스키마, 파티션 정보).
   - 다른 AWS 분석 서비스(Athena, Redshift Spectrum 등)와 공유 가능.
2. **Crawler**
   - 데이터 소스를 스캔해 자동으로 스키마와 테이블 정의 생성.
3. **Jobs**
   - ETL 코드 실행 단위.
   - PySpark 또는 Scala 기반으로 동작.
4. **Triggers**
   - 일정 스케줄 또는 이벤트 기반으로 Job 실행.
5. **Development Endpoints**
   - 사용자 정의 코드 작성 및 디버깅 가능.

---

## 3. Glue 사용 사례
- 데이터 레이크 구축 및 관리.
- 로그/트랜잭션 데이터 수집 후 정제.
- 머신러닝 파이프라인 전처리.
- 실시간 또는 배치 ETL 작업 자동화.

---
