# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

# Project: Practice Claude (Claude Code 학습)

## Critical Rules (절대 규칙)

- `.env`, API 키 등 시크릿 파일 절대 커밋 금지
- main 브랜치에 직접 push 금지 — 반드시 PR을 통해 머지
- 실습 코드는 반드시 해당 일차 디렉토리(day1/, day2/ …)에 저장

## Architecture (학습 구조)

Anthropic 공식 강좌(https://anthropic.skilljar.com/) 17개를 7일 로드맵으로 수강하며, 일차별 디렉토리에 실습 코드와 결과물을 관리한다.

```
day1/   → AI Capabilities and Limitations, Claude 101, AI Fluency: Framework & Foundations
day2/   → Introduction to Claude Cowork, Claude Code 101
day3/   → Claude Code in Action, agent skills, subagents
day4/   → AI Fluency 시리즈 (educators, students, teaching, nonprofits)
day5/   → Building with the Claude API
day6/   → Introduction to MCP, MCP Advanced Topics
day7/   → Claude with Amazon Bedrock, Claude with Google Cloud Vertex AI
```

## Git 설정

- 원격 저장소: `git@github.com:seenbeomlee/practice_claude.git`
- SSH 키: `~/.ssh/seenbeomlee-GitHub` (SSH config에 `Host github.com`으로 등록됨)
- 기본 브랜치: `main`

## 학습 목표

행정 사무관 업무에 Claude Code를 활용하기 위한 입문 학습 저장소다.

- 보고서 작성 자동화 및 초안 생성
- 뉴스기사·정책 자료 분석
- 반복 행정 업무 효율화
