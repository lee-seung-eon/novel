# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 이 저장소는

Claude로 쓰는 HTML 웹소설 아카이브("서재")입니다 — 빌드 과정, 프레임워크, 번들러, 의존성이 전혀 없습니다. 모든 페이지는 브라우저에서 바로 열리거나 GitHub Pages에서 렌더링되는 순수 정적 `.html` 파일입니다. 본문은 한국어(`lang="ko"`)입니다.

## 구조 (3단 계층)

```
index.html            서재 — 최초 진입점. 모든 작품 카드를 나열.
novels/<작품명>/
  index.html          그 작품의 목차 — 각 화로 링크.
  <작품명>_N화.html    각 화. 자체 완결형 독립 HTML.
README.md             GitHub 진입점(작품 목록 + 로컬/Pages 열람법).
```

탐색 흐름은 **서재(루트 `index.html`) → 작품 목차(`novels/<작품명>/index.html`) → 각 화** 입니다.

## 핵심 규칙

- **각 화 HTML은 자체 완결형입니다.** 각 화 파일은 폰트 `<link>`, 전체 `<style>`, 본문, `<script>`를 자기 안에 전부 담습니다. 공유 CSS 파일이 없습니다 — 스타일을 바꾸려면 해당 파일의 `<style>` 블록을 편집합니다. (이는 의도된 설계이며, 각 화가 어디서든 단독으로 열리게 하기 위함입니다.)
- **새 화 추가는 두 파일 작업입니다**: `novels/<작품명>/<작품명>_N화.html`을 만들고 *동시에* 그 작품의 `novels/<작품명>/index.html` 목차 `<ul class="toc">`에 링크를 추가합니다. 목차에 없는 화는 사실상 존재하지 않는 화입니다.
- **새 작품 추가는**: `novels/<작품명>/` 폴더 + 그 안 목차 `index.html`을 만들고, 루트 `index.html`(서재)의 `.grid`에 작품 카드를, `README.md` 작품 목록 표에 행을 추가합니다.
- **화 간 이동 네비게이션은 수동입니다.** 각 화 본문 끝(`.colophon` 바로 앞)에 이전/목차/다음 링크를 담은 `<nav>`가 인라인 스타일로 박혀 있습니다. 화를 삽입·삭제·재정렬하면 앞뒤 화의 이전/다음 링크를 직접 고쳐야 합니다 — 자동 생성이 없습니다. 목차 링크는 항상 같은 폴더의 `index.html`(상대경로), 서재로 가는 링크는 `../../index.html`.
- **기존 화 파일을 편집할 때는 디자인을 보존하세요.** 각 화는 공들여 만든 시각 테마(예: 온실의 다크 "테라리움 관제 시스템" 톤 — `--ice`, `--line`, `--frost` 등 CSS 변수, 상단 스캔 라인, 관제 패널, 엔드카드)를 갖습니다. 새 요소를 넣을 때는 그 파일에 이미 정의된 CSS 변수를 재사용해 톤을 맞춥니다.
- **본문 마크업 관례**: 본문은 `<main>` 안, 각 문단은 `<p>`. 대사는 `<p class="line">`, 짧은 강조·독백 한 줄은 `<p class="beat">`, 장면 전환은 `<div class="brk">`. 화 끝에는 `.endcard`(종료 스탬프·점수 등)와 `.colophon`.

## 보기

`index.html`을 브라우저에서 바로 열거나, 저장소 폴더를 정적으로 서빙(`python -m http.server` → `http://localhost:8000`)합니다. 빌드·컴파일·설치할 것이 없습니다. GitHub에 올릴 때는 Settings → Pages(Branch: main / root)로 웹에 공개할 수 있습니다.
