# Git 日常使用筆記

本機專案採 **作法二（Fork）**：

| remote | 指向 | 用途 |
|--------|------|------|
| `origin` | 你的 `luojiate/llm_engineering` | push 自己的修改 |
| `upstream` | `ed-donner/llm_engineering` | 只拉課程更新，不 push |

> 若尚未設定，見下方「一次性設定」。

---

## 每天學完課（最常用）

```bash
cd /home/jaychang/project/LLM/llm_engineering

# 1. 看改了什麼
git status

# 2. 加入筆記（或你改過的檔案）
git add notes/week1/day2.md
# 或一次加整週筆記：git add notes/week1/

# 3. 提交（訊息寫清楚做了什麼）
git commit -m "notes: week1 day2 Ollama 筆記"

# 4. 推到你的 GitHub
git push
```

**習慣：** 筆記 commit 訊息用 `notes:` 開頭，程式練習用 `lab:` 或 `feat:`，比較好找歷史。

---

## 課程作者更新了課程（偶爾）

```bash
# 1. 抓上游最新
git fetch upstream

# 2. 合併到本機 main（可能出現衝突）
git merge upstream/main

# 3. 若有衝突：打開標記衝突的檔案，手動選要保留的內容，然後：
git add <解決完的檔案>
git commit -m "merge upstream/main"

# 4. 推到你的 repo
git push
```

繁體翻譯過的檔案（如 `week1/day1.ipynb`）合併時**很容易衝突**——通常保留你的翻譯版，或對照上游英文再手動合併。

---

## 常用指令速查

| 想做什麼 | 指令 |
|---------|------|
| 目前狀態 | `git status` |
| 改了哪些行 | `git diff` |
| 提交紀錄 | `git log --oneline -10` |
| 還原某檔案（未 commit） | `git restore 檔案路徑` |
| 看 remote | `git remote -v` |
| 第一次 push 新分支 | `git push -u origin main` |

---

## 一次性設定（Fork 後只做一次）

```bash
cd /home/jaychang/project/LLM/llm_engineering

git remote rename origin upstream
git remote add origin https://github.com/luojiate/llm_engineering.git

git config user.name "你的名字"
git config user.email "你的email@example.com"
```

---

## 不要 commit 的東西

- `.env`（API 金鑰）——已在 `.gitignore`
- 大型模型檔、快取、`.venv/`

提交前養成習慣：`git status` 掃一眼，確認沒有敏感檔。

---

## 踩過的坑（自己填）

| 日期 | 現象 | 原因 | 解法 |
|------|------|------|------|
|      |      |      |      |

---

## 參考

- 課程指南：`guides/03_git_and_github.ipynb`
- 筆記目錄說明：`notes/README.md`
