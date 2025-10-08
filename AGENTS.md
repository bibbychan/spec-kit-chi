# AGENTS.md

## 關於 Spec Kit 和 Specify

**GitHub Spec Kit** 是一個實施 Spec-Driven Development (SDD) 的完整工具包 - 這是一種強調在實作之前創建清晰規格的方法論。該工具包包含範本、腳本和工作流程，指導開發團隊透過結構化方法建構軟體。

**Specify CLI** 是命令列介面，使用 Spec Kit 框架引導專案。它設置必要的目錄結構、範本和 AI 代理整合，以支援 Spec-Driven Development 工作流程。

該工具包支援多個 AI 程式碼助手，允許團隊使用其偏好的工具，同時保持一致的專案結構和開發實踐。

---

## 一般實踐

- 對 Specify CLI 的 `__init__.py` 的任何變更都需要在 `pyproject.toml` 中進行版本修訂並在 `CHANGELOG.md` 中新增條目。

## 新增代理支援

本節說明如何為 Specify CLI 新增對新 AI 代理/助手的支援。將新 AI 工具整合到 Spec-Driven Development 工作流程時，請使用本指南作為參考。

### 概述

Specify 透過在初始化專案時生成代理特定的指令檔案和目錄結構來支援多個 AI 代理。每個代理都有自己的慣例：

- **指令檔案格式**（Markdown、TOML 等）
- **目錄結構**（`.claude/commands/`、`.windsurf/workflows/` 等）
- **指令呼叫模式**（斜線指令、CLI 工具等）
- **參數傳遞慣例**（`$ARGUMENTS`、`{{args}}` 等）

### 目前支援的代理

| 代理 | 目錄 | 格式 | CLI 工具 | 描述 |
|------|------|------|---------|------|
| **Claude Code** | `.claude/commands/` | Markdown | `claude` | Anthropic 的 Claude Code CLI |
| **Gemini CLI** | `.gemini/commands/` | TOML | `gemini` | Google 的 Gemini CLI |
| **GitHub Copilot** | `.github/prompts/` | Markdown | N/A (基於 IDE) | VS Code 中的 GitHub Copilot |
| **Cursor** | `.cursor/commands/` | Markdown | `cursor-agent` | Cursor CLI |
| **Qwen Code** | `.qwen/commands/` | TOML | `qwen` | 阿里巴巴的 Qwen Code CLI |
| **opencode** | `.opencode/command/` | Markdown | `opencode` | opencode CLI |
| **Windsurf** | `.windsurf/workflows/` | Markdown | N/A (基於 IDE) | Windsurf IDE 工作流程 |
| **Amazon Q Developer CLI** | `.amazonq/prompts/` | Markdown | `q` | Amazon Q Developer CLI |


### 逐步整合指南

請按照以下步驟新增代理（以 Windsurf 為例）：

#### 1. 更新 AI_CHOICES 常數

將新代理新增到 `src/specify_cli/__init__.py` 中的 `AI_CHOICES` 字典：

```python
AI_CHOICES = {
    "copilot": "GitHub Copilot",
    "claude": "Claude Code",
    "gemini": "Gemini CLI",
    "cursor": "Cursor",
    "qwen": "Qwen Code",
    "opencode": "opencode",
    "windsurf": "Windsurf",
    "q": "Amazon Q Developer CLI"  # 在此新增新代理
}
```

同時更新同一檔案中的 `agent_folder_map` 以包含新代理的資料夾用於安全通知：

```python
agent_folder_map = {
    "claude": ".claude/",
    "gemini": ".gemini/",
    "cursor": ".cursor/",
    "qwen": ".qwen/",
    "opencode": ".opencode/",
    "codex": ".codex/",
    "windsurf": ".windsurf/",
    "kilocode": ".kilocode/",
    "auggie": ".auggie/",
    "copilot": ".github/",
    "q": ".amazonq/" # 在此新增新代理資料夾
}
```

#### 2. 更新 CLI 說明文字

更新所有說明文字和範例以包含新代理：

- 指令選項說明：`--ai` 參數描述
- 函數文件字串和範例
- 包含代理清單的錯誤訊息

#### 3. 更新 README 文件

更新 `README.md` 中的 **支援的 AI 代理** 部分以包含新代理：

- 將新代理新增到表格中，並指定適當的支援級別（完整/部分）
- 包含代理的官方網站連結
- 新增關於代理實作的任何相關說明
- 確保表格格式保持對齊和一致

#### 4. 更新發布套件腳本

修改 `.github/workflows/scripts/create-release-packages.sh`：

##### 新增到 ALL_AGENTS 陣列：
```bash
ALL_AGENTS=(claude gemini copilot cursor qwen opencode windsurf q)
```

##### 新增目錄結構的 case 語句：
```bash
case $agent in
  # ... 現有案例 ...
  windsurf)
    mkdir -p "$base_dir/.windsurf/workflows"
    generate_commands windsurf md "\$ARGUMENTS" "$base_dir/.windsurf/workflows" "$script" ;;
esac
```

#### 5. 更新 GitHub 發布腳本

