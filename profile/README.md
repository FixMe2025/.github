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
- **Backend**: `Python`과 `FastAPI`를 기반으로 `skt/kobert-base-v1` Hugging Face 모델을 서빙하여 핵심적인 맞춤법 교정 기능을 수행합니다.
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

## 👨‍💻 기여자 (Contributors)

이 프로젝트는 아래 두 명의 개발자가 함께 만들었습니다.

<a href="https://github.com/KHY90" target="_blank">
  <img src="https://avatars.githubusercontent.com/KHY90" 
       alt="KHY90" 
       width="200" 
       height="auto" 
       style="max-width: 100%; height: auto;">
</a>
<a href="https://github.com/wooseungyeop" target="_blank">
  <img src="https://avatars.githubusercontent.com/wooseungyeop" 
       alt="wooseungyeop" 
       width="200" 
       height="auto" 
       style="max-width: 100%; height: auto;">
</a>

## 🛠️ 기술 스택 (Tech Stack)

### Frontend
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![Framer Motion](https://img.shields.io/badge/Framer%20Motion-0055FF?style=for-the-badge&logo=framer&logoColor=white)
![Recoil](https://img.shields.io/badge/Recoil-3578E5?style=for-the-badge&logo=recoil&logoColor=white)

### Backend
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

### ML
![Hugging Face](https://img.shields.io/badge/Hugging%20Face-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)
![Transformers](https://img.shields.io/badge/Transformers-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)

### Development Tools
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)