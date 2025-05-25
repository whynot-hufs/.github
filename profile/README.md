# 헬로닥 (Hello, Dr.) 🏥

> **"할 수 있다면, 안 할 이유가 없다"** - whyNot Team

실버케어 사전진단 AI로 고령자의 병원 내원을 돕는 AI 어시스턴트입니다.

[![Website](https://img.shields.io/badge/Website-whynot2025.com-blue)](https://whynot2025.com)
[![Hospital](https://img.shields.io/badge/Partner-용인세브란스병원-green)](https://www.yuhs.or.kr)

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
- 큰 글씨와 명확한 색상 대비
- 간결한 버튼 배치
- 직관적인 사용자 동선

### 📊 성능 최적화
- **BLEU Score**: 0.52 → 0.58 (튜닝 후)
- **Perplexity**: 64.31 → 54.15 (향상됨)
- **병원 접수 시간**: 13분 → 4분 (**69.2% 감소**)

## 🏗️ 시스템 아키텍처

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   사용자 음성    │ -> │   STT 처리      │ -> │  AI 모델 분석   │
│   (고령자)      │    │   (Whisper)     │    │  (Fine-tuned)   │
└─────────────────┘    └─────────────────┘    └─────────────────┘
                                                        │
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   진료과 추천    │ <- │   결과 처리      │ <- │   진단 결과     │
│     출력        │    │                 │    │                │
└─────────────────┘    └─────────────────┘    └─────────────────┘
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

### Docker 실행

```bash
# Docker 컨테이너 빌드 및 실행
docker-compose up -d
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

## 📝 사용자 후기

> *"헬로닥이 아니었다면 한참 도움을 기다려야 했을텐데, 덕분에 바로 정형외과로 내원할 수 있었다네"*  
> — 실제 사용자

> *"어르신께서 마치 진료 전에 예습을 한 사람처럼 이해가 빠르셔서 진료가 원활했어요"*  
> — 담당 의료진

## 🤝 기여하기

프로젝트에 기여하고 싶으시다면:

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 라이센스

이 프로젝트는 MIT 라이센스 하에 배포됩니다. 자세한 내용은 `LICENSE` 파일을 참조하세요.

## 📞 연락처

**whyNot Team**
- 웹사이트: [whynot2025.com](https://whynot2025.com)
- 이메일: contact@whynot2025.com

## 🙏 감사의 말

용인세브란스병원의 지원과 협력에 감사드리며, 고령자 의료 서비스 향상을 위해 함께 노력해주신 모든 분들께 감사드립니다.

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
