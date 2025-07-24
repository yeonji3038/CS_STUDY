# AWS Systems Manager Session Manager

### 🔐 장점
- **SSH 포트 개방 불필요 (22번 포트 X)**
- **IAM 역할로 접근 제어** (세분화된 권한 설정 가능)
- 접근 로그를 **CloudTrail 및 S3로 기록 가능**
- **Bastion Host 불필요**, 네트워크 보안 간소화
- VPC, 퍼블릭 IP 없이도 **프라이빗 서브넷 인스턴스에 접속 가능**

### 🛠️ 구성 요소
- SSM Agent: EC2에 기본 설치 (Amazon Linux 2 이상)
- IAM 역할: `AmazonSSMManagedInstanceCore` 권한 포함
- Systems Manager 콘솔 또는 AWS CLI로 접속

---

## 🧱 비교: SSH vs Session Manager

| 항목                  | SSH                             | Session Manager (SSM)             |
|-----------------------|----------------------------------|-----------------------------------|
| 네트워크 포트         | 22번 포트 개방 필요             | 포트 개방 필요 없음               |
| 키 관리               | SSH 키 관리 필요                | IAM 권한 기반 접근                |
| 운영 오버헤드         | 키 배포, 보안 관리 필요         | IAM 역할만 설정                   |
| 로그 기록             | 직접 설정 필요 (예: syslog)     | CloudTrail + S3 연동 가능         |
| 접근 위치 제한 가능   | 보통 Security Group으로 제한     | IAM 정책 + IP 제약으로 정밀 제어  |

---