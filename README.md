# 웹서비스 API 가이드 (AIX102)

AI 코딩 도구로 서비스를 만드는 초보자를 위한 원페이지 API 가이드입니다.
기능별로 쓸 만한 외부 API(AI · 지도 · 결제 · 로그인 · 메시지 · 공공데이터 등)를 모으고,
각 API의 역할, 주요 모델·제품군, 무료 정책, 공식 문서 링크를 정리했습니다. (2026년 10월 1일 기준)

## 폴더 구성

- `index.html` : 페이지 전체 (데이터 + 스타일 + 스크립트가 한 파일에 들어 있음)
- `images/` : 각 API의 로고 썸네일 (157개, png/svg)
- `README.md` : 이 문서

## GitHub Pages로 배포하기

1. 이 폴더 내용을 GitHub 저장소에 올립니다. (`index.html`과 `images/` 폴더가 같은 위치에 있어야 합니다)
2. 저장소 Settings → Pages → Source를 `Deploy from a branch`, Branch를 `main` / `(root)`로 설정합니다.
3. 잠시 후 `https://<계정>.github.io/<저장소>/` 에서 열립니다.

로컬에서는 `index.html`을 더블클릭해도 그대로 열립니다.

## 내용 수정하기

`index.html` 안의 `<script>` 첫 부분에 `SECTIONS`(섹션 정의)와 `API_DATA`(카드 데이터) 배열이 있습니다.
카드 하나는 아래 모양이며, 항목을 추가·수정하고 저장하면 끝입니다.

```js
{ id: "openai", name: "OpenAI API", domain: "openai.com", cat: "llm", origin: "글로벌", badge: "대표",
  desc: "한 줄 설명",
  lineup: [ { label: "최상위", items: ["GPT-6 Astra"] } ],
  free: "무료 정책",
  note: "참고 사항 (선택)",
  links: { site: "...", docs: "...", models: "...", pricing: "..." },
  tags: "검색용 키워드" }
```

새 카드를 추가할 때는 `images/<id>.png`(또는 `.svg`) 로고 파일을 함께 넣고,
`LOGOS` 객체(`API_DATA` 바로 아래)에 `"<id>": "<id>.png"` 한 줄을 추가하세요.

## 주의

모델명, 가격, 무료 한도는 매우 자주 바뀝니다. 실제 구현 전에는 카드의 **문서** 링크에서 최신 정보를 확인하세요.
로고와 상표는 각 회사의 자산이며 식별 목적으로만 사용했습니다.
