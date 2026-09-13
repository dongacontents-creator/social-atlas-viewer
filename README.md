# social-atlas-viewer

초등 사회과 부도 PDF 뷰어와 세계 인구 통계 검색 도구

- `index.html` — 메인 앱 (사회과 부도 페이지 뷰어 + 국가별 통계 검색/순위/지도)
- `pdfpage-1.png`, `pdfpage-2.png` — `book.pdf`에서 미리 렌더링한 쪽 이미지 (뷰어가 실제로 불러오는 파일)
- `book.pdf` — 원본 부도 PDF (보관용)
- `countries.geo.json` — 국가 경계선 데이터. [`@geo-maps/countries-land-10km`](https://www.npmjs.com/package/@geo-maps/countries-land-10km) (MIT License, 라이선스 전문은 `countries.geo.LICENSE.txt` 참고)

## 지도 기능

국가를 선택하면 OpenStreetMap 타일 위에 해당 국가 경계를 강조해서 보여줍니다.
API 키가 필요 없는 완전 무료 방식(Leaflet + OpenStreetMap)을 사용했습니다.
바티칸·모나코·산마리노·몰디브·세인트키츠 네비스·나우루·투발루처럼 국토가 매우
작은 나라는 경계선 데이터 해상도의 한계로 마커 표시로 대신합니다.

## 배포

`main` 브랜치에 푸시하면 GitHub Actions가 자동으로 GitHub Pages에 배포합니다.
배포 후 주소: `https://dongacontents-creator.github.io/social-atlas-viewer/`
