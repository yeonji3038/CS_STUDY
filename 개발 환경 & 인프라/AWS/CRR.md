# Amazon S3 Cross-Region Replication (CRR)

## 개요
- **Cross-Region Replication (CRR)** 은 한 AWS 리전의 S3 버킷 데이터를 **자동으로 다른 리전의 S3 버킷으로 복제**하는 기능.
- DR(재해 복구), 지연 시간 단축, 규제 준수 등을 위해 사용.
- 버킷 간 데이터 동기화를 자동화하여 운영 오버헤드를 줄여줌.

---

## 주요 특징
1. **자동 복제**
   - 원본 버킷(Source bucket)에 새로운 객체가 업로드되면 자동으로 대상 버킷(Destination bucket)에 복제.

2. **리전 간 복제**
   - 다른 리전에 위치한 S3 버킷으로 복제 가능.
   - 예: us-east-1 → ap-northeast-2

3. **암호화 지원**
   - SSE-S3, SSE-KMS로 암호화된 객체도 복제 가능.
   - 단, KMS를 사용하는 경우 키 정책 권한이 필요.

4. **객체 수준 복제**
   - 복제 단위: 객체 단위.
   - 특정 객체만 복제하거나, 전체 버킷 복제 가능 (버킷 정책 설정).

5. **실시간**
   - 거의 실시간에 가깝게 복제되지만, 지연(latency) 발생 가능.

---

## 요구 조건
- **버전 관리(Versioning) 활성화** (Source와 Destination 모두).
- **IAM 권한**: S3가 복제를 수행할 수 있도록 권한 부여.
- 원본과 대상 버킷은 **서로 다른 리전**에 존재해야 함.

---

## 사용 사례
1. **재해 복구 (DR)**
   - 한 리전 장애 발생 시 다른 리전에 동일한 데이터 보관.
   
2. **지연 시간 단축**
   - 글로벌 사용자에게 더 가까운 리전에서 데이터 제공.

3. **규제/컴플라이언스**
   - 특정 지역 법규에 따라 데이터를 다른 리전에 보관해야 할 때.

---

## 예시 아키텍처
- **Source Bucket**: `s3://mybucket-us-east-1`
- **Destination Bucket**: `s3://mybucket-ap-northeast-2`
- 복제 규칙(CRR Policy) 설정:
  ```json
  {
    "Rules": [
      {
        "Status": "Enabled",
        "Prefix": "",
        "Destination": {
          "Bucket": "arn:aws:s3:::mybucket-ap-northeast-2"
        }
      }
    ]
  }
