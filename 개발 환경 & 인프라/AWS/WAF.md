# AWS WAF (Web Application Firewall)

## 1. 개요
- **AWS WAF**는 웹 애플리케이션 방화벽으로, 웹 애플리케이션에 대한 악의적인 요청을 필터링하고 차단하는 서비스.
- Layer 7(애플리케이션 계층)에서 동작.
- **CloudFront, Application Load Balancer(ALB), API Gateway, AppSync**와 통합 가능.

---

## 2. 주요 기능
1. **웹 공격 차단**
   - SQL Injection
   - XSS (Cross-Site Scripting)
   - 기타 OWASP Top 10 공격 유형

2. **IP 기반 필터링**
   - 허용/차단할 특정 IP 주소, CIDR 블록 지정 가능

3. **요청 속도 제어 (Rate-based Rules)**
   - 일정 시간 내 요청 횟수를 제한하여 DDoS 완화

4. **Geo Match**
   - 특정 국가/지역에서 들어오는 요청 허용/차단 가능

5. **Custom Rules**
   - HTTP 헤더, 쿼리 스트링, URI 패턴 기반 규칙 정의 가능

---

## 3. 동작 방식
1. 클라이언트 요청이 **CloudFront / ALB / API Gateway**로 들어옴  
2. 연결된 **WAF WebACL**에서 정의된 규칙에 따라 요청을 검사  
3. 규칙에 맞으면 요청을 **차단(Block) / 허용(Allow) / 카운트(Count)**  

---

## 4. 사용 시나리오 (시험 트리거)
- "모든 웹 요청을 검사해야 한다"  
- "SQL Injection/XSS 방어"  
- "특정 국가/특정 IP 차단"  
- "특정 속도로 들어오는 요청 제한 (Rate limiting)"  
- "CloudFront/ALB/API Gateway에서 보안 강화 필요"  

---

## 5. 비교
| 서비스            | 특징                                    |
|-------------------|-----------------------------------------|
| **AWS WAF**       | L7 웹 보안, 규칙 기반 필터링, SQLi/XSS 차단 |
| **Shield Standard** | 기본 DDoS 방어 (모든 AWS 고객 무료 제공) |
| **Shield Advanced** | 고급 DDoS 방어, 비용 보호, 24/7 DRT 지원 |

---

## 6. 요약
- AWS WAF = **웹 애플리케이션 보안 필터**  
- CloudFront/ALB/API Gateway와 통합해서 모든 요청 검사 가능  
- 시험에서는 "모든 요청 보안 검사" → 정답은 거의 항상 **WAF**  