修改 `.github/workflows/scripts/create-github-release.sh` 以包含新代理的套件：

```bash
gh release create "$VERSION" \
  # ... 現有套件 ...
  .genreleases/spec-kit-template-windsurf-sh-"$VERSION".zip \
  .genreleases/spec-kit-template-windsurf-ps-"$VERSION".zip \
  # 在此新增新代理套件
```

#### 6. 更新代理上下文腳本

##### Bash 腳本 (`scripts/bash/update-agent-context.sh`)：

新增檔案變數：
```bash
WINDSURF_FILE="$REPO_ROOT/.windsurf/rules/specify-rules.md"
```

新增到 case 語句：
```bash
case "$AGENT_TYPE" in
  # ... 現有案例 ...
  windsurf) update_agent_file "$WINDSURF_FILE" "Windsurf" ;;
  "")
    # ... 現有檢查 ...
    [ -f "$WINDSURF_FILE" ] && update_agent_file "$WINDSURF_FILE" "Windsurf";
    # 更新預設建立條件
    ;;
esac
```

##### PowerShell 腳本 (`scripts/powershell/update-agent-context.ps1`)：

新增檔案變數：
```powershell
$windsurfFile = Join-Path $repoRoot '.windsurf/rules/specify-rules.md'
```

新增到 switch 語句：
```powershell
switch ($AgentType) {
    # ... 現有案例 ...
    'windsurf' { Update-AgentFile $windsurfFile 'Windsurf' }
    '' {
        foreach ($pair in @(
            # ... 現有對 ...
            @{file=$windsurfFile; name='Windsurf'}
        )) {
            if (Test-Path $pair.file) { Update-AgentFile $pair.file $pair.name }
        }
        # 更新預設建立條件
    }
}
```

#### 7. 更新 CLI 工具檢查（可選）

對於需要 CLI 工具的代理，在 `check()` 指令和代理驗證中新增檢查：

```python
# 在 check() 指令中
tracker.add("windsurf", "Windsurf IDE (optional)")
windsurf_ok = check_tool_for_tracker("windsurf", "https://windsurf.com/", tracker)

# 在 init 驗證中（僅當需要 CLI 工具時）
elif selected_ai == "windsurf":
    if not check_tool("windsurf", "Install from: https://windsurf.com/"):
        console.print("[red]Error:[/red] Windsurf CLI is required for Windsurf projects")
        agent_tool_missing = True
```

**注意**：對於基於 IDE 的代理（Copilot、Windsurf）跳過 CLI 檢查。

## 代理類別

### 基於 CLI 的代理
需要安裝命令列工具：
- **Claude Code**: `claude` CLI
- **Gemini CLI**: `gemini` CLI
- **Cursor**: `cursor-agent` CLI
- **Qwen Code**: `qwen` CLI
- **opencode**: `opencode` CLI

### 基於 IDE 的代理
在整合開發環境中工作：
- **GitHub Copilot**: 內建於 VS Code/相容編輯器
- **Windsurf**: 內建於 Windsurf IDE

## 指令檔案格式

### Markdown 格式
使用於：Claude、Cursor、opencode、Windsurf、Amazon Q Developer

```markdown
---
description: "指令描述"
---

包含 {SCRIPT} 和 $ARGUMENTS 佔位符的指令內容。
```

### TOML 格式
使用於：Gemini、Qwen

```toml
description = "指令描述"

prompt = """
包含 {SCRIPT} 和 {{args}} 佔位符的指令內容。
"""
```

## 目錄慣例

- **CLI 代理**：通常為 `.<agent-name>/commands/`
- **IDE 代理**：遵循 IDE 特定模式：
  - Copilot: `.github/prompts/`
  - Cursor: `.cursor/commands/`
  - Windsurf: `.windsurf/workflows/`

## 參數模式

不同的代理使用不同的參數佔位符：
- **基於 Markdown/提示的**：`$ARGUMENTS`
- **基於 TOML 的**：`{{args}}`
- **腳本佔位符**：`{SCRIPT}`（替換為實際腳本路徑）
- **代理佔位符**：`__AGENT__`（替換為代理名稱）

## 測試新代理整合

1. **建構測試**：在本地執行套件建立腳本
2. **CLI 測試**：測試 `specify init --ai <agent>` 指令
3. **檔案生成**：驗證正確的目錄結構和檔案
4. **指令驗證**：確保生成的指令與代理一起工作
5. **上下文更新**：測試代理上下文更新腳本

## 常見陷阱

1. **忘記更新腳本**：必須同時更新 bash 和 PowerShell 腳本
2. **缺少 CLI 檢查**：僅為實際具有 CLI 工具的代理新增
3. **錯誤的參數格式**：對每種代理類型使用正確的佔位符格式
4. **目錄命名**：完全遵循代理特定慣例
5. **說明文字不一致**：一致地更新所有面向使用者的文字

## 未來考量

新增代理時：
- 考慮代理的原生指令/工作流程模式
- 確保與 Spec-Driven Development 程序的相容性
- 記錄任何特殊要求或限制
- 使用經驗教訓更新本指南

---

*每當新增新代理時都應更新此文件，以保持準確性和完整性。*