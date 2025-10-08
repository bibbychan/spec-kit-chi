# Specification-Driven Development (SDD)

## 權力反轉

數十年來，程式碼一直是王道。規格服務於程式碼——它們是我們建構的鷹架，一旦程式設計的「真正工作」開始就被拋棄。我們撰寫 PRD 來指導開發，建立設計文件來告知實作，繪製圖表來視覺化架構。但這些都從屬於程式碼本身。程式碼是真理。其他一切都是，充其量，良好的意圖。程式碼是真相的來源，隨著它的前進，規格很少能跟上進度。由於資產（程式碼）和實作是一體的，如果不嘗試從程式碼建構，就很难有平行實作。

Spec-Driven Development (SDD) 顛覆了這種權力結構。規格不服務於程式碼——程式碼服務於規格。產品需求文件（PRD）不是實作的指南；它是產生實作的來源。技術計畫不是告知編碼的文件；它們是產生程式碼的精確定義。這不是對我們建構軟體方式的漸進式改進。這是對驅動開發的根本性重新思考。

規格和實作之間的差距自軟體開發誕生以來就一直困擾著它。我們試圖用更好的文件、更詳細的需求、更嚴格的流程來彌補這個差距。這些方法失敗了，因為它們接受這個差距是不可避免的。它們試圖縮小它，但從未消除它。SDD 通過使規格和從規格產生的具體實作計畫可執行來消除差距。當規格和實作計畫生成程式碼時，沒有差距——只有轉換。

這種轉換現在是可能的，因為 AI 可以理解和實作複雜的規格，並建立詳細的實作計畫。但沒有結構的原始 AI 生成會產生混亂。SDD 通過規格和後續的實作計畫提供這種結構，這些計畫足夠精確、完整和明確，可以生成運作的系統。規格成為主要的工件。程式碼成為其在特定語言和框架中的表達（作為從實作計畫的實作）。

在這個新世界中，維護軟體意味著進化規格。開發團隊的意圖以自然語言（「**意圖驅動開發**」）、設計資產、核心原則和其他指導方針表達。開發的 **通用語** 移動到更高層次，而程式碼是最後一哩的方法。

