<div align="center">
    <img src="./media/logo_small.webp"/>
    <h1>🌱 Spec Kit</h1>
    <h3><em>更快地建構高品質軟體。</em></h3>
</div>

<p align="center">
    <strong>藉由規格驅動開發的協助，讓組織能夠專注於產品場景，而不是撰寫無差異化的程式碼。</strong>
</p>

<p align="center">
    <a href="https://github.com/github/spec-kit/actions/workflows/release.yml"><img src="https://github.com/github/spec-kit/actions/workflows/release.yml/badge.svg" alt="Release"/></a>
    <a href="https://github.com/github/spec-kit/stargazers"><img src="https://img.shields.io/github/stars/github/spec-kit?style=social" alt="GitHub stars"/></a>
    <a href="https://github.com/github/spec-kit/blob/main/LICENSE"><img src="https://img.shields.io/github/license/github/spec-kit" alt="License"/></a>
    <a href="https://github.github.io/spec-kit/"><img src="https://img.shields.io/badge/docs-GitHub_Pages-blue" alt="Documentation"/></a>
</p>

---

## 目錄

- [🤔 什麼是規格驅動開發？](#-什麼是規格驅動開發)
- [⚡ 開始使用](#-開始使用)
- [📽️ 影片概覽](#️-影片概覽)
- [🤖 支援的 AI 代理](#-支援的-ai-代理)
- [🔧 Specify CLI 參考](#-specify-cli-參考)
- [📚 核心理念](#-核心理念)
- [🌟 開發階段](#-開發階段)
- [🎯 實驗目標](#-實驗目標)
- [🔧 先決條件](#-先決條件)
- [📖 更多資訊](#-更多資訊)
- [📋 詳細流程](#-詳細流程)
- [🔍 疑難排解](#-疑難排解)
- [👥 維護者](#-維護者)
- [💬 支援](#-支援)
- [🙏 致謝](#-致謝)
- [📄 授權](#-授權)

## 🤔 什麼是規格驅動開發？

規格驅動開發（Spec-Driven Development）**顛覆了**傳統軟體開發的模式。數十年來，程式碼一直是王道 — 規格只是我們建構並在編程「真正工作」開始後就丟棄的鷹架。規格驅動開發改變了這一點：**規格變得可執行**，直接生成可運作的實作，而不僅僅是指導它們。

## ⚡ 開始使用

### 1. 安裝 Specify

選擇您偏好的安裝方式：

#### 選項 1：持久安裝（推薦）

一次安裝，到處使用：

```bash
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git
```

然後直接使用工具：

```bash
specify init <PROJECT_NAME>
specify check
```

#### 選項 2：一次性使用

直接執行，無需安裝：

```bash
uvx --from git+https://github.com/github/spec-kit.git specify init <PROJECT_NAME>
```

**持久安裝的優點：**

- 工具保持安裝並在 PATH 中可用
- 無需建立 shell 別名
- 更好的工具管理，使用 `uv tool list`、`uv tool upgrade`、`uv tool uninstall`
- 更簡潔的 shell 配置

### 2. 建立專案原則

使用 **`/speckit.constitution`** 指令來建立專案的治理原則和開發指導方針，這將指導所有後續的開發工作。

```bash
/speckit.constitution Create principles focused on code quality, testing standards, user experience consistency, and performance requirements
```

### 3. 建立規格

使用 **`/speckit.specify`** 指令來描述您想建構的內容。專注於**什麼**和**為什麼**，而不是技術堆疊。

```bash
/speckit.specify Build an application that can help me organize my photos in separate photo albums. Albums are grouped by date and can be re-organized by dragging and dropping on the main page. Albums are never in other nested albums. Within each album, photos are previewed in a tile-like interface.
```

### 4. 建立技術實作計劃

使用 **`/speckit.plan`** 指令來提供您的技術堆疊和架構選擇。

```bash
/speckit.plan The application uses Vite with minimal number of libraries. Use vanilla HTML, CSS, and JavaScript as much as possible. Images are not uploaded anywhere and metadata is stored in a local SQLite database.
```

### 5. 分解為任務

使用 **`/speckit.tasks`** 從您的實作計劃建立可執行的任務清單。

```bash
/speckit.tasks
```

### 6. 執行實作

使用 **`/speckit.implement`** 來執行所有任務並根據計劃建構您的功能。

```bash
/speckit.implement
```

詳細的逐步說明，請參閱我們的[完整指南](./spec-driven.md)。

## 📽️ 影片概覽

想看看 Spec Kit 的實際操作嗎？觀看我們的[影片概覽](https://www.youtube.com/watch?v=a9eR1xsfvHg&pp=0gcJCckJAYcqIYzv)！

[![Spec Kit video header](/media/spec-kit-video-header.jpg)](https://www.youtube.com/watch?v=a9eR1xsfvHg&pp=0gcJCckJAYcqIYzv)

## 🤖 支援的 AI 代理

| Agent                                                     | 支援 | 備註                                             |
|-----------------------------------------------------------|------|--------------------------------------------------|
| [Claude Code](https://www.anthropic.com/claude-code)      | ✅   |                                                  |
| [GitHub Copilot](https://code.visualstudio.com/)          | ✅   |                                                  |
| [Gemini CLI](https://github.com/google-gemini/gemini-cli) | ✅   |                                                  |
| [Cursor](https://cursor.sh/)                              | ✅   |                                                  |
| [Qwen Code](https://github.com/QwenLM/qwen-code)          | ✅   |                                                  |
| [opencode](https://opencode.ai/)                          | ✅   |                                                  |
| [Windsurf](https://windsurf.com/)                         | ✅   |                                                  |
| [Kilo Code](https://github.com/Kilo-Org/kilocode)         | ✅   |                                                  |
| [Auggie CLI](https://docs.augmentcode.com/cli/overview)   | ✅   |                                                  |
| [Roo Code](https://roocode.com/)                          | ✅   |                                                  |
| [Codex CLI](https://github.com/openai/codex)              | ✅   |                                                  |
| [Amazon Q Developer CLI](https://aws.amazon.com/developer/learning/q-developer-cli/) | ⚠️   | Amazon Q Developer CLI [不支援](https://github.com/aws/amazon-q-developer-cli/issues/3064) 自訂斜線指令參數。 |

## 🔧 Specify CLI 參考

`specify` 指令支援以下選項：

### 指令

| 指令        | 描述                                                    |
|-------------|----------------------------------------------------------------|
| `init`      | 從最新範本初始化新的 Specify 專案      |
| `check`     | 檢查已安裝的工具 (`git`, `claude`, `gemini`, `code`/`code-insiders`, `cursor-agent`, `windsurf`, `qwen`, `opencode`, `codex`) |

### `specify init` 參數與選項

| 參數/選項              | 類型     | 描述                                                                  |
|------------------------|----------|------------------------------------------------------------------------------|
| `<project-name>`       | 參數     | 新專案目錄的名稱（使用 `--here` 時可選，或使用 `.` 表示當前目錄） |
| `--ai`                 | 選項     | 使用的 AI 助手：`claude`、`gemini`、`copilot`、`cursor`、`qwen`、`opencode`、`codex`、`windsurf`、`kilocode`、`auggie`、`roo` 或 `q` |
| `--script`             | 選項     | 使用的腳本變體：`sh` (bash/zsh) 或 `ps` (PowerShell)                 |
| `--ignore-agent-tools` | 標誌     | 跳過 AI 代理工具檢查，如 Claude Code                             |
| `--no-git`             | 標誌     | 跳過 git 儲存庫初始化                                          |
| `--here`               | 標誌     | 在當前目錄初始化專案，而不是建立新目錄   |
| `--force`              | 標誌     | 在當前目錄初始化時強制合併/覆蓋（跳過確認） |
| `--skip-tls`           | 標誌     | 跳過 SSL/TLS 驗證（不推薦）                                 |
| `--debug`              | 標誌     | 啟用詳細除錯輸出以進行疑難排解                            |
| `--github-token`       | 選項     | API 請求的 GitHub token（或設定 GH_TOKEN/GITHUB_TOKEN 環境變數）  |

### Examples

```bash
# Basic project initialization
specify init my-project

# Initialize with specific AI assistant
specify init my-project --ai claude

# Initialize with Cursor support
specify init my-project --ai cursor

# Initialize with Windsurf support
specify init my-project --ai windsurf

# Initialize with PowerShell scripts (Windows/cross-platform)
specify init my-project --ai copilot --script ps

# Initialize in current directory
specify init . --ai copilot
# or use the --here flag
specify init --here --ai copilot

# Force merge into current (non-empty) directory without confirmation
specify init . --force --ai copilot
# or 
specify init --here --force --ai copilot

# Skip git initialization
specify init my-project --ai gemini --no-git

# Enable debug output for troubleshooting
specify init my-project --ai claude --debug

# Use GitHub token for API requests (helpful for corporate environments)
specify init my-project --ai claude --github-token ghp_your_token_here

# Check system requirements
specify check
```

### 可用的斜線指令

執行 `specify init` 後，您的 AI 程式設計代理將可以使用這些斜線指令進行結構化開發：

#### 核心指令

規格驅動開發工作流程的基本指令：

| 指令                  | 描述                                                           |
|--------------------------|-----------------------------------------------------------------------|
| `/speckit.constitution`  | 建立或更新專案治理原則和開發指導方針 |
| `/speckit.specify`       | 定義您想建構的內容（需求和用戶故事）        |
| `/speckit.plan`          | 使用您選擇的技術堆疊建立技術實作計劃     |
| `/speckit.tasks`         | 為實作生成可執行的任務清單                     |
| `/speckit.implement`     | 執行所有任務以根據計劃建構功能         |

#### 選用指令

用於增強品質和驗證的額外指令：

| 指令              | 描述                                                           |
|----------------------|-----------------------------------------------------------------------|
| `/speckit.clarify`   | 澄清規格不足的區域（建議在 `/speckit.plan` 之前使用；前身為 `/quizme`) |
| `/speckit.analyze`   | 跨工件一致性和覆蓋率分析（在 `/speckit.tasks` 之後，`/speckit.implement` 之前執行） |
| `/speckit.checklist` | 生成自訂品質檢查清單，驗證需求的完整性、清晰性和一致性（如「英文的單元測試」） |

### 環境變數

| 變數         | 描述                                                                                    |
|------------------|------------------------------------------------------------------------------------------------|
| `SPECIFY_FEATURE` | 覆蓋非 Git 儲存庫的功能偵測。設定為功能目錄名稱（如 `001-photo-albums`），以便在不使用 Git 分支時處理特定功能。<br/>**必須在使用 `/speckit.plan` 或後續指令之前，在您正在使用的代理上下文中設定。 |

## 📚 核心理念

規格驅動開發是一個強調以下內容的結構化過程：

- **意圖驅動開發** - 規格在「如何」之前定義「什麼」
- **豐富的規格建立** - 使用防護欄和組織原則
- **多步驟改進** - 而不是從提示一次性生成程式碼
- **高度依賴** - 進階 AI 模型能力進行規格解釋

## 🌟 開發階段

| 階段 | 重點 | 關鍵活動 |
|-------|-------|----------------|
| **0 到 1 開發」("Greenfield") | 從頭生成 | <ul><li>從高層次需求開始</li><li>生成規格</li><li>規劃實作步驟</li><li>建構生產級應用程式</li></ul> |
| **創意探索** | 平行實作 | <ul><li>探索多樣化解決方案</li><li>支援多種技術堆疊和架構</li><li>試驗 UX 模式</li></ul> |
| **迭代增強」("Brownfield") | 舊系統現代化 | <ul><li>迭代新增功能</li><li>現代化遺留系統</li><li>調整流程</li></ul> |

## 🎯 實驗目標

我們的研究和實驗專注於：

### 技術獨立性

- 使用多樣化的技術堆疊建立應用程式
- 驗證規格驅動開發是一個不依賴特定技術、程式語言或框架的過程

### 企業限制

- 展示關鍵任務應用程式開發
- 納入組織限制（雲端提供商、技術堆疊、工程實務）
- 支援企業設計系統和合規要求

### 以用戶為中心的開發

- 為不同的用戶群組和偏好建立應用程式
- 支援各種開發方法（從 vibe-coding 到 AI 原生開發）

### 創意和迭代流程

- 驗證平行實作探索的概念
- 提供強健的迭代功能開發工作流程
- 擴展流程以處理升級和現代化任務

## 🔧 先決條件

- **Linux/macOS**（或 Windows 上的 WSL2）
- AI 程式設計代理：[Claude Code](https://www.anthropic.com/claude-code)、[GitHub Copilot](https://code.visualstudio.com/)、[Gemini CLI](https://github.com/google-gemini/gemini-cli)、[Cursor](https://cursor.sh/)、[Qwen CLI](https://github.com/QwenLM/qwen-code)、[opencode](https://opencode.ai/)、[Codex CLI](https://github.com/openai/codex)、[Windsurf](https://windsurf.com/) 或 [Amazon Q Developer CLI](https://aws.amazon.com/developer/learning/q-developer-cli/)
- [uv](https://docs.astral.sh/uv/) 用於套件管理
- [Python 3.11+](https://www.python.org/downloads/)
- [Git](https://git-scm.com/downloads)

如果您遇到代理問題，請開啟一個 issue，以便我們改進整合。

## 📖 更多資訊

- **[完整的規格驅動開發方法論](./spec-driven.md)** - 深入探討完整流程
- **[詳細逐步指南](#-詳細流程)** - 逐步實作指南

---

## 📋 Detailed process

<details>
<summary>Click to expand the detailed step-by-step walkthrough</summary>

You can use the Specify CLI to bootstrap your project, which will bring in the required artifacts in your environment. Run:

```bash
specify init <project_name>
```

Or initialize in the current directory:

```bash
specify init .
# or use the --here flag
specify init --here
# Skip confirmation when the directory already has files
specify init . --force
# or
specify init --here --force
```

![Specify CLI bootstrapping a new project in the terminal](./media/specify_cli.gif)

You will be prompted to select the AI agent you are using. You can also proactively specify it directly in the terminal:

```bash
specify init <project_name> --ai claude
specify init <project_name> --ai gemini
specify init <project_name> --ai copilot

# Or in current directory:
specify init . --ai claude
specify init . --ai codex

# or use --here flag
specify init --here --ai claude
specify init --here --ai codex

# Force merge into a non-empty current directory
specify init . --force --ai claude

# or
specify init --here --force --ai claude
```

The CLI will check if you have Claude Code, Gemini CLI, Cursor CLI, Qwen CLI, opencode, Codex CLI, or Amazon Q Developer CLI installed. If you do not, or you prefer to get the templates without checking for the right tools, use `--ignore-agent-tools` with your command:

```bash
specify init <project_name> --ai claude --ignore-agent-tools
```

### **STEP 1:** Establish project principles

Go to the project folder and run your AI agent. In our example, we're using `claude`.

![Bootstrapping Claude Code environment](./media/bootstrap-claude-code.gif)

You will know that things are configured correctly if you see the `/speckit.constitution`, `/speckit.specify`, `/speckit.plan`, `/speckit.tasks`, and `/speckit.implement` commands available.

The first step should be establishing your project's governing principles using the `/speckit.constitution` command. This helps ensure consistent decision-making throughout all subsequent development phases:

```text
/speckit.constitution Create principles focused on code quality, testing standards, user experience consistency, and performance requirements. Include governance for how these principles should guide technical decisions and implementation choices.
```

This step creates or updates the `.specify/memory/constitution.md` file with your project's foundational guidelines that the AI agent will reference during specification, planning, and implementation phases.

### **STEP 2:** Create project specifications

With your project principles established, you can now create the functional specifications. Use the `/speckit.specify` command and then provide the concrete requirements for the project you want to develop.

>[!IMPORTANT]
>Be as explicit as possible about _what_ you are trying to build and _why_. **Do not focus on the tech stack at this point**.

An example prompt:

```text
Develop Taskify, a team productivity platform. It should allow users to create projects, add team members,
assign tasks, comment and move tasks between boards in Kanban style. In this initial phase for this feature,
let's call it "Create Taskify," let's have multiple users but the users will be declared ahead of time, predefined.
I want five users in two different categories, one product manager and four engineers. Let's create three
different sample projects. Let's have the standard Kanban columns for the status of each task, such as "To Do,"
"In Progress," "In Review," and "Done." There will be no login for this application as this is just the very
first testing thing to ensure that our basic features are set up. For each task in the UI for a task card,
you should be able to change the current status of the task between the different columns in the Kanban work board.
You should be able to leave an unlimited number of comments for a particular card. You should be able to, from that task
card, assign one of the valid users. When you first launch Taskify, it's going to give you a list of the five users to pick
from. There will be no password required. When you click on a user, you go into the main view, which displays the list of
projects. When you click on a project, you open the Kanban board for that project. You're going to see the columns.
You'll be able to drag and drop cards back and forth between different columns. You will see any cards that are
assigned to you, the currently logged in user, in a different color from all the other ones, so you can quickly
see yours. You can edit any comments that you make, but you can't edit comments that other people made. You can
delete any comments that you made, but you can't delete comments anybody else made.
```

After this prompt is entered, you should see Claude Code kick off the planning and spec drafting process. Claude Code will also trigger some of the built-in scripts to set up the repository.

Once this step is completed, you should have a new branch created (e.g., `001-create-taskify`), as well as a new specification in the `specs/001-create-taskify` directory.

The produced specification should contain a set of user stories and functional requirements, as defined in the template.

At this stage, your project folder contents should resemble the following:

```text
└── .specify
    ├── memory
    │	 └── constitution.md
    ├── scripts
    │	 ├── check-prerequisites.sh
    │	 ├── common.sh
    │	 ├── create-new-feature.sh
    │	 ├── setup-plan.sh
    │	 └── update-claude-md.sh
    ├── specs
    │	 └── 001-create-taskify
    │	     └── spec.md
    └── templates
        ├── plan-template.md
        ├── spec-template.md
        └── tasks-template.md
```

### **STEP 3:** Functional specification clarification (required before planning)

With the baseline specification created, you can go ahead and clarify any of the requirements that were not captured properly within the first shot attempt.

You should run the structured clarification workflow **before** creating a technical plan to reduce rework downstream.

Preferred order:
1. Use `/speckit.clarify` (structured) – sequential, coverage-based questioning that records answers in a Clarifications section.
2. Optionally follow up with ad-hoc free-form refinement if something still feels vague.

If you intentionally want to skip clarification (e.g., spike or exploratory prototype), explicitly state that so the agent doesn't block on missing clarifications.

Example free-form refinement prompt (after `/speckit.clarify` if still needed):

```text
For each sample project or project that you create there should be a variable number of tasks between 5 and 15
tasks for each one randomly distributed into different states of completion. Make sure that there's at least
one task in each stage of completion.
```

You should also ask Claude Code to validate the **Review & Acceptance Checklist**, checking off the things that are validated/pass the requirements, and leave the ones that are not unchecked. The following prompt can be used:

```text
Read the review and acceptance checklist, and check off each item in the checklist if the feature spec meets the criteria. Leave it empty if it does not.
```

It's important to use the interaction with Claude Code as an opportunity to clarify and ask questions around the specification - **do not treat its first attempt as final**.

### **STEP 4:** Generate a plan

You can now be specific about the tech stack and other technical requirements. You can use the `/speckit.plan` command that is built into the project template with a prompt like this:

```text
We are going to generate this using .NET Aspire, using Postgres as the database. The frontend should use
Blazor server with drag-and-drop task boards, real-time updates. There should be a REST API created with a projects API,
tasks API, and a notifications API.
```

The output of this step will include a number of implementation detail documents, with your directory tree resembling this:

```text
.
├── CLAUDE.md
├── memory
│	 └── constitution.md
├── scripts
│	 ├── check-prerequisites.sh
│	 ├── common.sh
│	 ├── create-new-feature.sh
│	 ├── setup-plan.sh
│	 └── update-claude-md.sh
├── specs
│	 └── 001-create-taskify
│	     ├── contracts
│	     │	 ├── api-spec.json
│	     │	 └── signalr-spec.md
│	     ├── data-model.md
│	     ├── plan.md
│	     ├── quickstart.md
│	     ├── research.md
│	     └── spec.md
└── templates
    ├── CLAUDE-template.md
    ├── plan-template.md
    ├── spec-template.md
    └── tasks-template.md
```

Check the `research.md` document to ensure that the right tech stack is used, based on your instructions. You can ask Claude Code to refine it if any of the components stand out, or even have it check the locally-installed version of the platform/framework you want to use (e.g., .NET).

Additionally, you might want to ask Claude Code to research details about the chosen tech stack if it's something that is rapidly changing (e.g., .NET Aspire, JS frameworks), with a prompt like this:

```text
I want you to go through the implementation plan and implementation details, looking for areas that could
benefit from additional research as .NET Aspire is a rapidly changing library. For those areas that you identify that
require further research, I want you to update the research document with additional details about the specific
versions that we are going to be using in this Taskify application and spawn parallel research tasks to clarify
any details using research from the web.
```

During this process, you might find that Claude Code gets stuck researching the wrong thing - you can help nudge it in the right direction with a prompt like this:

```text
I think we need to break this down into a series of steps. First, identify a list of tasks
that you would need to do during implementation that you're not sure of or would benefit
from further research. Write down a list of those tasks. And then for each one of these tasks,
I want you to spin up a separate research task so that the net results is we are researching
all of those very specific tasks in parallel. What I saw you doing was it looks like you were
researching .NET Aspire in general and I don't think that's gonna do much for us in this case.
That's way too untargeted research. The research needs to help you solve a specific targeted question.
```

>[!NOTE]
>Claude Code might be over-eager and add components that you did not ask for. Ask it to clarify the rationale and the source of the change.

### **STEP 5:** Have Claude Code validate the plan

With the plan in place, you should have Claude Code run through it to make sure that there are no missing pieces. You can use a prompt like this:

```text
Now I want you to go and audit the implementation plan and the implementation detail files.
Read through it with an eye on determining whether or not there is a sequence of tasks that you need
to be doing that are obvious from reading this. Because I don't know if there's enough here. For example,
when I look at the core implementation, it would be useful to reference the appropriate places in the implementation
details where it can find the information as it walks through each step in the core implementation or in the refinement.
```

This helps refine the implementation plan and helps you avoid potential blind spots that Claude Code missed in its planning cycle. Once the initial refinement pass is complete, ask Claude Code to go through the checklist once more before you can get to the implementation.

You can also ask Claude Code (if you have the [GitHub CLI](https://docs.github.com/en/github-cli/github-cli) installed) to go ahead and create a pull request from your current branch to `main` with a detailed description, to make sure that the effort is properly tracked.

>[!NOTE]
>Before you have the agent implement it, it's also worth prompting Claude Code to cross-check the details to see if there are any over-engineered pieces (remember - it can be over-eager). If over-engineered components or decisions exist, you can ask Claude Code to resolve them. Ensure that Claude Code follows the [constitution](base/memory/constitution.md) as the foundational piece that it must adhere to when establishing the plan.

### STEP 6: Implementation

Once ready, use the `/speckit.implement` command to execute your implementation plan:

```text
/speckit.implement
```

The `/speckit.implement` command will:
- Validate that all prerequisites are in place (constitution, spec, plan, and tasks)
- Parse the task breakdown from `tasks.md`
- Execute tasks in the correct order, respecting dependencies and parallel execution markers
- Follow the TDD approach defined in your task plan
- Provide progress updates and handle errors appropriately

>[!IMPORTANT]
>The AI agent will execute local CLI commands (such as `dotnet`, `npm`, etc.) - make sure you have the required tools installed on your machine.

Once the implementation is complete, test the application and resolve any runtime errors that may not be visible in CLI logs (e.g., browser console errors). You can copy and paste such errors back to your AI agent for resolution.

</details>

---

## 🔍 疑難排解

### Linux 上的 Git 憑證管理器

如果您在 Linux 上遇到 Git 認證問題，可以安裝 Git 憑證管理器：

```bash
#!/usr/bin/env bash
set -e
echo "正在下載 Git 憑證管理器 v2.6.1..."
wget https://github.com/git-ecosystem/git-credential-manager/releases/download/v2.6.1/gcm-linux_amd64.2.6.1.deb
echo "正在安裝 Git 憑證管理器..."
sudo dpkg -i gcm-linux_amd64.2.6.1.deb
echo "正在設定 Git 使用 GCM..."
git config --global credential.helper manager
echo "正在清理..."
rm gcm-linux_amd64.2.6.1.deb
```

## 👥 維護者

- Den Delimarsky ([@localden](https://github.com/localden))
- John Lam ([@jflam](https://github.com/jflam))

## 💬 支援

如需支援，請開啟 [GitHub issue](https://github.com/github/spec-kit/issues/new)。我們歡迎錯誤報告、功能請求以及關於使用規格驅動開發的問題。

## 🙏 致謝

這個專案深受 [John Lam](https://github.com/jflam) 的工作和研究的影響並基於其內容。

## 📄 授權

此專案根據 MIT 開源授權條款授權。請參閱 [LICENSE](./LICENSE) 文件了解完整條款。
