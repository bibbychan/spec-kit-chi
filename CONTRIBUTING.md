## 貢獻給 Spec Kit

嗨！我們很高興您想為 Spec Kit 做出貢獻。此專案的貢獻根據[專案的開源授權](LICENSE)向公眾[發布](https://help.github.com/articles/github-terms-of-service/#6-contributions-under-repository-license)。

請注意，此專案隨[貢獻者行為準則](CODE_OF_CONDUCT.md)發布。通過參與此專案，您同意遵守其條款。

## 運行和測試程式碼的前置需求

這些是一次性安裝，能夠作為提取請求（PR）提交過程的一部分在本地測試您的更改。

1. 安裝 [Python 3.11+](https://www.python.org/downloads/)
1. 安裝 [uv](https://docs.astral.sh/uv/) 用於套件管理
1. 安裝 [Git](https://git-scm.com/downloads)
1. 準備好 [AI 程式碼代理](README.md#-supported-ai-agents)

## 提交提取請求

>[!NOTE]
>如果您的提取請求引入了重大變更，對 CLI 或儲存庫其餘部分的工作產生實質性影響（例如，您引入新範本、參數或其他重大變更），請確保它已經**被專案維護者討論並同意**。沒有事先對話和同意的重大變更的提取請求將被關閉。

1. 分支和複製儲存庫
1. 配置和安裝依賴項：`uv sync`
1. 確保 CLI 在您的機器上運行：`uv run specify --help`
1. 建立新分支：`git checkout -b my-branch-name`
1. 進行您的變更，添加測試，並確保一切仍然正常工作
1. 如果相關，使用範例專案測試 CLI 功能
1. 推送到您的分支並提交提取請求
1. 等待您的提取請求被審查和合併。

以下是一些您可以做的事情，這些將增加您的提取請求被接受的機會：

- 遵循專案的編碼慣例。
- 為新功能撰寫測試。
- 如果您的變更影響使用者面向的功能，請更新文件（`README.md`、`spec-driven.md`）。
- 讓您的變更盡可能專注。如果您想進行多個不相互依賴的變更，請考慮將它們作為單獨的提取請求提交。
- 撰寫[良好的提交訊息](http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html)。
- 使用 Spec-Driven Development 工作流程測試您的變更以確保相容性。

## 開發工作流程

在處理 spec-kit 時：

1. 在您選擇的程式碼代理中使用 `specify` CLI 命令（`/speckit.specify`、`/speckit.plan`、`/speckit.tasks`）測試變更
2. 驗證 `templates/` 目錄中的範本是否正常工作
3. 測試 `scripts/` 目錄中的腳本功能
4. 如果進行重大流程變更，確保記憶體文件（`memory/constitution.md`）已更新

## Spec Kit 中的 AI 貢獻

> [!IMPORTANT]
>
> 如果您使用**任何類型的 AI 協助**來貢獻給 Spec Kit，
> 必須在提取請求或問題中披露。

我們歡迎並鼓勵使用 AI 工具來協助改進 Spec Kit！許多有價值的貢獻已經透過 AI 協助進行程式碼生成、問題檢測和功能定義而得到增強。

話雖如此，如果您在貢獻給 Spec Kit 時使用任何類型的 AI 協助（例如代理、ChatGPT），
**這必須在提取請求或問題中披露**，以及 AI 協助的使用程度（例如，文件註釋與程式碼生成）。

如果您的 PR 回應或評論是由 AI 生成的，也請披露。

作為例外，瑣碎的間距或拼字錯誤修復不需要披露，只要變更限於程式碼的小部分或短語。

披露範例：

> 此 PR 主要由 GitHub Copilot 撰寫。

或更詳細的披露：

> 我諮詢了 ChatGPT 來理解程式碼庫，但解決方案
> 完全由我手動撰寫。

不披露這一點首先對提取請求另一端的人類操作員是不禮貌的，但這也使得難以確定
對貢獻應用多少審查。

在一個完美的世界中，AI 協助會產生與任何人類同等或更高品質的工作。這不是我們今天生活的世界，在大多數情況下
如果沒有人類監督或專業知識在迴圈中，它正在生成無法合理維護或進化的程式碼。

### 我們尋找什麼

提交 AI 協助的貢獻時，請確保它們包括：

- **明確披露 AI 使用** - 您對 AI 使用和您對貢獻的使用程度保持透明
- **人類理解和測試** - 您已經個人測試了變更並理解它們的作用
- **明確的基本原理** - 您可以解釋為什麼需要變更以及它如何適合 Spec Kit 的目標
- **具體證據** - 包括測試案例、場景或展示改進的範例
- **您自己的分析** - 分享您對端到端開發人員體驗的想法

### 我們會關閉什麼

我們保留關閉似乎是以下內容的貢獻的權利：

- 未经驗證提交的未測試變更
- 不解決特定 Spec Kit 需求的通用建議
- 顯示沒有人類審查或理解的大量提交

### 成功的指導方針

關鍵是證明您理解並已經驗證了您提出的變更。如果維護者能夠輕易看出貢獻完全由 AI 生成而沒有人類輸入或測試，它可能在提交前需要更多工作。

持續提交低努力 AI 生成變更的貢獻者可能會被維護者酌情限制進一步貢獻。

請尊重維護者並披露 AI 協助。

## 資源

- [Spec-Driven Development 方法論](./spec-driven.md)
- [如何貢獻給開源](https://opensource.guide/how-to-contribute/)
- [使用提取請求](https://help.github.com/articles/about-pull-requests/)
- [GitHub 說明](https://help.github.com)
