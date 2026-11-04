# SlimeSweep V3 — V2 推出擴散／回拉收膠動畫

三段使用情境：機械鍵盤縫隙、家具底部狹縫、座椅之間的縫隙。各 6 秒，合併版 18 秒，1920×1080、H.264、中文步驟字幕、無聲。

凝膠以連續隱式曲面製作。多個控制點分別生長、分枝、合流、拉長及收攏，並非整塊固定網格的縮放。灰塵的位置逐格投影至變形後的表面，略微嵌入以緊密貼合。操作改為向前推滑塊出膠，接觸吸附後機身保持原位，向後拉滑塊，凝膠收攏並退回出口內，最後移開機身。

此為美術控制的機構概念動畫，未執行真實黏菌生長、材料黏附或流體力學驗證。回收可採用與活塞連動的柔性牽引網，搭配可拆洗回收腔；材料、牽引力與髒污隔離仍需工程測試。

畫質處理：Blender Cycles 原生 1080p 渲染，輸出線性色彩、材質與法線輔助通道，使用 Intel Open Image Denoise 執行 HDR 輔助降噪，再做顯示色彩轉換。動畫時間軸 72 格／12fps，隔格渲染後以動態補幀輸出 24fps。

三個 `.blend` 原檔包含動畫、灰塵位置烘焙與材質，可在 Blender 4.3.2 開啟編輯。重建場景使用 `build.py -- --build-only`，以 `SWEEP_SCENE=keyboard|crevice|seat` 選取場景；需上一版模型 `/workspace/output/slimesweep/SlimeSweep_V3.blend` 與場景基礎 `/workspace/output/slimesweep_video/animate.py`。獨立 `.blend` 原檔開啟與播放無須這些腳本。

`render_guided.py` 渲染三段 EXR；`denoise_guided.py` 監看並降噪；`encode_v2.py` 加字幕並編碼。降噪套件：oidn 0.2.1、OpenEXR 3.5.3、numpy、Pillow；編碼使用 FFmpeg。
