# 범어로제피부과의원 — 시안

대구 수성구 범어동 범어로제피부과의원의 검색 노출용 사이트 **시안**입니다.
확인을 받기 위한 판이며, 아직 정식으로 연 사이트가 아닙니다.

**보기 → https://eplhansol.github.io/rosee-site/**

## 지금 상태

- 48쪽 (허브 9 · 글 32 · 안내 7)
- **검색 색인을 막아 두었습니다** — `robots.txt` 전면 차단, 모든 쪽에
  `noindex, nofollow`. 확인 전 원고가 검색에 잡히면 나중에 정식 도메인으로
  열 때 같은 글이 두 곳에 있는 꼴이 되기 때문입니다.
- 도메인이 정해지지 않아 `canonical` 은 걸지 않았습니다.
- 하위 경로(`/rosee-site/`)에 놓여 있어 내부 링크에 그 접두사가 붙어 있습니다.
- 시술 전후 사진은 싣지 않았습니다. 비급여 진료비는 병원 공식 페이지로 잇습니다.

## 구조

    docs/            사이트 그대로 (GitHub Pages 가 여기를 봅니다)
    wrangler.toml    Cloudflare Workers 로 옮길 때 쓰는 설정

생성기(`data.py`·`pages.py` 등)는 비공개 저장소에 있고, 여기에는 만들어진
결과만 올립니다.

## 다시 만들 때

시안용 — 세 값을 함께 준다.

    SITE_NOINDEX=1
    SITE_HOST=https://eplhansol.github.io/rosee-site
    SITE_BASE=/rosee-site

정식 오픈 때는 `SITE_NOINDEX` 와 `SITE_BASE` 없이 도메인만 주면 됩니다.
`canonical`·`og:url`·`sitemap`·`rss` 가 함께 따라갑니다.

    SITE_HOST=https://<정한 도메인> python make.py
