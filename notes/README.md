# 學習筆記

個人筆記目錄，與課程原文分開，方便 `git fetch upstream` 時減少衝突。

## 檔案一覽

| 檔案 | 用途 |
|------|------|
| [`git.md`](git.md) | **Git 日常使用**（commit、push、拉課程更新） |
| [`template.md`](template.md) | 複製用空白模板 |
| `week1/`～`week8/` | 各週每日筆記 |

## 怎麼用

1. 上完課 → 打開對應 `weekN/dayM.md` 填寫
2. 沒有檔案時：`cp notes/template.md notes/week2/day3.md` 並改標題
3. 存進 git：

```bash
git add notes/week1/day2.md
git commit -m "notes: week1 day2"
git push
```

詳細 git 流程見 [`git.md`](git.md)。

## 目錄結構

```
notes/
  git.md
  template.md
  week1/   day1.md day2.md day4.md day5.md exercise.md
  week2/   day1.md … day5.md
  week3/   day1.md … day5.md
  week4/   day3.md day4.md day5.md   （本課程無 day1、day2）
  week5/   day1.md … day5.md
  week6/   day1.md … day5.md
  week7/   day1.md day2.md day3-and-4.md day5.md results.md
  week8/   day1.md … day5.md
```

## 建議填寫時機

- 跑完當天 lab 所有儲存格後
- 遇到錯誤並解決後
- 想到可應用在工作上的點子時
