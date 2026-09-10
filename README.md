# 이도현 · Do Hyeon Lee — Portfolio Website

반응형(모바일·데스크탑) 정적 웹사이트. 서버·빌드 도구 없이 그대로 배포됩니다.

## 구조
```
index.html            사이트 전체 (단일 파일, 오프라인 동작)
docs/                 PDF 원본 — 페이지 내 뷰어 · 새 탭 · 다운로드
vendor/               PDF 렌더러 (pdf.js 4.10)
assets/               아트인컬처 지면 원본 이미지 (클릭 시 새 탭으로 열림)
.nojekyll             GitHub Pages가 파일을 그대로 서빙하도록 함
```

## GitHub Pages 배포
1. 새 저장소 생성 (예: `portfolio`, 또는 `<username>.github.io`)
2. 이 폴더의 파일을 저장소 **루트**에 업로드 (index.html이 루트에 있어야 함)
3. Settings → Pages → Source: `Deploy from a branch` → Branch `main` / `/ (root)` → Save
4. 1–2분 후 `https://<username>.github.io/portfolio/` 에서 확인

## 콘텐츠 수정
- 텍스트·색상: `index.html` 안의 `<x-dc>` 블록 (국문은 `data-ko`, 영문은 `data-en` span)
- PDF 교체: `docs/`에 같은 파일명으로 덮어쓰기. 파일명·페이지 수를 바꾸려면 `index.html`의 `docList()` 배열 수정
- 색 테마: `data-props`의 `direction` 기본값 — `mono`(기본) / `mono-dark` / `a` / `b` / `c`

## 참고
- 본문 서체 Pretendard는 CDN(jsDelivr)에서 로드됩니다. 오프라인에서는 시스템 산세리프로 대체됩니다.
- PDF는 파일 크기 때문에 `index.html`에 포함하지 않고 별도 파일로 로드합니다. `docs/`, `vendor/`를 함께 올려야 포트폴리오 탭이 동작합니다.
