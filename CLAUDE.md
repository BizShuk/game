# 遊戲研究專案 — 技術脈絡 (Technical Context - Game Research)

## 專案性質 (Project Nature)

本專案為「遊戲開發與計算研究 (Game Development & Calculation Research)」子專案，純文件形式，主要關注特定遊戲之設計機制、數值計算、大綱設計與美術生產契約。

## 專案目標 (Project Goal)

`統一介面 (Unified Interface):` 以 `README.md` 作為業務領域之導覽與索引，以 `CLAUDE.md` 作為技術脈絡，並確保專案下所有 Markdown 文件命名均符合小寫英文與底線之全局規範。

## 專案結構 (Project Structure)

```tree
/Users/shuk/projects/game/
├── README.md                # 遊戲專案業務導覽與業務領域索引
├── CLAUDE.md                # 專案技術脈絡 (you are here)
├── game-architect/          # 遊戲架構知識庫 (nested repo：BizShuk/game-architect)
│   ├── README.md            # 子域入口、內容索引與依賴方向
│   ├── guideline.md         # 遊戲開發完整大綱 (機制檔的章節錨點來源)
│   ├── monster_spawning.md  # 怪物生成與觸發機制 (專題深潛)
│   ├── light_and_dark.md    # 光明與黑暗一代機制解析
│   ├── lineage_calculation.md # 天堂數值與收益計算
│   ├── mechanisms/          # 系統機制設計指南 (通用框架 + 數值模板)
│   │   ├── README.md        # 機制索引與 backlog
│   │   ├── design_template.md # 通用機制設計模板
│   │   ├── clan_system.md   # 血盟/公會系統
│   │   ├── gambling_racing.md # 賭博競賽系統
│   │   ├── pvp_siege.md     # PVP/攻城戰系統
│   │   ├── item_planning.md # 道具規劃
│   │   ├── monster_stats_spawning.md # 怪物數值與生怪規則
│   │   ├── map_scene_design.md # 場景地圖設計
│   │   ├── quest_activity.md # 任務與活動系統
│   │   ├── economy_trading.md # 經濟與交易系統
│   │   ├── weather_season.md # 天氣/季節系統
│   │   ├── pet_mount.md     # 寵物/坐騎系統
│   │   ├── ranked_ladder.md # 排位賽系統
│   │   ├── social_friends.md # 社交/好友系統
│   │   ├── achievement_system.md # 成就系統
│   │   ├── crafting_life_skills.md # 製造/生活技能系統
│   │   └── case_study_lineage.md # 案例反推：經典天堂
│   ├── lineage/             # 天堂 Clone 前瞻設計 (正向設計規格集)
│   │   ├── README.md        # 索引、使用方式、版權聲明
│   │   ├── design_template.md # lineage 專用前瞻設計骨架 (5-7 節)
│   │   ├── design/          # 玩法設計 16 檔
│   │   ├── tech/            # 技術 3 檔
│   │   └── ops/             # 交付與法務 3 檔
│   └── art_pipeline/        # 契約驅動的 AI 遊戲美術生產知識域
│       ├── README.md        # 定位、成熟度、閱讀順序與 owner 導覽
│       ├── art_pipeline_spec.md # 七階段、五介面、狀態與 gate SSOT
│       ├── concept/         # Reference Contract procedure
│       ├── production/      # AI、render-to-sprite、atlas、環境與 UI
│       ├── integration/     # 引擎 adapter contract 與 Godot mapping
│       ├── examples/        # reference vertical slice
│       └── evolution/       # 2D 至 3D bridge
├── game-direction/          # 遊戲發展方向研究
│   ├── activity_types.md    # 遊戲活動類型
│   ├── game_genres.md       # 遊戲類型與特色
│   └── occupations_roles.md # 職業與定位
├── docs/
│   └── specs/               # 已實作計畫轉換之規格文件
│       └── system_mechanism_guidelines_spec.md
└── plans/                   # 專案內規劃文件 (實作後轉為 docs/specs/)
```

