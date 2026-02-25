# MUI Grid Import 규칙 (CRITICAL - 절대 위반 금지)

## 잘못된 Import (절대 사용 금지)

```jsx
import Grid from '@mui/material/Grid2';  // 틀림! 사용 금지!
```

## 올바른 Import (반드시 이것만 사용)

```jsx
import Grid from '@mui/material/Grid';   // 정확함! 이것만 사용!
```

**중요**: MUI v7에서는 `Grid2`가 아닌 `Grid`를 직접 import해야 합니다.

---

## Grid 사용 예시

```jsx
import Grid from '@mui/material/Grid';

// MUI v7: size prop으로 반응형 크기 지정
<Grid container spacing={2}>
  <Grid size={{ xs: 6, md: 8 }}>내용</Grid>
  <Grid size={{ xs: 6, md: 4 }}>내용</Grid>
</Grid>
```
