# 📖 서재 · Web Novel Archive

Claude로 쓰는 HTML 웹소설 모음입니다. 각 화는 브라우저에서 바로 열리는 정적 HTML이며, 빌드·설치 과정이 없습니다.

## ▶ 읽기 시작 (웹에서 바로 보기)

### **👉 [여기를 눌러 서재 열기](https://lee-seung-eon.github.io/novel/)**

GitHub Pages로 렌더링된 실제 웹페이지입니다. (저장소 안의 `.html` 링크를 GitHub에서 누르면 페이지가 아니라 **코드**가 보이므로, 읽을 때는 반드시 위 Pages 링크를 이용하세요.)

> **처음 한 번은 Pages를 켜야 합니다.** 저장소 **Settings → Pages → Build and deployment → Source: `Deploy from a branch` → Branch: `main` / `(root)` → Save**. 1~2분 뒤 위 링크가 열립니다.

### 로컬에서 보기
```bash
# 저장소 폴더에서
python -m http.server
# 브라우저에서 http://localhost:8000 접속
```

## 📚 작품 목록

| 작품 | 장르 | 상태 | 바로가기 |
|------|------|------|----------|
| **온실** | 생존 · 헌터 · 휴먼 드라마 | 연재 중 · 5화 | [웹에서 읽기](https://lee-seung-eon.github.io/novel/novels/%EC%98%A8%EC%8B%A4/) |

## 🗂 구조

```
index.html                  ← 서재 (최초 진입점, 작품 목록)
novels/
  └─ 온실/
       ├─ index.html        ← 온실 목차
       ├─ 온실_1화.html      ← 각 화 (독립 HTML)
       ├─ 온실_2화.html
       └─ …
README.md
CLAUDE.md                   ← Claude Code용 저장소 안내
```

작품을 추가하려면 `novels/<작품명>/` 폴더를 만들고, 그 안에 목차 `index.html`과 각 화 HTML을 넣은 뒤, 루트 `index.html`(서재)과 이 README의 작품 목록에 링크를 더합니다.

*written with Claude*
