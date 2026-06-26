# LLM Engineering - 精通 AI 與 LLM

## PC、Mac 與 Linux 安裝說明

_若你在 Cursor 中閱讀此檔，請在左側 Explorer 對檔名右鍵，選擇「Open preview」以查看格式化版本。_

歡迎，未來的 LLM 工程師！

我得先坦白：要搭建一個能在 AI 前沿工作的強大環境，並不如我希望的那麼簡單。對多數人來說，這些步驟會很順利；但在某些情況下，你仍可能遇到問題。請隨時聯絡我——我會盡快幫你跑起來。沒有什麼比感到 _卡住_ 更糟的了。在 Udemy 傳訊息或寄信給我，我會很快幫你解困！

Email：ed@edwarddonner.com  
LinkedIn：https://www.linkedin.com/in/eddonner/  

## 步驟 0 - 開始之前 - 處理讓許多人栽跟頭的「陷阱」

別忽略這一節！我收到的安裝問題中，約 80% 都能用這些常見的系統問題解決。

1. PC 使用者：權限。請閱讀這篇關於 Windows 權限的 [教學](https://chatgpt.com/share/67b0ae58-d1a8-8012-82ca-74762b0408b0)。若你遇到沒有權限／無法執行腳本或安裝軟體的錯誤，請先看這篇。ChatGPT 能詳細說明 Windows 上的權限設定。

2. 防毒軟體、防火牆、VPN。這些可能干擾安裝與網路連線；必要時可暫時關閉。用手機熱點測試，可判斷是否為網路問題。

3. PC 使用者：Windows 惡名昭彰的 260 字元檔名長度限制——完整 [說明與修復](https://chatgpt.com/share/67b0afb9-1b60-8012-a9f7-f968a5a910c7)！

4. PC 使用者：若你先前未在電腦上使用過 Data Science 套件，可能需要安裝 Microsoft Build Tools。請參考 [說明](https://chatgpt.com/share/67b0b762-327c-8012-b809-b4ec3b9e7be0)。也有學員提到 [這份說明](https://github.com/bycloudai/InstallVSBuildToolsWindows) 對 Windows 11 使用者很有幫助。

5. Mac 使用者：若你剛開始在 Mac 上開發，可能需要安裝 XCode developer tools。請參考 [說明](https://chatgpt.com/share/67b0b8d7-8eec-8012-9a37-6973b9db11f5)。

6. 企業資安造成的 SSL 與其他網路問題：若遇到 SSL 問題（例如 API 連線錯誤、憑證錯誤，或從 Ollama 下載檔案時出現 Cloudflare 錯誤），請參閱 [此處](https://edwarddonner.com/faq) 的 Q15。

## 步驟 1 - 安裝 git、建立 projects 目錄、安裝 Cursor

這是唯一一節 PC 與 Mac/Linux 步驟分開寫的部分！請選擇你的章節，完成後再進入步驟 2……

___

**步驟 1（PC 使用者）：**

1. **安裝 Git**（若尚未安裝）：

- 開啟新的 Powershell（開始選單 >> Powershell）。若遇到權限錯誤，可右鍵選擇「以系統管理員身分執行」
- 執行 `git`，確認會顯示指令說明或錯誤訊息
- 若出現錯誤，從 https://git-scm.com/download/win 下載 Git
- 執行安裝程式並依提示操作，使用預設選項（一直按 OK 即可！）

2. **視需要建立 projects 目錄**

- 開啟新的 Powershell，如前述。你應在使用者主目錄，例如 `C:\Users\YourUserName`
- 是否已有 projects 目錄？輸入 `cd projects` 確認
- 若出現錯誤，建立目錄：`mkdir projects`，然後 `cd projects`
- 現在應在 `C:\Users\YourUserName\projects`
- 可放在任何方便的位置，但避免 OneDrive 同步的目錄

3. **執行 git clone：**

在 `projects` 資料夾的命令提示字元中執行下方 clone 指令。若出現檔名過長錯誤，請先做本文開頭「陷阱」第 3 點，重開電腦，並可能需要執行：`git config --system core.longpaths true`

clone 指令如下：

`git clone https://github.com/ed-donner/llm_engineering.git`

這會在 projects 目錄下建立 `llm_engineering` 並下載課程程式碼。  
執行 `cd llm_engineering` 進入。此 `llm_engineering` 目錄稱為「專案根目錄」（project root directory）。

4. **Cursor** 若需要請安裝 Cursor 並開啟專案：

造訪 https://cursor.com

點選 Download for Windows，執行安裝程式，全部接受預設即可。

然後從開始選單開啟 cursor。Cursor 啟動後可能需要回答一些問題。你應會看到可點「Open Project」的新視窗畫面。若沒有，請到 File >> New Window，再點「Open Project」。**重要：** 較新版本的 Cursor 可能預設開啟「Agents」畫面而非一般視窗。要開新視窗請按 Ctrl+Shift+N（Windows）或 Cmd+Shift+N（Mac），再點「Open Project」。


在 projects 目錄中找到 `llm_engineering`，雙擊進入，再點 Open 或 Open Folder。

Cursor 應會開啟 `llm_engineering`。若左上角看到大寫的 LLM_ENGINEERING，表示設定正確。

___

**步驟 1（Mac/Linux 使用者）**

1. **安裝 Git**（若尚未安裝）：

開啟 Terminal：Mac 上在 Finder >> Applications >> Utilities >> Terminal。Linux 使用者多半很熟悉 Terminal，我就不多說了！

- 執行 `git --version`，應會顯示版本號。若沒有，依提示安裝，或參考本文開頭「陷阱」第 5 點。

2. **視需要建立 projects 目錄**

- 開啟新 Terminal，輸入 `pwd` 查看目前位置。應在使用者主目錄，例如 `/Users/username`
- 是否已有 projects？輸入 `cd projects` 確認
- 若出現錯誤：`mkdir projects`，然後 `cd projects`
- 再執行 `pwd`，應在 `/Users/username/projects`
- 可放在方便的位置，但避免 iCloud 同步的目錄

3. **執行 git clone：**

在 Projects 資料夾中執行：

`git clone https://github.com/ed-donner/llm_engineering.git`

這會建立 `llm_engineering` 並下載課程程式碼。  
執行 `cd llm_engineering` 進入。此目錄為「專案根目錄」。

4. **Cursor** 若需要請安裝並開啟專案：

造訪 https://cursor.com

下載 Mac OS 或 Linux 版本，執行安裝程式，接受預設即可。

然後從開始選單開啟 cursor，依提示操作，應可看到「Open Project」。若沒有，File >> New Window >> Open Project。

找到 projects 下的 `llm_engineering`，雙擊後點 Open。

Cursor 應會開啟專案。左上角出現 LLM_ENGINEERING 即表示成功。

___

## 步驟 2：安裝 **uv** 並執行 `uv sync`

本課程使用 uv 這個極快的套件管理器，在 Data Science 圈已廣泛採用，理由充分。

它又快又可靠，你會愛上它！

在 Cursor 中選 View >> Terminal 開啟終端機。輸入 `pwd` 確認在專案根目錄。

輸入 `uv --version` 檢查是否已安裝。若有版本號就太好了！若出現錯誤，請依 [安裝說明](https://docs.astral.sh/uv/getting-started/installation/) 安裝 uv——建議用頁面最上方的 Standalone Installer，也可用其他方式。在 Cursor 終端機執行指令。若一種方式不行，換另一種試試。

安裝 uv 後，請在 Cursor 開新終端機視窗（加號或 Ctrl+shift+backtick），`uv --version` 才會生效。請確認！

若 uv 安裝或使用有問題，請參閱 [FAQ Q11](https://edwarddonner.com/faq/#11)。

### 安裝完成後：

執行 `uv self update` 確保 uv 為最新版。

然後執行：  
`uv sync`  
uv 會快速安裝所有依賴。若有問題，同樣參閱 [FAQ Q11](https://edwarddonner.com/faq/#11)。

你現在擁有完整的 spec 環境！

使用 uv 很簡單：  
1. 不用 `pip install xxx`，改為 `uv add xxx`  
2. 不必手動啟動虛擬環境——uv 會代勞  
3. 不用 `python xxx`，改為 `uv run xxx`

___

## 步驟 3 - 選用 - 設定 OpenAI 帳號

替代方案：guides 資料夾中的 Guide 9 有免費替代方案！

前往 https://platform.openai.com

- 若沒有帳號請 Sign Up。可能需要先建立 Organization，填合理預設即可。若不確定 ChatGPT 與 OpenAI API 的差異，請參閱 Guides 中的 Guide 4。
- 點右上角 Settings，左側選 Billing。
- 關閉 Auto-Recharge。視需要「Add to Credit Balance」，選 $5 預付，並設定付款方式。
- 仍在 Settings，左側選 API keys。
- 按「Create new secret key」——選「Owned by you」，任意命名，project 選「Default project」，Permissions 保持 All。
- 按「Create secret key」，複製金鑰到剪貼簿。

___

## 步驟 4 - 使用 OpenAI、Gemini 等模型時需要；若只用 Ollama 可略過 - 建立（並儲存）你的 .env 檔

**請認真完成這一節！** 金鑰設定錯誤很難排查！我收到大量學員問題都源於這裡的疏漏……最重要的是：修改後記得儲存檔案。

1. 建立 `.env` 檔

- 回到 Cursor
- 在左側 File Explorer 空白處右鍵，選「New File」，檔名為 `.env`
- 我必須強調：檔名必須**精確**為 `.env`——就這四個字元，不能多也不能少。不能是 ".env.txt"、"john.env"、"openai.env" 等！且必須在專案根目錄。

若你好奇我為何一再強調：很多人把檔名取錯卻以為沒關係。不行！必須在 llm_engineering 目錄下叫做 `.env` 😂

2. 填入 `.env` 並儲存：

在左側選取該檔，右側應為空白編輯區。輸入：

`OPENAI_API_KEY=`

然後貼上金鑰！應類似：

`OPENAI_API_KEY=sk-proj-lots-and-lots-of-digits`

當然要換成你的真實金鑰，不是字面 "sk-proj-lots-and-lots-of-digits"。

記得儲存！File >> Save 或 Ctrl+S（PC）／Command+S（Mac）。很多人忘了儲存，一定要存！

`.env` 旁可能出現停止符號——別擔心，這是好事！原因見 [FAQ Q7](https://edwarddonner.com/faq)。

__

## 步驟 5 - 安裝 Cursor 擴充功能、開啟 Day 1、設定 Kernel，開始！

（若 Cursor 提示安裝建議的擴充功能，直接同意即可，這是此步驟的捷徑。）

- View >> Extensions  
- 搜尋 "python"，安裝 "ms-python" 或 "anysphere" 的 Python 擴充（若尚未安裝）  
- 搜尋 "jupyter"，安裝 "ms-toolsai" 的 Jupyter 擴充（若尚未安裝）

View >> Explorer，開啟 week1 資料夾，點選 `day1.ipynb`。

- 看到右上角「Select Kernel」？點它，選「Python Environments」
- 選帶星號、類似 `.venv (Python 3.12.x) .venv/bin/python Recommended` 的選項
- 若沒出現，請到 Setup 資料夾的 troubleshooting lab

# 恭喜！！你成功了！課程其餘部分會輕鬆許多 😂

**最後提醒：**

課程早期（Day 2）我會示範 Claude Code 這款很棒的 AI 編程工具，類似我們使用的 Cursor。我只是用它展示 Agentic AI 的實例；課程不會深入教這個工具，我們主要在 Cursor 中學習。若你想自行使用 Claude Code，Anthropic 的 Quick Start 在 [這裡](https://docs.claude.com/en/docs/claude-code/quickstart)。
