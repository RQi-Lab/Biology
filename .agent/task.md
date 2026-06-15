# 任務清單：光合作用小測驗高互動性與遊戲化升級

- [x] **階段 1：編寫與整合 CSS 樣式**
  - [x] 撰寫生命值與破碎/縮小動畫 CSS (`.heart-container`, `.heart`, `@keyframes heart-break`)
  - [x] 撰寫計時器進度條與紅色警告閃爍 CSS (`.timer-bar`, `.timer-fill`, `@keyframes pulse-red`)
  - [x] 撰寫答錯震動特效 CSS (`.shake`, `@keyframes shake`)
  - [x] 撰寫答對時的微型拋射粒子 CSS (`.particle`)
  - [x] 撰寫分類題與排序題操作區 CSS (`.classify-quiz`, `.basket`, `.draggable`, `.order-quiz`, `.order-item`)
  - [x] 撰寫玻璃擬態發光成就徽章 CSS (`.badge-container`, `.badge`, `@keyframes float`)
  - [x] 撰寫 3D 卡片翻轉複習專區 CSS (`.flashcard-wrapper`, `.flashcard`, `.flashcard-front`, `.flashcard-back`)

- [x] **階段 2：重構 HTML 測驗容器結構**
  - [x] 在 `#quizProgress` 中加入生命值區與倒數計時進度條
  - [x] 調整 `#quizContainer` 用於渲染各種動態交互介面
  - [x] 調整結束後的計分與成果展示區 `#scorePanel`，加入徽章掛載點與「錯題複習區」掛載點

- [x] **階段 3：重構 JS 測驗控制引擎**
  - [x] 擴充 `questions` 資料，新增並擴充至 10 道「單選、分類與排序」題目
  - [x] 建立 `QuizState` 控制狀態（生命值 3、題限時 15 秒、錯題記錄陣列）
  - [x] 實作倒數計時功能（`startTimer`、`stopTimer`、`updateTimerDisplay`、超時懲罰）
  - [x] 實作生命值扣減與心碎效果（`deductLife`、`renderLives`）
  - [x] 實作答錯觸發震動動畫及答對觸發粒子噴灑效果（`triggerShake`、`triggerParticles`）
  - [x] 實作各題型專屬渲染與交互邏輯：
    * [x] 單選題：限時答題、選項 disable、正確答案與解析呈現
    * [x] 分類題：點擊/拖放分類、籃子縮放微動畫、確認提交與答案判定
    * [x] 排序題：「上移/下移」即時重排、確認提交與答案判定
  - [x] 實作計分面板升級：
    * [x] 玻璃擬態徽章動態頒發與浮動特效
    * [x] 完美通關時加強綠葉灑落慶祝動畫
  - [x] 實作 3D 翻轉錯題複習系統：
    * [x] 動態生成錯題的 3D 卡片，正面為錯答，背面為正確答案與詳細科學解析
    * [x] 綁定點擊 3D 翻轉事件

- [x] **階段 4：整體測試與品質驗證**
  - [x] 驗證答題計時歸零時，正確扣心並顯示解析
  - [x] 驗證心扣完時，流暢切換到「挑戰失敗」畫面，並能按「重新挑戰」復原
  - [x] 驗證分類題與排序題操作體驗與判定正確性
  - [x] 驗證 3D 卡片翻轉效果無穿透與重疊
  - [x] 確保代碼中所有註解詳細、文字為正體中文、檔案使用 UTF-8 編碼

- [x] **隨機抽題與大題庫擴充 (Follow-up)**
  - [x] 擴充大題庫 (MASTER_QUESTIONS) 至 14 道高水準生物題型
  - [x] 實作重新測驗時的隨機抽取 6 題機制，增加每次重新測驗的新鮮感與多樣性
  - [x] 於計分結算面板中新增「隨機新題目」引導文字與提示

- [x] **將隨機抽題數調整為 8 題 (Follow-up)**
  - [x] 修改 HTML 中的進度列與計分面板的靜態題數由 5 題改為 8 題，與動態載入完全同步
  - [x] 修改 JS 中的 `getRandomQuestions` 預設題數與實際呼叫參數，將隨機抽選題數由 6 題改為 8 題
  - [x] 修改代碼內的所有中文註解，將 6 題改為 8 題

- [x] **停用倒數計時功能 (Follow-up)**
  - [x] 在 HTML 中將 `timer-container` 改為 `style="display: none;"` 進行隱藏
  - [x] 修改 JS 中的 `startTimer` 函數使其不啟動倒數邏輯，避免任何超時判定
  - [x] 更新 `index.html` 及相關代理文件的註解與說明

- [x] **取消生命值限制 (Follow-up)**
  - [x] 修改 `deductLife` 函數，答錯時僅觸發左右震動回饋，不再扣減生命值與判定失敗
  - [x] 確保學生不論答對答錯皆可完成所有題目，並順利進入錯題 3D 卡片複習專區

- [x] **移除未教學項目 RuBisCO (Follow-up)**
  - [x] 移除主畫面的「三大階段」中關於 RuBisCO 酵素的文字描述
  - [x] 移除「卡爾文循環」展開說明中關於 RuBisCO 的說明
  - [x] 將小測驗中考 RuBisCO 的單選題替換為「ATP 與 NADPH 的能量消耗路徑」
  - [x] 修改測驗中關於葉綠體分工的題目，移除選項中的 RuBisCO 關鍵字
  - [x] 更新 `walkthrough.md` 文件以同步最新題型描述

- [x] **移除未教學項目 G3P, RuBP, 3-PGA (Follow-up)**
  - [x] 移除主畫面簡介與「三大階段」中關於 G3P 的專有名詞
  - [x] 移除「卡爾文循環」與「葡萄糖合成」詳細展開說明中關於 G3P, RuBP, 3-PGA 的縮寫，替換為三碳醣、五碳化合物等通稱
  - [x] 調整小測驗第 6 題單選題，將其考法簡化為「卡爾文循環生成的直接有機產物」（三碳糖）
  - [x] 簡化小測驗第 13 題步驟排序題的文字說明，移除專有名詞縮寫
  - [x] 更新 `walkthrough.md` 的考題摘要以符合更新後的題目描述
