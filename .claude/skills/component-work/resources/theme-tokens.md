# Theme Tokens

> MUI 커스텀 테마 상세 레퍼런스.
> 컴포넌트 스타일링, 테마 수정, 디자인 토큰 적용 시 참조한다.

## 테마 파일

- 위치: `src/styles/themes/default.js`

## 핵심 철학: Violet-Tinted Monochrome Dark

- **B&W 기반**: 순수 #000/#FFF 대신 violet이 미세하게 틸트된 흑백
- **다크 모드 기본**: `palette.mode: 'dark'`
- **White Accent**: 액센트 색상도 흰색 (violet-tinted off-white)
- **Monoline System**: 1px 선 중심 시각 체계

## Typography — 2서체 체계

### 폰트 패밀리 상수 (default.js)
```jsx
FONT_BRAND       // 브랜드 서체 — display만 (IBM Plex Sans)
FONT_MONO        // 코드 서체 — code, codeBlock (Geist Mono)
FONT_PRETENDARD  // 프로덕트 서체 — h1~h6, body, subtitle, button, caption, overline
FONT_HEADING     // (레거시, 현재 미사용) Outfit + Pretendard 폴백
```

### 역할별 서체
| 역할 | 서체 | 용도 |
|------|------|------|
| Brand / Display | **IBM Plex Sans** | display (히어로, 슬로건, 키비쥬얼) |
| Code | **Geist Mono** | 인라인 코드, 코드 블록 |
| Product / Body | **Pretendard Variable** | h1~h6, 본문, 서브타이틀, 버튼, 캡션, overline, UI 텍스트 |

### 커스텀 variant (MUI 기본에 없음)
```jsx
// sx로 적용 (Typography variant prop 아님)
<Box sx={ theme.typography.display }>히어로 텍스트</Box>
<Box component="code" sx={ theme.typography.code }>inline code</Box>
<Box component="pre" sx={ theme.typography.codeBlock }>code block</Box>
```

### 다크 모드 최적화
- 본문 `letterSpacing: '0.01em'` (밝은 글자는 같은 weight도 무겁게 보이므로)
- 본문 `lineHeight: 1.7` (가독성 향상)
- Caption `fontWeight: 300` (Light)

## Color

### 배경 계층 (Violet-Tinted Darks)
```jsx
vdl.bg.deep      : '#0F0E13'   // 최하단
vdl.bg.default   : '#13121A'   // 앱 기본 배경
vdl.bg.surface   : '#1A1922'   // 카드, 패널
vdl.bg.elevated  : '#21202B'   // 모달, 드롭다운
vdl.bg.hover     : '#282734'   // hover 상태
```

### Primary Color (White Accent)
```jsx
primary: {
  main: '#EDECF1',        // violet-tinted off-white
  contrastText: '#0F0E13' // 다크 배경
}
```

### 텍스트 색상
```jsx
text: {
  primary: '#EDECF1',   // 높은 대비
  secondary: '#8C8A95', // 보조
  disabled: '#55535E',   // 비활성
}
```

### VDL 커스텀 토큰
```jsx
vdl: {
  lineActive: '#EDECF1',  // 활성 선, 아이콘
  lineSubtle: '#2A2932',  // 그리드 선, 보조선
  gridColor: 'rgba(237, 236, 241, 0.03)',
}
```

### Grey 스케일 (Violet-Tinted)
```jsx
grey: {
  50: '#F5F4F8',   900: '#1A1922'
}
```

## Elevation

다크 배경에서의 그림자 — 높은 opacity로 존재감 확보:

```jsx
shadows: [
  'none',
  '0 0 12px rgba(0, 0, 0, 0.30)',
  '0 0 16px rgba(0, 0, 0, 0.35)',
  // ...
]
```

## Border Radius

인라인으로 직접 지정하지 않는 이상 모든 컴포넌트의 borderRadius는 **0**

```jsx
shape: {
  borderRadius: 0
}
```

## 아이콘

- 기본 스타일: **rounded** (따뜻한 톤)
- 기본 weight: **300** (가벼운 monoline 느낌)
- 색상: `theme.vdl.lineActive` 토큰 참조

## 테마 적용 예시

```jsx
// theme.vdl 토큰 접근
<Box sx={{ color: theme.vdl.lineActive }} />
<Box sx={{ borderColor: theme.vdl.lineSubtle }} />

// palette 토큰 접근
<Box sx={{ backgroundColor: 'background.paper' }} />
<Typography sx={{ color: 'text.secondary' }}>보조 텍스트</Typography>
```
