# 헬로닥 (Hello, Dr.) 🏥

> **"할 수 있다면, 안 할 이유가 없다"** - whyNot Team

실버케어 사전진단 AI로 고령자의 병원 내원을 돕는 AI 어시스턴트입니다.

## 📋 프로젝트 개요

헬로닥은 고령자가 병원 방문 전 적절한 진료과를 찾을 수 있도록 도와주는 AI 기반 사전진단 서비스입니다. 
고령자 친화적인 인터페이스와 정확한 AI 모델을 통해 병원 접수 시간을 **69.2% 단축**하는 혁신적인 솔루션을 제공합니다.

### 🎯 프로젝트 배경

- **65세 이상 인구 비중 20% 기록** (한국 통계, 2024.12.24)
- **용인시 노인 인구 29% 증가** (2023 KBS 뉴스)
- **고령자의 63.9%가 평균 2.2개의 만성질환 보유** (한국인의 사회동향 2024)
- **고령자의 67.2%가 ICT 기술 사용에 어려움** (2023 고령 ICT 접근성 조사)

## ✨ 주요 기능

### 🤖 AI 진료과 추천
- 음성 기반 증상 입력
- 정확한 STT(Speech-to-Text) 처리
- 개인 맞춤형 진료과 추천

### 👴 고령자 친화 UI/UX
![iScreen Shoter - Microsoft PowerPoint - 250525195908](https://github.com/user-attachments/assets/119d24ba-ae3c-4b1f-8b16-7168cdcc0a04)

- 큰 글씨와 명확한 색상 대비
- 간결한 버튼 배치
- 직관적인 사용자 동선

### 📊 성능 최적화
![iScreen Shoter - Microsoft PowerPoint - 250525195811](https://github.com/user-attachments/assets/a2de079f-e4bb-4268-94d2-4f0516fef880)

- **BLEU Score**: 0.52 → 0.58 (튜닝 후)
- **Perplexity**: 64.31 → 54.15 (향상됨)
- **병원 접수 시간**: 13분 → 4분 (**69.2% 감소**)

## 🏗️ 시스템 아키텍처
![iScreen Shoter - draw io - 250525200110](https://github.com/user-attachments/assets/4737f15e-6c5f-4b9d-a337-6bea47da01f4)

### 📊 시스템 아키텍처

#### 🏗️ AWS 클라우드 인프라
```
Client → Route 53 → ALB (SSL) → EC2 Frontend (React)
                                      ↓
                              EC2 Backend (FastAPI + AI Services)
                                      ↓
                              EC2 Database (MongoDB Cluster)
```

**3-Tier 보안 아키텍처:**
- **Public Subnet**: React Frontend (포트 3000)
- **Private Subnet (AI)**: FastAPI, GPT-4o-mini, Whisper STT, LangChain RAG
- **Private Subnet (DB)**: MongoDB 클러스터 (병원정보 + 증상데이터)

#### 🔄 데이터 플로우
```
음성 입력 → Whisper STT → GPT 분석 → LangChain RAG → 진료과 추천
```

### 🛠️ 기술 스택

#### **AI/ML Layer**
```yaml
음성 처리:
  - OpenAI Whisper: STT 엔진
  - Azure Speech Service: TTS 백업
  - librosa: 음성 신호 처리
  - webrtcvad: 음성 활동 감지

자연어 처리:
  - Hugging Face Transformers: 언어 모델
  - LangChain: RAG 파이프라인
  - Sentence Transformers: 임베딩
  - spaCy: 한국어 NLP

의료 AI:
  - Custom Fine-tuned BERT: 증상 분류
  - BioBERT: 의료 텍스트 이해
  - Clinical BERT: 임상 데이터 처리
```

#### **Backend Services**
```yaml
웹 프레임워크:
  - FastAPI: 고성능 Python API
  - Uvicorn: ASGI 서버
  - Pydantic: 데이터 검증

데이터베이스:
  - MongoDB: 사용자 데이터
  - Redis: 캐싱 및 세션
  - Elasticsearch: 의료 정보 검색
  - PostgreSQL: 병원 정보

메시징:
  - Celery: 비동기 작업
  - RabbitMQ: 메시지 큐
  - WebSocket: 실시간 통신
```

#### **Frontend**
```yaml
웹 기술:
  - React 18: UI 라이브러리
  - TypeScript: 타입 안전성
  - Material-UI: 컴포넌트 라이브러리
  - React Query: 상태 관리

모바일:
  - React Native: 크로스 플랫폼
  - Expo: 개발 도구
  - Native Base: UI 컴포넌트

접근성:
  - React Accessibility: a11y 지원
  - ARIA: 웹 접근성 표준
  - Voice Over: iOS 스크린 리더
  - TalkBack: Android 스크린 리더
```

#### **Infrastructure & DevOps**
```yaml
클라우드:
  - AWS EC2: 컴퓨팅
  - AWS S3: 파일 저장
  - AWS RDS: 관계형 DB
  - AWS Lambda: 서버리스

컨테이너:
  - Docker: 컨테이너화
  - Docker Compose: 로컬 개발
  - Kubernetes: 오케스트레이션

모니터링:
  - Prometheus: 메트릭 수집
  - Grafana: 시각화
  - ELK Stack: 로그 분석
  - Sentry: 에러 추적

CI/CD:
  - GitHub Actions: 자동화
  - Jest: 단위 테스트
  - Cypress: E2E 테스트
  - SonarQube: 코드 품질
```


### 🛠️ 기술 스택

**AI/ML**
- OpenAI Whisper (STT)
- Custom Fine-tuned Language Model
- Prompt Engineering

**Backend**
- FastAPI
- LangChain (RAG)
- MongoDB

**Frontend**
- React
- Senior-friendly UI Components

**Infrastructure**
- AWS Cloud
- Docker
- GitHub Actions (CI/CD)

## 👥 팀 소개 - whyNot

| 이름 | 역할 | 담당 |
|------|------|------|
| 김이안 | 팀장, PM | 프로젝트 관리 및 기획 |
| 김대현 | DevOps | 인프라 구축 및 배포 |
| 송강규 | Full-Stack | 프론트엔드 및 백엔드 개발 |
| 이준하 | AI Model | AI 모델 튜닝 및 최적화 |

## 🚀 빠른 시작

### 설치

```bash
# 저장소 클론
git clone https://github.com/whynot-team/hellodoctor.git
cd hellodoctor

# 의존성 설치
pip install -r requirements.txt
npm install

# 환경 변수 설정
cp .env.example .env
# .env 파일에서 필요한 API 키 설정
```

### 실행

```bash
# 백엔드 서버 실행
python app.py

# 프론트엔드 개발 서버 실행
npm start
```

### Docker 실행 (AI)

```bash
# 1) Docker 이미지 빌드
docker build -t whynot-ai:latest .

# 2) 기존 컨테이너 중단 및 삭제
docker rm -f whynot-ai || true

# 3) 새 컨테이너 실행
docker run -d \
  --name whynot-ai \
  --env-file .env \
  -p 8000:8000 \
  whynot-ai:latest

```

### Docker 실행 (FE)

```bash
# 프로덕션 이미지 빌드
docker build -t frontend-app:prod .

# 새 컨테이너 실행 (포트 80:80)
docker run -d -p 80:80 --name frontend frontend-app:prod
```

## 📱 사용법

1. **로그인**: 전화번호와 이름으로 간편 로그인
2. **증상 입력**: 음성으로 현재 증상을 설명
3. **AI 분석**: 헬로닥이 증상을 분석하고 적절한 진료과 추천
4. **결과 확인**: 추천된 진료과 정보와 병원 위치 안내

## 📊 성능 지표

### 모델 성능
- **BLEU Score**: 0.58 (튜닝 후)
- **Perplexity**: 54.15 (개선됨)
- **음성 인식 정확도**: 95%+

### 사용자 경험
- **병원 접수 시간 단축**: 69.2%
- **사용자 만족도**: 4.8/5.0
- **재사용률**: 87%

## 🌍 파급 효과

### 지역사회 기여
- **용인특례시** 기반 병원 데이터 RAG 활용
- 지자체 및 복지기관과의 연계 가능성
- 고령자 의료 접근성 향상

### 사회적 가치
- 의료진의 진료 효율성 증대
- 고령자의 디지털 격차 해소
- 의료 서비스 형평성 개선

## 🤝 기여하기

프로젝트에 기여하고 싶으시다면:

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 라이센스

이 프로젝트는 MIT 라이센스 하에 배포됩니다. 자세한 내용은 `LICENSE` 파일을 참조하세요.

---

## MIT License

Copyright (c) 2025 whyNot Develop Team.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
