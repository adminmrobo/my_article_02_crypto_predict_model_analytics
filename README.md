# 가상자산 시계열 데이터의 분석과 예측 — 연구실 대시보드 (01번)

**[한국어](#ko) · [English](#en) · [中文](#zh) · [日本語](#ja) · [Oʻzbekcha](#uz) · [Русский](#ru) · [Tiếng Việt](#vi)**

---

<a id="ko"></a>

## 한국어

안상선(2024)의 논문 「가상자산 시계열 데이터의 분석과 예측: 시계열 모델 및 인공지능 모델의 비교 및 개선점 제시」(미래사회 15권 1호, 21~33쪽)의 통계 수치와 연구 설계를 그대로 옮겨, 연구실 식구 네 명(박사·조수·초파리 연구원·Money-Robo)의 해설과 브라우저 실습으로 풀어낸 인터랙티브 교육 페이지다. 그림·데이터·스크립트를 한 파일에 모두 담아(base64) 빌드 과정 없이 브라우저로 열기만 하면 동작한다. 외부에서 불러오는 것은 IBM Plex Sans KR 폰트뿐이다.

### 바로 보기

- `https://adminmrobo.github.io/<저장소이름>/` — 저장소 첫 화면 (index.html): 7개 언어 입구.
- `https://adminmrobo.github.io/<저장소이름>/01_crypto_timeseries.html` — 한국어판. `<저장소이름>`은 실제 저장소 이름으로 바꿔 적는다 (플레이스홀더).

### 저자

글 · 안상선 ((주)M-Robo 대표) — 원전 논문 및 등장인물의 원저자.

### 언어

- 언어 전환: 상단 메뉴의 🌐 선택 상자, 내비게이션 바로 아래의 🌐 언어 배너. 고른 언어는 브라우저에 기억되고(localStorage), 다음 방문 때 한국어 페이지에서 파일이 있는지 확인한 뒤 자동으로 그 언어로 옮겨간다.
- 언어별 파일은 같은 폴더에 나란히 둔다(하위 폴더 없음 — GitHub 웹 업로드 대응). 다른 시리즈 링크는 한국어로 연결된다.

| 언어 | 파일 | 바로 보기 |
|---|---|---|
| 한국어 | `01_crypto_timeseries.html` | [열기](https://adminmrobo.github.io/<저장소이름>/01_crypto_timeseries.html) |
| English | `01_crypto_timeseries.en.html` | [Open](https://adminmrobo.github.io/<저장소이름>/01_crypto_timeseries.en.html) |
| 中文 | `01_crypto_timeseries.zh.html` | [打开](https://adminmrobo.github.io/<저장소이름>/01_crypto_timeseries.zh.html) |
| 日本語 | `01_crypto_timeseries.ja.html` | [開く](https://adminmrobo.github.io/<저장소이름>/01_crypto_timeseries.ja.html) |
| Oʻzbekcha | `01_crypto_timeseries.uz.html` | [Ochish](https://adminmrobo.github.io/<저장소이름>/01_crypto_timeseries.uz.html) |
| Русский | `01_crypto_timeseries.ru.html` | [Открыть](https://adminmrobo.github.io/<저장소이름>/01_crypto_timeseries.ru.html) |
| Tiếng Việt | `01_crypto_timeseries.vi.html` | [Mở](https://adminmrobo.github.io/<저장소이름>/01_crypto_timeseries.vi.html) |

### 파일 구성

```
index.html                             저장소 첫 화면 - 7개 언어 입구 페이지
01_crypto_timeseries.html              본편 (한국어, 이미지·스크립트 전부 내장)
01_crypto_timeseries.en|zh|ja.html     번역판 (영어·중국어·일본어)
01_crypto_timeseries.uz|ru|vi.html     번역판 (우즈베크어·러시아어·베트남어)
README.md                              소개 · 구성 · 데이터 출처 · 라이선스 (7개 언어 수록)
INDEX.md                               저장소 파일 색인
img/*.png                              도판 원본 9장 (HTML에는 base64로 내장되어 있음)
```

### 페이지 구성

| # | 섹션 | 내용 |
|---|---|---|
| C | 등장인물과 앵커 장부 | 네 식구 소개, 회계실·금고실(C 장부) 앵커 |
| 1 | 지표의 재발견 | RMSE·MAE의 한계와 괴리율(Accuracy Ratio) |
| 2 | 모델 구조도 비교 | RNN · LSTM · 마르코프 체인 · HMM 다이어그램 |
| 3 | HMM 국면 경로 | 비테르비 최적 상태 경로 · 9개 은닉 상태 전이 행렬 |
| 4 | 시계열 실험실 | 60일 순환 기억(Lookback) 슬라이더 비교 시뮬레이션 |
| 5 | 라이벌 대결 | ARIMA(초파리 연구원) vs LSTM(HMM 경로) 판정 — 차이 7%p |
| 6 | 지식 색인 | 논문 핵심 개념 지식 그래프 검색 |
| 7 | 온톨로지 꾸러미 | kg.json · JSON-LD · BibTeX/RIS · CSL 내려받기 |

### 핵심 숫자와 출처 (설명용 모형인 것)

| 숫자 | 성격 | 출처 |
|---|---|---|
| 전체 표본 2,114일 · 검증(Test) 112일 | 논문 수치 | 원전 논문 |
| RNN 괴리율 −5.5% (과소편향) · LSTM 괴리율 +6.7% (과대편향) | 논문 수치 | 원전 논문 |
| ARIMA 괴리율 표준편차 11%p vs LSTM 4%p (대결 차이 7%p) | 논문 수치 | 원전 논문 |
| 은닉 상태 9개 (논문 그림 4-10) | 논문 수치 | 원전 논문 |
| 브라우저 캔버스의 가격 시뮬레이션 · 전이 행렬 값 · 지식 그래프 배치 | 설명용 모형 | 논문 그림의 성격을 모사한 예시 값 — 실제 재현 계산이 아님 |

### 이미지

- **새로 그린 9장** (16비트 RPG 픽셀아트, 굵은 외곽선, 2~3단계 명암): `bg_01`(배경 1920×720), `sc_01_hero`·`sc_01_outro`(장면 1200×800), `cut_01_think`·`cut_01_lv1`·`cut_01_lv3`(컷 960×540), `doc_think`(192×192), `asst_ledger`(180×220), `thumb_01`(600×400, 목차 카드용). 모든 장면에 글자·숫자·로고·비트코인 심볼을 넣지 않았다.
- **재사용 8장**: 공용 표정 세트(`IMG_00_index.md` 참조) — `doc_front` · `asst_smile` · `fly_point` · `robo_coin` · `fly_coffee` · `robo_happy` · `doc_judge` · `robo_chart`.
- 말풍선 캐릭터 스프라이트는 `fruitfly-lab-expressions` 저장소의 공식 표정 스프라이트(E13_neutral)를 배경을 지우고 192px로 정리해 내장했다

### 용어 표기

- 괴리율 = Accuracy Ratio — 절대 오차(RMSE·MAE)의 스케일 종속성을 피하기 위해 논문이 도입한 지표로, 본 페이지 전체에서 같은 말로 쓴다.
- 은닉 상태·국면 = Hidden State — 시장의 보이지 않는 상태를 뜻하며 「국면」과 혼용하지 않는다.
- 순환 기억 = Lookback — LSTM이 한 번에 되돌아보는 과거 구간 길이.

### 라이선스

이 문서와 페이지는 **크리에이티브 커먼즈 저작자표시-비영리 4.0 국제 라이선스(CC BY-NC 4.0)**로 배포한다.

- 출처 표기 예: `안상선 (2024). 가상자산 시계열 데이터의 분석과 예측. 미래사회, 15(1), 21-33. — 연구실 대시보드 해설판, CC BY-NC 4.0`
- 원전 논문: 미래사회학회 「미래사회」 15(1). 자세한 것은 논문 원문을 확인한다.

---

<a id="en"></a>

## English

# Analysis and Prediction of Cryptocurrency Time-Series Data — Lab Dashboard (No. 01)

The statistics and research design of Ahn Sangsun's (2024) paper "Analysis and Prediction of Crypto Currency Time Series Data: Comparison of time series models and artificial intelligence models and suggestions for improvement" (Journal of Future Society 15(1), pp. 21-33) are carried over exactly, and unfolded through the commentary of the four lab residents — the Doctor, the Assistant, the Fruit Fly Researcher and Money-Robo — plus hands-on browser practice. All figures, data and scripts are packed into a single file (base64): no build step, just open it in a browser. The only external request is the IBM Plex Sans font.

### Quick view

- `https://adminmrobo.github.io/<repository-name>/01_crypto_timeseries.en.html` — English edition. Replace `<repository-name>` with the real repository name (placeholder).

### Author

Text · Ahn Sangsun (CEO, M-Robo Co., Ltd.) — original author of the source paper and of the characters.

### Languages

- Switching: the 🌐 selector in the top menu and the 🌐 language banner right below the navigation bar. Your chosen language is remembered by the browser (localStorage); on your next visit the Korean page checks that the file exists and then redirects automatically.
- The language files sit side by side in the same folder (no subfolders — for GitHub web upload). Links to other papers in the series stay Korean.

| Language | File | Open |
|---|---|---|
| 한국어 | `01_crypto_timeseries.html` | [열기](https://adminmrobo.github.io/<repository-name>/01_crypto_timeseries.html) |
| English | `01_crypto_timeseries.en.html` | [Open](https://adminmrobo.github.io/<repository-name>/01_crypto_timeseries.en.html) |
| 中文 | `01_crypto_timeseries.zh.html` | [打开](https://adminmrobo.github.io/<repository-name>/01_crypto_timeseries.zh.html) |
| 日本語 | `01_crypto_timeseries.ja.html` | [開く](https://adminmrobo.github.io/<repository-name>/01_crypto_timeseries.ja.html) |
| Oʻzbekcha | `01_crypto_timeseries.uz.html` | [Ochish](https://adminmrobo.github.io/<repository-name>/01_crypto_timeseries.uz.html) |
| Русский | `01_crypto_timeseries.ru.html` | [Открыть](https://adminmrobo.github.io/<repository-name>/01_crypto_timeseries.ru.html) |
| Tiếng Việt | `01_crypto_timeseries.vi.html` | [Mở](https://adminmrobo.github.io/<repository-name>/01_crypto_timeseries.vi.html) |

### Files

```
index.html                             Repository landing page - entry to all 7 languages
01_crypto_timeseries.html              Main edition (Korean, all images and scripts embedded)
01_crypto_timeseries.en|zh|ja.html     Translations (English · Chinese · Japanese)
01_crypto_timeseries.uz|ru|vi.html     Translations (Uzbek · Russian · Vietnamese)
README.md                              Introduction · structure · data sources · license (7 languages)
INDEX.md                               Repository file index
img/*.png                              9 original figures (embedded in the HTML as base64)
```

### Page structure

| # | Section | Content |
|---|---|---|
| C | Characters and the anchor ledger | The four residents, accounting- and vault-room (C ledger) anchors |
| 1 | Rediscovering metrics | The limits of RMSE·MAE and the Accuracy Ratio |
| 2 | Comparing model structures | RNN · LSTM · Markov chain · HMM diagrams |
| 3 | HMM regime paths | Viterbi optimal state path · 9-hidden-state transition matrix |
| 4 | Time-series lab | 60-day lookback slider comparison simulation |
| 5 | The rival duel | ARIMA (Fruit Fly Researcher) vs LSTM (HMM path) verdict — a 7 pp gap |
| 6 | Knowledge index | Searchable knowledge graph of the paper's key concepts |
| 7 | Ontology bundle | kg.json · JSON-LD · BibTeX/RIS · CSL downloads |

### Key figures and sources (explanatory mock-ups)

| Figure | Nature | Source |
|---|---|---|
| Full sample 2,114 days · test 112 days | Paper figure | Source paper |
| RNN deviation ratio −5.5% (under-estimation bias) · LSTM +6.7% (over-estimation bias) | Paper figure | Source paper |
| ARIMA deviation-ratio std 11 pp vs LSTM 4 pp (duel gap 7 pp) | Paper figure | Source paper |
| 9 hidden states (paper Fig. 4-10) | Paper figure | Source paper |
| Browser-canvas price simulation · transition-matrix values · knowledge-graph layout | Explanatory mock-up | Illustrative values mimicking the nature of the paper's figures — not an actual recomputation |

### Images

- **9 newly drawn** (16-bit RPG pixel art, bold outlines, 2–3 shading steps): `bg_01` (background 1920×720), `sc_01_hero`·`sc_01_outro` (scenes 1200×800), `cut_01_think`·`cut_01_lv1`·`cut_01_lv3` (cuts 960×540), `doc_think` (192×192), `asst_ledger` (180×220), `thumb_01` (600×400, for the index card). No letters, numerals, logos or Bitcoin symbols appear in any scene.
- **8 reused**: the shared expression set (see `IMG_00_index.md`) — `doc_front` · `asst_smile` · `fly_point` · `robo_coin` · `fly_coffee` · `robo_happy` · `doc_judge` · `robo_chart`.
- Speech-bubble character sprites are the official expression sprites (E13_neutral) from the `fruitfly-lab-expressions` repository, keyed out of their background and packed at 192 px.

### Terminology

- Deviation ratio = Accuracy Ratio — the metric the paper introduced to escape the scale dependence of absolute errors (RMSE·MAE); used consistently throughout the page.
- Hidden state — an invisible state of the market; not used interchangeably with "regime".
- Lookback — the length of the past window the LSTM looks back over at once.

### License

This document and page are distributed under the **Creative Commons Attribution-NonCommercial 4.0 International License (CC BY-NC 4.0)** ([deed](https://creativecommons.org/licenses/by-nc/4.0/deed.en)).

- Attribution example: `Ahn Sangsun (2024). Analysis and Prediction of Crypto Currency Time Series Data. Journal of Future Society, 15(1), 21-33. — Lab dashboard explainer edition, CC BY-NC 4.0`
- Source paper: Journal of Future Society 15(1). See the original paper for details.

---

<a id="zh"></a>

## 中文

# 加密货币时间序列数据的分析与预测 — 实验室仪表盘（第01篇）

安相善（2024）论文《加密货币时间序列数据的分析与预测：时间序列模型与人工智能模型的比较及改进建议》（《未来社会》15卷1期，第21–33页）中的统计数值与研究设计被原样移植，通过实验室四名成员（博士、助手、果蝇研究员、Money-Robo）的解说和浏览器实操展开成互动教学页面。全部图片、数据和脚本都封装在一个文件里（base64），无需构建步骤，用浏览器打开即可运行。唯一的外部请求是 IBM Plex Sans 字体。

### 快速查看

- `https://adminmrobo.github.io/<仓库名>/01_crypto_timeseries.zh.html` — 中文版。`<仓库名>`请替换为实际仓库名称（占位符）。

### 作者

文字 · 安相善（M-Robo 株式会社代表）——原论文及登场人物的原作者。

### 语言

- 语言切换：顶部菜单的 🌐 选择框，以及导航栏正下方的 🌐 语言横幅。所选语言会被浏览器记住（localStorage）；下次访问时，韩语页面会先确认文件存在，再自动跳转。
- 各语言文件并列放在同一文件夹中（无子文件夹——便于 GitHub 网页上传）。指向系列其他论文的链接保持韩语。

| 语言 | 文件 | 打开 |
|---|---|---|
| 한국어 | `01_crypto_timeseries.html` | [열기](https://adminmrobo.github.io/<仓库名>/01_crypto_timeseries.html) |
| English | `01_crypto_timeseries.en.html` | [Open](https://adminmrobo.github.io/<仓库名>/01_crypto_timeseries.en.html) |
| 中文 | `01_crypto_timeseries.zh.html` | [打开](https://adminmrobo.github.io/<仓库名>/01_crypto_timeseries.zh.html) |
| 日本語 | `01_crypto_timeseries.ja.html` | [開く](https://adminmrobo.github.io/<仓库名>/01_crypto_timeseries.ja.html) |
| Oʻzbekcha | `01_crypto_timeseries.uz.html` | [Ochish](https://adminmrobo.github.io/<仓库名>/01_crypto_timeseries.uz.html) |
| Русский | `01_crypto_timeseries.ru.html` | [Открыть](https://adminmrobo.github.io/<仓库名>/01_crypto_timeseries.ru.html) |
| Tiếng Việt | `01_crypto_timeseries.vi.html` | [Mở](https://adminmrobo.github.io/<仓库名>/01_crypto_timeseries.vi.html) |

### 文件构成

```
index.html                             仓库首页 - 7 种语言入口页面
01_crypto_timeseries.html              正篇（韩语，图片与脚本全部内嵌）
01_crypto_timeseries.en|zh|ja.html     翻译版（英语·中文·日语）
01_crypto_timeseries.uz|ru|vi.html     翻译版（乌兹别克语·俄语·越南语）
README.md                              简介 · 构成 · 数据来源 · 许可证（含7种语言）
INDEX.md                               仓库文件索引
img/*.png                              9 张图表原图（HTML 中以 base64 内嵌）
```

### 页面构成

| # | 章节 | 内容 |
|---|---|---|
| C | 登场人物与锚点账本 | 四位成员介绍，会计室·金库室（C 账本）锚点 |
| 1 | 指标的再发现 | RMSE·MAE 的局限与偏离率（Accuracy Ratio） |
| 2 | 模型结构图比较 | RNN · LSTM · 马尔可夫链 · HMM 示意图 |
| 3 | HMM 状态路径 | 维特比最优状态路径 · 9 个隐藏状态转移矩阵 |
| 4 | 时间序列实验室 | 60 天回看窗口（Lookback）滑块对比模拟 |
| 5 | 对手对决 | ARIMA（果蝇研究员）vs LSTM（HMM 路径）判定 — 相差 7 个百分点 |
| 6 | 知识索引 | 论文核心概念知识图谱检索 |
| 7 | 本体包裹 | kg.json · JSON-LD · BibTeX/RIS · CSL 下载 |

### 关键数字与来源（说明用模型）

| 数字 | 性质 | 来源 |
|---|---|---|
| 全样本 2,114 天 · 验证（Test）112 天 | 论文数值 | 原论文 |
| RNN 偏离率 −5.5%（低估偏差）· LSTM 偏离率 +6.7%（高估偏差） | 论文数值 | 原论文 |
| ARIMA 偏离率标准差 11 个百分点 vs LSTM 4 个百分点（对决差距 7 个百分点） | 论文数值 | 原论文 |
| 隐藏状态 9 个（论文图 4-10） | 论文数值 | 原论文 |
| 浏览器画布的价格模拟 · 转移矩阵数值 · 知识图谱布局 | 说明用模型 | 模拟论文图性质的示例值 — 并非实际复现计算 |

### 图片

- **新绘制 9 张**（16 位 RPG 像素画，粗描边，2–3 级明暗）：`bg_01`（背景 1920×720）、`sc_01_hero`·`sc_01_outro`（场景 1200×800）、`cut_01_think`·`cut_01_lv1`·`cut_01_lv3`（分镜 960×540）、`doc_think`（192×192）、`asst_ledger`（180×220）、`thumb_01`（600×400，目录卡用）。所有场景均未加入文字、数字、标志或比特币符号。
- **复用 8 张**：共用表情集（见 `IMG_00_index.md`）— `doc_front` · `asst_smile` · `fly_point` · `robo_coin` · `fly_coffee` · `robo_happy` · `doc_judge` · `robo_chart`。
- 对话气泡角色精灵取自 `fruitfly-lab-expressions` 仓库的官方表情精灵（E13_neutral），去除背景后整理成 192px 内嵌。

### 术语约定

- 偏离率 = Accuracy Ratio — 论文为摆脱绝对误差（RMSE·MAE）的尺度依赖性而引入的指标，全页统一使用该称呼。
- 隐藏状态 = Hidden State — 指市场不可见的状态，不与"局面"混用。
- 回看 = Lookback — LSTM 一次性回看的过去区间长度。

### 许可证

本文档与页面按 **知识共享 署名-非商业性使用 4.0 国际许可协议（CC BY-NC 4.0）** 发布（[deed](https://creativecommons.org/licenses/by-nc/4.0/deed.zh)）。

- 出处标注示例：`安相善 (2024). 加密货币时间序列数据的分析与预测. 未来社会, 15(1), 21-33. — 实验室仪表盘解说版, CC BY-NC 4.0`
- 原论文：未来社会学会《未来社会》15(1)。详情请查阅论文原文。

---

<a id="ja"></a>

## 日本語

# 仮想通貨時系列データの分析と予測 — 研究室ダッシュボード（第01篇）

安相善（2024）の論文「仮想通貨時系列データの分析と予測：時系列モデルと人工知能モデルの比較および改善点の提示」（『未来社会』15巻1号、21〜33頁）の統計数値と研究設計をそのまま移し、研究室の住人四人（博士・助手・ショウジョウバエ研究員・Money-Robo）の解説とブラウザ実習で展開したインタラクティブ教育ページです。図・データ・スクリプトを一つのファイルにすべて収め（base64）てあり、ビルド工程なしでブラウザで開くだけで動作します。外部から読み込むのは IBM Plex Sans フォントだけです。

### すぐ見る

- `https://adminmrobo.github.io/<リポジトリ名>/01_crypto_timeseries.ja.html` — 日本語版。`<リポジトリ名>`は実際のリポジトリ名に置き換えてください（プレースホルダー）。

### 作者

文 · 安相善（株式会社M-Robo代表）— 原典論文および登場人物の原作者。

### 言語

- 言語切替：上部メニューの 🌐 セレクトボックス、ナビゲーションバー直下の 🌐 言語バナー。選んだ言語はブラウザに記憶され（localStorage）、次の訪問時、韓国語ページがファイルの存在を確認してから自動的にその言語へ移ります。
- 言語別ファイルは同じフォルダに並べて置きます（サブフォルダなし — GitHub ウェブアップロード対応）。シリーズ他編へのリンクは韓国語のままです。

| 言語 | ファイル | 開く |
|---|---|---|
| 한국어 | `01_crypto_timeseries.html` | [열기](https://adminmrobo.github.io/<リポジトリ名>/01_crypto_timeseries.html) |
| English | `01_crypto_timeseries.en.html` | [Open](https://adminmrobo.github.io/<リポジトリ名>/01_crypto_timeseries.en.html) |
| 中文 | `01_crypto_timeseries.zh.html` | [打开](https://adminmrobo.github.io/<リポジトリ名>/01_crypto_timeseries.zh.html) |
| 日本語 | `01_crypto_timeseries.ja.html` | [開く](https://adminmrobo.github.io/<リポジトリ名>/01_crypto_timeseries.ja.html) |
| Oʻzbekcha | `01_crypto_timeseries.uz.html` | [Ochish](https://adminmrobo.github.io/<リポジトリ名>/01_crypto_timeseries.uz.html) |
| Русский | `01_crypto_timeseries.ru.html` | [Открыть](https://adminmrobo.github.io/<リポジトリ名>/01_crypto_timeseries.ru.html) |
| Tiếng Việt | `01_crypto_timeseries.vi.html` | [Mở](https://adminmrobo.github.io/<リポジトリ名>/01_crypto_timeseries.vi.html) |

### ファイル構成

```
index.html                             リポジトリの最初のページ - 7言語の入り口
01_crypto_timeseries.html              本編（韓国語、画像・スクリプト全部内蔵）
01_crypto_timeseries.en|zh|ja.html     翻訳版（英語・中国語・日本語）
01_crypto_timeseries.uz|ru|vi.html     翻訳版（ウズベク語・ロシア語・ベトナム語）
README.md                              概要 · 構成 · データ出典 · ライセンス（7言語収録）
INDEX.md                               リポジトリファイル索引
img/*.png                              図版オリジナル9枚（HTMLにはbase64で内蔵）
```

### ページ構成

| # | セクション | 内容 |
|---|---|---|
| C | 登場人物とアンカー台帳 | 四人の住人紹介、会計室・金庫室（C台帳）アンカー |
| 1 | 指標の再発見 | RMSE・MAEの限界と乖離率（Accuracy Ratio） |
| 2 | モデル構造図の比較 | RNN · LSTM · マルコフ連鎖 · HMM ダイアグラム |
| 3 | HMM 局面パス | ビタービ最適状態パス · 9隠れ状態の遷移行列 |
| 4 | 時系列ラボ | 60日ルックバック（Lookback）スライダー比較シミュレーション |
| 5 | ライバル対決 | ARIMA（ショウジョウバエ研究員）vs LSTM（HMMパス）判定 — 差7ポイント |
| 6 | 知識索引 | 論文の核心概念ナレッジグラフ検索 |
| 7 | オントロジー包み | kg.json · JSON-LD · BibTeX/RIS · CSL ダウンロード |

### 主要数値と出典（説明用モデル）

| 数値 | 性格 | 出典 |
|---|---|---|
| 全標本2,114日 · 検証（Test）112日 | 論文数値 | 原典論文 |
| RNN乖離率 −5.5%（過小偏向）· LSTM乖離率 +6.7%（過大偏向） | 論文数値 | 原典論文 |
| ARIMA乖離率標準偏差11ポイント vs LSTM 4ポイント（対決差7ポイント） | 論文数値 | 原典論文 |
| 隠れ状態9個（論文図4-10） | 論文数値 | 原典論文 |
| ブラウザキャンバスの価格シミュレーション · 遷移行列の値 · ナレッジグラフ配置 | 説明用モデル | 論文図の性格を模した例示値 — 実際の再現計算ではない |

### 画像

- **新規描き下ろし9枚**（16ビットRPGピクセルアート、太い輪郭線、2〜3段階の陰影）：`bg_01`（背景1920×720）、`sc_01_hero`·`sc_01_outro`（場面1200×800）、`cut_01_think`·`cut_01_lv1`·`cut_01_lv3`（カット960×540）、`doc_think`（192×192）、`asst_ledger`（180×220）、`thumb_01`（600×400、目次カード用）。すべての場面に文字・数字・ロゴ・ビットコインシンボルを入れていません。
- **再利用8枚**：共用表情セット（`IMG_00_index.md` 参照）— `doc_front` · `asst_smile` · `fly_point` · `robo_coin` · `fly_coffee` · `robo_happy` · `doc_judge` · `robo_chart`。
- 吹き出しキャラスプライトは `fruitfly-lab-expressions` リポジトリの公式表情スプライト（E13_neutral）を背景除去して192pxに整理し、内蔵しました。

### 用語表記

- 乖離率 = Accuracy Ratio — 絶対誤差（RMSE・MAE）のスケール依存性を避けるため論文が導入した指標で、本ページ全体で同じ呼び方を使います。
- 隠れ状態 = Hidden State — 市場の見えない状態を指し、「局面」とは混用しません。
- ルックバック = Lookback — LSTMが一度に振り返る過去区間の長さ。

### ライセンス

この文書とページは **クリエイティブ・コモンズ 表示-非営利 4.0 国際ライセンス（CC BY-NC 4.0）** で公開します（[deed](https://creativecommons.org/licenses/by-nc/4.0/deed.ja)）。

- 出典表記例：`安相善 (2024). 仮想通貨時系列データの分析と予測. 未来社会, 15(1), 21-33. — 研究室ダッシュボード解説版, CC BY-NC 4.0`
- 原典論文：未来社会学会『未来社会』15(1)。詳細は論文原文をご確認ください。

---

<a id="uz"></a>

## Oʻzbekcha

# Kriptovalyuta vaqt qatorlarini tahlil qilish va bashorat qilish — Laboratoriya paneli (01-son)

An Sangsun (2024)ning "Kriptovalyuta vaqt qatorlarini tahlil qilish va bashorat qilish: vaqt qatorlari modellari va sunʼiy intellekt modellarini taqqoslash hamda yaxshilash tavsiyalari" (Journal of Future Society 15(1), 21–33-betlar) maqolasidagi statistik raqamlar va tadqiqot dizayni aynan saqlab qolindi hamda ular laboratoriya aʼzolari toʻrtligi — Doktor, Yordamchi, Drozofila tadqiqotchisi va Money-Robo — sharhlari va brauzerda amaliy mashqlar orqali ochib beriladigan interaktiv oʻquv sahifasiga aylandi. Barcha rasmlar, maʼlumotlar va skriptlar bitta faylga (base64) joylashtirilgan: qurish bosqichisiz, brauzerda ochish kifoya. Tashqaridan faqat IBM Plex Sans shrifti yuklanadi.

### Tez koʻrish

- `https://adminmrobo.github.io/<ombor-nomi>/01_crypto_timeseries.uz.html` — oʻzbekcha nashr. `<ombor-nomi>` oʻrniga haqiqiy repozitoriya nomini yozing (placeholder).

### Muallif

Matn · An Sangsun (M-Robo Co., Ltd. direktori) — asl maqola va qahramonlarning asl muallifi.

### Tillar

- Tilni almashtirish: yuqori menyudagi 🌐 tanlash oynasi va navigatsiya paneli ostidagi 🌐 til banneri. Tanlangan til brauzerda eslab qolinadi (localStorage); keyingi tashrifda koreys sahifasi fayl mavjudligini tekshirib, avtomatik ravishda oʻsha tilga oʻtadi.
- Til fayllari bir xil papkada yonma-yon turadi (papkichalar yoʻq — GitHub veb-yuklash uchun). Seriyaning boshqa maqolalari havolalari koreys tilida qoladi.

| Til | Fayl | Ochish |
|---|---|---|
| 한국어 | `01_crypto_timeseries.html` | [열기](https://adminmrobo.github.io/<ombor-nomi>/01_crypto_timeseries.html) |
| English | `01_crypto_timeseries.en.html` | [Open](https://adminmrobo.github.io/<ombor-nomi>/01_crypto_timeseries.en.html) |
| 中文 | `01_crypto_timeseries.zh.html` | [打开](https://adminmrobo.github.io/<ombor-nomi>/01_crypto_timeseries.zh.html) |
| 日本語 | `01_crypto_timeseries.ja.html` | [開く](https://adminmrobo.github.io/<ombor-nomi>/01_crypto_timeseries.ja.html) |
| Oʻzbekcha | `01_crypto_timeseries.uz.html` | [Ochish](https://adminmrobo.github.io/<ombor-nomi>/01_crypto_timeseries.uz.html) |
| Русский | `01_crypto_timeseries.ru.html` | [Открыть](https://adminmrobo.github.io/<ombor-nomi>/01_crypto_timeseries.ru.html) |
| Tiếng Việt | `01_crypto_timeseries.vi.html` | [Mở](https://adminmrobo.github.io/<ombor-nomi>/01_crypto_timeseries.vi.html) |

### Fayl tarkibi

```
index.html                             Repozitoriya bosh sahifasi - 7 til kirish nuqtasi
01_crypto_timeseries.html              Asosiy nashr (koreys, barcha rasm va skriptlar ichida)
01_crypto_timeseries.en|zh|ja.html     Tarjima nashrlar (ingliz · xitoy · yapon)
01_crypto_timeseries.uz|ru|vi.html     Tarjima nashrlar (oʻzbek · rus · vetnam)
README.md                              Tanishtirish · tuzilma · maʼlumot manbalari · litsenziya (7 til)
INDEX.md                               Repozitoriya fayllari koʻrsatkichi
img/*.png                              9 ta asl chizma (HTML ichida base64 koʻrinishida)
```

### Sahifa tuzilmasi

| # | Boʻlim | Mazmun |
|---|---|---|
| C | Qahramonlar va anketa daftari | Toʻrt aʼzo tanishtiruvi, hisob va zirona xonasi (C daftari) anchorlari |
| 1 | Koʻrsatkichlarni qayta kashf etish | RMSE·MAE cheklovlari va chetlanish koeffitsienti (Accuracy Ratio) |
| 2 | Modellar tuzilishini taqqoslash | RNN · LSTM · Markov zanjiri · HMM diagrammalari |
| 3 | HMM rejim yoʻllari | Viterbi optimal holat yoʻli · 9 yashirin holat oʻtish matrisasi |
| 4 | Vaqt qatorlari laboratoriyasi | 60 kunlik Lookback slayderi taqqoslash simulyatsiyasi |
| 5 | Raqib dueli | ARIMA (Drozofila tadqiqotchisi) vs LSTM (HMM yoʻli) hukmi — 7 foiz punkt farq |
| 6 | Bilim indeksi | Maqolaning asosiy tushunchalari bilim grafi qidiruvi |
| 7 | Ontologiya toʻplami | kg.json · JSON-LD · BibTeX/RIS · CSL yuklab olish |

### Asosiy raqamlar va manbalar (tushuntirish uchun namuna)

| Raqam | Xususiyat | Manba |
|---|---|---|
| Toʻliq namuna 2 114 kun · test 112 kun | Maqola raqami | Asl maqola |
| RNN chetlanishi −5,5% (past baholash) · LSTM +6,7% (yuqori baholash) | Maqola raqami | Asl maqola |
| ARIMA chetlanish standogʻi 11 punkt vs LSTM 4 punkt (duel farqi 7 punkt) | Maqola raqami | Asl maqola |
| 9 yashirin holat (maqola 4-10-rasm) | Maqola raqami | Asl maqola |
| Brauzer kanvasidagi narx simulyatsiyasi · oʻtish matritsa qiymatlari · bilim grafi joylashuvi | Tushuntirish namunasi | Maqola rasmlariga xos tabiatni takrorlagan misol qiymatlar — haqiqiy qayta hisob emas |

### Rasmlar

- **Yangi chizilgan 9 ta** (16-bit RPG piksel-art, qalin kontur, 2–3 bosqichli soya): `bg_01` (fon 1920×720), `sc_01_hero`·`sc_01_outro` (sahna 1200×800), `cut_01_think`·`cut_01_lv1`·`cut_01_lv3` (kadr 960×540), `doc_think` (192×192), `asst_ledger` (180×220), `thumb_01` (600×400, koʻrsatkich kartasi uchun). Hech bir sahnaga harf, raqam, logotip yoki bitkoin belgisi qoʻshilmagan.
- **Qayta ishlatilgan 8 ta**: umumiy mimika toʻplami (`IMG_00_index.md` ga qarang) — `doc_front` · `asst_smile` · `fly_point` · `robo_coin` · `fly_coffee` · `robo_happy` · `doc_judge` · `robo_chart`.
- Nutq pufakchali qahramon spritelari `fruitfly-lab-expressions` omborining rasmiy ifoda spritelari (E13_neutral) asosida, fonini olib tashlab 192 px shaffof PNG qilib ichiga joylangan.

### Atamalar

- Chetlanish koeffitsienti = Accuracy Ratio — mutlaq xatolikning (RMSE·MAE) oʻlchamga bogʻliqligidan qochish uchun maqola joriy qilgan koʻrsatkich; butun sahifada shu atama ishlatiladi.
- Yashirin holat = Hidden State — bozorning koʻrinmas holati; "rejim" atamasi bilan almashtirib ishlatilmaydi.
- Lookback — LSTM bir yoʻla orqaga qaraydigan oʻtgan davr uzunligi.

### Litsenziya

Bu hujjat va sahifa **Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)** litsenziyasi ostida tarqatiladi ([deed](https://creativecommons.org/licenses/by-nc/4.0/deed.en)).

- Manbani koʻrsatish namunasi: `Ahn Sangsun (2024). Analysis and Prediction of Crypto Currency Time Series Data. Journal of Future Society, 15(1), 21-33. — Laboratoriya paneli sharh nashri, CC BY-NC 4.0`
- Asl maqola: Journal of Future Society 15(1). Batafsil maʼlumot uchun maqolaning asl nusxasiga qarang.

---

<a id="ru"></a>

## Русский

# Анализ и прогнозирование временных рядов криптовалют — лабораторная панель (№ 01)

Статистические показатели и исследовательский дизайн статьи Ан Сан Сона (2024) «Анализ и прогнозирование временных рядов данных криптовалют: сравнение моделей временных рядов и моделей искусственного интеллекта с предложениями по улучшению» (Journal of Future Society 15(1), стр. 21–33) перенесены в точности и раскрыты через комментарии четырёх обитателей лаборатории — Доктора, Ассистента, Исследователя-дрозофилу и Money-Robo — а также практику прямо в браузере. Все изображения, данные и скрипты упакованы в один файл (base64): этап сборки не нужен, достаточно открыть файл в браузере. Единственный внешний запрос — шрифт IBM Plex Sans.

### Быстрый просмотр

- `https://adminmrobo.github.io/<имя-репозитория>/01_crypto_timeseries.ru.html` — русская версия. `<имя-репозитория>` замените на реальное имя репозитория (заполнитель).

### Автор

Текст · Ан Сан Сон (генеральный директор компании M-Robo) — автор оригинальной статьи и персонажей.

### Языки

- Переключение: селектор 🌐 в верхнем меню и языковой баннер 🌐 сразу под панелью навигации. Выбранный язык запоминается браузером (localStorage); при следующем визите корейская страница проверит наличие файла и автоматически перейдёт на него.
- Файлы языков лежат рядом в одной папке (без подпапок — для загрузки через веб-интерфейс GitHub). Ссылки на другие статьи серии остаются корейскими.

| Язык | Файл | Открыть |
|---|---|---|
| 한국어 | `01_crypto_timeseries.html` | [열기](https://adminmrobo.github.io/<имя-репозитория>/01_crypto_timeseries.html) |
| English | `01_crypto_timeseries.en.html` | [Open](https://adminmrobo.github.io/<имя-репозитория>/01_crypto_timeseries.en.html) |
| 中文 | `01_crypto_timeseries.zh.html` | [打开](https://adminmrobo.github.io/<имя-репозитория>/01_crypto_timeseries.zh.html) |
| 日本語 | `01_crypto_timeseries.ja.html` | [開く](https://adminmrobo.github.io/<имя-репозитория>/01_crypto_timeseries.ja.html) |
| Oʻzbekcha | `01_crypto_timeseries.uz.html` | [Ochish](https://adminmrobo.github.io/<имя-репозитория>/01_crypto_timeseries.uz.html) |
| Русский | `01_crypto_timeseries.ru.html` | [Открыть](https://adminmrobo.github.io/<имя-репозитория>/01_crypto_timeseries.ru.html) |
| Tiếng Việt | `01_crypto_timeseries.vi.html` | [Mở](https://adminmrobo.github.io/<имя-репозитория>/01_crypto_timeseries.vi.html) |

### Состав файлов

```
index.html                             Начальная страница репозитория - вход на 7 языках
01_crypto_timeseries.html              Основная редакция (корейский, все изображения и скрипты встроены)
01_crypto_timeseries.en|zh|ja.html     Переводы (английский · китайский · японский)
01_crypto_timeseries.uz|ru|vi.html     Переводы (узбекский · русский · вьетнамский)
README.md                              Введение · структура · источники данных · лицензия (7 языков)
INDEX.md                               Указатель файлов репозитория
img/*.png                              9 исходных иллюстраций (в HTML встроены как base64)
```

### Структура страницы

| # | Раздел | Содержание |
|---|---|---|
| C | Персонажи и якорная книга | Четверо обитателей, якоря бухгалтерии и хранилища (книга C) |
| 1 | Переоткрытие метрик | Ограничения RMSE·MAE и коэффициент отклонения (Accuracy Ratio) |
| 2 | Сравнение структур моделей | Диаграммы RNN · LSTM · цепи Маркова · HMM |
| 3 | Пути режимов HMM | Оптимальный путь состояний по Витерби · матрица переходов 9 скрытых состояний |
| 4 | Лаборатория временных рядов | Симуляция сравнения со слайдером окна Lookback (60 дней) |
| 5 | Дуэль соперников | ARIMA (Исследователь-дрозофила) против LSTM (путь HMM) — разрыв 7 п.п. |
| 6 | Индекс знаний | Поиск по графу знаний ключевых понятий статьи |
| 7 | Онтологический свёрток | Загрузка kg.json · JSON-LD · BibTeX/RIS · CSL |

### Ключевые числа и источники (объяснительные модели)

| Число | Характер | Источник |
|---|---|---|
| Вся выборка 2 114 дней · тест 112 дней | Число статьи | Исходная статья |
| Коэффициент отклонения RNN −5,5% (недооценка) · LSTM +6,7% (переоценка) | Число статьи | Исходная статья |
| СКО коэффициента отклонения ARIMA 11 п.п. против LSTM 4 п.п. (разрыв дуэли 7 п.п.) | Число статьи | Исходная статья |
| 9 скрытых состояний (рис. 4-10 статьи) | Число статьи | Исходная статья |
| Симуляция цены на канвасе браузера · значения матрицы переходов · раскладка графа знаний | Объяснительная модель | Примерные значения, имитирующие характер рисунков статьи — не фактический пересчёт |

### Изображения

- **9 новых** (пиксель-арт в духе 16-битных RPG, жирный контур, 2–3 ступени тени): `bg_01` (фон 1920×720), `sc_01_hero`·`sc_01_outro` (сцены 1200×800), `cut_01_think`·`cut_01_lv1`·`cut_01_lv3` (кадры 960×540), `doc_think` (192×192), `asst_ledger` (180×220), `thumb_01` (600×400, для карточки оглавления). Ни в одной сцене нет букв, цифр, логотипов или символа биткоина.
- **8 повторно использованных**: общий набор выражений (см. `IMG_00_index.md`) — `doc_front` · `asst_smile` · `fly_point` · `robo_coin` · `fly_coffee` · `robo_happy` · `doc_judge` · `robo_chart`.
- Спрайты персонажей для реплик — официальные спрайты выражений (E13_neutral) из репозитория `fruitfly-lab-expressions`, фон удалён, размер 192 px.

### Терминология

- Коэффициент отклонения = Accuracy Ratio — показатель, введённый статьёй, чтобы уйти от масштабозависимости абсолютных ошибок (RMSE·MAE); по всей странице используется одно название.
- Скрытое состояние = Hidden State — ненаблюдаемое состояние рынка; со словом «режим» не смешивается.
- Lookback — длина прошлого окна, на которое LSTM оглядывается за один шаг.

### Лицензия

Этот документ и страница распространяются по лицензии **Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)** ([deed](https://creativecommons.org/licenses/by-nc/4.0/deed.ru)).

- Пример указания источника: `Ahn Sangsun (2024). Analysis and Prediction of Crypto Currency Time Series Data. Journal of Future Society, 15(1), 21-33. — Лабораторная панель, поясняющее издание, CC BY-NC 4.0`
- Исходная статья: Journal of Future Society 15(1). Подробности — в оригинале статьи.

---

<a id="vi"></a>

## Tiếng Việt

# Phân tích và dự báo dữ liệu chuỗi thời gian tiền mã hóa — Bảng điều khiển phòng thí nghiệm (Số 01)

Các con số thống kê và thiết kế nghiên cứu của bài báo của Ahn Sangsun (2024) "Analysis and Prediction of Crypto Currency Time Series Data: Comparison of time series models and artificial intelligence models and suggestions for improvement" (Journal of Future Society 15(1), tr. 21–33) được chuyển nguyên vẹn, rồi triển khai qua phần bình luận của bốn cư dân phòng thí nghiệm — Tiến sĩ, Trợ lý, Nhà nghiên cứu Ruồi giấm và Money-Robo — cùng thực hành ngay trên trình duyệt. Toàn bộ hình ảnh, dữ liệu và tập lệnh được gói trong một tệp duy nhất (base64): không cần bước build, chỉ cần mở bằng trình duyệt. Yêu cầu bên ngoài duy nhất là phông chữ IBM Plex Sans.

### Xem nhanh

- `https://adminmrobo.github.io/<ten-kho>/01_crypto_timeseries.vi.html` — bản tiếng Việt. `<ten-kho>` thay bằng tên kho thực tế (placeholder).

### Tác giả

Chữ · Ahn Sangsun (Giám đốc công ty M-Robo) — tác giả gốc của bài báo và các nhân vật.

### Ngôn ngữ

- Chuyển ngôn ngữ: ô chọn 🌐 trên menu đầu trang và biểu ngữ ngôn ngữ 🌐 ngay dưới thanh điều hướng. Ngôn ngữ đã chọn được trình duyệt ghi nhớ (localStorage); lần truy cập sau, trang tiếng Hàn sẽ kiểm tra tệp có tồn tại rồi tự động chuyển sang ngôn ngữ đó.
- Các tệp ngôn ngữ nằm cạnh nhau trong cùng một thư mục (không có thư mục con — phục vụ tải lên web GitHub). Liên kết tới các bài khác của chuỗi giữ nguyên tiếng Hàn.

| Ngôn ngữ | Tệp | Mở |
|---|---|---|
| 한국어 | `01_crypto_timeseries.html` | [열기](https://adminmrobo.github.io/<ten-kho>/01_crypto_timeseries.html) |
| English | `01_crypto_timeseries.en.html` | [Open](https://adminmrobo.github.io/<ten-kho>/01_crypto_timeseries.en.html) |
| 中文 | `01_crypto_timeseries.zh.html` | [打开](https://adminmrobo.github.io/<ten-kho>/01_crypto_timeseries.zh.html) |
| 日本語 | `01_crypto_timeseries.ja.html` | [開く](https://adminmrobo.github.io/<ten-kho>/01_crypto_timeseries.ja.html) |
| Oʻzbekcha | `01_crypto_timeseries.uz.html` | [Ochish](https://adminmrobo.github.io/<ten-kho>/01_crypto_timeseries.uz.html) |
| Русский | `01_crypto_timeseries.ru.html` | [Открыть](https://adminmrobo.github.io/<ten-kho>/01_crypto_timeseries.ru.html) |
| Tiếng Việt | `01_crypto_timeseries.vi.html` | [Mở](https://adminmrobo.github.io/<ten-kho>/01_crypto_timeseries.vi.html) |

### Cấu trúc tệp

```
index.html                             Trang đầu của kho - lối vào 7 ngôn ngữ
01_crypto_timeseries.html              Bản chính (tiếng Hàn, nhúng toàn bộ hình và tập lệnh)
01_crypto_timeseries.en|zh|ja.html     Bản dịch (tiếng Anh · Trung · Nhật)
01_crypto_timeseries.uz|ru|vi.html     Bản dịch (tiếng Uzbek · Nga · Việt)
README.md                              Giới thiệu · cấu trúc · nguồn dữ liệu · giấy phép (7 ngôn ngữ)
INDEX.md                               Chỉ mục tệp của kho
img/*.png                              9 hình gốc (được nhúng base64 trong HTML)
```

### Cấu trúc trang

| # | Mục | Nội dung |
|---|---|---|
| C | Nhân vật và sổ neo | Bốn cư dân, neo phòng kế toán · kho bạc (sổ C) |
| 1 | Tái khám phá chỉ số | Giới hạn của RMSE·MAE và tỷ lệ sai lệch (Accuracy Ratio) |
| 2 | So sánh cấu trúc mô hình | Sơ đồ RNN · LSTM · chuỗi Markov · HMM |
| 3 | Đường trạng thái HMM | Đường trạng thái tối ưu Viterbi · ma trận chuyển 9 trạng thái ẩn |
| 4 | Phòng thí nghiệm chuỗi thời gian | Mô phỏng so sánh thanh trượt Lookback 60 ngày |
| 5 | Trận đấu kình địch | Phán quyết ARIMA (Nhà nghiên cứu Ruồi giấm) vs LSTM (đường HMM) — chênh 7 điểm phần trăm |
| 6 | Chỉ mục tri thức | Tìm kiếm đồ thị tri thức các khái niệm cốt lõi của bài báo |
| 7 | Gói bản thể luận | Tải xuống kg.json · JSON-LD · BibTeX/RIS · CSL |

### Các con số then chốt và nguồn (mô hình minh họa)

| Số | Tính chất | Nguồn |
|---|---|---|
| Toàn bộ mẫu 2.114 ngày · kiểm định 112 ngày | Số liệu bài báo | Bài báo gốc |
| Tỷ lệ sai lệch RNN −5,5% (thiên lệch thấp hơn) · LSTM +6,7% (thiên lệch cao hơn) | Số liệu bài báo | Bài báo gốc |
| Độ lệch chuẩn tỷ lệ sai lệch ARIMA 11 điểm phần trăm vs LSTM 4 (chênh trận đấu 7) | Số liệu bài báo | Bài báo gốc |
| 9 trạng thái ẩn (hình 4-10 của bài báo) | Số liệu bài báo | Bài báo gốc |
| Mô phỏng giá trên canvas · giá trị ma trận chuyển · bố cục đồ thị tri thức | Mô hình minh họa | Giá trị ví dụ bắt chước tính chất hình của bài báo — không phải tính toán tái lập thực tế |

### Hình ảnh

- **9 hình vẽ mới** (pixel art RPG 16-bit, viền đậm, 2–3 mức sáng tối): `bg_01` (nền 1920×720), `sc_01_hero`·`sc_01_outro` (cảnh 1200×800), `cut_01_think`·`cut_01_lv1`·`cut_01_lv3` (cảnh cắt 960×540), `doc_think` (192×192), `asst_ledger` (180×220), `thumb_01` (600×400, dùng cho thẻ mục lục). Không cảnh nào có chữ, số, logo hay ký hiệu Bitcoin.
- **8 hình dùng lại**: bộ biểu cảm chung (xem `IMG_00_index.md`) — `doc_front` · `asst_smile` · `fly_point` · `robo_coin` · `fly_coffee` · `robo_happy` · `doc_judge` · `robo_chart`.
- Sprite nhân vật bong bóng thoại lấy từ các sprite biểu cảm chính thức (E13_neutral) của kho `fruitfly-lab-expressions`, đã xóa phông và đóng gói 192 px.

### Thuật ngữ

- Tỷ lệ sai lệch = Accuracy Ratio — chỉ số bài báo đưa ra để thoát khỏi sự phụ thuộc thang đo của sai số tuyệt đối (RMSE·MAE); dùng thống nhất trên toàn trang.
- Trạng thái ẩn = Hidden State — trạng thái vô hình của thị trường; không dùng lẫn với "chế độ".
- Lookback — độ dài đoạn quá khứ LSTM nhìn lại trong một lần.

### Giấy phép

Tài liệu và trang này được phân phát theo giấy phép **Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)** ([deed](https://creativecommons.org/licenses/by-nc/4.0/deed.en)).

- Ví dụ ghi nguồn: `Ahn Sangsun (2024). Analysis and Prediction of Crypto Currency Time Series Data. Journal of Future Society, 15(1), 21-33. — Bản giải thích bảng điều khiển phòng thí nghiệm, CC BY-NC 4.0`
- Bài báo gốc: Journal of Future Society 15(1). Chi tiết xem bài báo gốc.
