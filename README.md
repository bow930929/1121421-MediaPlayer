# 多媒體播放器

## 功能說明

| 按鈕 | 功能 |
|------|------|
| 瀏覽 | 開啟檔案對話方塊，選取影音檔案 |
| 播放 | 播放所選影音檔案 |
| 暫停 | 暫停目前播放 |
| 停止 | 停止目前播放 |

---

## 支援格式

| 格式 | 副檔名 |
|------|--------|
| Windows Media Video | `.wmv` |
| MPEG-4 Video | `.mp4` |
| Audio Video Interleave | `.avi` |
| 所有檔案 | `*.*` |

---

## 介面配置

<img width="1205" height="799" alt="image" src="https://github.com/user-attachments/assets/94631b60-1594-4da9-97bd-3b0995d42f37" />


## 核心程式說明

### 引用 Windows Media Player 元件

透過 Visual Studio 工具箱加入 COM 元件 `Windows Media Player`（`wmp.dll`），並將 `uiMode` 設為 `none` 以隱藏內建控制列，改由自訂按鈕操作。

### 按鈕邏輯

```csharp
// 瀏覽並載入檔案
wmpVideo.URL = ofd.FileName;
wmpVideo.Ctlcontrols.stop();

// 播放
wmpVideo.Ctlcontrols.play();

// 暫停
wmpVideo.Ctlcontrols.pause();

// 停止
wmpVideo.Ctlcontrols.stop();
```

### Windows Media Player 主要屬性設定

| 屬性 | 設定值 | 說明 |
|------|--------|------|
| `uiMode` | `none` | 隱藏內建控制列 |
| `Dock` | `Fill` | 填滿上方區域 |
| `stretchToFit` | `true` | 自動調整影片大小 |

---

## 注意事項

- 需安裝 Windows Media Player（Windows 內建，一般無需額外安裝）
- 引用 COM 元件時須在工具箱選擇項目中勾選 `Windows Media Player`
