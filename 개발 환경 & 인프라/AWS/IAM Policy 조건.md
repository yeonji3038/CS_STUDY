# IAM Policy 조건 관련 개념 정리

## 1. 정책 평가 논리
- **기본 규칙**: Explicit Deny > Allow > Default Deny
- 여러 Statement가 적용될 경우, 조건을 모두 평가한 뒤 최종 권한 결정.

---

## 2. Condition 연산자
- **IpAddress**: 특정 IP 대역에서만 허용.
  ```json
  "Condition": { "IpAddress": { "aws:SourceIp": "10.100.100.0/24" } }

---

## 3. StringNotEquals: 특정 값이 아닐 경우 거부.

    ```json
    "Condition": { "StringNotEquals": { "ec2:Region": "us-east-1" } }



---

{
  "Effect": "Deny",
  "Action": "ec2:*",  -> 모든 EC2 거부
  "Resource": "*",
  "Condition": {
    "StringNotEquals": { "ec2:Region": "us-east-1" }   -> us-east-1  여기서 만 가능
  }
}
