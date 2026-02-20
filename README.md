# llm-proxy-skills

Codex CLI 및 Gemini CLI를 활용한 로직 최적화·프론트엔드 UI/UX 전문 스킬 플러그인

## 설치

### Claude Code에서 플러그인 설치

1. Claude Code CLI를 실행합니다
2. 다음 명령어로 플러그인을 설치합니다:

```bash
claude plugin marketplace add Mineru98/llm-proxy-skills
/plugin marketplace add Mineru98/llm-proxy-skills
```

또는

```bash
claude plugin install llm-proxy-skills
/plugin install llm-proxy-skills
```

3. 설치 후 사용 가능한 스킬을 확인합니다:

```bash
claude plugin list
```

## 내장 스킬

### logic-master

Codex CLI `--yolo` 모드로 로직 최적화 및 이미지 기반 코드 작업을 수행합니다.

**사용 시점:**

- 로직 최적화: 알고리즘 개선, 성능 튜닝
- 이미지 기반 작업: 스크린샷, 목업, 다이어그램에서 코드 생성
- 리팩토링: 함수 추출, 조건문 단순화, 복잡도 감소
- 비즈니스 로직: 검증 규칙, 데이터 변환, 상태 머신
- 디버깅: 복잡한 로직 버그, 레이스 컨디션 수정

**사용하지 않는 시점:**

- 시각/스타일 변경 (이 경우 `frontend-master` 사용)

### frontend-master

Gemini CLI `--yolo` 모드로 프론트엔드 UI/UX 작업을 수행합니다.

**사용 시점:**

- 시각적 변경: 색상, 배경, 테두리, 그림자
- 레이아웃: flexbox, grid, margin, padding, positioning
- 타이포그래피: 폰트 크기, 굵기, 줄 높이
- 애니메이션: transition, keyframes, hover 상태
- 반응형 디자인: breakpoint, media query
- 컴포넌트 스타일링: Tailwind, CSS-in-JS, styled-components

**사용하지 않는 시점:**

- 순수 로직 변경 (API 호출, 상태 관리, 이벤트 핸들러)
- 타입 정의, 유틸 함수, 비즈니스 로직
- 로직 최적화 또는 이미지 기반 작업 (이 경우 `logic-master` 사용)

## 요구사항

- Claude Code CLI 설치
- **logic-master**: Codex CLI 설치 및 API 키 설정
- **frontend-master**: Gemini CLI 설치 및 API 키 설정

## 사용 예시

### logic-master (Codex CLI)

```bash
# 로직 최적화
cat src/utils/sort.ts | codex exec --yolo - "Optimize this sorting algorithm for large datasets"

# 이미지에서 컴포넌트 생성
codex exec --yolo --image mockup.png "Generate React component matching this design"

# 리팩토링
cat src/handlers/user.ts | codex exec --yolo - "Extract reusable validation logic into separate functions"
```

### frontend-master (Gemini CLI)

```bash
# 버튼 스타일 변경
cat src/components/Button.tsx | gemini --yolo -p "Change button color to blue-500, add hover:scale-105 transition"

# 반응형 네비게이션
gemini --yolo -p "Make the navbar responsive with hamburger menu on mobile" --include-directories src/components

# 다크 모드 테마
gemini --yolo -p "Update all components to use dark mode color palette" --all-files
```

## 프로젝트 구조

```
llm-proxy-skills/
├── .claude-plugin/
│   ├── marketplace.json
│   └── plugin.json
├── skills/
│   ├── logic-master/
│   │   └── SKILL.md
│   └── frontend-master/
│       └── SKILL.md
├── LICENSE
└── README.md
```

## 라이선스

GPL-3.0

## 기여

이슈 및 PR은 GitHub에서 환영합니다.

## 작성자

- **Mineru** - mineru@usefullabs.co.kr
