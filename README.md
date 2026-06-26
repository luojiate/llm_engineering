# LLM 工程實戰 — 精通 AI 與大型語言模型

## 你的 8 週精通之旅，從今天開始

![Voyage](assets/voyage.jpg)

_若你在 Cursor 中閱讀，請在左側檔案總管對檔名按右鍵，選擇「Open preview」以檢視排版後的版本。_

很高興你加入這趟旅程。接下來幾週我們會打造許多令人滿足的專案——有的簡單、有的有挑戰性，很多會讓你驚豔！專案彼此銜接，每週都會累積更深的實力。可以肯定的是：一路上會很好玩。

有任何問題，歡迎在 Udemy 上問我，或寄信至 ed@edwarddonner.com。課程資源頁面頂部有[更多說明](https://edwarddonner.com/2024/11/13/llm-engineering-resources/)。

### 開始之前

我會盡力協助你學得最好。若遇到卡關，或對課程有改進建議，請在平台上聯絡我，或直接寄信（ed@edwarddonner.com）。也歡迎在 LinkedIn 上連結，一起壯大社群：  
https://www.linkedin.com/in/eddonner/   

我正在經營 YouTube 頻道，有更多補充內容——[歡迎來看看](https://youtube.com/@edward.donner)。  
另外我也剛開始用 X/Twitter：[@edwarddonner](https://x.com/edwarddonner)——若你也在 X 上，歡迎教教我怎麼玩 😂  

課程配套資源（投影片、實用連結等）在這裡：  
https://edwarddonner.com/2024/11/13/llm-engineering-resources/

可回答常見 FAQ 的數位分身（需要時也會轉給我本人）在這裡：  
https://edwarddonner.com/avatar/

## 第一週第一天的即時成就感 — 使用 Llama 3.2，**不要**用 Llama 3.3

### 重要提醒：請看下方關於 Llama 3.3 的警告——對家用電腦來說太大了！請堅持使用 llama3.2——已有好幾位學生忽略了這點……

我們會先安裝 Ollama，讓你立刻看到成果！
1. 從 https://ollama.com 下載並安裝 Ollama；在 PC 上可能需要管理員權限才能正常安裝
2. PC：開啟命令提示字元 / PowerShell（按 Win + R，輸入 `cmd`，Enter）。Mac：開啟終端機（應用程式 > 工具程式 > 終端機）
3. 執行 `ollama run llama3.2`；若機器較小可試 `ollama run llama3.2:1b`——**請注意**避開 Meta 最新的 llama3.3，70B 參數對多數家用電腦過大！
4. 若不行：在另一個 PowerShell（Windows）或終端機（Mac）執行 `ollama serve`，再重試步驟 3。PC 上可能需要在「以系統管理員身分執行」的 PowerShell 中操作
5. 若本機仍無法使用，我已放在雲端。這是 Google Colab，需 Google 帳號登入，但免費：https://colab.research.google.com/drive/1-_f5XZPsChvfU1sJ0QqCePtIuc55LSdu?usp=sharing

有任何問題，請聯絡我！

## 正式安裝說明之前 — 特別說明

課程早期（第二天）我會示範 Claude Code——一款很酷的 AI 程式工具，類似本課程使用的 Cursor。那只是代理式 AI 的範例；本課程不會深入教這套工具，尤其我們用的是 Cursor。若你想自行使用 Claude Code，Anthropic 的快速入門在[這裡](https://docs.claude.com/en/docs/claude-code/quickstart)。

## 好 — 進入安裝說明

完成 Ollama 快速專案、聽完自我介紹與課程概覽後，我們會進行完整環境設定。

希望這些指南夠穩——若仍卡關，請立刻聯絡我：

安裝說明：[各平台安裝說明](setup/SETUP-new.md)

### 關於 API 費用（可選！不想花錢也完全沒問題）

課程中我會建議你試用處於 AI 最前沿的領先模型（Frontier models），也會建議用 Google Colab 跑開源模型。這些服務會收費，但我會把成本壓到很低——例如每次幾美分。若不想用，我也會提供替代方案。

請監控 API 用量，確保支出在你可接受範圍；下方有連結。整門課不必花超過幾美元。部分供應商（如 OpenAI）可能要求最低儲值（例如 \$5 或當地等值）；我們只會用到其中一小部分，剩餘額度還能用在個人專案。第七週若玩得很開心，可以選擇多花一點——我自己大約花 \$10，結果很滿意！但完全非必要；重點是學習。

### 付費 API 的免費替代方案

詳見 guides 目錄的[指南 9](guides/09_ai_apis_and_ollama.ipynb)，內含 Ollama、Gemini、OpenRouter 等的具體程式碼。

### 本 Repo 的組織方式

依「週」分資料夾，對應課程模組，最後在第八週整合成強大的自主代理式 AI 方案，會用到前面多週的內容。  
請先完成上方安裝，再開啟 Week 1 資料夾，準備享受吧。

### 最重要的一點

課程口訣：**動手做**才是最好學法。課上我不會邊打程式邊讓你看；我會執行給你看結果。請跟著我做，或在每堂課後自己跑每個儲存格、檢查物件，真正理解發生了什麼。然後改程式、變成你的版本。課程中有很多值得挑戰的練習。若願意用 Pull Request 分享你的程式（見 guides 裡的 GitHub 指南），我可以讓其他人看到你的成果；你也會在 GitHub 上被記名感謝。專案好玩，但首要目的是**教學**，讓你學到能用在工作上的商業技能。

## 從第三週起，我們也會用 Google Colab 跑 GPU

用免費方案或極少支出，應能完成所有專案。我個人訂了 Colab Pro+，很滿意——但非必要。

了解 Google Colab、建立 Google 帳號（若還沒有）[點這裡](https://colab.research.google.com/)

Colab 連結在 Week 3 與 Week 7 資料夾——打開每天的 lab 即可看到直接連結。

### 監控 API 費用

整門課 API 支出可以很低；可在儀表板監控：OpenAI [這裡](https://platform.openai.com/usage)，Anthropic [這裡](https://console.anthropic.com/settings/cost)。

本課練習費用通常很低；若想壓到最低，請一律選最便宜的模型：
1. OpenAI：程式中一律用 `gpt-4.1-nano`
2. Anthropic：一律用 `claude-3-haiku-20240307`，不要用其他 Claude 型號
3. 第七週留意我關於使用較便宜資料集的說明

若仍有問題或需要協助，請訊息或寄信 ed@edwarddonner.com。很期待聽到你的進展！

<table style="margin: 0; text-align: left;">
    <tr>
        <td style="width: 150px; height: 150px; vertical-align: middle;">
            <img src="assets/resources.jpg" width="150" height="150" style="display: block;" />
        </td>
        <td>
            <h2 style="color:#f71;">其他資源</h2>
            <span style="color:#f71;">我整理了這個網頁，彙整課程實用資源，包含所有投影片連結。<br/>
            <a href="https://edwarddonner.com/2024/11/13/llm-engineering-resources/">https://edwarddonner.com/2024/11/13/llm-engineering-resources/</a><br/>
            請加入書籤，我會持續補充連結。
            </span>
        </td>
    </tr>
</table>
