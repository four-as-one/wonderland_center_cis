<!-- 產品／專案：wonderland_center_cis｜法人／事業體：水月道場有限合夥（WonderLand Center）[暫定]；登記狀態與設立沿革 [待確認]｜日期：2026-11-11（Asia/Taipei）｜草稿 v0.3 -->
# wonderland_center_cis
水月道場 / Wonderland Center 官方旗艦入口、CIS 企業形象識別系統
# wonderland-center-corporate (C1-WC-CORP)
> 水月道場 / Wonderland Center 官方旗艦入口、CIS 企業形象識別系統與協同作業規範

---

## 目錄
1. [README.md - 專案導讀與全域架構](#1-readmemd)
2. [CIS_SPECIFICATION.md - 品牌識別與設計規範手冊](#2-cis_specificationmd)
3. [REQUIREMENTS.md - 官網功能與業務需求規格書](#3-requirementsmd)
4. [ARCHITECTURE.md - 技術架構與部署工程指南](#4-architecturemd)
5. [QA-ACCEPTANCE.md - 品質閘門與驗收測試標準](#5-qa-acceptancemd)

---

# 1. README.md

```markdown
# 水月道場 / Wonderland Center（wonderland-center-corporate）

歡迎來到 **水月道場 / Wonderland Center** 官方形象與平台核心門戶之原始碼儲存庫。本專案為「四即一、一即四」全球全域事業體之控制中樞入口與公共門戶。

## 核心定位與願景

> **「水月道場，以幻修真；千江有水千江月，萬里無雲萬里天。」**
> 
> 在科技浪潮與數位時代中，我們運用最前沿的資訊技術投入傳統、轉化傳統、重現人文溫情。水月道場 / Wonderland Center 的法人名稱暫定為「水月道場有限合夥（WonderLand Center）」[暫定]，登記狀態、正式登記名稱與設立沿革 [待確認]；本平台結合「群眾募資（Crowdfunding）」、「群眾發包（Crowdsourcing）」以及「非營利社會公益（Public Good）」的全球協同樞紐。

### 「四即一、一即四」體系定位
- **「一」之核心**：Wonderland Center 作為全域平台經濟的入口，對接全球資源、志工網絡、阿米巴組織與主權級金融資源。
- **「四之四」之落地**：作為直接面向大眾（B2C）的心靈撫慰、生死關懷、公益動員母艦。
- **三大初期群眾倡議**：
  1. **永恆記憶 EternalMemory（C2-WC-DMR）**：讓往生者重現當世（數位記憶重組與思念昇華）
  2. **《安寧緩和醫療條例》預立意願推廣**（健保卡註記與自主善終守護）
  3. **寰宇無界 SeniorTravel（C2-WC-VST；不便出行長者之虛擬旅行陪伴）**（沉浸式跨國走讀與世代共融）

---

## 儲存庫責任範疇

本 Repository（`C1-WC-CORP`）恪遵 PMO 第 00 至 07 號架構原則，承擔以下責任：
1. **官網源碼管理**：以現代前瞻、極簡純淨之視覺呈現水月道場官方網站。
2. **CIS 企業形象真理之源（Single Source of Truth）**：
   - 品牌標準字、標誌幾何圖形、色彩系統規範。
   - 名片、公文信封、投影片簡報母片（Pitch Deck Master）。
   - 官方社群平台（YouTube, X/Twitter, Facebook, LinkedIn）頭版視覺。
   - 官方活動及專題 Hero Pages 視覺指引。
3. **專案與倡議跳轉導流**：作為所有第二類預售（Presale）與公益活動的信任背書母站。
4. **阿米巴志工與點數介接協議入口**：提供遠距/在地志工人力點數轉換系統之公共接入端點。

---

## 角色信箱與治理團隊

依據 PMO 控制體系規範，本專案不以個人私有信箱直接綁定權限，統一部署專案角色 Alias：

| 專案角色 | 角色 Alias 信箱 | 責任邊界 |
| :--- | :--- | :--- |
| **Dev Lead** | `dev-wonderland-center-corporate@wonderland.center` | 前端開發、CI/CD Pipeline、資產打包審查 |
| **Collaborator** | `collab-wonderland-center-corporate@wonderland.center` | 視覺設計師、文案編輯、Crowdsourcing 開發成員 |
| **QA Lead** | `qa-wonderland-center-corporate@wonderland.center` | 執行 7 道 QA 閘門檢驗、驗收測試案例簽核 |
| **Repo Admin** | `admin-wonderland-center-corporate@wonderland.center` | 分支保護（Branch Protection）、存取控制、發布簽署 |

---

## 部署路徑與託管策略

依據 PMO 安全合約，**嚴禁將正式商用入口與牽涉捐款、個資、註記意願之交易系統直接託管於 GitHub Pages**。
- **GitHub Pages**：僅用於內部 UI Review、設計規範展示（Style Guide）及開發者 Preview。
- **正式發布目標**：
  `GitHub Repo` $\rightarrow$ `GitHub Actions` $\rightarrow$ `Azure Static Web Apps (Enterprise Grade)` $\rightarrow$ 自訂網域 `https://wonderland.center`。

---

## 快速啟動

```bash
# 複製儲存庫
git clone https://github.com/wonderland-center/wonderland-center-corporate.git

# 安裝相依套件
cd wonderland-center-corporate
npm install

# 啟動本機預覽伺服器 (包含 CIS Styleguide)
npm run dev

# 執行驗收測試與 Lint 檢查
npm run test:qa
```
```

---

# 2. CIS_SPECIFICATION.md

```markdown
# Wonderland Center 企業形象識別系統（CIS）設計規範手冊

## 1. 品牌哲學與核心意象

- **品牌中文全稱**：水月道場
- **品牌英文全稱**：Wonderland Center
- **品牌核心精神**：**「因願而在，如約而行；虛實相濟，慈悲入世。」**
- **視覺哲學**：
  取「水之至柔、月之清輝、鏡之澄澈、道場之安定」。拋棄傳統宗教場所的沉重或封閉感，融合前瞻科技感（如量子穿透、全同態隱私、光影干涉）與東方人文關懷（澄澈、留白、包容、安詳）。

---

## 2. 色彩系統（Color System）

本識別系統採用科學定義之精確色票，確保在數位介面、印刷物及大圖輸出上具備一致性。

```
+-----------------------------------------------------------------------------+
|                               主要品牌色系                                  |
+---------------------+---------------------+---------------------------------+
|  水月青 (Primary)   |  月光白 (Surface)   |  玄墨黑 (Text/Structure)        |
|  Hex: #0B253A       |  Hex: #F4F7F6       |  Hex: #1A1E24                   |
|  RGB: 11, 37, 58    |  RGB: 244, 247, 246 |  RGB: 26, 30, 36                |
|  Pantone: 539 C     |  Pantone: 656 C     |  Pantone: Black 6 C             |
+---------------------+---------------------+---------------------------------+
|                               輔助與強調色系                                |
+---------------------+---------------------+---------------------------------+
|  澄心金 (Accent)     |  琉璃青 (Sub-Brand) |  願力紫 (Spiritual Sub)         |
|  Hex: #D4AF37       |  Hex: #2A9D8F       |  Hex: #6C5CE7                   |
|  RGB: 212, 175, 55  |  RGB: 42, 157, 143  |  RGB: 108, 92, 231              |
|  Pantone: 7752 C    |  Pantone: 7716 C    |  Pantone: 2095 C                |
+---------------------+---------------------+---------------------------------+
```

### 色彩使用權重比例
- **底色／留白（Surface）**：60%（創造開闊、不壓迫、呼吸自如的心靈場域）
- **結構／內文（Structure）**：30%（玄墨黑與水月青，提供最高閱讀性與穩重信任感）
- **點綴／願力觸發（Accent）**：10%（澄心金用於承諾確認、關鍵行動 CTA、守護標記）

---

## 3. 標誌幾何規範（Logo Construction）

標誌由兩大元素疊合而成：
1. **外環圓融（水月圓環）**：外層為微漸層之無縫圓環，象徵生命的循環、承諾的圓滿，以及全球阿米巴網絡的互聯。
2. **中心結構（雙相水波與晶格光芒）**：
   - 內置如水波漣漪與同態加密晶格相交之數學幾何線條。
   - 代表將心靈願望（往生記憶、預立意願、長者關懷）經由科技結晶妥善封存與重現。

### 安全邊界與最小尺寸
- **安全邊界（Clear Space）**：以 Logo 高度之 $0.5X$ 為周圍禁止任何文字侵入之淨空區。
- **數位介面最小尺寸**：`32px × 32px`（低於此尺寸使用專用單色簡化版 Favicon）。
- **印刷品最小尺寸**：`12mm × 12mm`。

---

## 4. 字體規範（Typography）

### 繁體中文標準字體
- **標題層級（Display/H1/H2）**：思源黑體（Noto Sans TC）Bold / 台灣楷體（特定宣傳語與心靈文案微量點綴）
- **內文層級（Body/P）**：思源黑體（Noto Sans TC）Regular / Light（字距微張 $+0.05em$，行高 $1.75$）
- **程式碼與數據（Code/Data）**：JetBrains Mono / Fira Code

### 英文標準字體
- **標題層級**：Cinzel（展現古典道場莊嚴感）搭配 Inter（展現數位現代感）
- **內文層級**：Inter Regular（高度支援視網膜螢幕與無障礙可讀性）

---

## 5. 實體與數位應用物規範（Applications）

### 5.1 商務名片（Business Card）
- **尺寸**：$90\text{ mm} \times 54\text{ mm}$。
- **紙質指定**：350g 特級凝雪映畫紙或頂級純白棉卡。
- **正面**：
  - 水月青底色，左上角燙「澄心金」Logo 與「水月道場 / Wonderland Center」。
  - 人員姓名（繁體中文 思源黑體 Medium）、職稱。
  - 專屬身分識別 Hash 與對應之二維碼（對接至該成員之驗證頁或公開點數榮譽榜）。
- **背面**：
  - 月光白底色，標示四個角色信箱與官方全球網址。
  - 印製信條：「以科技守護心願，以行動實踐承諾」。

### 5.2 官方公文封與信紙（Stationery）
- **西式 10 號信封**：水月青外封，內襯印有微細防偽水波紋圖騰；封口處預留火漆印章或防拆封籤專用區。
- **A4 公文用紙**：邊界留白不小於 $25\text{ mm}$，頁尾置入合法設立法人資訊、防偽識別碼及支援主權基金專案註記。

### 5.3 簡報母片（Pitch Deck Template - 16:9）
- **封面頁（Cover）**：深色水月青基底，右側配置柔和之水月微光粒子動態或高品質 3D 渲染圖。
- **章節轉場頁（Divider）**：單一精闢文案，例如：「承諾的重量——從願力到實踐」。
- **內容頁（Body Slide）**：月光白底色，玄墨黑內文；嚴格遵循圖表數據視覺化規範，使用澄心金突顯關鍵 KPI。

### 5.4 官方社交平台版面規範
- **Header 規格**：
  - YouTube Banner：`2560 × 1440 px`（安全顯示區域 `1546 × 423 px` 集中在中央）。
  - X (Twitter) Header：`1500 × 500 px`。
  - Facebook Cover：`820 × 312 px`。
- **視覺重心**：中央為水月道場標準字與當季倡議主題，右側呈現阿米巴網絡粒子節點，左側保留呼吸留白空間。

### 5.5 Hero Page 視覺構架
- **首屏三秒原則**：
  - 第一視覺：靜謐而震撼的高清晰水月光影 Canvas 動態渲染。
  - 主標題（H1）：「承諾，是留在人間唯一的真實。」
  - 副標題：「水月道場 / Wonderland Center——結合群眾之力與前瞻科技的全球庇護平台。」
  - 兩大核心按鈕（CTA）：
    1. `[ 探索初始群募倡議 ]`（實心澄心金底，玄墨字）
    2. `[ 加入阿米巴志工發包 ]`（透明水月青邊框，水月青字）
```

---

# 3. REQUIREMENTS.md

```markdown
# Wonderland Center 需求規格書（SRS）

## 1. 系統範疇與業務目標

本系統為 水月道場 / Wonderland Center 之旗艦官方入口（法人名稱暫定為「水月道場有限合夥（WonderLand Center）」[暫定]；登記狀態及設立沿革 [待確認]），需在 2026 年底前完成高可靠性之全球資訊展示、群眾募資專案導覽、群眾發包活動公告，以及全球阿米巴志工資源點數之查詢入口。

---

## 2. 功能需求（Functional Requirements）

### FR-001：官方品牌與法人形象展示
- **FR-001.1**：系統應完整展示 Wonderland Center 之法人設立沿革、使命宣言（Mission）、守諾哲學與願景。
- **FR-001.2**：系統應提供符合 CIS 規範之高解析度資產下載專區（媒體套件 Media Kit、Logo 向量檔、白皮書 PDF）。
- **FR-001.3**：多語系切換支援（初期支援：繁體中文 `zh-TW`、英文 `en-US`、日文 `ja-JP`）。

### FR-002：初始三大公益群募倡議專頁導流（B2C）
- **FR-002.1**：**永恆記憶 EternalMemory（C2-WC-DMR；往生者重現當世）**
  - 介面需以溫暖、莊重且具備科技敬意的方式呈現。
  - 提供預售與需求登記跳轉端點（指向 `wonderland-digital-memory-presale`）。
  - 明確揭示交付期（2027-02-15，Asia/Taipei 日期，依 t12u；交付範圍與履約條件 [待確認]）、隱私權保護邊界（個人生前語音影像資料絕不上公鏈，採受控私密保存）。
- **FR-002.2**：**善終守護 AdvanceCare（C2-WC-ACP；安寧緩和醫療意願註記推廣）**
  - 公益性衛教互動計算器：讓民眾了解預立安寧緩和醫療與器官捐贈註記至健保卡之法定權利與流程。
  - 志願諮詢預約與宣導手冊下載。
  - 導流至 `wonderland-advance-care-directive-presale` 專案頁。
- **FR-002.3**：**虛擬高齡長者旅遊陪伴（Virtual Senior Travel）**
  - 呈現沉浸式虛擬實境（VR/360 影音）陪伴方案介紹。
  - 招募在地陪伴志工與硬體設備贊助方案。
  - 導流至 `wonderland-virtual-senior-travel-presale` 專案頁。

### FR-003：群眾發包與阿米巴志工網絡公告板
- **FR-003.1**：發布即時公益任務（小至剩食運送、偏鄉探視；大至跨國災後重建專案協調）。
- **FR-003.2**：提供志願者登錄表單（串接後端 SharePoint / Power Pages 原子化模組）。
- **FR-003.3**：展示「全域資源點數系統」概念說明（人力點數、計算機資源點數、財務資源週轉透明化模型）。

### FR-004：法規與誠信揭露
- **FR-004.1**：明確揭露台灣個人資料保護法（PDPA）遵循方針與隱私權宣告。
- **FR-004.2**：聲明群眾預售資金隔離專戶託管機制，杜絕「以新單補舊帳」之不正當運作。

---

## 3. 非功能需求（Non-Functional Requirements）

### NFR-001：效能與加載速度
- 在全球主要節點（台灣、日本、北美）之首屏載入時間（LCP - Largest Contentful Paint）需小於 $1.8\text{ 秒}$。
- Google Lighthouse 效能評分需達 90 分以上。

### NFR-002：安全性與合規性（Security & Compliance）
- **SEC-001**：官網全站強制啟用 HTTPS（TLS 1.3），配置嚴格之 HSTS、CSP（Content Security Policy）與 DNSSEC。
- **SEC-002**：官網前端嚴禁收集、暫存任何信用卡號或高敏感病歷資訊；涉及款項之 CTA 必須跳轉至經 PCI-DSS 認證之第三方合規金流端點。

### NFR-003：無障礙體驗（Accessibility）
- 全站符合 W3C WCAG 2.1 AA 級標準，文字與背景之對比度（Contrast Ratio）至少大於 $4.5:1$。
- 提供長者友善模式（一鍵切換大字體與高清晰語音朗讀輔助）。
```

---

# 4. ARCHITECTURE.md

```markdown
# Wonderland Center 系統架構與部署規範

## 1. 總體架構拓撲

```
               [ 使用者瀏覽器 / 行動端 ]
                          │
                          ▼
            [ Azure Front Door / CDN ]
            ( Anycast IP, WAF, TLS 1.3 )
                          │
                          ▼
         [ Azure Static Web Apps (PROD) ]
             Domain: wonderland.center
                          │
     ┌────────────────────┴────────────────────┐
     ▼                                         ▼
[ 靜態資產 (Edge Cache) ]             [ 輕量 API 路由 (Azure Functions) ]
├── 官網靜態頁面 (HTML5/Tailwind)       ├── 聯絡表單送出 (Audit Logged)
├── CIS Style Guide / Media Kit      ├── 志工登記意向接收
└── Hero Interactive Canvas           └── 狀態監控 Ping
                                               │
                                               ▼
                              [ 後端企業控制層 (Microsoft 365) ]
                              ├── SharePoint Global Control
                              ├── Power Automate Flow
                              └── 資源點數管理帳本 (Authoritative DB)
```

---

## 2. 原始碼結構規範

儲存庫必須維持清楚、低耦合之單元結構：

```
wonderland-center-corporate/
├── .github/
│   ├── CODEOWNERS                      # 權責指派檔
│   ├── pull_request_template.md        # PR 規範模板
│   └── workflows/
│       ├── azure-static-web-apps.yml   # 自動建置與佈署
│       └── qa-audit-gate.yml           # CI 自動化測試閘門
├── cis-assets/                         # CIS 數位資產源真理庫
│   ├── logos/                          # SVG / EPS 格式標誌
│   ├── brand-book/                     # CIS 規格手冊原始檔
│   ├── templates/                      # 簡報 (PPTX)、名片 (AI/PDF)、信封
│   └── social-headers/                 # 社群平台 Header 完稿檔
├── public/                             # 靜態外部資源
│   ├── favicon.ico
│   └── robots.txt
├── src/                                # 網站原始碼
│   ├── components/                     # 通用元件 (NavBar, Footer, Hero)
│   ├── layouts/                        # 頁面框架
│   ├── pages/                          # 各路由端點 (Home, About, Initiatives)
│   ├── styles/                         # CSS / Tailwind 樣式規範
│   └── utils/                          # 多語系、無障礙輔助函式
├── tests/                              # QA 驗收測試腳本
│   ├── e2e/                            # Playwright 端對端測試
│   └── visual-regression/              # 視覺比對自動化 (PixelMatch)
├── README.md
├── CIS_SPECIFICATION.md
├── REQUIREMENTS.md
├── ARCHITECTURE.md
├── QA-ACCEPTANCE.md
└── package.json
```

---

## 3. 分支策略與發布流程

嚴格遵循 Trunk-Based Development 配合 Protected Branches 原則：

1. `main` 分支：
   - 僅允許由通過所有 QA Checks 之 Pull Request 合併。
   - 任何 push 直接被拒絕。
   - 自動觸發 Production Pipeline 發布至 Azure Static Web Apps 正式環境。
2. `staging` / `preview` 分支：
   - 用於內部 PMO 與主管同仁進行審查。
   - 可依需求產生 GitHub Pages 或臨時預覽 URL。
3. `feature/*` 與 `fix/*` 分支：
   - 由開發人員或群眾發包協作者切出。
   - PR 審查者必須包含 `@dev-lead` 與 `@qa-lead`。
```

---

# 5. QA-ACCEPTANCE.md

```markdown
# Wonderland Center 品質閘門與驗收測試規範

本儲存庫遵循 PMO 七道品質閘門（7-Gate Quality Governance）流程。任何版本發布前，必須取得相應閘門之驗收確認。

---

## 1. 七道品質閘門定義

```
+---------------+     +---------------+     +---------------+     +---------------+
| Gate 1: Scope | --> | Gate 2: Design| --> | Gate 3: Build | --> | Gate 4: Integ |
+---------------+     +---------------+     +---------------+     +---------------+
                                                                          │
                                                                          ▼
+---------------+     +---------------+     +---------------+     +---------------+
| Gate 7: Post  | <-- | Gate 6: Rel   | <-- | Gate 5: Legal | <───┘
+---------------+     +---------------+     +---------------+
```

| 閘門代號 | 閘門名稱 | 核心查核問題 | 負責審查簽核者 |
| :--- | :--- | :--- | :--- |
| **G1** | **Scope Ready** | 需求是否完整？三大倡議邊界是否清晰？ | PMO / Business Analyst |
| **G2** | **Design Ready**| CIS 規範是否符合？色票、字體、無障礙對比度是否達標？ | Lead Designer / CIS Owner |
| **G3** | **Build Ready** | 程式碼 Lint、Unit Test、TypeScript 型別檢查是否 100% 通過？ | Dev Lead |
| **G4** | **Integration**| 跳轉至三大預售 Repo 與 SharePoint 之連結是否正常？ | Integration Specialist |
| **G5** | **Content/Legal**| 文案是否避開過度承諾？隱私政策與免責聲明是否經法遵核可？| Legal / Compliance Lead |
| **G6** | **Release Ready**| E2E 測試、跨瀏覽器測試、安全掃描（ZAP/SonarQube）是否合規？| QA Lead |
| **G7** | **Post-Release**| 上線後 Smoke Test、全球 CDN 快取與監控通報是否一切運作正常？| DevOps / SRE Lead |

---

## 2. 測試案例矩陣（Test Case Matrix）

| 需求編號 | 測試案例 ID | 驗收項目與驗證步驟 | 預期結果 | 通過門檻 |
| :--- | :--- | :--- | :--- | :--- |
| **FR-001** | `TC-CIS-001` | 驗證首頁 Logo、背景色彩值是否精確符合 `#0B253A` 與 `#F4F7F6`。 | 色彩採樣誤差 $\Delta E < 1.0$。 | 必備 (P0) |
| **FR-001** | `TC-ACC-001` | 執行 Axe-Core 無障礙自動化審計。 | 無任何 Level A/AA 違規項目。 | 必備 (P0) |
| **FR-002.1**| `TC-INIT-001`| 點擊「往生者重現當世」倡議連結。 | 正確導向專案說明與預售頁，且標記預售交付期為 3 個月後。 | 必備 (P0) |
| **FR-002.2**| `TC-INIT-002`| 測試安寧緩和意願健保註記互動流程。 | 能正確引導填寫並給予法定健保署意願書下載指引。 | 必備 (P0) |
| **FR-002.3**| `TC-INIT-003`| 測試虛擬高齡長者旅遊陪伴展示區之影音與 360 預覽。 | 跨桌面與行動瀏覽器皆能流暢播放，不產生記憶體洩漏。 | 建議 (P1) |
| **SEC-001** | `TC-SEC-001` | 驗證全站 HTTPS 強制轉發與 HSTS Header。 | HTTP 請求自動 301 轉至 HTTPS；SSL Labs 評級達 A+。 | 必備 (P0) |
| **SEC-002** | `TC-SEC-002` | 檢查首頁及所有子頁面之原始碼與 Request。 | 絕無直接處理、傳輸信用卡或敏感個人隱私個資之端點。 | 必備 (P0) |

---

## 3. 發布檢查單（Release Sign-off Checklist）

在簽核發布至 `https://wonderland.center` 正式環境前，必須在 PR 內勾選完成：

- [ ] **CIS 一致性確認**：所有社群 Header、Favicon、Hero 頁面符合規範。
- [ ] **多語系核對**：繁中、英文、日文文案校對無脫漏。
- [ ] **三大公益倡議聲明審查**：文案符合台灣法令，明確標明為預售/倡議模式，絕無假募資之嫌。
- [ ] **角色 Alias 寄送測試**：四個角色信箱可正常接收轉寄通知。
- [ ] **QA 閘門 G1-G6 簽核**：由 QA Lead 於 GitHub Pull Request 留言核准。
```


## v0.3 變更註記（2026-11-11，Asia/Taipei）

僅修正本次涉及之品牌顯示名稱、網域文字及與 t12u 直接衝突的法人關係段落；repo／org、技術代碼、URL、路徑、分支及 email local part 均未變更。品牌與網域確認不代表內容核准；本文件為草稿 v0.3，其他來源規格僅供參考，未驗證的功能、效能、時程及合規不得視為核准。

後續 CIS 全面採 PR 流程 [待確認]；本次起實際一律透過 PR，不直接推送 main。

### 人工審核清單

- 完整法定名稱、登記資訊、設立沿革、網域持有人與技術協作／託管契約仍以已確認錨點為限，其他 [待確認] 標註維持。
- 既有版權權利人與授權條款未由本次品牌修訂推定變更；請確認 README 的版權行及 LICENSE 第 189 行 `Copyright [yyyy] [name of copyright owner]` 範本尚未填寫之權利人與年份。
- 保留的技術 URL／徽章／代碼若含歷史文字，並非現行品牌或法人歸屬聲明；如需替換 URL 或改名須另行確認。
- 其餘效能、法遵、交付與產品主張未經核驗，均待人工審核，不因本次修字或 PR 合併視為核准。
