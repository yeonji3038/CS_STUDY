# Amazon EKS (Elastic Kubernetes Service)

## 개요
- Amazon EKS는 AWS에서 제공하는 **관리형 Kubernetes 서비스**.
- Kubernetes(K8s) = 오픈소스 컨테이너 오케스트레이션 플랫폼.
- EKS는 AWS가 Kubernetes **제어 플레인(Control Plane)** 을 대신 관리 → 사용자는 애플리케이션 배포/운영에 집중 가능.

---

## 주요 특징
- **관리형 Kubernetes**  
  → 제어 플레인(마스터 노드) 자동 관리 (확장, 업그레이드, 고가용성).  
- **EC2 또는 Fargate에서 실행 가능**  
  → 워커 노드를 EC2로 직접 운영하거나, 서버리스 Fargate에서 실행 가능.  
- **멀티 리전/멀티 AZ 지원**  
  → 고가용성과 내결함성 제공.  
- **AWS 통합**  
  → IAM, VPC, CloudWatch, ALB/NLB와 통합되어 보안 및 관리가 쉬움.  

---

## 핵심 개념
- **Cluster**: Kubernetes 자원 실행 환경.  
- **Node**: 컨테이너 실행 서버 (EC2 또는 Fargate).  
- **Pod**: Kubernetes에서 실행되는 컨테이너 최소 단위.  
- **Deployment**: Pod를 정의하고 자동 확장/롤백 관리.  
- **Service**: Pod에 네트워크 접근을 제공하는 추상화 계층 (Load Balancer 연동 가능).  

---

## 실행 옵션
1. **EKS on EC2**
   - 워커 노드 = EC2 인스턴스.
   - 사용자가 인스턴스 관리, 비용은 온디맨드/리저브/스팟 선택 가능.

2. **EKS on Fargate**
   - 서버리스 모드.
   - 인프라 관리 불필요, Pod 단위 과금.
   - 운영 오버헤드 최소화.

---

## 장점
- 쿠버네티스 생태계 활용 가능 (Helm, Istio 등).
- AWS 관리형 서비스라 제어 플레인 운영 부담 없음.
- EC2/Spot/Fargate 등 다양한 비용 최적화 선택 가능.
- 보안(IAM, VPC)과 관측(CloudWatch, CloudTrail) 완전 통합.

---

## 사용 사례
- 마이크로서비스 아키텍처 운영.
- 멀티 클라우드 또는 하이브리드 환경에서 Kubernetes 활용.
- ML 워크로드, 데이터 처리, 이벤트 기반 앱 실행.
- 컨테이너 기반 CI/CD 파이프라인.

---

## 비교 (ECS vs EKS vs Fargate)
| 항목            | ECS                           | EKS                                | Fargate                        |
|-----------------|-------------------------------|------------------------------------|--------------------------------|
| 오케스트레이션   | AWS 독자적                    | Kubernetes (오픈소스 표준)           | ECS/EKS 워크로드 실행 모드     |
| 제어 플레인 관리 | AWS 자동 관리                 | AWS 자동 관리                      | AWS 자동 관리                  |
| 워커 노드        | EC2/Fargate                   | EC2/Fargate                        | 없음 (서버리스)                |
| 학습 곡선        | 낮음 (단순)                   | 높음 (Kubernetes 개념 필요)         | 가장 낮음                      |
| 사용 사례        | AWS 전용, 단순 앱             | 쿠버네티스 생태계 활용, 멀티 클라우드 | 서버리스 단순 워크로드          |

---

## 시험 포인트
- "쿠버네티스 기반, 오픈소스 호환 필요" → **EKS**  
- "운영 단순화, AWS 전용, 빠른 배포" → **ECS**  
- "서버리스 컨테이너 실행" → **Fargate (ECS/EKS 실행 모드)**  
