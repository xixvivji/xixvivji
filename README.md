# 김지원 (xixvivji)

Backend · Infra · AI Serving

Java/Spring Boot 기반 백엔드 개발자입니다. API 구현에서 끝내지 않고, 캐싱·실시간 처리·배포 자동화·운영 장애 진단까지 서비스가 실제로 안정적으로 동작하는 구조를 고민합니다.

[Email](mailto:kjw3568@naver.com) ·
[GitHub](https://github.com/xixvivji) ·
[Portfolio](https://xixvivji.github.io) ·
[Baekjoon](https://solved.ac/profile/kjw96041938)

---

## About

- Java/Spring Boot 기반으로 REST API, 인증, 데이터 모델링, 거래/상태 흐름을 구현해왔습니다.
- Redis 캐싱, WebSocket/STOMP, FCM을 활용해 반복 요청과 실시간 알림 흐름을 개선했습니다.
- Docker, Nginx, Jenkins, AWS EC2 기반으로 배포 자동화와 운영 환경 문제 해결을 경험했습니다.
- AI 서비스에서는 데이터 수집/라벨링, 모델 개선, 추론 서버 폴백 구조까지 함께 설계했습니다.

---

## Tech Stack

- **Backend**: Java, Spring Boot, JPA, Spring Security, JWT
- **Database / Cache**: MySQL, PostgreSQL, Redis
- **Realtime / Messaging**: WebSocket, STOMP, RabbitMQ, FCM
- **Infra / DevOps**: AWS EC2, AWS S3, Docker, Nginx, Jenkins
- **AI / Data**: Python, FastAPI, PyTorch, YOLOv11, SegFormer

---

## Featured Projects

### MUNG! - 유기견 입양·사후관리 통합 플랫폼

- 기간/인원: 2026.01 - 2026.02 · 6명
- 역할: Backend 30%, Infra/DevOps 100%
- Repo: [xixvivji/mung-shall](https://github.com/xixvivji/mung-shall)
- Stack: Spring Boot, JPA, MySQL, Docker, Nginx, Jenkins, OpenVidu
- 입양 신청부터 단계 승인, 체크리스트, 사후관리, 화상 상담까지 하나의 프로세스로 연결한 플랫폼입니다.
- 입양 단계를 `Enum` 기반 상태 모델로 설계하고, 보호소/입양자/관리자 권한을 분리했습니다.
- OpenVidu를 별도 EC2에서 운영하고 Nginx 경로 기반 라우팅으로 Spring Boot API와 WebRTC 트래픽을 분리했습니다.
- Jenkins 파이프라인, Docker Compose 배포, Prometheus/Grafana 모니터링을 구성했습니다.

### Z멋대로 - 숏폼 기반 AI 투자·그룹 공동 투자 플랫폼

- 기간/인원: 2026.03 - 2026.04 · 6명
- 역할: Backend / Infra
- Repo: [xixvivji/z-invest](https://github.com/xixvivji/z-invest)
- Stack: Spring Boot, JPA, PostgreSQL, Redis, WebSocket/STOMP, FCM
- 숏폼 투자 피드, AI 종목 리포트, 개인 투자 관리, 그룹 공동 투자, 실시간 주식 정보를 제공하는 투자 플랫폼입니다.
- KIS 주식 API 연동, 시세 스케줄링, 매수/매도 거래 흐름, 주문/보유/관심종목 DB 구조를 구현했습니다.
- Redis TTL 캐싱으로 주요 조회 API 응답 속도를 약 480ms에서 90ms 수준으로 개선했습니다.
- FCM 푸시 알림과 실시간 데이터 흐름을 연동하고, 반복 Polling 구조를 WebSocket/STOMP 기반 Push 구조로 전환했습니다.

### LUMEN / SmartCane - AI 기반 시각장애인 보행 안전 서비스

- 기간/인원: 2026.04 - 2026.05 · 6명
- 역할: AI 모델·데이터·인프라
- Repo: [xixvivji/C102_LUMEN_PROJECT](https://github.com/xixvivji/C102_LUMEN_PROJECT)
- Stack: Python, PyTorch, YOLOv11, SegFormer, Spring Boot, Redis, Docker
- 카메라 기반으로 보도, 차도, 점자블록, 횡단보도, 신호등, 장애물 등 보행 위험 요소를 감지하고 음성/햅틱 피드백을 제공하는 서비스입니다.
- 야간, 역광, 측면 환경에서 성능이 낮아지는 원인을 데이터 편중으로 보고 12,000장 이상의 실환경 이미지를 수집·라벨링했습니다.
- YOLOv11 기반 재학습으로 mAP@0.5를 0.41에서 0.78 수준으로 개선했습니다.
- SegFormer 기반 보행 환경 분류와 YOLO 객체 탐지 결과를 조합해 보행 판단 파이프라인을 구성했습니다.
- 고사양 기기는 온디바이스 추론, 저사양 기기는 EC2 추론 서버로 폴백하는 이중 추론 구조를 설계했습니다.

### Fintech Mock Investing Platform - 리그형 모의투자 서비스

- Repo: [xixvivji/fintech-project](https://github.com/xixvivji/fintech-project)
- Stack: Spring Boot, JPA, PostgreSQL, Redis, RabbitMQ, WebSocket
- 공용 리그 날짜를 기준으로 과거 시세를 리플레이하며 여러 사용자가 같은 시점에서 경쟁하는 모의투자 서비스입니다.
- 시장가/지정가 주문, 체결내역, 미체결 주문, 보유 종목, 수익률 랭킹, 리그 운영 상태를 구현했습니다.
- 외부 KIS API 의존을 줄이기 위해 `daily_price` DB 캐시 구조와 요청 범위 커버 검사를 도입했습니다.
- `2015-01-01 ~ 2025-12-31` 일봉 데이터를 선적재하는 백필 API와 PowerShell 자동화 스크립트를 구성했습니다.
- 백필 결과 예시 기준 50개 종목, 124,982 rows 데이터를 적재했습니다.

---

## Problem Solving

- 운영 환경 이슈를 네트워크, 보안 그룹, 프록시, 포트, 인증서 흐름으로 분리해 진단합니다.
- 반복 요청과 지연이 발생하는 API는 Redis 캐싱, Push 전환, 비동기 큐를 기준으로 개선합니다.
- 배포 중단 리스크를 낮추기 위해 Docker Compose, Jenkins, Nginx 기반 배포 자동화를 설계합니다.
- AI 서비스는 모델 변경보다 데이터 품질, 추론 위치, 폴백 전략까지 함께 고려합니다.

---

## Stats

<p align="center">
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=xixvivji&theme=tokyonight" alt="GitHub profile summary" />
</p>

<p align="center">
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=xixvivji&theme=tokyonight" height="160" alt="GitHub stats" />
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=xixvivji&theme=tokyonight" height="160" alt="Repos per language" />
</p>

## Baekjoon

<p align="center">
  <a href="https://solved.ac/profile/kjw96041938">
    <img src="https://mazassumnida.wtf/api/v2/generate_badge?boj=kjw96041938" height="150" alt="Solved.ac profile badge" />
  </a>
</p>
