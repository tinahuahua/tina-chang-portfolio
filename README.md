# Tina Chang 張庭華 – Portfolio (static site)

這是從 Notion 作品集
<https://tina-hua.notion.site/Tina-Chang-281e9b510f08804a9c95c857e31b1a7e>
轉出來的純 HTML/CSS 靜態網站，不需要任何建置步驟，可以直接放上 GitHub Pages。

## 檔案結構

```
portfolio-site/
├── index.html                        首頁（Education / Experience / School Clubs / Portfolio）
├── thesis.html                       Master Thesis 摘要
├── cv.html                           English CV（內嵌 cv/ 內的 HTML，可下載 PDF）
├── vr-game-bias.html                 Unity：VR Game “Bias”
├── thesis-vr-stimuli.html            Unity：Master’s Thesis Stimuli
├── snow-code.html                    Unity：<⁄snow code>
├── pecking-bird.html                 互動裝置：《啄色鳥》
├── anti-theft-device.html            互動裝置：《邊緣人防盜裝置》
├── freelance-frontend.html           前端：Freelance Frontend Development
├── production-marketing-system.html  前端：Production and Marketing Information System
├── minecraft-teacher-guide.html      虛擬空間：Minecraft《新進教師人員指南》
├── gather-town-imics.html            虛擬空間：Gather Town《IMICS GATHER SPACE》
├── cv/                               Tina_Chang_CV.html、Tina_Chang_CV.pdf
└── assets/                           style.css、照片、封面圖、作品圖片、PDF
```

影片（YouTube）以嵌入方式播放，沒有下載到 repo。

## 在本機預覽

直接用瀏覽器打開 `index.html` 就可以看。
若想模擬 GitHub Pages 的環境（PDF 內嵌在部分瀏覽器用 `file://` 開時會被擋），可在此資料夾執行：

```bash
python -m http.server 8000
```

再開 <http://localhost:8000>。

## 推上 GitHub 並開啟 GitHub Pages

1. 到 GitHub 建立一個新的 **public** repository，例如 `portfolio`
   （若取名為 `<你的帳號>.github.io`，網址會是 `https://<你的帳號>.github.io/`）。
2. 在 `portfolio-site` 資料夾內執行：

   ```bash
   git init
   git add .
   git commit -m "Initial portfolio site"
   git branch -M main
   git remote add origin https://github.com/<你的帳號>/portfolio.git
   git push -u origin main
   ```

3. 在 GitHub 的 repo 頁面：**Settings → Pages → Build and deployment**
   - Source 選 **Deploy from a branch**
   - Branch 選 **main**、資料夾選 **/ (root)**，按 **Save**
4. 等 1–2 分鐘，網址會顯示在同一頁，通常是
   `https://<你的帳號>.github.io/portfolio/`。

## 上線後記得更新

- `cv/Tina_Chang_CV.html` 和 CV PDF 內的 **Portfolio** 連結目前仍指向 Notion，
  上線後可改成 GitHub Pages 網址。
- 首頁的「中文作品集」按鈕仍連到 Notion 上的中文版頁面。

## 修改內容

所有文字都直接寫在各 HTML 檔中，用任何文字編輯器修改即可；樣式集中在 `assets/style.css`。
新增作品時，複製一個作品頁（例如 `snow-code.html`）修改內容，並在 `index.html` 的 Portfolio 區塊新增一張卡片。
