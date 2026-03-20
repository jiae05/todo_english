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
├── 0.jpg        ← 스플래시 화면 (게이트 태블릿에 표시)
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
① Gate Page   — 파스텔 블루(#DCE8F5) + 3D 기울어진 태블릿(0.jpg) + 하단 CTA 카드
② Tour Modal  — 0.jpg의 START 버튼 클릭 시 열리는 10단계 전체화면 투어
```

## 핵심 규칙

### 파일
- **단일 HTML 파일 유지**: CSS와 JS는 항상 `index.html` 안에 인라인으로 작성
- **새 파일 생성 금지**: 별도 `.css` `.js` 파일 생성하지 않음
- **이미지 경로**: `0.jpg` 형태 사용 (`./` 접두사 없음)

### 코드 스타일
- 폰트: `Nunito` (Google Fonts CDN)
- 색상 변수:
  ```css
  --navy:#2D2B5A  --pink:#FF6B9D  --gold:#FFD700
  --purple:#8B5CF6  --orange:#F97316  --green:#22C55E  --blue:#0091FF
  배경: #DCE8F5
  ```
- 반응형 브레이크포인트: `1000px`, `768px`

### START 버튼 (투명 오버레이)
- `0.jpg` 안에 있는 앱 내 START 버튼 위에 투명 클릭 영역을 겹쳐서 사용
- CSS: `position:absolute; bottom:22%; left:50%; width:38%; height:10%;`
- 위치가 맞지 않으면 `bottom` 값을 조정

### 투어 스텝 수정 위치
- `index.html` 내 `<script>` 태그 안 `const STEPS = [...]`
- 현재 10단계: `0.jpg` → `1.jpg` → ... → `6_2.jpg` (파일명 순서)
- 이미지·가이드 텍스트를 바꿀 때 이 배열만 편집

### CTA 버튼
- 모든 버튼 `href="#"` 플레이스홀더
- 실제 URL 연결 전까지 `<!-- TODO: 실제 URL로 교체 -->` 주석 유지

### 언어
- UI 설명: **한국어** (학부모 대상)
- 앱 기능명은 영어 그대로 (Daily Course, Glossary, Weekly Magazine 등)

## 제거된 섹션 (복구하지 않음)
- 기능 소개 카드 (feat-grid)
- 인터랙티브 미니게임 (단어 맞추기, 미션, 단어장)
- Final CTA 섹션 (가격 비교)
- 플로팅 이모지 마스코트

## 검증 방법
Chrome 브라우저에서 `index.html` 직접 열기 (file:// 프로토콜)
