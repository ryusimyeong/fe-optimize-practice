# fe-optimize-practice

항해플러스 FE 3기 7팀 류시명

## 프론트엔드 배포 파이프라인

### 개요

<img width="625" alt="스크린샷 2024-11-20 11 46 34" src="https://github.com/user-attachments/assets/c9ecd8d8-ab9f-4c9b-af01-76ff1e509810">

1. 저장소 체크아웃
2. Node.js 18.x 버전 설정
3. origin master 브랜치에 push
4. 프로젝트 의존성 설치
5. Next.js 프로젝트 빌드
6. AWS 자격 증명 구성
7. 빌드된 파일 S3 버킷에 동기화(out 디렉토리 내 모든 파일)
8. CloudFront 캐시를 무효화

### 주요 링크

- S3 버킷 웹사이트 엔드포인트: http://hanghaeplus-optimize-fe.s3-website-ap-southeast-1.amazonaws.com/
- CloudFrount 배포 도메인 이름: d2iuoptgpn1j56.cloudfront.net

### 주요 개념

- GitHub Actions과 CI/CD 도구:
- S3와 스토리지:
- CloudFront와 CDN:
- 캐시 무효화(Cache Invalidation):
- Repository secret과 환경변수:

### 성능 최적화 보고서

#### CDN 연결 전(S3 버킷 웹사이트 엔드포인트로 접근)

<img width="698" alt="스크린샷 2024-11-20 14 48 07" src="https://github.com/user-attachments/assets/f8932d45-b14c-472f-97b7-3228ff115315">

#### CDN 연결 후(CloudFrount 배포 도메인으로 접근)

<img width="695" alt="스크린샷 2024-11-20 14 48 14" src="https://github.com/user-attachments/assets/73061673-4b74-4c92-ac5d-0c246e624c40">

- CDN을 통해 캐싱된 소스코드를 가져오기 때문에 HTML 및 이미지 파일 다운로드가 매우 빨라진 것을 확인할 수 있다.
