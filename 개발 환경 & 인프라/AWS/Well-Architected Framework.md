# AWS Well-Architected Framework

## 1. 개요
- AWS에서 권장하는 **클라우드 아키텍처 설계 원칙** 모음
- 안정성, 보안, 효율성, 비용 최적화 등을 고려해 **Best Practice**를 제공
- Well-Architected Tool을 사용하여 워크로드를 점검하고 개선 사항을 제안받을 수 있음

---

## 2. 6가지 핵심 원칙 (Pillars)

### 1) Operational Excellence (운영 우수성)
- 시스템 운영을 자동화하고 지속적으로 개선
- 모니터링, 이벤트 대응, 코드 기반 인프라 관리(IaC)

### 2) Security (보안)
- 데이터 보호, 권한 최소화(Least Privilege), 보안 이벤트 추적
- IAM, CloudTrail, KMS, GuardDuty 같은 서비스 활용

### 3) Reliability (신뢰성)
- 시스템이 장애나 중단에도 복구 가능해야 함
- Auto Scaling, Multi-AZ, 백업/복구 전략

### 4) Performance Efficiency (성능 효율성)
- 리소스를 효율적으로 사용해 성능 최적화
- 최신 인스턴스 타입, 서버리스, 캐싱, 글로벌 리전 활용

### 5) Cost Optimization (비용 최적화)
- 불필요한 리소스 제거, 적절한 요금제 선택
- RI/Savings Plans, S3 Storage Class 최적화

### 6) Sustainability (지속 가능성) ★신규
- 친환경적 설계, 에너지 효율 고려
- 리소스 최적화로 탄소 배출 최소화

---

## 3. 왜 중요한가?
- 아키텍처 품질을 객관적으로 점검 가능
- 보안/규정 준수/비용 문제를 사전에 예방
- 클라우드 활용 최적화 → **비용 절감 + 안정성 강화**

---

## 4. 비유
- 건축물 안전 점검 매뉴얼처럼, 클라우드 시스템을 점검하는 **체크리스트**
- 건물을 설계할 때 기초공사, 전기, 배관, 안전 설비를 확인하듯,
  클라우드도 Well-Architected 원칙에 맞게 점검해야 함
