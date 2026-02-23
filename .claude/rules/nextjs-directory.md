# Next.js Directory Rules (MUST)

## App Router 디렉토리 구조

```
app/                          # Next.js App Router (라우팅만)
  layout.jsx                  # 루트 레이아웃 (서버 컴포넌트, metadata, 폰트)
  providers.jsx               # 'use client' ThemeRegistry (MUI + Emotion SSR)
  fonts.js                    # next/font 설정 (Outfit, Pretendard)
  page.jsx                    # 홈페이지 (서버 컴포넌트)
  globals.css                 # 전역 CSS
  (pages)/                    # Route group (추가 페이지)
    [slug]/
      page.jsx
```

## app/ vs src/ 역할 구분

| 디렉토리 | 역할 | `'use client'` |
|----------|------|---------------|
| `app/` | 라우팅, 레이아웃, 메타데이터 | page.jsx에서 금지 |
| `app/providers.jsx` | ThemeRegistry | 필수 |
| `src/components/` | UI 컴포넌트 라이브러리 | MUI 사용 시 필수 |
| `src/stories/` | Storybook 문서 전용 | 불필요 (클라이언트 환경) |

## 기존 src/ 구조 유지

`src/components/` 하위 텍소노미 기반 디렉토리 구조는 **그대로 유지**.
project-directory.md의 컴포넌트 분류를 따른다.

## 정적 자산 규칙

- 이미지, 비디오 등 정적 자산은 `public/` 하위에 배치
- Vite 스타일 import (`import video from './assets/video.mp4'`) 대신 공개 경로 사용 (`'/video/video.mp4'`)

```
public/
  fonts/                      # 로컬 폰트 파일
    PretendardVariable.woff2
  video/                      # 비디오 자산
  favicon.svg                 # 파비콘
```

## 새 페이지 추가 시

1. `app/` 하위에 폴더 생성 (라우트 세그먼트)
2. `page.jsx` 생성 (서버 컴포넌트)
3. `metadata` 또는 `generateMetadata` export
4. UI 컴포넌트는 `src/components/`에서 import
5. page.jsx에 `'use client'` 사용 금지
