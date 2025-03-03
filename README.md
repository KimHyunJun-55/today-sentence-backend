
## 🏗️ 아키텍처 개요  
오늘의 명언 백엔드 시스템의 전체적인 구조를 나타낸 다이어그램입니다.  
**CI/CD 자동화, AWS 클라우드 인프라, Docker 기반 컨테이너 운영, 모니터링 시스템**을 포함하고 있습니다..  
<details>
<summary>프로젝트 아키텍처(클릭해서 보기)</summary>
  
 ![Image](https://github.com/user-attachments/assets/8c780ac6-1ac2-4958-94f9-d2da3b5a342d)
 
</details>

---

## 🛠️ 기술 스택
| 분류          | 기술 스택 |
|--------------|------------------------------------------------|
| **언어**      | Java 17, Spring Boot 3.4.0 |
| **CI/CD**    | GitHub Actions, Docker Hub |
| **서버**      | AWS EC2, Amazon RDS |
| **컨테이너**  | Docker, Docker Compose |
| **웹 서버**  | Nginx |
| **캐시**      | Redis |
| **보안**      | Spring Security |
| **모니터링**  | Prometheus, Grafana |
| **로깅**      | Loki |

---

## ⚙️ **서버 인프라 구성**
- **AWS EC2**: 애플리케이션이 실행되는 서버  
- **Amazon S3**: 파일 저장소  
- **Amazon RDS**: 데이터베이스 (MySQL)  
- **Docker & Docker Compose**: 컨테이너화된 서비스 운영  

---

## 🔄 **CI/CD 파이프라인**
### 1️⃣ **개발 브랜치 전략**
- `main` → **CI/CD (자동 배포)**
- `develop` → **CI (빌드 및 테스트)**
- `featureBranch` → **새로운 기능 개발**

### 2️⃣ **배포 과정**
1. `develop` 브랜치에서 코드 푸시 시 **CI (빌드 및 테스트)** 실행  
2. `main` 브랜치로 머지되면 **CI/CD 실행 → `.jar` 파일 빌드 → Docker Hub로 푸시**  
3. AWS EC2에서 **Docker Compose로 컨테이너 실행 및 배포**  

---
