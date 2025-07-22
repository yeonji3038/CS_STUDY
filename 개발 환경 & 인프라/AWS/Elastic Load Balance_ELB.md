# AWS Elastic Load Balancer (ELB) 
> AWS에서 **트래픽을 여러 서버(EC2 등)로 자동으로 분산**시켜주는 트래픽 분산 서비스 
> 
> 고가용성, 자동 복구, 확장성 확보를 위해 필수적으로 사용

---

## 주요 역할

| 역할 | 설명 |
|------|------|
| **트래픽 분산** | 사용자 요청을 여러 EC2 인스턴스로 나눠 처리 |
| **장애 자동 감지** | 건강하지 않은 인스턴스는 자동으로 제외 |
| **확장성 향상** | Auto Scaling과 연동하여 수요에 따라 서버 자동 증가/감소 |
| **보안 강화** | WAF, SSL 인증서, Shield Advanced와 연동 가능 |
| **모니터링** | CloudWatch와 연동하여 요청 수, 지연 시간, 에러 추적 가능 |

---

## ELB의 세 가지 유형

| 유형 | 설명 | 지원 프로토콜 |
|------|------|----------------|
| **ALB (Application Load Balancer)** | L7 계층, URL/경로 기반 라우팅 | HTTP, HTTPS |
| **NLB (Network Load Balancer)** | L4 계층, 초고속 트래픽 처리 | TCP, UDP |
| **CLB (Classic Load Balancer)** | 구형, L4 + 일부 L7 기능 | HTTP, HTTPS, TCP |

---

## 🛠 사용 예시

1. 사용자가 `https://myapp.com` 접속
2. ELB가 해당 요청 수신
3. 연결된 EC2 인스턴스 중 **건강한 인스턴스에만 트래픽 전달**

---

## 통합 가능한 서비스

- **Auto Scaling**: 인스턴스 수 자동 조절
- **AWS WAF**: 웹 공격 필터링
- **AWS Shield**: DDoS 보호
- **ACM**: SSL 인증서 자동 적용
- **CloudWatch**: 요청 수, 상태 코드, 지연 시간 모니터링

---


