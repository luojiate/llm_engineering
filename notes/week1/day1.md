# Week 1 Day 1 — 網頁摘要（OpenAI API）

**日期：**  
**對應 lab：** `week1/day1.ipynb`

## 今天學到什麼

- Frontier 模型透過 OpenAI API 呼叫：`openai.chat.completions.create()`
- 訊息格式：`system` + `user` 兩種 role
- `fetch_website_contents(url)` 抓網頁文字 → 送進 LLM 做摘要

## 關鍵程式／API

```python
messages = [
    {"role": "system", "content": system_prompt},
    {"role": "user", "content": user_prompt_prefix + website},
]
response = openai.chat.completions.create(model="gpt-4.1-mini", messages=messages)
```

## 踩過的坑

| 現象 | 原因 | 解法 |
|------|------|------|
| Name Error | 沒從上到下跑儲存格 | 重新 Run All |
| API key 錯誤 | `.env` 檔名或格式不對 | 確認檔名是 `.env` 且已儲存 |

## 還不懂／待查

- [ ] 

## 工作應用點子

- 郵件內容 → 自動建議主旨
- 內部文件 URL → 一頁摘要

## 明天要做

- [ ] 完成 day1 下方練習儲存格（email 主旨建議）
- [ ] 讀 `week1/day2.ipynb`
