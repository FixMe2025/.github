# ✒️ 맞춤법 검사기 (FixME)

![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Hugging%20Face-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)

> "더 정확하고 아름다운 글을 위한 첫걸음"

FixME는 최신 AI 언어 모델을 기반으로 한 한국어 맞춤법 및 문법 교정 서비스입니다. 사용자가 작성한 글을 더 정확하고 자연스럽게 다듬어주어, 글쓰기 자신감을 높여주는 것을 목표로 합니다.

## ✨ 주요 기능 (Features)

- **실시간 맞춤법 검사**: 텍스트 입력 시 빠르고 정확하게 오류를 찾아냅니다.
- **오류 하이라이팅**: 틀린 부분을 시각적으로 명확하게 표시하여 쉽게 인지할 수 있습니다.
- **교정 제안**: 단순히 틀린 부분을 찾는 것을 넘어, 더 나은 표현과 올바른 단어를 추천합니다.
- **원문-교정문 비교**: `diff-match-patch` 라이브러리를 활용하여 수정 전후를 한눈에 비교할 수 있습니다.
- **편리한 UX**: 검사 결과를 손쉽게 복사하고, 다크/라이트 모드를 지원하여 사용자 눈의 피로를 덜어줍니다.
- **재미 요소**: 검사를 기다리는 동안 즐길 수 있는 간단한 미니게임을 제공합니다.

## 🏛️ 아키텍처 (Architecture)

FixME는 최신 웹 기술을 활용하여 빠르고 안정적인 서비스를 제공합니다.

- **Frontend**: `Next.js`와 `TypeScript`를 사용하여 반응형 및 인터랙티브 UI를 구현했습니다.
- **Backend**: `FastAPI`를 기반으로 구축된 한글 맞춤법 교정 및 문장 개선 API 서비스입니다. FixMe 백엔드는 두 가지 주요 서비스 흐름을 가집니다.
  1.  **통합 서비스 (Integrated Service)**: `comprehensive`, `spellcheck`, `improvement` 엔드포인트를 담당합니다. `IntegratedCorrectionService`가 `ThreadPoolExecutor`를 사용해 여러 모델(`KoAlpaca`, `et5-typos-corrector`)을 병렬로 호출하여 빠른 응답을 제공합니다.
  2.  **LangGraph 파이프라인**: `pipeline` 엔드포인트를 담당합니다. `LangGraph`를 사용하여 `et5-typos-corrector` (1차 교정)와 `kogrammar-base` (2차 교정) 모델을 순차적으로 실행하는 워크플로우를 구성하여, 더 깊이 있는 교정을 수행합니다.
- **배포**: `Docker`를 통해 각 구성 요소를 컨테이너화하여 일관성 있는 배포 및 운영 환경을 구축합니다.

### **Frontend 폴더 구조**
```
frontend/
├── app/
│   ├── page.tsx
│   └── layout.tsx
├── components/
│   ├── InputBox.tsx
│   ├── ResultBox.tsx
│   └── DiffViewer.tsx
├── lib/
│   └── api.ts
└── hooks/
    └── useSpellcheck.ts
```

### **Backend 폴더 구조**
```
backend/
├── app/
│   ├── api/
│   │   └── v1/
│   │       └── endpoints.py
│   ├── services/
│   │   └── spellchecker.py
│   └── main.py
├── requirements.txt
└── Dockerfile
```

### **API 엔드포인트**

| Method | Endpoint                               | 설명                                         |
| ------ | -------------------------------------- | -------------------------------------------- |
| POST   | `/api/v1/comprehensive/comprehensive`  | 맞춤법, 타이포, 문장 개선을 종합적으로 수행합니다. |
| POST   | `/api/v1/pipeline/run`                 | LangGraph 파이프라인을 통해 텍스트를 교정합니다. |
| GET    | `/api/v1/comprehensive/health`         | 종합 서비스의 모든 모델 상태를 확인합니다.   |
| GET    | `/api/v1/pipeline/health`              | LangGraph 파이프라인의 상태를 확인합니다.    |
| GET    | `/health`                              | API 서버의 기본 상태를 확인합니다.           |

## 👨‍💻 기여자 (Contributors)

이 프로젝트는 아래 두 명의 개발자가 함께 만들었습니다.
<br />
  <table align="center">
    <tr>
      <td align="center">
        <strong>김화연</strong><br>
        <img src="https://avatars.githubusercontent.com/KHY90" width="100" height="100"><br>
        <a href="https://github.com/KHY90">GitHub</a>
      </td>
      <td align="center">
        <strong>우승엽</strong><br>
        <img src="https://avatars.githubusercontent.com/wooseungyeop" width="100" height="100"><br>
        <a href="https://github.com/wooseungyeop">GitHub</a>
      </td>
  <table>
<br />
      
## 🛠️ 기술 스택 (Tech Stack)

### Frontend
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![Framer Motion](https://img.shields.io/badge/Framer%20Motion-0055FF?style=for-the-badge&logo=framer&logoColor=white)
![Recoil](https://img.shields.io/badge/Recoil-3578E5?style=for-the-badge&logo=recoil&logoColor=white)

### Backend
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=for-the-badge&logo=python&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-blue?style=for-the-badge)
![Transformers](https://img.shields.io/badge/Transformers-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)

### ML
![Hugging Face](https://img.shields.io/badge/Hugging%20Face-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)
![Transformers](https://img.shields.io/badge/Transformers-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)

### Development Tools
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
