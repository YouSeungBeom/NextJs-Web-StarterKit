# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

@AGENTS.md

## 개발 명령어

```bash
npm run dev      # 개발 서버 실행 (http://localhost:3000)
npm run build    # 프로덕션 빌드
npm run start    # 프로덕션 서버 실행
npm run lint     # ESLint 검사
```

## 아키텍처 개요

**Next.js 16 App Router** 기반 스타터킷. Pages Router는 사용하지 않는다.

```
app/
  layout.tsx       # 전역 레이아웃: ThemeProvider → TooltipProvider → Header/main/Footer/Toaster
  page.tsx         # 랜딩 페이지 (HeroSection, FeaturesSection, CTASection)
  loading.tsx      # 전역 로딩 UI
  not-found.tsx    # 404 페이지
components/
  layout/          # Header (sticky, 반응형 네비), Footer
  providers/       # ThemeProvider (next-themes 래퍼)
  theme/           # ThemeToggle (라이트/다크/시스템 전환)
  ui/              # shadcn/ui 컴포넌트 (직접 수정 가능)
lib/
  constants.ts     # SITE_CONFIG, NAV_LINKS, FOOTER_LINKS, FEATURES
```

## 스타일링

- **Tailwind CSS 4** + CSS 변수 방식. `globals.css`에서 `@import "tailwindcss"`, `@import "shadcn/tailwind.css"` 순서로 임포트.
- 다크모드는 `attribute="class"` 방식(`.dark` 클래스). `globals.css`의 `@custom-variant dark (&:is(.dark *))` 와 연동.
- 색상 토큰은 `--background`, `--foreground`, `--primary` 등 CSS 변수로 정의되며 Tailwind `@theme inline` 블록에서 매핑.
- `cn()` 유틸리티(`clsx` + `tailwind-merge`)로 조건부 클래스 병합.

## 테마 시스템

`ThemeProvider`(`components/providers/theme-provider.tsx`)가 `next-themes`를 래핑. `defaultTheme="system"`, `enableSystem` 활성화. `html` 태그에 `suppressHydrationWarning` 필수.

## 상수 관리

사이트 메타 정보·네비 링크·푸터 링크·랜딩 기능 카드 데이터는 모두 `lib/constants.ts`에서 관리. 페이지·컴포넌트에서 직접 하드코딩 금지.

## shadcn/ui 컴포넌트 추가

```bash
npx shadcn add <component>
```

생성된 파일은 `components/ui/`에 위치하며 직접 수정 가능.
