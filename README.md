MinecraftJarTranslator v0.1.1-beta (Windows x64)
================================================
[![Download v0.1.1 Beta](https://img.shields.io/badge/Download-v0.1.1%20Beta-blue?style=for-the-badge&logo=windows)](https://github.com/knife0001/Minecraft-JAR-Translator-Public/releases/download/v0.1.1-Beta/MinecraftJarTranslator-v0.1.1-beta-win-x64.zip)
系統需求
- Windows 10 或 Windows 11，64-bit。
- 翻譯時需要可連線至 Internet。

使用方式
1. 執行 MinecraftJarTranslator.App.exe。
2. 可在右上角選擇繁體中文、簡體中文、English、日本語或한국어介面。
3. 拖曳 Minecraft mod JAR 到視窗，或使用選擇按鈕加入一個或多個 JAR。
4. 確認可翻譯的語言檔並選擇目標語言。
5. 選擇輸出資料夾後開始翻譯。
6. 預設會輸出所有已選 JAR；未翻譯或略過項目會以相同 SHA-256 原樣複製。
7. 翻譯完成的 JAR 會寫入所選輸出資料夾，可直接放入相容的 Minecraft mods 資料夾。

資料與安全
- 原始 JAR 永遠不會被覆寫。
- 需要翻譯的文字會透過本應用程式的 HTTPS Translation Gateway 傳送至 Azure Translator；只有 Azure 額度用完或暫時故障時才會改送 Gemini API。
- 傳送內容只包含遮罩後的待翻譯文字、來源／目標語言與批次索引，不包含完整 JAR、檔案路徑或 JSON key。
- 小型翻譯量會立即處理；大型翻譯量會自動改用 50 筆／12,000 字元的小批次，且請求間至少等待 15 秒，以降低短時間流量過高造成 API 限制的風險。
- 遇到 Gemini 429 時，程式會保存批次、逐秒倒數並自動降速；沒有提示時採 15／30／60／120／120 秒與少量 jitter。連續 5 次限制或明確額度耗盡後會暫停，不會無限重試；可繼續、立即重試或取消。
- Windows 客戶端不包含、不儲存，也不會要求使用者輸入 Azure Translator API key。
- Windows 客戶端也不包含 Gemini API key；兩種憑證都只存在伺服器環境變數中。
- JSON keys、Minecraft 格式碼、printf/ICU placeholders 與程式識別字會在翻譯前受到保護並於輸出前驗證。

限制
- 此測試版支援 Minecraft 1.13+ 的扁平 UTF-8 JSON 語言檔。
- 複雜 ICU MessageFormat、舊版 .lang、重新簽署與遞迴 jar-in-jar 修改不在本版本支援範圍。

