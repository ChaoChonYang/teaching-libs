# teaching-libs

教學遊戲平台用到的外部函式庫，路徑和原本的網址一一對應：

| 原本的網址 | 這裡的路徑 |
|---|---|
| `https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js` | `cdnjs/three.js/r128/three.min.js` |
| `https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js` | `cdnjs/html2canvas/1.4.1/html2canvas.min.js`（平台截圖用） |
| `https://cdn.jsdelivr.net/npm/three@0.169.0/build/three.module.js` | `npm/three@0.169.0/build/three.module.js` |
| `https://cdn.jsdelivr.net/npm/three@0.169.0/examples/jsm/…` | `npm/three@0.169.0/examples/jsm/…`（OrbitControls、GLTFLoader、BufferGeometryUtils、CSS2DRenderer） |

## 上傳到 GitHub

1. 到 https://github.com/new 建一個 **Public** 的 repo，例如 `teaching-libs`（jsDelivr 讀不到私有 repo）。
2. 按 **uploading an existing file**，把這個資料夾裡的 `cdnjs` 和 `npm` 兩個資料夾一起拖進去（用 Chrome 或 Edge 會保留子資料夾），按 Commit changes。
3. 右邊 **Releases → Create a new release**，tag 輸入 `v1`，按 Publish release。
4. 用瀏覽器打開下面的網址，看到一大段程式碼就成功了：
   `https://cdn.jsdelivr.net/gh/<帳號>/teaching-libs@v1/cdnjs/three.js/r128/three.min.js`
5. 到平台的老師後台「⚙ 設定 → 函式庫網址」填：
   `https://cdn.jsdelivr.net/gh/<帳號>/teaching-libs@v1/`

## 注意

- **不要用 `raw.githubusercontent.com` 的網址**：GitHub 對它回傳的類型是純文字，瀏覽器會拒絕執行。
- 也可以改用 GitHub Pages：repo 的 Settings → Pages → Branch 選 main → Save，網址就是 `https://<帳號>.github.io/teaching-libs/`。jsDelivr 和 GitHub Pages 擇一即可，學校網路擋掉其中一個時可以換另一個。
- 之後新增函式庫，照原本網址的路徑放進對應資料夾，再發一個**新的 tag**（`v2`），並把後台的網址改成 `@v2/`。jsDelivr 對 tag 是永久快取，覆蓋舊 tag 不會生效。
- 遊戲如果用了這裡沒有的函式庫，那個檔案會載入失敗。新增遊戲時，記得檢查它用到的函式庫有沒有放上來。
