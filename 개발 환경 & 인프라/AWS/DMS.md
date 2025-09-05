# AWS DMS (Database Migration Service)
- DB를 다른 엔진/동일 엔진으로 마이그레이션하는 서비스.
- **Change Data Capture (CDC)** 기능 지원 → 소스 DB 변경 사항을 대상 DB에 실시간 반영.
- 다운타임 최소화 가능.
- 일반적으로 SCT(AWS Schema Conversion Tool)와 함께 사용.
  - 서로 다른 DB 엔진 간 마이그레이션 (예: Oracle → PostgreSQL)일 때 필요.
  - 같은 엔진(PostgreSQL → Aurora PostgreSQL)일 때는 SCT 불필요