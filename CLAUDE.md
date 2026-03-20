# TODO ENGLISH 학습체험관 — CLAUDE.md

## 프로젝트 개요
어린이 영어 학습 앱 **TODO ENGLISH (by enuma)**의 인터랙티브 학습체험관 웹페이지.
학부모가 앱 구매 전 주요 기능을 직접 체험하고, 무료체험 신청·구매를 유도하는 단일 HTML 페이지.

## 파일 구조
```
todo english/
├── index.html   ← 유일한 산출물 (CSS·JS 모두 인라인)
├── plan.md      ← 구현 계획서
├── CLAUDE.md    ← 이 파일
├── 0.jpg        ← 스플래시 화면
├── 1.jpg        ← 홈 대시보드
├── 2.jpg        ← 데일리 코스
├── 3.jpg        ← 오늘의 미션
├── 4_1.jpg      ← 단어장 Glossary
├── 4_2.jpg      ← 단어 게임
├── 5_1.jpg      ← 매거진 목록
├── 5_2.jpg      ← 매거진 펼침
├── 6_1.jpg      ← 펫 챌린지 방
└── 6_2.jpg      ← 챌린지 맵
```

## 현재 페이지 구조
```
① Gate Page   — 파란 배경 + 3D 기울어진 태블릿(1.jpg) + "학습체험관 입장 ›" 버튼 + 하단 CTA 카드
② Tour Modal  — "입장" 클릭 시 전체화면 모달, 7단계 순차 가이드 투어
```

## 핵심 규칙

### 파일
- **단일 HTML 파일 유지**: CSS와 JS는 항상 `index.html` 안에 인라인으로 작성
- **새 파일 생성 금지**: 별도 `.css` `.js` 파일 생성하지 않음
- **이미지 경로**: `1.jpg` 형태 사용 (`./` 접두사 없음)

### 코드 스타일
- 폰트: `Nunito` (Google Fonts CDN)
- 색상 변수 사용:
  ```css
  --navy:#2D2B5A  --pink:#FF6B9D  --gold:#FFD700
  --purple:#8B5CF6  --orange:#F97316  --green:#22C55E  --blue:#0091FF
  ```
- 반응형 브레이크포인트: `1000px`, `768px`

### CTA 버튼
- 모든 버튼은 `href="#"` 플레이스홀더
- 실제 URL 연결 전까지 `<!-- TODO: 실제 URL로 교체 -->` 주석 유지

### 언어
- UI 설명 텍스트: **한국어** (학부모 대상)
- 앱 내 기능명은 영어 그대로 유지 (Daily Course, Glossary, Weekly Magazine 등)

## 투어 스텝 데이터 위치
`index.html` 내 `<script>` 태그 안 `const STEPS = [...]`
이미지·스팟라이트 좌표·가이드 텍스트를 수정할 때 이 배열만 편집하면 됨.

## 검증 방법
Chrome 브라우저에서 `index.html` 직접 열기 (file:// 프로토콜)
