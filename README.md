# Claude Code 학습 저장소 (Studying Claude Code)

## 공부 목적

현직 행정 사무관으로 근무할 때 Claude Code를 실무에 활용하기 위해 학습한다.

- 보고서 작성 자동화 및 초안 생성
- 뉴스기사·정책 자료 분석
- 반복 행정 업무 효율화

---

## Critical Rules (절대 규칙)

- `.env` 등 시크릿 파일 절대 커밋 금지
- main 브랜치에 직접 push 금지 — 별도 branch를 생성한 뒤 push, 내가 merge 명령 시에만 main에 머지

---

## CLAUDE.md 운영 규칙

- CLAUDE.md는 300자 이내로 유지
- 디렉토리별로 CLAUDE.md를 별도 생성해서 분리

---

## 학습 로드맵 (7일)

### Day 1 — 기초 개념 정립
> Claude가 무엇이고, AI는 어떻게 동작하는가

- [ ] AI Capabilities and Limitations
- [ ] Claude 101
- [ ] AI Fluency: Framework & Foundations

### Day 2 — 실무 활용 입문
> Claude와 함께 실제 업무를 어떻게 하는가

- [ ] Introduction to Claude Cowork
- [ ] Claude Code 101

### Day 3 — Claude Code 실전 + 에이전트
> Claude Code를 개발 workflow에 통합하고 자동화한다

- [ ] Claude Code in Action
- [ ] Introduction to agent skills
- [ ] Introduction to subagents

### Day 4 — AI Fluency 시리즈
> 대상별 변주, 빠르게 일괄 수강

- [ ] AI Fluency for educators
- [ ] AI Fluency for students
- [ ] Teaching AI Fluency
- [ ] AI Fluency for nonprofits

### Day 5 — Claude API 개발
> API를 직접 다루는 방법 전반

- [ ] Building with the Claude API

### Day 6 — MCP (Model Context Protocol)
> Claude를 외부 도구·시스템과 연결하는 방법

- [ ] Introduction to Model Context Protocol
- [ ] Model Context Protocol: Advanced Topics

### Day 7 — 클라우드 플랫폼 + 복습 및 실습
> AWS/GCP 환경에서의 Claude 운용 + 전체 실습

- [ ] Claude with Amazon Bedrock
- [ ] Claude with Google Cloud Vertex AI
- [ ] 보고서 작성·뉴스분석 시나리오 직접 실습

---

## 우선순위 정리

| 중요도 | 일차 | 핵심 이유 |
|--------|------|-----------|
| ★★★ | Day 1~3 | 실무 직접 활용 |
| ★★ | Day 4~5 | 이해도 강화 |
| ★ | Day 6~7 | 기술 심화 (선택적) |

> MCP·Bedrock·Vertex AI는 당장 행정 업무에 필요성이 낮으므로 시간 부족 시 개요만 파악 후 추후 학습 가능.

---

## 참고 자료

- [Anthropic 공식 강좌 목록](https://anthropic.skilljar.com/)
- [Anthropic 강좌 GitHub](https://github.com/anthropics/courses)
- [Claude Code 공식 문서](https://docs.anthropic.com/claude-code)

---

## CLAUDE.md 예시 (실제 프로젝트 적용 참고용)

> 아래는 실제 서비스 프로젝트에 CLAUDE.md를 작성할 때의 예시입니다.

### Architecture (아키텍처) 예시

모노레포 구조, Turborepo 기반

```
apps/
  web/      → Next.js 14 (App Router) - 고객용 프론트엔드
  admin/    → Next.js 14 - 어드민 대시보드
  api/      → Express + TypeScript - REST API 서버
packages/
  ui/       → 공유 UI 컴포넌트 (Shadcn/ui 기반)
  db/       → Prisma ORM + PostgreSQL
  shared/   → 공통 타입, 유틸리티
```

### Tech Stack (기술 스택) 예시

- Frontend: Next.js 14, TypeScript, Tailwind CSS, Zustand
- Backend: Express, TypeScript, Prisma ORM
- DB: PostgreSQL (Supabase), Redis (캐싱)
- Infra: Vercel (프론트), Railway (API), GitHub Actions (CI/CD)

### Build & Test Commands (빌드/테스트) 예시

```bash
pnpm install  # 의존성 설치
pnpm dev      # 전체 dev 서버 실행
pnpm build    # 전체 빌드
pnpm test     # Vitest 전체 테스트
pnpm lint     # ESLint + Prettier 체크
```

### Domain Context (도메인 컨텍스트) 예시

- **Product**: 상품. 여러 Variant(옵션 조합)을 가짐
- **Variant**: 색상/사이즈 등 옵션 조합. 각각 독립된 재고(stock) 보유
- **Cart → Order → Payment**: 장바구니 → 주문 생성 → 결제 순서
- **Fulfillment**: 배송 처리, 주문 완료 후 자동 생성

### Coding Conventions (코딩 컨벤션) 예시

- 컴포넌트: PascalCase (`ProductCard.tsx`)
- 유틸/훅: camelCase (`useCart.ts`, `formatPrice.ts`)
- API 라우트: kebab-case (`/api/order-items`)
- 커밋 메시지: Conventional Commits (`feat:`, `fix:`, `chore:`)
- 커밋 메시지는 영어, 코드 주석은 한국어 허용
- React 컴포넌트는 named export 사용 (default export 금지)
- API 응답은 항상 `{ success, data, error }` 형태로 통일

### Key Patterns (핵심 패턴) 예시

- Server Components 우선, 클라이언트 상태 필요할 때만 `"use client"`
- API 에러는 `AppError` 클래스로 통일 (`packages/shared/errors.ts`)
- DB 접근은 반드시 `packages/db`와 repository 패턴을 통해서만
- 환경변수는 `packages/shared/env.ts`에서 zod로 검증 후 사용
