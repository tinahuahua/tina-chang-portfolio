# 作品集網站 編輯與發布指南

網站網址：<https://tinahuahua.github.io/tina-chang-portfolio/>
GitHub repo：<https://github.com/tinahuahua/tina-chang-portfolio>
本機資料夾：`D:\English CV\portfolio-site`

這個網站是純 HTML/CSS，**沒有任何建置步驟**：用記事本或 VS Code 打開 `.html` 檔，改文字、存檔、推上 GitHub，就完成了。

---

## 1. 網站結構：哪個檔案是哪一頁

英文版在資料夾最外層，中文版在 `zh/` 裡，**兩邊的檔名一一對應**。右上角的「EN / 中文」按鈕會切換到另一個語言的同一頁。

| 頁面 | 英文版 | 中文版 |
|---|---|---|
| 首頁（學歷、經歷、社團、作品集卡片） | `index.html` | `zh/index.html` |
| 碩士論文摘要 | `thesis.html` | `zh/thesis.html` |
| VR 遊戲《有色眼鏡》 | `vr-game-bias.html` | `zh/vr-game-bias.html` |
| 碩論刺激物 | `thesis-vr-stimuli.html` | `zh/thesis-vr-stimuli.html` |
| snow code | `snow-code.html` | `zh/snow-code.html` |
| 《啄色鳥》 | `pecking-bird.html` | `zh/pecking-bird.html` |
| 《邊緣人防盜裝置》 | `anti-theft-device.html` | `zh/anti-theft-device.html` |
| 前端切版接案 | `freelance-frontend.html` | `zh/freelance-frontend.html` |
| 產銷資訊系統 | `production-marketing-system.html` | `zh/production-marketing-system.html` |
| Minecraft《新進教師人員指南》 | `minecraft-teacher-guide.html` | `zh/minecraft-teacher-guide.html` |
| Gather Town | `gather-town-imics.html` | `zh/gather-town-imics.html` |
| 英文履歷頁（中英共用） | `cv.html` | — |

其他資料夾：

| 資料夾 / 檔案 | 內容 |
|---|---|
| `assets/style.css` | 全站共用的顏色、字體、排版 |
| `assets/` | 大頭照、作品封面、作品內文圖片、PDF |
| `cv/` | `Tina_Chang_CV.html`、`Tina_Chang_CV.pdf`（履歷頁內嵌與下載用） |

> **改內容時記得中英兩版都要改。** 兩個版本是獨立的檔案，不會自動同步。

---

## 2. 常見修改：去哪裡改

### 首頁的個人資訊（姓名、職稱、電話、Email、地點）
- 檔案：`index.html`、`zh/index.html`
- 位置：最上方的 `<section class="hero">` 區塊。
  - 職稱：`<p class="role">…</p>`
  - 電話／Email／地點：`<ul class="facts">` 裡的三個 `<li>`
- 頁尾的 Email 在檔案最下面的 `<footer>`，每個頁面都有，要換 Email 時記得一起改。

### 學歷
- 位置：`<section class="section" id="education">`
- 每一筆學歷是一個區塊：

  ```html
  <div class="entry">
    <h3>學位名稱 <span class="org">· 學校名稱</span></h3>
    <p class="date">2022/9 – 2025/2</p>
  </div>
  ```

### 工作經驗（新增一份工作最常用）
- 位置：`<section class="section" id="experience">`
- **複製一整個 `<div class="entry"> … </div>`**，貼在最上面（最新的在前），再修改內容。

  英文版（條列式）：
  ```html
  <div class="entry">
    <h3>職稱 <span class="org">｜公司名稱</span></h3>
    <p class="date">2026/1 – Current</p>
    <ul>
      <li>第一點成果</li>
      <li>第二點成果</li>
    </ul>
  </div>
  ```

  中文版（段落式）：
  ```html
  <div class="entry">
    <h3>職稱 <span class="org">｜公司名稱</span></h3>
    <p class="date">2026/1 – 至今</p>
    <p>工作內容描述。</p>
  </div>
  ```

### 社團經驗
- 位置：`<section class="section" id="clubs">`，格式與工作經驗相同。

### 語言、碩士論文連結（右側小卡）
- 位置：`<aside class="section">` 裡的 `<div class="side-card">`。

### 修改某個作品的內容
- 作品頁（例如 `pecking-bird.html`）：
  - 標題：`<h1 class="page-title">`
  - 標籤：`<ul class="tags">` 裡的 `<li>`
  - 簡介／我的角色：`<dl class="meta">` 裡的 `<dd>`
  - 下方內文：圖片是 `<figure>`，影片是 `<div class="video">`，文字是 `<p>`
- **首頁的卡片也要一起改**：`index.html` 的 `<section id="portfolio">` 裡，對應的 `<a class="card" href="pecking-bird.html">`，卡片上的標題、標籤、簡介是另外寫的。

