---
description: 使用計畫範本執行實作規劃工作流程，生成設計產物。
scripts:
  sh: scripts/bash/setup-plan.sh --json
  ps: scripts/powershell/setup-plan.ps1 -Json
agent_scripts:
  sh: scripts/bash/update-agent-context.sh __AGENT__
  ps: scripts/powershell/update-agent-context.ps1 -AgentType __AGENT__
---

## 使用者輸入

```text
$ARGUMENTS
```

您**必須**在繼續之前考慮使用者輸入（如果不為空）。

## 概要

1. **設定**：從儲存庫根目錄執行 `{SCRIPT}` 並解析 JSON 中的 FEATURE_SPEC、IMPL_PLAN、SPECS_DIR、BRANCH。

2. **載入上下文**：讀取 FEATURE_SPEC 和 `.specify/memory/constitution.md`。載入 IMPL_PLAN 範本（已複製）。

3. **執行計畫工作流程**：遵循 IMPL_PLAN 範本中的結構來：
   - 填寫技術上下文（將未知項標記為 "NEEDS CLARIFICATION"）
   - 從憲法填寫憲法檢查部分
   - 評估閘門（如果違規未經正當理由則報錯）
   - 階段 0：生成 research.md（解決所有 NEEDS CLARIFICATION）
   - 階段 1：生成 data-model.md、contracts/、quickstart.md
   - 階段 1：透過執行代理腳本更新代理上下文
   - 設計後重新評估憲法檢查

4. **停止並報告**：命令在階段 2 規劃後結束。報告分支、IMPL_PLAN 路徑和生成的產物。

## 階段

### 階段 0：大綱與研究

1. **從上方技術上下文中提取未知項**：
   - 對於每個 NEEDS CLARIFICATION → 研究任務
   - 對於每個依賴項 → 最佳實踐任務
   - 對於每個整合 → 模式任務

2. **生成和分派研究代理**：
   ```
   對於技術上下文中的每個未知項：
     任務：「為 {功能上下文} 研究 {未知項}」
   對於每個技術選擇：
     任務：「在 {領域} 中找到 {技術} 的最佳實踐」
   ```

3. **在 `research.md` 中整合發現**，使用格式：
   - 決策：[選擇了什麼]
   - 理由：[為什麼選擇]
   - 考慮的替代方案：[評估了什麼其他選項]

**輸出**：research.md，解決所有 NEEDS CLARIFICATION

### 階段 1：設計與合約

**前提條件**：`research.md` 完成

1. **從功能規格中提取實體** → `data-model.md`：
   - 實體名稱、欄位、關係
   - 來自需求的驗證規則
   - 適用的狀態轉換

2. **從功能需求生成 API 合約**：
   - 對於每個使用者動作 → 端點
   - 使用標準 REST/GraphQL 模式
   - 將 OpenAPI/GraphQL schema 輸出到 `/contracts/`

3. **代理上下文更新**：
   - 執行 `{AGENT_SCRIPT}`
   - 這些腳本檢測正在使用的 AI 代理
   - 更新適當的代理特定上下文檔案
   - 僅添加來自當前計畫的新技術
   - 保留標記之間的手動添加

**輸出**：data-model.md、/contracts/*、quickstart.md、代理特定檔案

## 關鍵規則

- 使用絕對路徑
- 閘門失敗或未解決的澄清時報錯
