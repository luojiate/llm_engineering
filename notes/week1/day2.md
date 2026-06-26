# Week 1 Day 2 — Ollama 與 OpenAI 相容 API

**日期：**  
**對應 lab：** `week1/day2.ipynb`

## 今天學到什麼

- Chat Completions API：用對話格式讓模型預測下一句
- `openai` 套件只是 HTTP 客戶端，不是模型本體
- 其他供應商（Gemini、Ollama）可用相同介面，改 `base_url` + `api_key`
- Ollama 本機：`http://localhost:11434/v1/`

## 關鍵程式／API

```python
from openai import OpenAI

ollama = OpenAI(base_url="http://localhost:11434/v1", api_key="ollama")
response = ollama.chat.completions.create(model="llama3.2", messages=[...])
```

## 踩過的坑

| 現象 | 原因 | 解法 |
|------|------|------|
| Ollama 連不上 | 服務沒啟動 | 另開終端機執行 `ollama serve` |
| 模型太慢 | 機器資源不足 | 改 `llama3.2:1b` |

## 還不懂／待查

- [ ] 

## 工作應用點子

- 敏感資料用 Ollama 本機跑，不外傳
- 原型用免費本機，上線再換雲端 API

## 明天要做

- [ ] 作業：把 day1 摘要專案改成走 Ollama
