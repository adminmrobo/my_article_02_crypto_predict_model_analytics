# INDEX — 저장소 파일 색인

| 파일 | 용도 |
|---|---|
| `index.html` | 저장소 첫 화면 (GitHub Pages 진입) - 7개 언어 입구 링크와 안내 |
| `01_crypto_timeseries.html` | 본편. 한국어 인터랙티브 페이지 — 그림·데이터·스크립트 전부 base64 내장, 단독으로 열린다 |
| `01_crypto_timeseries.en.html` | 영어판 — 한국어판과 동일 구성, IBM Plex Sans |
| `01_crypto_timeseries.zh.html` | 중국어판 (zh-CN, Noto Sans SC, CJK 줄바꿈 규칙 적용) |
| `01_crypto_timeseries.ja.html` | 일본어판 (Noto Sans JP, CJK 줄바꿈 규칙 적용) |
| `01_crypto_timeseries.uz.html` | 우즈베크어판 |
| `01_crypto_timeseries.ru.html` | 러시아어판 |
| `01_crypto_timeseries.vi.html` | 베트남어판 |
| `README.md` | 시리즈 소개 · 페이지 구성 · 핵심 숫자 출처 · 이미지 목록 · 언어 전환 · 라이선스 |
| `INDEX.md` | 이 파일 — 저장소 파일 색인 |
| `img/bg_01.png` | 히어로 배경 1920×720 (8:3) — 회계실·금고실, 좌측 45% 제목 여백 |
| `img/sc_01_hero.png` | 히어로 무대 1200×800 — 4인 토론 장면 (등장인물 섹션) |
| `img/cut_01_think.png` | 논문 모드 히어로 컷 960×540 — 생각 구름 (히어로 섹션) |
| `img/cut_01_lv1.png` | 컷 960×540 — ARIMA 장부 → 신경망 곡선 (섹션 2) |
| `img/cut_01_lv3.png` | 컷 960×540 — HMM 상태 전이 + Prophet식 예측 범위 (섹션 3) |
| `img/sc_01_outro.png` | 아웃트로 1200×800 — 대결 승리 축하 (마무리 섹션) |
| `img/doc_think.png` | 박사 사고 스프라이트 192×192 투명 (말풍선) |
| `img/asst_ledger.png` | 조수 장부 스프라이트 180×220 투명 (말풍선) |
| `img/thumb_01.png` | 목차 카드 썸네일 600×400 — `bg_01` 우측 3:2 크롭 |

- HTML에는 위 이미지가 **base64(WebP/PNG)로 내장**되어 있으므로 `img/` 폴더는 원본 보관용이다. 삭제해도 페이지는 그대로 동작한다.
- 재사용 8장(`doc_front` · `asst_smile` · `fly_point` · `robo_coin` · `fly_coffee` · `robo_happy` · `doc_judge` · `robo_chart`)은 공용 이미지 뱅크(`IMG_00_index.md`) 소속으로 이 저장소에 포함되지 않는다.
- 번역판 6종(`*.en` · `*.zh` · `*.ja` · `*.uz` · `*.ru` · `*.vi`)은 한국어판과 **같은 폴더**에 나란히 있다(하위 폴더 없음). 언어 전환은 각 페이지 상단의 🌐 선택 상자·배너 — 고른 언어는 저장되고(localStorage), 자동 전환은 한국어 페이지에서만 파일 확인 후 동작한다.
