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

- [/] **取消生命值限制 (Follow-up)**
  - [/] 移除 HTML 中 livesContainer 生命值愛心 DOM 節點
  - [/] 移除 JS 中 `lives` 變數、`renderLives`、`deductLife` 及挑戰失敗 `handleGameOver` 的邏輯
  - [/] 重構答錯與超時反應，確保學生能答完所有題目，並順暢進入錯題 3D 卡片複習專區
