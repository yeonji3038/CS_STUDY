#  Bucket Policy(버킷 정책)# AWS S3 Bucket Policy 정리

> - **S3 버킷 단위로 적용되는 리소스 기반 정책(Resource-based Policy)**.
> - 특정 **사용자, 역할, VPC 엔드포인트, 계정, 서비스**가 버킷과 객체에 접근할 수 있는 권한을 정의.
> - JSON 문서 형식으로 작성.

---

## 2. 주요 특징
- **리소스 기반 정책**: IAM User/Role에 붙는 것이 아닌, **S3 버킷 자체에 붙음**.
- **퍼블릭 액세스 제어 가능**: `Principal: *` → 전체 인터넷 사용자 허용 (주의 필요).
- **조건(Condition) 지원**: IP 제한, VPC 엔드포인트 제한, 암호화 요구 등 세부 제어 가능.

---

## 3. 구성 요소
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow" | "Deny",
      "Principal": "누가 접근 가능한가 (AWS 계정, IAM User/Role, 서비스)",
      "Action": "s3:GetObject / s3:PutObject / s3:*",
      "Resource": "arn:aws:s3:::버킷이름/경로/*",
      "Condition": { "조건 키": "값" }
    }
  ]
}
