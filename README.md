# 遊戲開發與計算研究 (Game Development & Calculation Research)

## 專案性質 (Project Nature)

本專案為 `純文件 (Documentation-Only) 研究專案`，研究特定遊戲之設計機制、數值計算，以及由概念到引擎交接的美術生產契約；不包含可執行程式碼或引擎專案。

## 目錄結構 (Directory Structure)

```tree
game/
├── README.md                # 本檔：遊戲研究導覽
├── game-architect/          # 遊戲架構知識庫 (獨立 repo：BizShuk/game-architect)
│   ├── README.md            # 子域入口、內容索引與依賴方向
│   ├── guideline.md         # 遊戲開發完整大綱 (二十一章全景)
│   ├── monster_spawning.md  # 怪物生成與觸發機制 (專題深潛)
│   ├── light_and_dark.md    # 光明與黑暗一代之遊戲機制與深度解析
│   ├── lineage_calculation.md # 天堂龍之谷版本前之數值計算與裝備平衡研究
│   ├── mechanisms/          # 系統機制設計指南 (通用、可跨遊戲類型，17 檔)
│   │   ├── README.md        # 機制索引、模板使用說明與 backlog
│   │   ├── design_template.md # 通用機制設計模板
│   │   ├── clan_system.md   # 血盟/公會系統 (含血盟小屋)
│   │   ├── gambling_racing.md # 賭博競賽系統 (賭狗競賽/賠率/RTP)
│   │   ├── pvp_siege.md     # PVP/攻城戰系統
│   │   ├── item_planning.md # 道具規劃
│   │   ├── monster_stats_spawning.md # 怪物數值設定與生怪規則
│   │   ├── map_scene_design.md # 場景地圖設計
│   │   ├── quest_activity.md # 任務與活動系統
│   │   ├── economy_trading.md # 經濟與交易系統 (含 Sink 登記表)
│   │   ├── weather_season.md # 天氣/季節系統 (規則調變器)
│   │   ├── pet_mount.md     # 寵物/坐騎系統
│   │   ├── ranked_ladder.md # 排位賽系統 (MMR/段位)
│   │   ├── social_friends.md # 社交/好友系統 (好感度/師徒/婚姻)
│   │   ├── achievement_system.md # 成就系統
│   │   ├── crafting_life_skills.md # 製造/生活技能系統
│   │   └── case_study_lineage.md # 案例反推：經典天堂逐機制參數對照
│   ├── lineage/             # 天堂 Clone 前瞻設計 (單一遊戲完整重建規格)
│   │   ├── README.md        # 索引、使用方式與版權聲明
│   │   ├── design_template.md # 前瞻設計骨架 (5-7 節)
│   │   ├── design/          # 玩法設計 (16 檔)
│   │   ├── tech/            # 技術 (伺服器/客戶端/資料模型)
│   │   └── ops/             # 交付與法務 (路線圖/商業化/IP 風險)
│   └── art_pipeline/        # 契約驅動的 AI 遊戲美術生產線
│       ├── README.md        # 定位、成熟度與閱讀順序
│       ├── art_pipeline_spec.md # 七階段、介面、gate 與狀態 SSOT
│       ├── concept/         # 參考契約與視覺邊界
│       ├── production/      # AI、2.5D、sprite、環境與 UI procedure
│       ├── integration/     # 引擎中立 adapter 與 Godot 接入
│       ├── examples/        # 2D 整合縱切片
│       └── evolution/       # 2D 至 3D 橋接邊界
└── game-direction/          # 遊戲發展方向研究
    ├── activity_types.md    # 遊戲活動類型
    ├── game_genres.md       # 遊戲類型與特色
    └── occupations_roles.md # 職業與定位
```

> 本樹只涵蓋文件研究子域；同層另有 `3D-game-prototype/`、`3DSimulator-Singapore/`、`gameboy-rpg/`、`history_map/`（submodule 未初始化）、`lineage/`、`lineage-v380/`（一般目錄，非 submodule）、`map_generator/`、`maze/` 等實作型專案，以及分類層自身的 `skills/codex-gamestudio-skill/` 與 `.claude-plugin/`，尚未納入本導覽。