## 關鍵決策 (Key Decisions)

- `決策 1 — 扁平化與小寫英文底線命名`：為利於自動化工具識別與 Git 跨平台管理，所有研究檔案均從中文目錄移出，並改為小寫英文加底線命名。
- `決策 2 — 使用 Markdown 提供互動性與圖表`：採用 GFM 表格與 Mermaid 圖表來呈現複雜的數值期望值與工作流程（例如怪物生成核心流程）。
- `決策 3 — mechanisms/ 採薄腰式交叉引用`：`game-architect/mechanisms/` 機制檔聚焦「可調參數表 + 公式模板」，深度推導（演算法、案例數學）一律交叉引用 `game-architect/guideline.md`、`game-architect/monster_spawning.md` 與同 repo 反推案例，不重複內容；所有機制定義的 sink 須登記於 `game-architect/mechanisms/economy_trading.md` 消耗登記表。所有機制檔遵循 `game-architect/mechanisms/design_template.md` 統一骨架。
- `決策 4 — game-architect/guideline.md 章節編號慣例`：H3 小節編號前綴必須與所屬 H2 章號一致（§八 = 8.x、§九 = 9.x …）；跨文件引用一律以此編號為準（歷史上 §八 起曾整段錯位 1，已於 2026-07 修正）。
- `決策 5 — game-architect/lineage/ 採前瞻設計骨架`：`game-architect/lineage/` 為單一遊戲的正向設計規格集，不套用 `game-architect/mechanisms/design_template.md` 的 11 節骨架（跨類型適配、Bartle 動機映射對重建單一遊戲屬空洞填充），改用 `game-architect/lineage/design_template.md` 的 5-7 節骨架，重點防呆為「原版行為對照節僅摘要 + 引用（薄腰式），設計節一律原創取值與原創命名」；IP 約束集中於 `game-architect/lineage/ops/legal_ip_risk.md`。sink 經 `game-architect/lineage/design/economy_and_trading.md` 總帳彙總後登記至 `game-architect/mechanisms/economy_trading.md` 消耗登記表。來源計畫：`plans/2026-07-05-lineage-clone-doc-plan.md`。
- `決策 6 — art_pipeline/ 採契約驅動生產圖`：`game-architect/art_pipeline/art_pipeline_spec.md` 是七階段、G1-G6、五個跨階段介面與共用狀態的 canonical owner；所有 gate 只能由人員核准，AI 不得建立 `GateDecision`。核心契約維持引擎中立，`integration/godot_pipeline.md` 是第一個 adapter。Phase 1 僅交付本 repo 的 verified documentation，Phase 2 才在外部引擎 repo 建立工具工作流、資產與實機畫面。依賴方向固定為通用 `game-architect/art_pipeline/` 不依賴 `game-architect/lineage/`，個案可單向引用通用契約。
- `決策 7 — 基礎大綱與專題深潛併入 game-architect/`：`guideline.md` 與 `monster_spawning.md` 原置於 repo 根目錄，2026-07-22 移入 `game-architect/`，與其引用者 `mechanisms/`、`lineage/` 同 repo。理由是 `game-architect/` 內所有 backtick 路徑皆以該 repo 根目錄為基準，移入後既有數十處 `guideline.md` §x、`monster_spawning.md` §⑧ 引用無須改寫即可解析；反之留在外層則跨 repo 引用永遠斷鏈。

## 慣例 (Conventions)

### 命名 (Naming)

- `檔案命名`：小寫英文 + 底線 (如 `light_and_dark.md`、`lineage_calculation.md` 風格)。
- `雙語標題`：繁中為主、英文以括號註解。

### 限制與格式 (Constraints & Format)

- `不使用粗體`：在 any Markdown 文件中，皆不使用雙星號粗體語法，一律改以 `backtick` 進行強調。
- `Mermaid 圖表`：所有 Mermaid 邊線文字 (edge text) 必須用雙引號包覆 (例如: `A -->|"文字"| B`)。
