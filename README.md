# NextStarter

![Next.js](https://img.shields.io/badge/Next.js-16-black?logo=next.js)
![React](https://img.shields.io/badge/React-19-61DAFB?logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-4-06B6D4?logo=tailwindcss)

Next.js 16 기반 프로덕션 레디 모던 웹 개발 스타터킷

## 기술 스택

| 라이브러리 | 버전 | 설명 |
|---|---|---|
| Next.js | 16 | App Router 기반 풀스택 프레임워크 |
| React | 19 | UI 라이브러리 |
| TypeScript | 5 | 정적 타입 검사 |
| Tailwind CSS | 4 | CSS 변수 기반 유틸리티 퍼스트 스타일링 |
| shadcn/ui | 최신 | Radix UI 기반 접근성 컴포넌트 |
| Lucide React | 최신 | 오픈소스 아이콘 라이브러리 |
| next-themes | 최신 | 라이트/다크/시스템 테마 지원 |

## 시작하기

```bash
# 의존성 설치
npm install

# 개발 서버 실행
npm run dev
```

브라우저에서 [http://localhost:3000](http://localhost:3000)을 열어 확인합니다.

## 개발 명령어

```bash
npm run dev      # 개발 서버 실행
npm run build    # 프로덕션 빌드
npm run start    # 프로덕션 서버 실행
npm run lint     # ESLint 검사
```

## 프로젝트 구조

```
app/
  layout.tsx       # 전역 레이아웃 (ThemeProvider, Header, Footer)
  page.tsx         # 랜딩 페이지
  loading.tsx      # 전역 로딩 UI
  not-found.tsx    # 404 페이지
components/
  layout/          # Header, Footer 컴포넌트
  providers/       # ThemeProvider
  theme/           # ThemeToggle
  ui/              # shadcn/ui 컴포넌트
lib/
  constants.ts     # 사이트 메타 정보, 네비 링크, 기능 데이터
```

## shadcn/ui 컴포넌트 추가

```bash
npx shadcn add <component>
```

추가된 컴포넌트는 `components/ui/`에 생성되며 직접 수정 가능합니다.
