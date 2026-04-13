# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

LH 매입임대 입주 가이드 - 단일 HTML 정적 페이지.

## Stack

- Single `index.html` (no build step, no dependencies)
- Tailwind CSS via CDN (`cdn.tailwindcss.com`)
- Vanilla JavaScript (no framework)

## Deploy

Cloudflare Pages (`lh-guide` project) → `lh-guide.gamja.top`

```bash
# Deploy via wrangler (index.html must be in the deploy directory)
CLOUDFLARE_ACCOUNT_ID=f09b385ba9e97f59d343b618146b9a05 npx wrangler pages deploy . --project-name=lh-guide --commit-dirty=true --branch=main
```

## Structure

Everything lives in `index.html`:
- `<style>` block: custom CSS (input styles, tab states, bottom sheet, animations)
- `<body>`: two tab views — "계좌별 자금 흐름도" (fund flow) and "입주 타임라인" (timeline)
- `<script>` block: calculation logic, tab switching, bottom sheet settings panel
