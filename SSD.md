# 🛠️ 軟體設計文件 (SDD) — HTML5 LRC 繁簡中文同步播放器

## 1. 系統架構與技術棧
本程式採用 **Single-File App (單一檔案應用程式)** 架構設計，將結構、樣式、邏輯濃縮於單個 `.html` 檔案中，免除任何建置步驟與依賴包安裝。
* **結構層 (Structure)**：HTML5（語意化標籤、`<audio>` 原生媒體元件）。
* **樣式層 (Style)**：CSS3（Flexbox 彈性佈局、Scroll-Behavior 平滑控制、CSS Transition 動態特效）。
* **邏輯層 (Logic)**：原生 JavaScript（ES6+、FileReader API、TextDecoder API、Web Audio 核心事件）。

## 2. 核心模組與資料結構設計

### 2.1 歌詞資料結構 (Lyrics Array)
LRC 檔案經解析後，於記憶體中維護一個結構化的 JavaScript 陣列：
```javascript
lyrics = [
    { time: 0.0,   text: "《妙雲集》序目", id: "line_1" },
    { time: 11.5,  text: "民國五十八年九月...", id: "line_2" }
];