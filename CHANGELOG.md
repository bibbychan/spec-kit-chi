# 變更日誌

<!-- markdownlint-disable MD024 -->

所有對 Specify CLI 和範本的重要變更都記錄在此。

格式基於 [Keep a Changelog](https://keepachangelog.com/en/1.0.0/)，
並且此專案遵循 [Semantic Versioning](https://semver.org/spec/v2.0.0.html)。

## [0.0.18] - 2025-10-06

### 新增功能

- 支援在 `specify init .` 指令中使用 `.` 作為當前目錄的簡寫，相當於 `--here` 標誌但對使用者更直觀。
- 使用 `/speckit.` 指令前綴來輕鬆發現 Spec Kit 相關指令。
- 重構提示和範本以簡化其功能和追蹤方式。不再在不需要測試時污染檔案。
- 確保根據使用者故事創建任務（簡化測試和驗證）。
- 新增對 Visual Studio Code 提示快捷鍵和自動腳本執行的支援。

### 變更

- 所有指令檔案現在前綴為 `speckit.`（例如 `speckit.specify.md`、`speckit.plan.md`）以便在 IDE/CLI 指令選擇器和檔案瀏覽器中更好地發現和區分

## [0.0.17] - 2025-09-22

### 新增功能

- 新的 `/clarify` 指令範本，為現有規格提供最多 5 個針對性的澄清問題，並將答案保存到規格的 Clarifications 部分中。
- 新的 `/analyze` 指令範本，提供非破壞性的跨工件差異和一致性報告（規格、澄清、計畫、任務、憲法），插入在 `/tasks` 之後和 `/implement` 之前。
	- 注意：憲法規則被明確視為不可協商的；任何衝突都是 CRITICAL 發現，需要工件修復，而不是削弱原則。

## [0.0.16] - 2025-09-22

### 新增功能

- `--force` 標誌用於 `init` 指令，在非空目錄中使用 `--here` 時繞過確認並繼續合併/覆蓋檔案。

## [0.0.15] - 2025-09-21

### 新增功能

- 支援 Roo Code。

## [0.0.14] - 2025-09-21

### 變更

- 錯誤訊息現在顯示一致。

## [0.0.13] - 2025-09-21

### 新增功能

- 支援 Kilo Code。感謝 [@shahrukhkhan489](https://github.com/shahrukhkhan489) 在 [#394](https://github.com/github/spec-kit/pull/394) 中的貢獻。
- 支援 Auggie CLI。感謝 [@hungthai1401](https://github.com/hungthai1401) 在 [#137](https://github.com/github/spec-kit/pull/137) 中的貢獻。
- 在專案配置完成後顯示代理資料夾安全通知，警告使用者某些代理可能在其代理資料夾中儲存憑證或身份驗證令牌，並建議將相關資料夾新增到 `.gitignore` 以防止意外憑證洩漏。

### 變更

- 顯示警告以確保人們意識到他們可能需要將其代理資料夾新增到 `.gitignore`。
- 清理了 `check` 指令的輸出。

## [0.0.12] - 2025-09-21

### 變更

- 為 OpenAI Codex 使用者新增了額外的上下文 - 他們需要設定一個額外的環境變數，如 [#417](https://github.com/github/spec-kit/issues/417) 中所述。

## [0.0.11] - 2025-09-20

### 新增功能

- Codex CLI 支援（感謝 [@honjo-hiroaki-gtt](https://github.com/honjo-hiroaki-gtt) 在 [#14](https://github.com/github/spec-kit/pull/14) 中的貢獻）
- Codex 感知的上下文更新工具（Bash 和 PowerShell），讓功能計畫能夠與現有助手一起重新整理 `AGENTS.md` 而無需手動編輯。

## [0.0.10] - 2025-09-20

### 修復

- 解決了 [#378](https://github.com/github/spec-kit/issues/378) 中 GitHub token 在為空時可能附加到請求的問題。

## [0.0.9] - 2025-09-19

### 變更

- 改進了代理選擇器 UI，代理鍵使用青色高亮顯示，完整名稱使用灰色括號

## [0.0.8] - 2025-09-19

### 新增功能

- Windsurf IDE 支援作為額外的 AI 助手選項（感謝 [@raedkit](https://github.com/raedkit) 在 [#151](https://github.com/github/spec-kit/pull/151) 中的工作）
- GitHub token 支援 API 請求以處理企業環境和速率限制（由 [@zryfish](https://github.com/@zryfish) 在 [#243](https://github.com/github/spec-kit/pull/243) 中貢獻）

### 變更

- 更新了 README，增加了 Windsurf 範例和 GitHub token 使用方式
- 增強了發布工作流程以包含 Windsurf 範本

## [0.0.7] - 2025-09-18

### 變更

- 更新了 CLI 中的指令說明。
- 清理了程式碼，使其在通用情況下不渲染代理特定資訊。


## [0.0.6] - 2025-09-17

### 新增功能

- opencode 支援作為額外的 AI 助手選項

## [0.0.5] - 2025-09-17

### 新增功能

- Qwen Code 支援作為額外的 AI 助手選項

## [0.0.4] - 2025-09-14

### 新增功能

- 透過 `httpx[socks]` 依賴項為企業環境新增 SOCKS proxy 支援

### 修復

無

### 變更

無
