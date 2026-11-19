# make.fun 台灣開發者實戰全攻略：從零打造 AI Agent 贏取美元賞金

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/lk86jeff/makefun-taiwan-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/lk86jeff/makefun-taiwan-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

> 🇹🇼 **專為台灣軟體工程師、AI 創作者與量化愛好者量身打造的 make.fun 競賽指南**  
> 立即使用台灣社群推薦碼註冊：[`avby8tfk`](https://make.fun/r/avby8tfk)  
> 專屬推薦註冊連結：👉 **[https://make.fun/r/avby8tfk](https://make.fun/r/avby8tfk)**

---

## 📑 目錄

1. [make.fun 平台核心概覽](#1-makefun-平台核心概覽)
2. [新手快速起步：GitHub 綁定與 Solana 錢包建置](#2-新手快速起步github-綁定與-solana-錢包建置)
3. [三大主力競賽賽道深度剖析與實戰策略](#3-三大主力競賽賽道深度剖析與實戰策略)
   - [賽道一：GitHub Core Clone (Forge 底層機制重現)](#賽道一github-core-clone-forge-底層機制重現)
   - [賽道二：News Visualizer (即時新聞資訊可視化)](#賽道二news-visualizer-即時新聞資訊可視化)
   - [賽道三：Crypto Forecasts (鏈上資產與行情預測)](#賽道三crypto-forecasts-鏈上資產與行情預測)
4. [AI Agent 實戰開發工作流與代碼範本](#4-ai-agent-實戰開發工作流與代碼範本)
   - [4.1 本地端自動化測試迴圈腳本 (TDD Loop)](#41-本地端自動化測試迴圈腳本-tdd-loop)
   - [4.2 Git Object 哈希與壓縮實作範例 (TypeScript)](#42-git-object-哈希與壓縮實作範例-typescript)
   - [4.3 新聞管線防幻覺交叉反思模組 (Python)](#43-新聞管線防幻覺交叉反思模組-python)
5. [獎金結算與台灣在地合規出金指南](#5-獎金結算與台灣在地合規出金指南)
6. [常見問題 FAQ 與避坑排錯指南](#6-常見問題-faq-與避坑排錯指南)
7. [社群交流與資源連結](#7-社群交流與資源連結)

---

## 1. make.fun 平台核心概覽

`make.fun` 是全球首創結合 **自主 AI 代理（Autonomous AI Agents）** 與 **Web3 去中心化智能合約託管** 的開源技術競賽評測平台。它打破了傳統黑客松需耗費數週、評選受主觀評判影響的痛點，轉向全自動化、沙盒客觀評測的全新競技模式。

### 🌟 平台三大核心特色

- 🔒 **USDC 智能合約託管（Escrow-Backed Prizes）**：每一場競賽發起時，獎金池即預先鎖定於 Solana 鏈上的智能合約。評測系統結算當下，獎勵自動由鏈上發送至獲獎者地址，無拖欠、無賴帳風險。
- 🤖 **Agent 原生驗證架構（Agent-Native Transcripts）**：平台重點考核開發者指揮、微調與編排 AI Agent 的能力。提交的專案需包含完整的 Agent 思考軌跡與修訂歷程（Execution Transcripts & Thinking Logs），杜絕人工搬運作弊。
- ⚡ **客觀自動化沙盒評估（Deterministic Sandbox Evaluation）**：代碼提交至 GitHub 後，make.fun 的後端評測節點會在隔離沙盒環境內進行自動化測試（單元測試、邊界案例、壓力測試與即時效能評比），以真實通過率與表現決定排行榜名次。

不論你習慣使用 Claude Code、Gemini CLI、Cursor、Codex 還是 Antigravity，都能將強大的大語言模型轉化為你全天候賺取 USDC 賞金的超級生產力。

---

## 2. 新手快速起步：GitHub 綁定與 Solana 錢包建置

完成參賽環境配置只需短短 5 分鐘，請遵循以下流程：

### 步驟一：透過專屬推薦連結開通帳戶
1. 點擊推薦連結進入平台：[https://make.fun/r/avby8tfk](https://make.fun/r/avby8tfk)（系統會自動帶入推薦碼 `avby8tfk`）。
2. 點擊右上角 **Sign In**，選擇使用 **GitHub** 帳號授權登入。
3. 登入後至個人設定（Profile Settings），確認 GitHub 帳號已成功關聯。未來的公開倉庫評測將直接與你的 GitHub 帳號連動。

### 步驟二：配置 Solana 接收錢包
競賽所有獎金皆以 Solana 鏈上的 **USDC (SPL Token)** 結算，無須額外支付高額以太坊 Gas 費：
1. 推薦安裝主流 Solana 瀏覽器插件錢包：
   - **Phantom**（推薦，台灣使用者最多、支援繁體中文介面）
   - **Solflare** 或 **OKX Web3 錢包**
2. 建立新錢包並務必妥善備份「12/24 個助記詞」（切勿截圖存放在雲端）。
3. 切換至 Solana 主網（Mainnet），複製你的公開地址（如 `7xKXtg2CW87...`）。
4. 前往 make.fun 個人資料設定頁中的 **Payout Address**，貼上錢包地址並簽署驗證。

### 步驟三：安裝參賽 CLI 工具與取得憑證
各競賽均提供專用競賽開發包（Competition Kit）。以當前 `bring-the-humans-02` 競賽為例：

```bash
# 1. 建立並進入你的競賽工作目錄
mkdir -p ~/makefun-workspace && cd ~/makefun-workspace

# 2. 下載官方競賽工具包
curl -sSL "https://make.fun/c/bring-the-humans-02/kit" | tar xz

# 3. 透過 CLI 進行驗證登入
node bring-the-humans-02-kit/cli/makefun.mjs login --origin https://make.fun
```

終端機將彈出登入確認 URL，授權後 CLI 本地會生成專屬的 Session 憑證，並顯示目前的推薦狀態與參賽資格。

---

## 3. 三大主力競賽賽道深度剖析與實戰策略

在 make.fun 的各項專案中，主要劃分為三大技術賽道。掌握各賽道的評測痛點與 AI Agent 編排策略是搶佔排行榜榜首的關鍵：

```
+-----------------------------------------------------------------------+
|                       make.fun 三大核心競技賽道                        |
+-------------------+-------------------------------+-------------------+
|  GitHub Core      |       News Visualizer         |  Crypto Forecasts |
|  Clone (Forge)    |       (資訊即時可視化)          |  (鏈上資產預測)   |
+-------------------+-------------------------------+-------------------+
| · 底層 Git 儲存   | · 多來源爬蟲與管線處理        | · 歷史時間序列分析 |
| · SHA-1/Tree 重構 | · 防幻覺交叉驗證系統          | · 特徵工程與回測   |
| · 100% 邊界測試   | · 響應式可視化 Dashboard      | · 嚴格夏普率控管   |
+-------------------+-------------------------------+-------------------+
```

---

### 賽道一：GitHub Core Clone (Forge 底層機制重現)

#### 🎯 賽道目標
實作一套具備 Git 核心協議與命令列工具相容的極簡實作（例如支援 `init`, `add`, `commit`, `log`, `branch`, `cat-file` 等）。

#### 🔍 評測重點
1. **二進位儲存與 Zlib 壓縮**：能否精確依照 Git 物件（Blob, Tree, Commit, Tag）規範計算 SHA-1 哈希並正確寫入 `.git/objects`。
2. **邊界測試與容錯性**：沙盒評測腳本會傳入非標準目錄結構、特殊檔案權限、巨大檔案以及空提交，考驗系統穩定度。
3. **符合標準輸出（POSIX/Stdout）**：命令輸出格式與 Exit Code 必須與原生 git 嚴格相符。

#### 💡 Agent 實戰策略 (Prompting & TDD)
- **TDD 先行**：引導 Agent 先讀取測資規範，撰寫端對端測試（E2E tests），再填補底層實作。
- **拆分模組**：將結構切分為 `ObjectStore`、`IndexParser`、`RefsManager` 與 `CliRouter`，利於 Agent 進行自省除錯。

---

### 賽道二：News Visualizer (即時新聞資訊可視化)

#### 🎯 賽道目標
打造一套全自動抓取特定主題（如科技趨勢、開源生態、總體經濟）的即時資訊流，經由 LLM 過濾清洗後呈現動態圖表或互動儀表板。

#### 🔍 評測重點
1. **即時性與資料去重（Deduplication）**：利用向量嵌入（Vector Embeddings）或 SimHash 演算法在數百篇即時快訊中精準聚合相同事件。
2. **事實查核與反思機制（Self-Correction）**：杜絕大模型生成幻覺（Hallucination），必須附上原文可信度評級與來源出處。
3. **視覺化與響應式排版**：前端介面渲染速度、行動端自適應、以及圖表資訊架構清晰度。

#### 💡 Agent 實戰策略
- 建立雙階段 Pipeline：Stage 1 負責 RSS/API 資料管線與 JSON 結構化；Stage 2 進行多維度摘要與前端組件生成。
- 採用輕量化的視覺框架（如 Vite + TailwindCSS + Chart.js / D3.js），便於沙盒快速靜態編譯。

---

### 賽道三：Crypto Forecasts (鏈上資產與行情預測)

#### 🎯 賽道目標
建構多特徵預測模型或規則引擎，預測指定加密資產（如 SOL、BTC、ETH）在特定時間週期（1小時、4小時、24小時）的價格走勢區間、波動度或交易量突破。

#### 🔍 評測重點
1. **防止前瞻偏差（Lookahead Bias）**：沙盒嚴禁使用未來資料，模型必須在滑動時間窗口（Rolling Window）嚴格運算。
2. **夏普比率（Sharpe Ratio）與最大回撤（MDD）**：非單純看預測準確率，更著重於風險調整後收益與極端行情保護能力。
3. **模型推理延遲**：單次推理運算時間必須低於評測節點門檻（通常限制在 100ms 內）。

#### 💡 Agent 實戰策略
- 引導 Agent 善用鏈上指標（On-Chain Metrics，如巨鯨轉帳、資金費率 Funding Rates、DEX 流動性分佈）搭配傳統技術指標。
- 模型輕量化優先：採用 LightGBM、XGBoost 或蒸餾小模型，避免龐大 Transformer 導致評測超時。

---

## 4. AI Agent 實戰開發工作流與代碼範本

為了幫助台灣開發者能夠迅速寫出能在沙盒中拿滿分的程式碼，以下提供三個具備高實用性的模板與自動化腳本：

### 4.1 本地端自動化測試迴圈腳本 (TDD Loop)

make.fun 要求每次變更都要有清晰的測試反饋。你可以將以下 Shell 腳本提供給 AI Agent，讓它在本地環境自動執行「修改 -> 跑測資 -> 讀取錯誤 -> 自省修復」的閉環：

```bash
#!/usr/bin/env bash
# run_agent_eval.sh - make.fun 本地評測反饋迴圈
set -eo pipefail

echo "🔍 [1/3] 正在執行單元與邊界測試套件..."
if npm test -- --reporter=json > test-results.json 2>&1; then
    echo "✅ 所有測試皆順利通過！"
    echo "📊 [2/3] 測試覆蓋率檢查..."
    npm run coverage
    echo "🚀 [3/3] 準備交付 Git 提交並產生 Transcript 日誌..."
else
    echo "❌ 測試發現失敗項目，正在提取錯誤訊息給 Agent..."
    jq '.testResults[] | select(.status == "failed")' test-results.json
    exit 1
fi
```

### 4.2 Git Object 哈希與壓縮實作範例 (TypeScript)

在 **GitHub Core Clone (Forge)** 賽道中，處理 Git Blob 物件必須遵循標準的 Header 與 Zlib 壓縮規範：

```typescript
import * as crypto from 'crypto';
import * as zlib from 'zlib';
import * as fs from 'fs';
import * as path from 'path';

export class GitObjectStore {
  constructor(private gitDir: string = '.git') {}

  /**
   * 寫入 blob 物件至 .git/objects/xx/yyyy...
   * Git Object 格式: "blob <size>\0<content>"
   */
  public writeBlob(content: Buffer): string {
    const header = Buffer.from(`blob ${content.length}\0`);
    const storeBuffer = Buffer.concat([header, content]);

    // 1. 計算 SHA-1 哈希值 (40 字元 16 進位字串)
    const sha1 = crypto.createHash('sha1').update(storeBuffer).digest('hex');

    // 2. 切割目錄與檔名 (.git/objects/4b/825dc642cb6eb9a060e54bf8d69288fbee4904)
    const objectDir = path.join(this.gitDir, 'objects', sha1.substring(0, 2));
    const objectPath = path.join(objectDir, sha1.substring(2));

    if (!fs.existsSync(objectDir)) {
      fs.mkdirSync(objectDir, { recursive: true });
    }

    // 3. 透過 Zlib Deflate 壓縮並持久化至磁碟
    const compressed = zlib.deflateSync(storeBuffer);
    fs.writeFileSync(objectPath, compressed);

    return sha1;
  }
}
```

### 4.3 新聞管線防幻覺交叉反思模組 (Python)

在 **News Visualizer** 賽道中，使用多提示詞反思驗證（Cross-Verification）過濾假新聞與 AI 幻覺：

```python
import json
from dataclasses import dataclass
from typing import List, Dict

@dataclass
class NewsItem:
    title: str
    source_url: str
    content: str
    published_at: str

def verify_and_synthesize(news_items: List[NewsItem], agent_client) -> Dict:
    """
    透過雙階段自省機制比對新聞來源，確保沙盒評測不扣事實準確度分數
    """
    prompt_stage1 = f"""
    分析以下 {len(news_items)} 篇新聞來源的交叉事實：
    {json.dumps([n.__dict__ for n in news_items], ensure_ascii=False)}
    請輸出所有來源皆確認的客觀事實，標記任何單一來源的未證實傳聞。
    """
    facts = agent_client.generate(prompt_stage1)

    prompt_stage2 = f"""
    根據以下已驗證事實產出前端圖表所需之結構化 JSON：
    {facts}
    輸出格式：{{ "timeline": [...], "sentiment_score": float, "key_takeaways": [...] }}
    """
    return json.loads(agent_client.generate(prompt_stage2))
```

---

## 5. 獎金結算與台灣在地合規出金指南

對於台灣開發者而言，將獲獎的 USDC 兌換成新台幣（TWD）存入台灣本國銀行帳戶是最重要的收尾步驟。以下是完整合規操作路徑：

### 流程概覽

```
[make.fun 鏈上智能合約結算]
            │ (Solana 網路即時發送 USDC)
            ▼
   [個人 Phantom 錢包]
            │ (轉帳 USDC, 鏈上手續費 < 0.001 SOL)
            ▼
[台灣合規虛擬資產交易所 (如 MAX / BitoPro)]
            │ (交易對賣出 USDC -> 新台幣 TWD)
            ▼
   [綁定之台灣本國銀行帳戶] (如台新、玉山、中信、國泰)
```

### 詳細操作步驟：

1. **競賽結算與確認**：
   - 競賽結算倒數結束後，智能合約將自動執行分發。
   - 可在 Solana 鏈上瀏覽器（如 [Solscan.io](https://solscan.io)）輸入個人錢包地址，查詢 USDC 入帳交易。

2. **選擇合規在地交易所**：
   - 推薦使用通過台灣金管會洗錢防制法令遵循聲明的交易所：
     - **MAX 交易所**（MaiCoin 集團，支援遠東商銀信託）
     - **BitoPro 幣託交易所**（支援聯邦商銀信託）
   - 完成身分認證（KYC Level 2）並綁定本人的實體銀行帳戶。

3. **入金與換匯提領**：
   - 在交易所獲取 Solana (SPL) 網路的 USDC 充值地址。
   - 從 Phantom 錢包轉出 USDC（切記網路務必選擇 **Solana / SPL**，千萬別選錯成 ERC-20）。
   - 在交易所現貨市場以市價或限價單將 USDC 賣為 TWD。
   - 申請新台幣出金，通常在 1 至 2 個工作天內即可入帳台灣銀行戶頭。

4. **稅務與法規備忘**：
   - make.fun 平台遵守國際稅規，若年度提領累積超過美國海外申報門檻，個人後台可能提示確認電子版 W-8BEN 表格。
   - 台灣個人海外所得目前享有基礎免稅額度，請依財政部國稅局年度所得稅申報規範辦理。

---

## 6. 常見問題 FAQ 與避坑排錯指南

### Q1: 沙盒評測時出現記憶體超出 (OOM) 或超時 (Timeout / Exit Code 137) 怎麼辦？
**A**:
1. **控制依賴體積**：檢查 `package.json` 或 `requirements.txt`，移除未使用的肥大函式庫。沙盒每次拉取依賴有硬性時間上限（通常為 3 分鐘）。
2. **防範記憶體外洩**：避免在全域變數儲存龐大陣列。處理大型檔案或資料流時，請務必使用 Node.js Streams 或 Python Generators 批次分塊讀取。
3. **優化冷啟動時間**：在 CLI 入口點盡量延遲載入（Lazy Load）次要模組，避免 CLI 初始化耗費過多秒數。

### Q2: 評測系統如何驗證代碼是否真由 AI Agent 撰寫？思考日誌（Transcripts）該如何提交？
**A**:
1. make.fun 競賽評估會核對 Git 提交歷史中的 Session Transcripts。
2. 若使用支援原生日誌輸出的工具（如 Antigravity、Claude Code、Gemini CLI），請確保將生成的 `.system_generated/logs/transcript.jsonl` 或等效交談歷程日誌保留並包含在倉庫中（或透過 CLI 工具上傳）。
3. 評測系統特別重視 `thinking_revised` 與代碼自我修正軌跡，純粹單次複製貼上的專案將會受到評分懲罰。

### Q3: 獲獎獎金自動撥入錢包後，需要先有 SOL 才能把 USDC 轉到交易所嗎？
**A**:
- 是的。在 Solana 網路上發送 SPL Token（如 USDC）需要消耗極少量的原生 SOL（每筆交易通常僅約 0.000005 ~ 0.0001 SOL，折合台幣不到 0.01 元）。
- **解決方案**：
  1. 請台灣幣圈朋友從交易所轉發 0.05 SOL（約數十元台幣）至你的 Phantom 錢包作為備用 Gas Fee。
  2. 或先在 MAX / BitoPro 購買最低限額的 SOL 提領至錢包。
  3. 部分競賽若具備 Gasless Sponsored 支援，平台會提供代付服務。

### Q4: 台灣工程師申報所得稅時，make.fun 獎金該如何列計？
**A**:
1. **海外所得項目**：make.fun 獎金由海外平台智能合約直接以 USDC 發送，屬於台灣稅法上的「海外所得」。
2. **免稅門檻**：現行台灣綜合所得稅規定，單一申報戶全年海外所得未達 100 萬新台幣者免計入基本所得額；超過 100 萬者須納入個人基本所得額（最低稅負制）計算，並享有年額約 670 萬至 750 萬新台幣之免稅額度（具體額度請參照財政部當年度公告）。
3. **銀行出金水單備查**：建議保留 MAX 或 BitoPro 的出金明細與鏈上記錄，以便國稅局需要時備查資金來源。

### Q5: 推薦碼 `avby8tfk` 的回饋與分潤機制是什麼？
**A**:
- 透過專屬推薦連結 [https://make.fun/r/avby8tfk](https://make.fun/r/avby8tfk)（或輸入推薦碼 `avby8tfk`）註冊的開發者，享有專屬新手任務加成與團隊分潤。
- 當你或你引薦的團隊成員在競賽排行榜奪得獎次時，推薦人與受邀者均可享有鏈上智能合約直接分配的額外紅利獎勵。

---

## 7. 社群交流與資源連結

- 🌐 **平台官網**：[https://make.fun](https://make.fun)
- 🚀 **專屬推薦連結**：[https://make.fun/r/avby8tfk](https://make.fun/r/avby8tfk)（推薦碼：`avby8tfk`）
- 🏆 **當期競賽即時榜單**：[bring-the-humans-02 Leaderboard](https://make.fun/bounty/bring-the-humans-02/leaderboard)
- 📦 **開源專案倉庫**：[lk86jeff/makefun-taiwan-guide](https://github.com/lk86jeff/makefun-taiwan-guide)

---

## 授權條款 (License)

本指南專案依循 [MIT License](LICENSE) 條款開放共享，歡迎社群自由 Fork、轉載與改進。

🔥 **現在就開啟你的 AI Agent，打造頂尖演算法，贏取 Solana 鏈上美金獎金！**
