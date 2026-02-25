# Design Tokens Detail

> design-system.md 핵심 원칙의 상세 BAD/GOOD 패턴 레퍼런스.
> 컴포넌트 스타일링 시 참조한다.

## 색상 — 시멘틱 토큰 사용

```jsx
// BAD — 하드코딩된 hex/rgba
sx={{ color: '#EDECF1' }}
sx={{ backgroundColor: 'rgba(0, 0, 0, 0.7)' }}
sx={{ boxShadow: '0 0 0 3px rgba(0, 0, 255, 0.1)' }}

// GOOD — 시멘틱 토큰
sx={{ color: 'text.primary' }}
sx={{ backgroundColor: (theme) => `${theme.vdl.bg.deep}B3` }}
sx={{ boxShadow: (theme) => `0 0 0 3px ${theme.palette.primary.main}26` }}
```

주요 매핑:
| 하드코딩 값 | 시멘틱 토큰 |
|---|---|
| `'#EDECF1'` | `'primary.main'` 또는 `'text.primary'` |
| `'#0F0E13'` | `theme.vdl.bg.deep` |
| `'#13121A'` | `'background.default'` |
| `'#1A1922'` | `'background.paper'` 또는 `theme.vdl.bg.surface` |
| `'#8C8A95'` | `'text.secondary'` |
| `'#55535E'` | `'text.disabled'` |
| `'white'` | `'common.white'` |
| `rgba(25, 118, 210, ...)` | `theme.palette.primary.main` + hex opacity |
| `rgba(0, 0, 255, ...)` | `theme.palette.primary.main` + hex opacity |

## 그림자 — `theme.customShadows` 사용

```jsx
// BAD
sx={{ boxShadow: '0 1px 3px rgba(0,0,0,0.08)' }}

// GOOD
sx={{ boxShadow: (theme) => theme.customShadows.sm }}
```

사용 가능 토큰: `none`, `sm`, `md`, `lg`, `xl`

## 오버레이 — vdl.bg.deep 기반

```jsx
// BAD
sx={{ bgcolor: 'rgba(0, 0, 0, 0.7)' }}

// GOOD — vdl.bg.deep (#0F0E13) + hex opacity
sx={{ bgcolor: (theme) => `${theme.vdl.bg.deep}B3` }}
```

hex opacity 참고: `26`=15%, `33`=20%, `4D`=30%, `66`=40%, `80`=50%, `99`=60%, `B3`=70%, `CC`=80%, `E6`=90%

## 간격 — `theme.spacing` 단위 사용

```jsx
// BAD
sx={{ padding: '8px 16px' }}

// GOOD
sx={{ py: 1, px: 2 }}
```

## 폰트 크기 — Typography variant 우선

```jsx
// BAD
sx={{ fontSize: 14 }}

// GOOD
<Typography variant="body2">텍스트</Typography>
```

예외: 크기별 스타일 맵(sizeMap) 내부에서 숫자 fontSize는 허용
