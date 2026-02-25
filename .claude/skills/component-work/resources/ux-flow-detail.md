# UX Flow Detail

> ux-flow.md의 상세 레퍼런스.
> 페이지 구현, 섹션 빌드, 전환 설계 시 참조한다.

## Landing 스크롤 여정 (B-type)

브랜드 서사 3층위를 스크롤 여정으로 변환한다.
흐름: 관심 유발 → 문제 제기 → 가치 제안 → 증명 → 전환 유도.

| 순서 | 섹션명 | 목적 | 핵심 메시지 | 브랜드 서사 층위 |
|------|--------|------|------------|-----------------|
| 1 | **Hero** | 관심 유발, 정체성 선언 | "바이브 코딩을 디자인 툴처럼 사용합니다" + 한 문장 정의 | 표면 |
| 2 | **Problem** | 공감, 페인포인트 인식 | "내 디자인인데 완성은 남의 몫이다" — 피동적 업무 상태 묘사 | ① 진입 |
| 3 | **Myth Busting** | 통념 반전, 관점 전환 | "도구는 이미 있습니다. 빠진 건 도구를 지휘하는 언어입니다" | ①→② 전환 |
| 4 | **Value Proposition** | VDL 접근법 제시 | System Over Drawing → The Vibe Standard → Design As Build (인과 흐름) | ② |
| 5 | **Dictionary Bridge** | 리드 마그넷 전환, 가치 체험 유도 | "'예쁘게 만들어줘'를 졸업하는 사전 — 200+ 디자인 키워드" | ② 증거 |
| 6 | **Before/After** | 가치 증명 | "같은 도구, 같은 AI. 다른 건 프롬프트에 담긴 기준뿐이다" | ② 증명 |
| 7 | **Course Bridge** | Primary CTA 전환 | "디자인 의도를 끝까지 직접 만드는 법 — 8주 코호트" | ① 솔루션 |
| 8 | **Experiment Bridge** | 결과물 증거, 신뢰 구축 | "바이브 스타터키트로 만든 가상 브랜드들" | ② 증거 |
| 9 | **Final CTA** | 최종 전환 | "코호트 알아보기" + "Dictionary 먼저 둘러보기" | 전환 |

### 섹션 상세

**1. Hero**
- 메인 헤드라인: 태그라인 ("바이브 코딩을 디자인 툴처럼 사용합니다")
- 서브카피: 한 문장 정의 또는 부제
- 비쥬얼: Design Decision Anatomy 키비쥬얼 (완성된 UI + Naming Line)
- CTA 없음 — 스크롤 유도

**2. Problem**
- 페르소나별 감성적 페인포인트 3개 (캔버스 디자이너 70% 중심)
- "내 디자인인데 완성은 남의 몫이다"
- "말로 설득해야 하는데 보여줄 게 없다"
- "기능은 되는데 왜 어색한지 모르겠다"
- 톤: 해요체 허용 구간 (독자의 내면 독백)

**3. Myth Busting**
- Vibe Philosophy 기반 편견 깨기 1~2개 선별
- 편견 1: "더 좋은 도구가 나오면 달라진다" → "도구가 바뀌어도 정밀하지 않은 의도는 정밀하지 않은 결과를 만든다"
- 반전 구조: 통념 → 반전 → 핵심 문구

**4. Value Proposition**
- 3개 가치 제안의 인과 흐름 시각화
- System Over Drawing: "기준이 먼저다"
- The Vibe Standard: "정확하게 말하면 정확하게 나온다"
- Design As Build: "설계가 곧 구현이다"
- 시각: 등가 다이어그램 또는 Circuitry 연결 구조

**5. Dictionary Bridge**
- 헤드라인: "'예쁘게 만들어줘'를 졸업하는 사전"
- 서브: 200+ 디자인 키워드 체계
- 프리뷰: Dictionary 키워드 몇 개를 인터랙티브하게 체험
- CTA: "Dictionary 탐색하기" → `/dictionary` (Secondary CTA)

**6. Before/After**
- 프롬프트 Before/After 1~2개
- 시각: Before (opacity↓, Naming Line 없음) / After (선명, Naming Line 2~4개)
- 마무리: "차이를 만든 건 코딩 실력이 아니라 디자인 어휘다"