另有 `docs/specs/` 存放已實作計畫轉換之規格文件（如 `system_mechanism_guidelines_spec.md`：機制指南的結構、模板骨架與維護慣例）。

---

## 業務領域 (Business Domains)

- `遊戲開發完整大綱`：
    - 收錄於 `game-architect/guideline.md`。
    - 內容涵蓋核心遊戲設計、世界觀、角色系統、怪物系統、戰鬥系統、視野與可見度系統、經濟系統、連線機制與優化等大綱。
- `遊戲中怪物生成與觸發機制`：
    - 收錄於 `game-architect/monster_spawning.md`。
    - 內容包含生成方式（如 `定時生成`、`觸發區域生成`、`波次生成` ）、生成點的隨機化設計、用於提升效能的 `物件池` 技術，以及動態調整強度的 `AI 導演` 機制。
- `光明與黑暗一代遊戲機制`：
    - 收錄於 `game-architect/light_and_dark.md`。
    - 內容涵蓋劇情發展、托恩伍德王國與古人之四大試煉、十字型圖標選單、迷宮導航及秘銀鍛造與闇之石詛咒等數值解析。
- `天堂數值計算`：
    - 收錄於 `game-architect/lineage_calculation.md`。
    - 包含大小怪的 D&D 骰子傷害期望值計算、AC 迴避對抗與 -45 數值斷層、MR 魔法防禦斷點、強化成功機率與安定值博弈等機制。
- `遊戲發展方向研究`：
    - 收錄於 `game-direction/` 目錄。
    - 探討各種遊戲活動類型、遊戲類型特色與職業定位等設計。
- `天堂 Clone 前瞻設計`：
    - 收錄於 `game-architect/lineage/` 目錄，索引見 `game-architect/lineage/README.md`。
    - 單一遊戲的完整重建規格（正向設計）：玩法設計 16 檔（`design/`）、技術 3 檔（`tech/`）、交付與法務 3 檔（`ops/`），每個面向一檔（1-5 頁）。
    - 引用既有反推研究（`game-architect/lineage_calculation.md`、`game-architect/monster_spawning.md` §⑦⑧、`game-architect/mechanisms/case_study_lineage.md`）並自行取值、原創命名；IP 約束見 `game-architect/lineage/ops/legal_ip_risk.md`。
- `AI 遊戲美術生產線`：
    - 業務定位與閱讀路徑見 [game-architect/art_pipeline/README.md](game-architect/art_pipeline/README.md)，生命週期單一事實來源見 [game-architect/art_pipeline/art_pipeline_spec.md](game-architect/art_pipeline/art_pipeline_spec.md)。
    - Phase 1 在本 repo 建立 2D 優先、預渲染 2.5D、逐 gate 人工核准的純文件生產契約；Phase 2 才在外部遊戲引擎 repo 實作 ComfyUI、Blender、sprite/atlas、HUD 與 Godot 實機驗收。
    - 通用 `game-architect/art_pipeline/` 不依賴 `game-architect/lineage/` 專有規則；個案只能單向引用通用生產契約。
- `系統機制設計指南`：
    - 收錄於 `game-architect/mechanisms/` 目錄，索引見 `game-architect/mechanisms/README.md`。
    - 通用、可跨遊戲類型遵循的機制設計框架 + 數值模板：血盟/公會（含血盟小屋）、賭博競賽（賭狗競賽/賠率/RTP）、PVP/攻城戰、道具規劃、怪物數值與生怪規則、場景地圖、任務活動、經濟交易（含消耗登記表）。
    - 採 `薄腰式 (thin-waisted)` 寫法：深度推導交叉引用 `game-architect/guideline.md`、`game-architect/monster_spawning.md` 與同 repo 反推案例，機制檔聚焦可調參數表與公式模板。
