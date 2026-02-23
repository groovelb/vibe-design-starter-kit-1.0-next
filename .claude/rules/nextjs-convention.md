# Next.js App Router Convention (MUST)

## 핵심 원리

**"서버가 콘텐츠를 소유하고, 클라이언트가 움직임을 소유한다."**

SEO에 필요한 텍스트와 메타데이터는 서버 컴포넌트가 담당하고, 애니메이션과 인터랙션은 클라이언트 컴포넌트가 담당한다.

## 서버/클라이언트 분리 규칙

### `'use client'` 배치

- `'use client'`는 트리 끝단(leaf)에만 배치
- page.jsx에는 **절대** `'use client'` 사용 금지
- layout.jsx는 서버 컴포넌트 유지 (ThemeRegistry는 별도 providers.jsx로 분리)

### MUI 컴포넌트

- MUI를 import하는 모든 컴포넌트 파일에 `'use client'` 필수
- MUI는 내부적으로 Emotion context를 사용하므로 서버 컴포넌트에서 직접 사용 불가
- `@mui/material-nextjs/v15-appRouter`의 `AppRouterCacheProvider`로 SSR 호환

### children 패턴

```jsx
// app/page.jsx (서버 컴포넌트)
<AnimatedSection>        {/* 'use client' — 움직임 담당 */}
  <h1>SEO 핵심 텍스트</h1> {/* 서버에서 렌더됨 */}
</AnimatedSection>
```

## 애니메이션 규칙

### GPU 안전 속성만 사용

- **허용**: `transform` (x, y, scale, rotate), `opacity`, `filter`
- **금지**: `width`, `height`, `margin`, `top`, `left` 애니메이션 (CLS 유발)

### SEO 안전 초기 상태

- 애니메이션 초기 상태에서 `opacity: 0` 사용 **금지**
- `opacity: 0.01` 또는 `visibility: hidden` 사용
- 크롤러가 `opacity: 0` 텍스트를 무시할 수 있음

### `prefers-reduced-motion` 필수 대응

모든 모션/인터랙티브 컴포넌트에 reduced-motion 대응 필수:

```jsx
// CSS 기반 애니메이션
'@media (prefers-reduced-motion: reduce)': {
  transition: 'none',
  opacity: 1,
  transform: 'none',
}

// JS 기반 애니메이션
const prefersReducedMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
```

## SEO 규칙

### Metadata

- 모든 page.jsx에 `metadata` 또는 `generateMetadata` export 필수

```jsx
export const metadata = { title: '...', description: '...' };
// 또는
export async function generateMetadata({ params }) { ... }
```

### 이미지

- `next/image` 사용 권장, width/height 명시 (CLS 방지)
- 고정 치수 없는 이미지 금지

## 3D/WebGL 컴포넌트

- Three.js 등 무거운 라이브러리는 반드시 `next/dynamic({ ssr: false })` 사용
- 동적 import 래퍼 파일을 별도로 생성 (예: `GradientOverlayDynamic.jsx`)

## 폰트 규칙

- `next/font/google` 또는 `next/font/local`로만 폰트 로딩
- CSS Custom Property(`--font-*`)로 참조
- Storybook에서는 기존 DOM 기반 로딩 유지 (next/font 사용 불가)
