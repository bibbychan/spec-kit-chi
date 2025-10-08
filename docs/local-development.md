# 本地開發指南

本指南展示如何在本地迭代 `specify` CLI，而無需先發布版本或提交到 `main`。

> 腳本現在都有 Bash（`.sh`）和 PowerShell（`.ps1`）兩種版本。CLI 會根據作業系統自動選擇，除非您傳遞 `--script sh|ps`。

## 1. 複製並切換分支

```bash
git clone https://github.com/github/spec-kit.git
cd spec-kit
# 在功能分支上工作
git checkout -b your-feature-branch
```

## 2. 直接執行 CLI（最快反饋）

您可以透過模組入口點執行 CLI，無需安裝任何東西：

```bash
# 從儲存庫根目錄
python -m src.specify_cli --help
python -m src.specify_cli init demo-project --ai claude --ignore-agent-tools --script sh
```

如果您喜歡使用腳本文件風格（使用 shebang）：

```bash
python src/specify_cli/__init__.py init demo-project --script ps
```

## 3. 使用可編輯安裝（隔離環境）

使用 `uv` 建立隔離環境，這樣依賴項解析方式與終端使用者獲得的方式完全相同：

```bash
# 建立並啟動虛擬環境（uv 自動管理 .venv）
uv venv
source .venv/bin/activate  # 或在 Windows PowerShell 中：.venv\Scripts\Activate.ps1

# 以可編輯模式安裝專案
uv pip install -e .

# 現在 'specify' 入口點可用
specify --help
```

由於可編輯模式，程式碼編輯後重新執行不需要重新安裝。

## 4. 直接從 Git 使用 uvx 調用（當前分支）

`uvx` 可以從本地路徑（或 Git 引用）運行以模擬使用者流程：

```bash
uvx --from . specify init demo-uvx --ai copilot --ignore-agent-tools --script sh
```

您也可以將 uvx 指向特定分支而無需合併：

```bash
# 首先推送您的工作分支
git push origin your-feature-branch
uvx --from git+https://github.com/github/spec-kit.git@your-feature-branch specify init demo-branch-test --script ps
```

### 4a. 絕對路徑 uvx（從任何地方運行）

如果您在其他目錄中，請使用絕對路徑而不是 `.`：

```bash
uvx --from /mnt/c/GitHub/spec-kit specify --help
uvx --from /mnt/c/GitHub/spec-kit specify init demo-anywhere --ai copilot --ignore-agent-tools --script sh
```

為方便起見設置環境變數：
```bash
export SPEC_KIT_SRC=/mnt/c/GitHub/spec-kit
uvx --from "$SPEC_KIT_SRC" specify init demo-env --ai copilot --ignore-agent-tools --script ps
```

（可選）定義 shell 函數：
```bash
specify-dev() { uvx --from /mnt/c/GitHub/spec-kit specify "$@"; }
# 然後
specify-dev --help
```

## 5. 測試腳本權限邏輯

運行 `init` 後，檢查 shell 腳本在 POSIX 系統上是否可執行：

```bash
ls -l scripts | grep .sh
# 預期所有者執行位（例如 -rwxr-xr-x）
```
在 Windows 上，您將改為使用 `.ps1` 腳本（不需要 chmod）。

## 6. 運行 Lint / 基本檢查（自行添加）

目前沒有捆綁強制的 lint 配置，但您可以快速檢查可導入性：
```bash
python -c "import specify_cli; print('Import OK')"
```

## 7. 本地建構 Wheel（可選）

發布前驗證包裝：

```bash
uv build
ls dist/
```
如果需要，將建構的工件安裝到全新的丟棄環境中。

## 8. 使用臨時工作區

在骯髒目錄中測試 `init --here` 時，建立臨時工作區：

```bash
mkdir /tmp/spec-test && cd /tmp/spec-test
python -m src.specify_cli init --here --ai claude --ignore-agent-tools --script sh  # 如果儲存庫複製到這裡
```
或者，如果您想要更輕量的沙箱，只複製修改的 CLI 部分。

## 9. 調試網路 / TLS 跳過

如果您在實驗時需要繞過 TLS 驗證：

```bash
specify check --skip-tls
specify init demo --skip-tls --ai gemini --ignore-agent-tools --script ps
```
（僅用於本地實驗。）

## 10. 快速編輯迴圈摘要

| 動作 | 命令 |
|--------|---------|
| 直接運行 CLI | `python -m src.specify_cli --help` |
| 可編輯安裝 | `uv pip install -e .` 然後 `specify ...` |
| 本地 uvx 運行（儲存庫根目錄） | `uvx --from . specify ...` |
| 本地 uvx 運行（絕對路徑） | `uvx --from /mnt/c/GitHub/spec-kit specify ...` |
| Git 分支 uvx | `uvx --from git+URL@branch specify ...` |
| 建構 wheel | `uv build` |

## 11. 清理

快速移除建構工件 / 虛擬環境：
```bash
rm -rf .venv dist build *.egg-info
```

## 12. 常見問題

| 症狀 | 修復 |
|---------|-----|
| `ModuleNotFoundError: typer` | 運行 `uv pip install -e .` |
| 腳本不可執行（Linux） | 重新運行 init 或 `chmod +x scripts/*.sh` |
| Git 步驟跳過 | 您傳遞了 `--no-git` 或未安裝 Git |
| 下載了錯誤的腳本類型 | 明確傳遞 `--script sh` 或 `--script ps` |
| 企業網路上的 TLS 錯誤 | 嘗試 `--skip-tls`（不用於生產） |

## 13. 後續步驟

- 更新文件並使用您修改的 CLI 運行快速入門
- 滿意時開啟 PR
- （可選）更改 landing 到 `main` 後標記發布版本

