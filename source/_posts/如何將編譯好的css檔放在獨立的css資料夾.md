---
title: 如何使用VSCode編譯Sass檔案
date: 2024-05-26 01:30:20
tags:
- sass
- VSCode
categories:
- [gallery]
featured_image: https://sass-lang.com/assets/img/logos/logo.svg
---


使用 VSCode 和 `sass --watch` 命令來自動編譯 Sass 檔案並將結果輸出到指定的 `css` 資料夾，可以按照以下步驟進行設定：

### 1. 安裝 Sass
首先，確保你已經安裝了 Sass。如果尚未安裝，可以使用 npm 來安裝：

```bash
npm install -g sass
```

### 2. 準備目錄結構
確保你的項目目錄中有以下結構：
```
my-project/
├── source/
│   └── all.scss
└── css/
```

在這個示例中，`source` 資料夾包含了你的原始 Sass 檔案，`css` 資料夾是用來存放編譯後的 CSS 檔案。

### 3. 使用 `sass --watch`
開啟 VSCode 的終端（Terminal），然後導航到你的項目目錄。輸入以下命令以啟動 Sass 的 watch 模式：

```bash
sass --watch source/styles.scss:css/styles.css
```

這條命令會監視 `source/styles.scss` 檔案的變化，並自動將其編譯為 `css/styles.css`。

### 4. 自動化編譯多個檔案
如果你有多個 Sass 檔案需要編譯，可以監視整個目錄：

```bash
sass --watch source:css
```

這樣，`source` 資料夾中的所有 Sass 檔案都會被監視，並編譯後輸出到 `css` 資料夾。

### 5. 在 VSCode 中運行
1. 打開你的項目文件夾。
2. 開啟終端：`Terminal -> New Terminal`。
3. 輸入上述 `sass --watch` 命令並運行。

### 6. 使用 VSCode 擴展
VSCode 也有一些擴展可以幫助你更方便地編譯 Sass，例如：

- **Live Sass Compiler**：這是一個方便的 VSCode 擴展，可以自動編譯你的 Sass 檔案。

#### 安裝 Live Sass Compiler

1. 打開 VSCode。
2. 進入 Extensions 視圖：`View -> Extensions` 或按 `Ctrl+Shift+X`。
3. 搜尋 "Live Sass Compiler" 並點擊安裝。

#### 使用 Live Sass Compiler

1. 安裝後，打開你的 `.scss` 檔案。
2. 點擊右下角的 "Watch Sass" 按鈕，或按快捷鍵 `Ctrl+Alt+S`。

這會自動編譯你的 Sass 檔案並輸出到同一目錄中的 CSS 檔案。你可以在設置中更改輸出目錄：

1. 打開 VSCode 設置：`File -> Preferences -> Settings`。
2. 搜尋 "Live Sass Compiler"。
3. 找到並編輯 `settings.json`，例如：

```json
"liveSassCompile.settings.formats": [
  {
    "format": "expanded",
    "extensionName": ".css",
    "savePath": "/css"
  }
]
```

這樣，所有編譯的 CSS 檔案將會被存儲到 `css` 資料夾中。

通過這些步驟，你可以在使用 VSCode 和 `sass --watch` 命令的過程中，將編譯好的 CSS 檔案自動放置在獨立的 `css` 資料夾中。