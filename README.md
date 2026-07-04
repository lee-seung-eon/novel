# 📖 서재 · Web Novel Archive

Claude로 쓰는 HTML 웹소설 모음입니다. 각 화는 브라우저에서 바로 열리는 정적 HTML이며, 빌드·설치 과정이 없습니다.

## ▶ 읽기 시작 (최초 진입점)

**[index.html](index.html) — 서재 열기**

위 파일을 브라우저로 열면 전체 작품 목록(서재)이 나옵니다. 작품 → 목차 → 각 화 순으로 이동합니다.

> GitHub에서는 `.md`만 미리보기되고 `.html`은 소스로 표시됩니다. 실제로 읽으려면 저장소를 내려받아 `index.html`을 열거나, 아래 GitHub Pages를 켜세요.

### 로컬에서 보기
```bash
# 저장소 폴더에서
python -m http.server
# 브라우저에서 http://localhost:8000 접속
```

### GitHub Pages로 웹에 공개하기
저장소 **Settings → Pages → Branch: main / (root)** 로 설정하면
`https://<사용자명>.github.io/<저장소명>/` 에서 서재가 바로 열립니다.

## 📚 작품 목록

| 작품 | 장르 | 상태 | 바로가기 |
|------|------|------|----------|
| **온실** | 생존 · 헌터 · 휴먼 드라마 | 연재 중 · 5화 | [목차](novels/온실/index.html) |

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
