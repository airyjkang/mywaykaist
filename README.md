# My Way KAIST — 코드·데이터

- `docs/index.html` : 공개용 웹앱 (GitHub Pages에 올리는 파일). 현재 시각 그늘, 내 위치 출발, 현장조사 기록 반영.
- `app/template.html` : 웹앱 원본(데이터 넣기 전), `app/index.html` : docs와 같은 파일
- `DEVLOG.md` : 개발 원리와 과정 기록
- `data/` : v1 데이터(10/30), `data2/` : v2 데이터(11/4)와 현장조사 기록 묶음
- 재현 순서 (Python 3.10+, `pip install shapely pyproj networkx pvlib pandas`):
  1. `python3 scripts/build_graph.py data/export.json data2 "127.352,36.362,127.372,36.381"` → 보행 그래프·건물·입구·나무
  2. (검증용) `python3 scripts/build_shade.py data2/graph.json data/export.json data2` → 두 날짜의 그늘을 Python으로 계산해 앱 결과와 비교
  3. `python3 scripts/pack.py data2 app/template.html <leaflet.css 경로> app/mywaykaist.html` → 웹앱 조립
- 지도 데이터: © OpenStreetMap 기여자, ODbL
