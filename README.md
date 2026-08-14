# KOL-IQ

脊髓小腦運動失調症（SCA）領域的醫師與研究者資料庫 — 台灣版。

**線上版**：https://richlovegod.github.io/kol-iq/

A public, source-cited database of clinicians and researchers working on spinocerebellar ataxia — Taiwan edition.

---

## 這是什麼

回答四個問題：**誰在做 SCA、他們在做什麼、最近發表了什麼、在哪裡看診與收案。**

- 67 位人物（醫師、研究者、名單層）
- 17 個機構（醫學中心與學術機構）
- 12 件在台灣有站點的相關試驗
- 45 筆附日期與來源的研究與生態系動態
- 每筆資料附可查證的來源連結，中英雙語

姊妹站：[SCA-IQ](https://richlovegod.github.io/sca-iq/)（競品情報）、[MSA-IQ](https://richlovegod.github.io/msa-iq/)（多系統萎縮症）。

## 資料怎麼來的

五個步驟，換一個疾病領域或國家可以照同一套重跑：

1. **文獻層** — Europe PMC 與 PubMed 檢索「SCA 相關詞彙 × 機構國別 × 2021–2026」，本版涵蓋 64 篇台灣掛名論文
2. **試驗層** — ClinicalTrials.gov API 以疾病 × 國別站點拉試驗與主持人；登錄未列主持人時查當地官方登錄系統補齊（台灣＝TPIDB、日本＝jRCT）
3. **組織層** — 病友協會與專科學會的理監事、醫療院所名單、年會議程
4. **動態層** — 當地語言媒體掃近三年：受訪、獲獎、研究發布、政策公告
5. **交叉合併與分層** — 四層證據比對後分層，逐筆標註資料品質問題

## 收錄原則

- **只收公開的專業資訊**：論文、試驗登錄、醫院與學會官方頁、病友組織公告、新聞報導。不含私人聯絡方式。
- **有疑義就標明**：職稱版本不一、拼音未確認、名單未查證，都寫在該筆的「資料品質備註」，不寫死。
- **查不到就說查不到**：已知缺口列在「方法與更新」頁，不留白也不編。
- **不作推測**：例如某試驗的台灣站點在登錄中被匿名化，本站就不猜是哪家醫院。

## 架構

單檔 `index.html`（呈現層）＋ `data/*.json`（資料層），無建置步驟、無相依套件。

```
index.html            # 全部的呈現邏輯與樣式
data/people.json      # 人物（含 en 物件供英文模式）
data/institutions.json
data/trials.json
data/updates.json     # 研究與動態時間線
data/orgs.json        # 學會、病友組織、資源
data/events.json      # 活動行事曆
data/legacy.json      # 紀念頁
data/versions.json    # 版本更新紀錄
data/meta.json        # 資料截止日
```

新增資料只要改 JSON，不用動 HTML。**每筆新資料都要中英雙寫**（缺英文會自動回退中文，但會顯得沒做完）。

## 本機預覽

```bash
python -m http.server 8902 --directory .
```

直接雙擊 `index.html` 會空白 — 瀏覽器會擋 `file://` 的 fetch。

## 更正與移除

本站彙整公開資訊。若發現錯誤，或希望修正、移除自己的資料，歡迎透過該筆所列的來源機構聯繫。

本站為疾病領域的中立情報整理，與所列任何醫師、機構或企業無隸屬關係。
