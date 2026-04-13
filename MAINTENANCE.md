# 時光大盜殿堂 — 網站維護手冊

## 目錄
1. [網站架構說明](#網站架構說明)
2. [新增商品](#新增商品)
3. [修改商品](#修改商品)
4. [刪除商品](#刪除商品)
5. [更換商品圖片](#更換商品圖片)
6. [在 GitHub 上編輯（不需安裝任何軟體）](#在-github-上編輯)

---

## 網站架構說明

```
timebandits/
├── index.html        ← 網站主頁（所有商品都在這裡）
├── stylesheet.css    ← 網站樣式（通常不需要動）
├── images/           ← 所有商品圖片放這裡
│   ├── sample-01.jpg
│   ├── sample-02.jpg
│   └── ...
├── README.md         ← 說明文件
└── MAINTENANCE.md    ← 本維護手冊
```

**重點：你只需要動兩個東西：**
1. `index.html` — 新增/修改/刪除商品文字
2. `images/` 資料夾 — 上傳/替換商品圖片

---

## 新增商品

### 步驟 1：上傳圖片
1. 到 GitHub 的 `images` 資料夾
2. 點擊「Add file」→「Upload files」
3. 拖曳圖片上去（建議 JPG 格式，寬度 600px 以上）
4. 記住檔名，例如 `jade-vase.jpg`

### 步驟 2：新增商品到 index.html
1. 打開 `index.html`
2. 找到這段註解：`↓↓↓ 新增更多商品：複製下方模板，貼在這裡 ↓↓↓`
3. 在那段註解的**上方**，貼上以下模板：

```html
<div class="item-card">
  <img src="images/你的圖片檔名.jpg" alt="商品名稱">
  <div class="item-info">
    <div class="item-name">商品名稱</div>
    <div class="item-desc">商品描述文字，簡短說明這件古物的特色、年代、材質等。</div>
    <div class="item-price">NT$ 價格</div>
    <a href="https://shopee.tw/你的商品連結" class="item-link" target="_blank">蝦皮購買 →</a>
  </div>
</div>
```

4. 把模板中的中文替換成實際資料：
   - `你的圖片檔名.jpg` → 步驟 1 上傳的圖片檔名
   - `商品名稱` → 古物名稱（出現兩次，img alt 和 item-name）
   - `商品描述文字` → 簡短介紹
   - `NT$ 價格` → 實際售價
   - `你的商品連結` → 蝦皮商品頁面的完整網址

5. 儲存（Commit changes）

---

## 修改商品

1. 打開 `index.html`
2. 用瀏覽器的搜尋功能（Ctrl+F）搜尋商品名稱
3. 直接修改對應的文字
4. 儲存

---

## 刪除商品

1. 打開 `index.html`
2. 找到要刪除的商品區塊（從 `<div class="item-card">` 到 `</div><!-- 最後一個 -->`）
3. 整段刪掉
4. 儲存
5. （選用）到 `images/` 刪除對應的圖片檔案

**提示：** 每個商品區塊的開頭都有 `<div class="item-card">`，結尾有兩個 `</div>`（一個關閉 item-info，一個關閉 item-card）。

---

## 更換商品圖片

1. 到 `images/` 資料夾
2. 上傳新圖片（可以用一樣的檔名直接覆蓋，或用新檔名）
3. 如果用了新檔名，記得到 `index.html` 更新 `<img src="images/新檔名.jpg">`

**圖片建議：**
- 格式：JPG 或 PNG
- 寬度：600px 以上（太小會模糊）
- 大小：盡量壓在 500KB 以下（太大載入慢）
- 檔名：用英文或數字，不要用中文和空格

---

## 在 GitHub 上編輯

**你不需要安裝任何軟體！** 所有操作都可以在 GitHub 網頁上完成。

### 編輯 index.html
1. 前往 https://github.com/coreyml/timebandits
2. 點擊 `index.html`
3. 點擊右上角的鉛筆圖示（Edit this file）
4. 進行修改
5. 點擊綠色的「Commit changes」按鈕
6. 等待 1-2 分鐘，網站會自動更新

### 上傳圖片
1. 前往 https://github.com/coreyml/timebandits
2. 點進 `images` 資料夾
3. 點擊「Add file」→「Upload files」
4. 拖曳圖片進去
5. 點擊「Commit changes」

### 查看網站
修改後等 1-2 分鐘，前往 https://coreyml.github.io/timebandits 查看更新。

---

## 常見問題

**Q: 圖片上傳後沒顯示？**
A: 確認 `index.html` 裡的 `src="images/檔名.jpg"` 和實際上傳的檔名完全一致（大小寫也要一樣）。

**Q: 網站沒有更新？**
A: GitHub Pages 有 1-2 分鐘的延遲。清除瀏覽器快取（Ctrl+Shift+R）再試。

**Q: 想改網站顏色/字體？**
A: 修改 `stylesheet.css`，但建議有經驗後再嘗試。
