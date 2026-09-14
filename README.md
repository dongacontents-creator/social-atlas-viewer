# social-atlas-viewer

초등 사회과 부도 PDF 뷰어와 세계 인구 통계 검색 도구

- `index.html` — 메인 앱 (사회과 부도 페이지 뷰어 + 국가별 통계 검색/순위/지도)
- `pdfpage-1.png`, `pdfpage-2.png` — `book.pdf`에서 미리 렌더링한 쪽 이미지 (뷰어가 실제로 불러오는 파일)
- `book.pdf` — 원본 부도 PDF (보관용)
- `countries.geo.json` — 국가 경계선 데이터. 기본은 [`@geo-maps/countries-land-10km`](https://www.npmjs.com/package/@geo-maps/countries-land-10km)이고, 그 해상도에서는
  빠지는 바티칸·모나코·산마리노·몰디브·세인트키츠 네비스·나우루·투발루 7개국만 같은
  저작자의 [`@geo-maps/countries-land-10m`](https://www.npmjs.com/package/@geo-maps/countries-land-10m)에서 해당 폴리곤만 추려 보충했습니다
  (둘 다 MIT License, 라이선스 전문은 `countries.geo.LICENSE.txt` 참고)

## 지도 기능

외부 지도 라이브러리·API 없이 순수 SVG로 세계지도를 직접 그립니다(사내 보안
스캐너가 벤더링된 Leaflet의 태그 선택자·`!important` 등을 위반으로 잡아내
걷어냈습니다). 국가를 선택하면 실제 국경 윤곽선이 강조색으로 표시되고, 그
나라 크기에 맞춰 자동으로 확대되며, +/- 버튼으로 더 확대·축소할 수 있습니다.
195개국 전부 점이 아니라 실제 국경 윤곽으로 표시됩니다. 독도·울릉도는 국경
데이터에 폴리곤이 없을 만큼 작아 대한민국 선택 시 실제 면적 비율을 반영한
점으로 별도 표시합니다.

## 배포

`main` 브랜치에 푸시하면 GitHub Actions가 자동으로 GitHub Pages에 배포합니다.
배포 후 주소: `https://dongacontents-creator.github.io/social-atlas-viewer/`