除錯意味著修復產生錯誤程式碼的規格和其實作計畫。重構意味為清晰度而重組結構。整個開發工作流程圍繞規格作為中心真相來源重新組織，實作計畫和程式碼作為持續重新生成的輸出。用新功能更新應用程式或因為我們是有創造力的生物而建立新的平行實作，意味著重新審視規格並建立新的實作計畫。因此，這個過程是 0 -> 1, (1', ..), 2, 3, N。

開發團隊專注於他們的創造力、實驗和他們的批判性思維。

## 實踐中的 SDD 工作流程

工作流程始於一個想法——通常是模糊和不完整的。通過與 AI 的迭代對話，這個想法變成全面的 PRD。AI 提出澄清問題，識別邊緣情況，並協助定義精確的驗收標準。在傳統開發中可能需要幾天會議和文件的工作，在幾小時的專注規格工作中完成。這改變了傳統的 SDLC——需求和設計變成持續的活動，而不是離散的階段。這支援 **團隊流程**，其中團隊審查的規格被表達和版本控制，在分支中建立並合併。

當產品經理更新驗收標準時，實作計畫會自動標記受影響的技術決策。當架構師發現更好的模式時，PRD 會更新以反映新的可能性。

在整個規格過程中，研究代理收集關鍵上下文。他們調查函式庫相容性、效能基準和安全影響。組織限制被發現並自動應用——您公司的資料庫標準、身分驗證要求和部署政策無縫整合到每個規格中。

從 PRD，AI 生成將需求映射到技術決策的實作計畫。每個技術選擇都有記錄的基本原理。每個架構決策都追溯到特定的需求。在整個過程中，一致性驗證持續改進品質。AI 分析規格的模糊性、矛盾和差距——不是作為一次性閘門，而是作為持續的精煉。

程式碼生成在規格和其實作計畫足夠穩定時開始，但它們不必是「完整的」。早期生成可能是探索性的——測試規格在實踐中是否有意義。領域概念變成資料模型。使用者故事變成 API 端點。驗收場景變成測試。這通過規格合併開發和測試——測試場景不是在程式碼之後撰寫的，它們是產生實作和測試的規格的一部分。

反饋迴圈延伸到初始開發之外。生產指標和事件不僅觸發熱修復——它們更新下次重新生成的規格。效能瓶頸變成新的非功能性需求。安全漏洞變成影響所有未來生成的限制。規格、實作和運作現實之間的這種迭代舞蹈是真正理解出現的地方，也是傳統 SDLC 轉變為持續進化的地方。

## 為什麼 SDD 現在很重要

三個趨勢使 SDD 不僅可能而且必要：

首先，AI 能力已經達到一個閾值，自然語言規格可以可靠地生成運作的程式碼。這不是關於替換開發人員——而是通過自動化從規格到實作的機械翻譯來放大他們的有效性。它可以放大探索和創造力，輕鬆支援「重新開始」，並支援加法、減法和批判性思維。

其次，軟體複雜性繼續呈指數級增長。現代系統整合了數十個服務、框架和依賴項。通過手動流程保持所有這些部分與原始意圖一致變得越來越困難。SDD 通過規格驅動的生成提供系統性的一致性。框架可能會演變以提供 AI 優先的支援，而不是人類優先的支援，或圍繞可重用元件進行架構設計。

第三，變化的步伐加速。需求現在比以往任何時候都變化得更快。轉向不再例外——這是預期的。現代產品開發需要基於使用者反饋、市場條件和競爭壓力的快速迭代。傳統開發將這些變化視為干擾。每次轉向都需要手動將變化傳播到文件、設計和程式碼中。結果要麼是限制速度的緩慢、謹慎的更新，要麼是累積技術債務的快速、魯莽的變化。

SDD 可以支援假設/模擬實驗：「如果我們需要重新實作或更改應用程式以促進銷售更多 T 恤的業務需求，我們將如何實作和實驗？」

SDD 將需求變化從障礙轉變為正常工作流程。當規格驅動實作時，轉向變成系統性的重新生成，而不是手動重寫。更改 PRD 中的核心需求，受影響的實作計畫會自動更新。修改使用者故事，相應的 API 端點會重新生成。這不僅僅是關於初始開發——這是關於通過不可避免的變化保持工程速度。

## 核心原則

**規格作為通用語**：規格成為主要的工件。程式碼成為其在特定語言和框架中的表達。維護軟體意味著進化規格。

**可執行規格**：規格必須足夠精確、完整和明確，以生成運作的系統。這消除了意圖和實作之間的差距。

**持續精煉**：一致性驗證持續發生，而不是作為一次性閘門。AI 分析規格的模糊性、矛盾和差距作為持續的過程。

**研究驅動的上下文**：研究代理在整個規格過程中收集關鍵上下文，調查技術選項、效能影響和組織限制。

**雙向反饋**：生產現實告知規格進化。指標、事件和運作學習成為規格精煉的輸入。

**探索分支**：從同一規格生成多種實作方法，以探索不同的優化目標——效能、可維護性、使用者體驗、成本。

## 實作方法

今天，實踐 SDD 需要組裝現有工具並在整個過程中保持紀律。這種方法論可以透過以下方式實踐：

- AI 助手用於迭代規格開發
- 研究代理用於收集技術上下文
- 程式碼生成工具用於將規格翻譯為實作
- 適應規格優先工作流程的版本控制系統
- 通過 AI 分析規格文件進行一致性檢查

關鍵是將規格視為真相來源，程式碼作為生成的輸出服務於規格，而不是相反。

## 使用命令簡化 SDD

SDD 方法論通過三個強大的命令顯著增強，這些命令自動化規格 → 規劃 → 任務分配工作流程：

### `/speckit.specify` 命令

此命令將簡單的功能描述（使用者提示）轉換為完整的結構化規格，並具有自動存儲庫管理：

1. **自動功能編號**：掃描現有規格以確定下一個功能編號（例如 001、002、003）
2. **分支建立**：從您的描述生成語義分支名稱並自動建立它
3. **基於範本的生成**：複製和自訂功能規格範本與您的需求
4. **目錄結構**：為所有相關文件建立正確的 `specs/[branch-name]/` 結構

### `/speckit.plan` 命令

一旦功能規格存在，此命令建立全面的實作計畫：

1. **規格分析**：閱讀和理解功能需求、使用者故事和驗收標準
2. **憲法合規性**：確保與專案憲法和架構原則的一致性
3. **技術翻譯**：將業務需求轉換為技術架構和實作細節
4. **詳細文件**：為資料模型、API 合約和測試場景生成支援文件
5. **快速入門驗證**：產生捕獲關鍵驗證場景的快速入門指南

### `/speckit.tasks` 命令

計畫建立後，此命令分析計畫和相關設計文件以生成可執行的任務清單：

1. **輸入**：讀取 `plan.md`（必需）以及存在的 `data-model.md`、`contracts/` 和 `research.md`
2. **任務推導**：將合約、實體和場景轉換為特定任務
3. **平行化**：標記獨立任務 `[P]` 並概述安全的平行組
4. **輸出**：在功能目錄中寫入 `tasks.md`，準備由任務代理執行

### Example: Building a Chat Feature

Here's how these commands transform the traditional development workflow:

**Traditional Approach:**

```text
1. Write a PRD in a document (2-3 hours)
2. Create design documents (2-3 hours)
3. Set up project structure manually (30 minutes)
4. Write technical specifications (3-4 hours)
5. Create test plans (2 hours)
Total: ~12 hours of documentation work
```

**SDD with Commands Approach:**

```bash
# Step 1: Create the feature specification (5 minutes)
/speckit.specify Real-time chat system with message history and user presence

# This automatically:
# - Creates branch "003-chat-system"
# - Generates specs/003-chat-system/spec.md
# - Populates it with structured requirements

# Step 2: Generate implementation plan (5 minutes)
/speckit.plan WebSocket for real-time messaging, PostgreSQL for history, Redis for presence

# Step 3: Generate executable tasks (5 minutes)
/speckit.tasks

# This automatically creates:
# - specs/003-chat-system/plan.md
# - specs/003-chat-system/research.md (WebSocket library comparisons)
# - specs/003-chat-system/data-model.md (Message and User schemas)
# - specs/003-chat-system/contracts/ (WebSocket events, REST endpoints)
# - specs/003-chat-system/quickstart.md (Key validation scenarios)
# - specs/003-chat-system/tasks.md (Task list derived from the plan)
```

In 15 minutes, you have:

- A complete feature specification with user stories and acceptance criteria
- A detailed implementation plan with technology choices and rationale
- API contracts and data models ready for code generation
- Comprehensive test scenarios for both automated and manual testing
- All documents properly versioned in a feature branch

### The Power of Structured Automation

These commands don't just save time—they enforce consistency and completeness:

1. **No Forgotten Details**: Templates ensure every aspect is considered, from non-functional requirements to error handling
2. **Traceable Decisions**: Every technical choice links back to specific requirements
3. **Living Documentation**: Specifications stay in sync with code because they generate it
4. **Rapid Iteration**: Change requirements and regenerate plans in minutes, not days

The commands embody SDD principles by treating specifications as executable artifacts rather than static documents. They transform the specification process from a necessary evil into the driving force of development.

### Template-Driven Quality: How Structure Constrains LLMs for Better Outcomes

The true power of these commands lies not just in automation, but in how the templates guide LLM behavior toward higher-quality specifications. The templates act as sophisticated prompts that constrain the LLM's output in productive ways:

#### 1. **Preventing Premature Implementation Details**

The feature specification template explicitly instructs:

```text
- ✅ Focus on WHAT users need and WHY
- ❌ Avoid HOW to implement (no tech stack, APIs, code structure)
```

This constraint forces the LLM to maintain proper abstraction levels. When an LLM might naturally jump to "implement using React with Redux," the template keeps it focused on "users need real-time updates of their data." This separation ensures specifications remain stable even as implementation technologies change.

#### 2. **Forcing Explicit Uncertainty Markers**

Both templates mandate the use of `[NEEDS CLARIFICATION]` markers:

```text
When creating this spec from a user prompt:
1. **Mark all ambiguities**: Use [NEEDS CLARIFICATION: specific question]
2. **Don't guess**: If the prompt doesn't specify something, mark it
```

This prevents the common LLM behavior of making plausible but potentially incorrect assumptions. Instead of guessing that a "login system" uses email/password authentication, the LLM must mark it as `[NEEDS CLARIFICATION: auth method not specified - email/password, SSO, OAuth?]`.

#### 3. **Structured Thinking Through Checklists**

The templates include comprehensive checklists that act as "unit tests" for the specification:

```markdown
### Requirement Completeness
- [ ] No [NEEDS CLARIFICATION] markers remain
- [ ] Requirements are testable and unambiguous
- [ ] Success criteria are measurable
```

These checklists force the LLM to self-review its output systematically, catching gaps that might otherwise slip through. It's like giving the LLM a quality assurance framework.

#### 4. **Constitutional Compliance Through Gates**

The implementation plan template enforces architectural principles through phase gates:

```markdown
### Phase -1: Pre-Implementation Gates
#### Simplicity Gate (Article VII)
- [ ] Using ≤3 projects?
- [ ] No future-proofing?
#### Anti-Abstraction Gate (Article VIII)
- [ ] Using framework directly?
- [ ] Single model representation?
```

These gates prevent over-engineering by making the LLM explicitly justify any complexity. If a gate fails, the LLM must document why in the "Complexity Tracking" section, creating accountability for architectural decisions.

#### 5. **Hierarchical Detail Management**

The templates enforce proper information architecture:

```text
**IMPORTANT**: This implementation plan should remain high-level and readable.
Any code samples, detailed algorithms, or extensive technical specifications
must be placed in the appropriate `implementation-details/` file
```

This prevents the common problem of specifications becoming unreadable code dumps. The LLM learns to maintain appropriate detail levels, extracting complexity to separate files while keeping the main document navigable.

#### 6. **Test-First Thinking**

The implementation template enforces test-first development:

```text
### File Creation Order
1. Create `contracts/` with API specifications
2. Create test files in order: contract → integration → e2e → unit
3. Create source files to make tests pass
```

This ordering constraint ensures the LLM thinks about testability and contracts before implementation, leading to more robust and verifiable specifications.

#### 7. **Preventing Speculative Features**

Templates explicitly discourage speculation:

```text
- [ ] No speculative or "might need" features
- [ ] All phases have clear prerequisites and deliverables
```

This stops the LLM from adding "nice to have" features that complicate implementation. Every feature must trace back to a concrete user story with clear acceptance criteria.

### The Compound Effect

These constraints work together to produce specifications that are:

- **Complete**: Checklists ensure nothing is forgotten
- **Unambiguous**: Forced clarification markers highlight uncertainties
- **Testable**: Test-first thinking baked into the process
- **Maintainable**: Proper abstraction levels and information hierarchy
- **Implementable**: Clear phases with concrete deliverables

The templates transform the LLM from a creative writer into a disciplined specification engineer, channeling its capabilities toward producing consistently high-quality, executable specifications that truly drive development.

## The Constitutional Foundation: Enforcing Architectural Discipline

At the heart of SDD lies a constitution—a set of immutable principles that govern how specifications become code. The constitution (`memory/constitution.md`) acts as the architectural DNA of the system, ensuring that every generated implementation maintains consistency, simplicity, and quality.

### The Nine Articles of Development

The constitution defines nine articles that shape every aspect of the development process:

#### Article I: Library-First Principle

Every feature must begin as a standalone library—no exceptions. This forces modular design from the start:

```text
Every feature in Specify MUST begin its existence as a standalone library.
No feature shall be implemented directly within application code without
first being abstracted into a reusable library component.
```

This principle ensures that specifications generate modular, reusable code rather than monolithic applications. When the LLM generates an implementation plan, it must structure features as libraries with clear boundaries and minimal dependencies.

#### Article II: CLI Interface Mandate

Every library must expose its functionality through a command-line interface:

```text
All CLI interfaces MUST:
- Accept text as input (via stdin, arguments, or files)
- Produce text as output (via stdout)
- Support JSON format for structured data exchange
```

This enforces observability and testability. The LLM cannot hide functionality inside opaque classes—everything must be accessible and verifiable through text-based interfaces.

#### Article III: Test-First Imperative

The most transformative article—no code before tests:

```text
This is NON-NEGOTIABLE: All implementation MUST follow strict Test-Driven Development.
No implementation code shall be written before:
1. Unit tests are written
2. Tests are validated and approved by the user
3. Tests are confirmed to FAIL (Red phase)
```

This completely inverts traditional AI code generation. Instead of generating code and hoping it works, the LLM must first generate comprehensive tests that define behavior, get them approved, and only then generate implementation.

#### Articles VII & VIII: Simplicity and Anti-Abstraction

These paired articles combat over-engineering:

```text
Section 7.3: Minimal Project Structure
- Maximum 3 projects for initial implementation
- Additional projects require documented justification

Section 8.1: Framework Trust
- Use framework features directly rather than wrapping them
```

When an LLM might naturally create elaborate abstractions, these articles force it to justify every layer of complexity. The implementation plan template's "Phase -1 Gates" directly enforce these principles.

#### Article IX: Integration-First Testing

Prioritizes real-world testing over isolated unit tests:

```text
Tests MUST use realistic environments:
- Prefer real databases over mocks
- Use actual service instances over stubs
- Contract tests mandatory before implementation
```

This ensures generated code works in practice, not just in theory.

### Constitutional Enforcement Through Templates

The implementation plan template operationalizes these articles through concrete checkpoints:

```markdown
### Phase -1: Pre-Implementation Gates
#### Simplicity Gate (Article VII)
- [ ] Using ≤3 projects?
- [ ] No future-proofing?

#### Anti-Abstraction Gate (Article VIII)
- [ ] Using framework directly?
- [ ] Single model representation?

#### Integration-First Gate (Article IX)
- [ ] Contracts defined?
- [ ] Contract tests written?
```

These gates act as compile-time checks for architectural principles. The LLM cannot proceed without either passing the gates or documenting justified exceptions in the "Complexity Tracking" section.

### The Power of Immutable Principles

The constitution's power lies in its immutability. While implementation details can evolve, the core principles remain constant. This provides:

1. **Consistency Across Time**: Code generated today follows the same principles as code generated next year
2. **Consistency Across LLMs**: Different AI models produce architecturally compatible code
3. **Architectural Integrity**: Every feature reinforces rather than undermines the system design
4. **Quality Guarantees**: Test-first, library-first, and simplicity principles ensure maintainable code

### Constitutional Evolution

While principles are immutable, their application can evolve:

```text
Section 4.2: Amendment Process
Modifications to this constitution require:
- Explicit documentation of the rationale for change
- Review and approval by project maintainers
- Backwards compatibility assessment
```

This allows the methodology to learn and improve while maintaining stability. The constitution shows its own evolution with dated amendments, demonstrating how principles can be refined based on real-world experience.

### Beyond Rules: A Development Philosophy

The constitution isn't just a rulebook—it's a philosophy that shapes how LLMs think about code generation:

- **Observability Over Opacity**: Everything must be inspectable through CLI interfaces
- **Simplicity Over Cleverness**: Start simple, add complexity only when proven necessary
- **Integration Over Isolation**: Test in real environments, not artificial ones
- **Modularity Over Monoliths**: Every feature is a library with clear boundaries

By embedding these principles into the specification and planning process, SDD ensures that generated code isn't just functional—it's maintainable, testable, and architecturally sound. The constitution transforms AI from a code generator into an architectural partner that respects and reinforces system design principles.

## The Transformation

This isn't about replacing developers or automating creativity. It's about amplifying human capability by automating mechanical translation. It's about creating a tight feedback loop where specifications, research, and code evolve together, each iteration bringing deeper understanding and better alignment between intent and implementation.

Software development needs better tools for maintaining alignment between intent and implementation. SDD provides the methodology for achieving this alignment through executable specifications that generate code rather than merely guiding it.