**7. Course Bridge**
- 헤드라인: "디자인 의도를 끝까지 직접 만드는 법"
- 서브: 8주 코호트 핵심 정보 요약
- CTA: "코호트 알아보기" → `/course` (Primary CTA)

**8. Experiment Bridge**
- 헤드라인: [미정 — contents 단계에서 확정]
- 서브: 바이브 스타터키트(코스 1)로 만든 가상 브랜드 예제
- 프리뷰: 대표 예제 3~4개 카드
- CTA: "예제 더 보기" → `/experiment`

**9. Final CTA**
- Primary: "코호트 알아보기" → `/course`
- Secondary: "Dictionary 먼저 둘러보기" → `/dictionary`
- 브랜드 미션 한 줄 마무리

## 페이지별 구성

### Course (/course)

코호트 소개 및 수강 신청 페이지. B-type 전환 목표.

| 순서 | 섹션 | 목적 |
|------|------|------|
| 1 | 코호트 헤더 | 코호트명, 기수, 일정, 상태 (모집중/대기중) |
| 2 | 무엇을 배우는가 | 커리큘럼 개요 — 도구가 아니라 언어 체계 |
| 3 | 누구를 위한 것인가 | 페르소나별 Before→After 변화 |
| 4 | 어떻게 진행되는가 | 8주 진행 방식, 코호트 특성 (동료 압력, 프롬프트 클리닉) |
| 5 | 파운더 소개 | DDD 포지셔닝 — "10년 디자이너-개발자 하이브리드" |
| 6 | 수강 신청 CTA | 가격, 일정, 신청 버튼 |

- 상태: 현재 코호트 1개 "대기중"
- CTA: 수강 신청 또는 알림 신청 (대기중일 때)

### Vibe Dictionary (/dictionary)

디자인 키워드 택소노미 인터랙티브 탐색. C-type 콘텐츠 + 리드 마그넷.

| 순서 | 섹션/기능 | 목적 |
|------|----------|------|
| 1 | Dictionary 헤더 | "AI가 이해하는 디자인 언어 체계" — Dictionary 소개 |
| 2 | 카테고리 탐색 | 택소노미 카테고리별 키워드 브라우징 |
| 3 | 검색/필터 | 키워드 검색, 태그 필터 |
| 4 | 키워드 상세 | 키워드 정의, 하위 결정, 프롬프트 활용 예시 |
| 5 | 관련 키워드 | 연관 키워드 추천 (Circuitry 구조) |

- 데이터 소스: `src/docs/taxonomy/` 기반
- 인터랙션: 카테고리 → 키워드 리스트 → 키워드 상세 (드릴다운)
- 리드 마그넷: Dictionary 자체가 무료 가치 → Course 관심 전환

### Vibe Experiment (/experiment)

바이브 스타터키트로 만든 가상 브랜드 예제 갤러리. C-type 콘텐츠.

| 순서 | 섹션/기능 | 목적 |
|------|----------|------|
| 1 | 갤러리 헤더 | "바이브 스타터키트로 만든 가상 브랜드들" |
| 2 | 필터 | 브랜드 유형, 업종, 사용 기법 등으로 필터 |
| 3 | 예제 카드 그리드 | 가상 브랜드 카드 — 썸네일, 브랜드명, 간략 설명 |
| 4 | 예제 상세 | 브랜드 컨셉, 사용 키워드, 결과 스크린샷, 프롬프트 일부 |

- 각 예제는 Course(스타터키트)의 결과물 증거
- "이 코스를 들으면 이런 결과를 만들 수 있다"를 보여주는 갤러리

### Brand Story (/brand-story)

브랜드 정체성, 철학, 미션 문서. C-type 콘텐츠.

| 순서 | 섹션 | 목적 |
|------|------|------|
| 1 | 미션 | "사고와 구현의 주체를 일치시킨다" |
| 2 | Vibe Philosophy | 3개 신념 — 구현은 언어를 따른다 / 언어는 경험을 함축한다 / 감각도 쪼개면 로직이다 |
| 3 | 가치 제안 | System Over Drawing → The Vibe Standard → Design As Build |
| 4 | 포지셔닝 | VDL ≠ vs VDL = 대비 |
| 5 | 파운더 | DDD 소개 |

- 톤: 합니다체 기본. 선언적. 연구소 정체성
- 랜딩의 압축 버전이 아니라 깊이 있는 풀 버전

## 페이지 간 연결 구조

