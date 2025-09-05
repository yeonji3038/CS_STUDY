# Amazon AppFlow

## 1. 개요
- Amazon AppFlow는 **SaaS 애플리케이션과 AWS 서비스 간 데이터 통합을 자동화**하는 완전관리형 서비스.
- 코드 작성 없이도 Salesforce, ServiceNow, Slack, Zendesk 같은 SaaS 앱과 AWS(S3, Redshift 등) 간에 안전하게 데이터를 주고받을 수 있음.
- 대량의 데이터를 **실시간 혹은 배치 처리 방식**으로 전송 가능.

---

## 2. 주요 특징
1. **양방향 데이터 전송**
   - SaaS → AWS (예: Salesforce 데이터를 S3로)
   - AWS → SaaS (예: Redshift 데이터를 Salesforce로)

2. **보안**
   - 데이터는 전송 중 자동 암호화
   - VPC 엔드포인트 지원 → 인터넷을 거치지 않고 내부 네트워크에서 데이터 이동 가능

3. **데이터 변환**
   - 흐름(Flow) 정의 시 데이터 매핑, 필터링, 마스킹 가능
   - 예: 개인정보(PII) 필드 제거 후 저장

4. **확장성**
   - 몇 건의 데이터부터 수백만 건의 이벤트까지 자동 확장
   - 별도의 서버/코드 관리 불필요

5. **이벤트 기반 실행**
   - SaaS 애플리케이션 내 이벤트 발생 시 데이터 자동 이동
   - 예: Zendesk 티켓 생성 시 S3에 로그 저장

---

## 3. 주요 사용 사례
1. **데이터 레이크 구축**
   - Salesforce/Slack/Google Analytics 데이터를 S3로 수집 → 중앙 데이터 레이크 생성
2. **분석 및 BI**
   - SaaS 데이터를 Amazon Redshift로 전송 후 QuickSight로 시각화
3. **보안 및 컴플라이언스**
   - SaaS에서 수집한 데이터를 S3로 아카이빙 → 장기 보관/규정 준수
4. **운영 자동화**
   - Zendesk, ServiceNow 알림 데이터를 AWS 서비스로 연계하여 자동 대응

---

## 4. 지원되는 주요 SaaS 소스
- Salesforce
- ServiceNow
- Slack
- Zendesk
- SAP
- Google Analytics
- Marketo
- 기타 다수 (지속적으로 확장 중)

---

## 5. 장점
- 코드 작성 없이 빠른 통합 가능 (No-code/Low-code)
- 확장성과 보안 내장
- 데이터 전송 중 자동 암호화 및 VPC 엔드포인트 지원
- 이벤트 기반 및 배치 모두 지원

---

## 6. 단점
- 지원되는 SaaS 애플리케이션 종류가 제한적 (점차 확대 중)
- 매우 복잡한 ETL 파이프라인은 AWS Glue 같은 다른 서비스 필요
- 사용량이 많을 경우 비용 증가 가능

---

## 7. 정리
- **Amazon AppFlow = SaaS ↔ AWS 데이터 전송 자동화 서비스**
- 서버리스, 코드리스, 보안 내장
- SaaS 데이터를 **S3, Redshift, DynamoDB 등으로 손쉽게 이동**해 분석 및 저장 가능
