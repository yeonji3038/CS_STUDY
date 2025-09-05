# Origin Access Identity (OAI)

## 개요
- **OAI (Origin Access Identity)** 는 Amazon CloudFront에서 S3 버킷에 접근할 때 사용하는 **가상 사용자(virtual user)**.
- CloudFront 배포와 연결되며, S3 버킷 정책에서 이 OAI에만 권한을 주어 **직접 S3 URL 접근을 차단**할 수 있음.
- 즉, "S3 퍼블릭 접근 차단 + CloudFront를 통한 보안 배포"를 구현하는 핵심 기능.

---

## 왜 필요한가?
- 기본적으로 S3 객체는 퍼블릭 URL로 직접 접근 가능.
- 회사 보안 요구사항: 
  - 모든 콘텐츠는 **CloudFront 배포를 통해서만 접근**해야 함.
  - 사용자가 직접 S3 URL(`https://s3.amazonaws.com/bucket/file`)로 접근하는 것을 차단해야 함.
- 이를 위해 **OAI를 사용해 CloudFront만 접근 허용**.

---

## 동작 방식
1. OAI 생성.
2. CloudFront 배포와 OAI를 연결.
3. S3 버킷 정책 수정:
   - 퍼블릭 접근 차단.