```
Landing ──┬──→ Course (Primary CTA, 상시)
          ├──→ Dictionary (Secondary CTA, 브릿지 섹션)
          ├──→ Experiment (브릿지 섹션)
          └──→ Brand Story (브릿지 섹션)

Dictionary ──→ Course (키워드 탐색 후 "더 깊이 배우려면" 유도)
Experiment ──→ Course ("이런 결과를 만들려면" 유도)
Brand Story ──→ Course (미션 공감 후 유도)

Course ──→ Dictionary ("먼저 Dictionary 둘러보기" — 아직 결정 전인 방문자용)
```

전환 퍼널: Dictionary(리드 마그넷 유입) → Landing 또는 Course → 수강 신청

## 전환 포인트

| 위치 | CTA | 액션 | 우선순위 |
|------|-----|------|---------|
| GNB (상시) | "코호트 알아보기" | → `/course` | Primary |
| Landing §5 Dictionary Bridge | "Dictionary 탐색하기" | → `/dictionary` | Secondary |
| Landing §7 Course Bridge | "코호트 알아보기" | → `/course` | Primary |
| Landing §9 Final CTA | "코호트 알아보기" + "Dictionary 먼저 둘러보기" | → `/course`, `/dictionary` | Primary + Secondary |
| Course §6 | "수강 신청" 또는 "알림 신청" | 외부 폼 또는 인앱 | Primary |
| Dictionary 하단 | "코스에서 실전 적용하기" | → `/course` | Soft |
| Experiment 하단 | "이런 결과를 만들려면" | → `/course` | Soft |

## 인터랙션 원칙 (페이지별)

### Landing 전용

- **섹션 간 여백 충분**: 각 섹션이 독립적으로 호흡할 수 있도록
- **CTA 시각 위계**: Primary CTA(Course)와 Secondary CTA(Dictionary) 시각적 구분 명확
- **Before/After 섹션**: 좌우 대비 또는 스와이프 인터랙션

### Dictionary 전용

- **카테고리 탭**: 택소노미 카테고리 간 전환
- **검색 즉시 반영**: 키워드 검색 시 결과 즉시 필터링
- **키워드 상세 진입**: 카드 클릭 → 상세 뷰 (모달 또는 페이지 내 확장)

## 반복 UI 패턴 (design-system에 전달)

| 패턴 | 사용 위치 | 설명 |
|------|----------|------|
| 섹션 컨테이너 | Landing 전체, 각 페이지 | 풀폭 섹션 + 내부 maxWidth 콘텐츠 |
| CTA 버튼 (Primary/Secondary) | Landing, Course, GNB | Primary: 채움, Secondary: 아웃라인 |
| 카드 | Dictionary 키워드, Experiment 예제 | 썸네일 + 제목 + 설명 패턴 |
| Before/After 대비 | Landing, Course | 좌우 대비 레이아웃 |
| 카테고리 탭/필터 | Dictionary, Experiment | 탭 또는 필터 바 |
| 페이지 헤더 | 모든 내부 페이지 | 페이지 제목 + 서브카피 |
| 브릿지 섹션 | Landing | 다른 페이지로 유도하는 프리뷰 + CTA |
| 인과 흐름 시각화 | Landing VP, Brand Story | 3단계 인과 구조 (1→2→3) |

## 데이터 요구사항 (technical에 전달)

| 페이지 | 필요 데이터 | 출처 |
|--------|-----------|------|
| Dictionary | 택소노미 키워드 목록, 카테고리, 태그, 상세 정보 | `src/docs/taxonomy/` 기반 정적 데이터 |
| Experiment | 예제 브랜드 목록, 썸네일, 설명, 사용 기법 | 정적 데이터 (JSON 또는 MDX) |
| Course | 코호트 정보 (일정, 상태, 가격, 커리큘럼) | 정적 데이터 (수동 업데이트) |
| Landing | 각 브릿지 섹션용 프리뷰 데이터 | 위 페이지 데이터의 부분 참조 |
| Brand Story | 브랜딩 문서 콘텐츠 | 정적 콘텐츠 |

- 외부 연동: 수강 신청 폼 (Google Forms 또는 Tally 등 — [미정])
- 애널리틱스: [미정 — technical 단계에서 확정]
- CMS: 없음 (정적 콘텐츠 중심, project-summary Non-goal)
