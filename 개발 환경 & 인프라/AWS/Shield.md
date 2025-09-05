# AWS Shield
> **AWS Shield**는 AWS 리소스를 **DDoS(분산 서비스 거부) 공격으로부터 보호**하는 관리형 보안 서비스
>- AWS에서 DDoS 공격 방어를 위한 솔루션

---
## 🛡️ AWS Shield 종류

| 종류 | 설명 | 가격 |
|------|------|------|
| **Shield Standard** | 모든 AWS 고객에게 **기본 제공**, 네트워크/전송 계층 공격 자동 방어 | 무료 |
| **Shield Advanced** | 고급 DDoS 방어 기능, **전문 대응팀, 비용 보호, 탐지 커스터마이징 제공** | 유료 (월 $3,000+) |

---

## 🔍 Shield Advanced 주요 기능

- **Layer 3/4 뿐 아니라 Layer 7 공격 탐지**
- **ELB, CloudFront, Global Accelerator, Route 53** 등 보호 가능
- DDoS 공격 발생 시 **비용 보호 제공**
- **AWS DDoS Response Team(DDRT)**에서 실시간 대응 지원

* CloudFront + WAF 사용 -> 전세계 엣지 위치에서 공격 방어 가능(방어 효과 극대화)

---

## 🎯 사용 시나리오

| 시나리오 | 필요한 방어 솔루션 |
|----------|-------------------|
| 공개 웹 애플리케이션 + ELB 사용 | ✅ Shield Advanced + ELB 연동 |
| DNS가 Route 53인 경우 | Shield Standard도 효과적 |
| 민감한 웹서비스(DNS 포함) 보호 | Shield Advanced + Route 53 연동 |

---