### 新增一個作品
1. 複製一個現有的作品頁，例如把 `snow-code.html` 複製成 `my-new-project.html`；中文版在 `zh/` 裡也複製一份，**檔名要一樣**。
2. 修改新檔案的內容：
   - `<title>`
   - 封面圖 `<img class="page-cover" src="assets/…">`（中文版是 `../assets/…`）
   - 標題、標籤、簡介、內文
   - 右上角語言切換的連結：英文版裡是 `zh/my-new-project.html`，中文版裡是 `../my-new-project.html`
3. 底部的「上一個／下一個」(`<nav class="pager">`) 連結要串好；不想串的話可以只留返回連結。
4. 在 `index.html` 和 `zh/index.html` 的作品集區塊，複製一張 `<a class="card">` 卡片，改成新作品的連結與文字。
5. 把新圖片放進 `assets/`。

### 嵌入 YouTube 影片
到 YouTube 影片頁 → 分享 → 嵌入，取得影片 ID（網址 `watch?v=` 後面那串），換掉下面的 `影片ID`：

```html
<div class="video"><iframe src="https://www.youtube.com/embed/影片ID?rel=0" title="影片標題" loading="lazy" allowfullscreen></iframe></div>
```

### 換照片、圖片
- 最簡單的方法：**用同樣的檔名覆蓋 `assets/` 裡的舊檔**，HTML 不用改。
- 檔名不同時，要把 HTML 裡的 `src="assets/舊檔名"` 改成新檔名（中文版是 `src="../assets/…"`）。
- 建議圖片寬度不要超過 1600px、大小在 500 KB 以內，網頁載入會比較快。可以先用小畫家「調整大小」，或用 squoosh.app 壓縮。
- 檔名建議用英文小寫加 `-`，不要用中文或空格。

### 更新履歷
- 履歷**只有一份**，就放在 `cv/`：`cv/Tina_Chang_CV.html`（原始檔）和 `cv/Tina_Chang_CV.pdf`（投遞與網站下載用）。不要在別的資料夾另存副本，才不會版本不一致。
- 修改流程：
  1. 改 `cv/Tina_Chang_CV.html` 的文字。
  2. 重新產生 PDF（在 `portfolio-site` 資料夾的終端機執行，會直接覆蓋舊的 PDF）：

     ```bash
     & "C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe" --headless --disable-gpu --no-pdf-header-footer --print-to-pdf="$PWD\cv\Tina_Chang_CV.pdf" "$PWD\cv\Tina_Chang_CV.html"
     ```

     或用瀏覽器打開 HTML → 列印 → 另存為 PDF（取消勾選「頁首及頁尾」），存回 `cv/Tina_Chang_CV.pdf`。
  3. 打開 PDF 確認還是一頁，再照第 4 節推上 GitHub。
- 履歷裡的「Portfolio」連結已經指向本網站：`https://tinahuahua.github.io/tina-chang-portfolio/`

### 改顏色、字體、版面
- 檔案：`assets/style.css`
- 最上方 `:root { … }` 是全站的顏色設定：
  - `--accent`：主色（按鈕、連結，目前是深藍 `#1f4e79`）
  - `--gold`：標題旁的金色小條
  - `--text`、`--muted`：文字顏色
  - `--max`：內容最大寬度

---

## 3. 改完先在自己電腦上看

**方法一（快速）**：在檔案總管雙擊 `index.html`。

**方法二（最接近正式網站，PDF 和履歷內嵌也會正常顯示）**：

```bash
cd "D:\English CV\portfolio-site"
```

```bash
python -m http.server 8000
```

打開 <http://localhost:8000>，看完回到終端機按 `Ctrl + C` 關閉。

---

## 4. 推上 GitHub（每次修改後）

在 `D:\English CV\portfolio-site` 打開終端機（檔案總管 → 資料夾空白處按右鍵 →「在終端機中開啟」），依序執行：

```bash
git add .
```

```bash
git commit -m "說明這次改了什麼，例如 Update experience"
```

```bash
git push
```

推上去後等 1～2 分鐘，網站就會更新。可以到 repo 的 **Actions** 分頁看部署進度（綠色勾勾 = 完成）。
如果網站沒變，按 `Ctrl + F5` 強制重新整理瀏覽器快取。

### 常見問題

| 狀況 | 解法 |
|---|---|
| `git` 不是可辨識的指令 | Git 沒裝好或終端機沒重開。安裝 Git for Windows 後關掉終端機再開。 |
| `nothing to commit` | 檔案沒有變更，或忘了存檔。 |
| `rejected … fetch first` | GitHub 上有你電腦沒有的修改（例如你在網頁上直接改過）。先執行 `git pull`，再 `git push`。 |
| `403` / `Permission denied` | 登入的 token 過期或權限不足。重新建立 Personal Access Token（Contents: Read and write，選這個 repo），執行 `cmdkey /delete:git:https://github.com` 清掉舊登入，再 `git push`。 |
| 想看改了哪些檔案 | `git status` |
| 改壞了想放棄某個檔案的修改（還沒 commit） | `git restore 檔名`（這個檔案未儲存到 commit 的變更會消失，請小心） |

---

## 5. GitHub Pages 設定（只需要做一次，已完成可略過）

repo → **Settings → Pages** → Source 選 **Deploy from a branch** → Branch 選 **main**、資料夾 **/ (root)** → **Save**。
