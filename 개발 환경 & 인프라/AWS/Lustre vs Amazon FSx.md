# Lustre vs Amazon FSx 정리

## 1. Lustre
- **정의**: 오픈소스 기반의 병렬 분산 파일 시스템 (Parallel File System).
- **특징**:
  - 초고성능 I/O 처리 (수십~수백 GB/s 이상).
  - 병렬 I/O 지원 → 수천 개 노드가 동시에 접근 가능.
  - HPC(High Performance Computing), 머신러닝, 미디어 렌더링, 금융 모델링 등에 사용.
- **단점**:
  - 직접 설치/운영해야 함 → 관리 복잡.
  - 유지보수 및 패치 부담이 큼.

---

## 2. Amazon FSx
- **정의**: AWS에서 제공하는 완전관리형 파일 스토리지 서비스.
- **종류**:
  1. **FSx for Windows File Server**
     - SMB(Windows 네이티브 프로토콜) 지원.
     - Active Directory와 통합 가능.
     - 기업용 파일 공유, 홈 디렉토리 등에 적합.
  2. **FSx for Lustre**
     - 오픈소스 Lustre를 AWS가 완전관리형으로 제공.
     - HPC, 머신러닝, 게임, 미디어 처리 등 고성능 워크로드에 최적.
     - Amazon S3와 네이티브 통합.
  3. **FSx for NetApp ONTAP**
     - NetApp ONTAP 파일 시스템을 관리형으로 제공.
     - Snapshot, 클론, 데이터 중복 제거 등 고급 기능 지원.
  4. **FSx for OpenZFS**
     - ZFS 파일 시스템 기반.
     - 스냅샷, 복제 등 데이터 관리 기능 제공.

---

## 3. Lustre vs FSx for Lustre

| 구분 | **Lustre (오픈소스)** | **FSx for Lustre (AWS 관리형)** |
|------|-----------------------|--------------------------------|
| 관리 | 직접 설치/운영 필요 | AWS 완전관리형 |
| 성능 | 초고성능 병렬 파일 시스템 | 동일하게 HPC급 성능 제공 |
| 통합성 | 별도 설정 필요 | Amazon S3와 네이티브 통합 |
| 사용 사례 | 슈퍼컴퓨터, 금융 시뮬레이션 | HPC, 머신러닝, 게임, 미디어 처리 |
| 운영 복잡성 | 높음 | 낮음 (AWS 관리) |

---

## 4. 한 줄 정리
- **Lustre** = 오픈소스 기반 초고성능 파일 시스템 (직접 운영).  
- **Amazon FSx for Lustre** = AWS가 Lustre를 완전관리형으로 제공 → 운영 부담 최소화.
