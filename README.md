MinecraftJarTranslator v0.1.0-beta (Windows x64)
================================================

系統需求
- Windows 10 或 Windows 11，64-bit。
- 翻譯時需要可連線至 Internet。

使用方式
1. 執行 MinecraftJarTranslator.App.exe。
2. 拖曳 Minecraft mod JAR 到視窗，或使用選擇按鈕加入一個或多個 JAR。
3. 確認可翻譯的語言檔並選擇目標語言。
4. 選擇輸出資料夾後開始翻譯。
5. 翻譯完成的 JAR 會寫入所選輸出資料夾，可直接放入相容的 Minecraft mods 資料夾。

資料與安全
- 原始 JAR 永遠不會被覆寫。
- 需要翻譯的文字會透過本應用程式的 HTTPS Translation Gateway 傳送至 Azure Translator。
- Windows 客戶端不包含、不儲存，也不會要求使用者輸入 Azure Translator API key。
- JSON keys、Minecraft 格式碼、printf/ICU placeholders 與程式識別字會在翻譯前受到保護並於輸出前驗證。

限制
- 此測試版支援 Minecraft 1.13+ 的扁平 UTF-8 JSON 語言檔。
- 複雜 ICU MessageFormat、舊版 .lang、重新簽署與遞迴 jar-in-jar 修改不在本版本支援範圍。
