# 마운자로 LP

셀이즈LAB 마운자로 캠페인 모바일 랜딩페이지

## 구성

- **랜딩페이지**: `index.html` (단일 파일, 이미지 인라인)
- **백엔드**: Google Apps Script (별도 Google Sheets 프로젝트)
- **데이터베이스/어드민**: Google Sheets
- **실시간 알림**: Telegram Bot
- **호스팅**: Netlify (GitHub 연동 자동 배포)

## 폼 흐름

```
사용자 → index.html 폼 제출
         ↓ POST
       Google Apps Script
         ├─→ Google Sheets (DB + 어드민)
         └─→ Telegram Bot (즉시 알림)
```

## 설정

`index.html` 내부 `ENDPOINT` 상수에 Google Apps Script 웹앱 URL을 입력해야 폼이 작동합니다.

```javascript
const ENDPOINT = 'https://script.google.com/macros/s/.../exec';
```

## 배포

- GitHub `main` 브랜치 push → Netlify 자동 재배포
- 또는 https://app.netlify.com/drop 에 `index.html` 직접 업로드

## 디자인 사양

- 모바일 우선, max-width 500px
- Pretendard 폰트
- 메인 컬러 `#2B4DBE` / 포인트 컬러 `#FFD93D`
- AOS 페이드업 애니메이션, scale 펄스 CTA
