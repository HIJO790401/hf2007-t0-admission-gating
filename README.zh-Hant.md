# HF2007｜T0 路徑合法性准入

## 公開驗證節點

**From Sample Safety to Path Legitimacy: T0 Admission Gating for Unauthorized Reasoning Transitions in LLM-Integrated Systems**

**作者：**許文耀／沈耀888π（Wen-Yao Hsu）  
**論文送審身分：**Independent Researcher, Silent School Studio  
**現行官方工作室：**沉靜流派工作室／SERENE SCHOOL STUDIO  
**論文編號：**HF2007  
**外部審查狀態：**2026 年 9 月 9 日獲 ICAISG 2026 正式錄取

> 系統不是從論文開始；HF2007 是我在當時已經進行中的工程開發節點裡，抽出的最小對外可驗證層。

這個 Repository 保存與該審查節點一致的公開證據：最終 Camera-ready 論文，以及在 Major Revision 階段提交並進入錄取審查的實驗包。兩個原始檔案均以逐位元不變的方式釋出，其 SHA-256 固定記錄於 [`SHA256SUMS.txt`](SHA256SUMS.txt)。

[English README](README.md)

## 官網閉環入口

- [繁體中文正式研究紀錄](https://silentschool.studio/zh/research/hf2007-t0-path-legitimacy)
- [英文正式研究紀錄](https://silentschool.studio/en/research/hf2007-t0-path-legitimacy)
- [ICAISG 2026 正式錄取證據](https://silentschool.studio/media/icaisg/HF2007-ICAISG-2026-Acceptance-Notification.pdf)
- [最終 Camera-ready 論文](paper/HF2007_CameraReady_MinorRevision_CLEAN.pdf)
- [審查採用的實驗包](experiments/HF2007_Major_Revision_Experiment_Pack.zip)
- [完整公開證據封裝](HF2007_Public_Evidence_Release_v1.0.zip)

官網保存本研究的正式公開敘事與錄取證據；這個 Repository 是同一節點之原始論文、實驗包、完整證據封裝、來源證明、重現方式與版本紀錄的公開來源。兩者分工清楚，並共同閉合這次公開驗證紀錄。

## 這個節點已經成立的內容

HF2007 把 AI 安全問題從「單一樣本看起來是否安全」，推進到「這一次推理轉移是否具有進入系統的合法路徑」。在推理進入一般運算以前，T0 先檢查定義者、領域、證據、因果、邊界、未解缺口、輸出權限與責任之間的關係，是否已在本次任務內合法成立。

這個獲錄取的公開節點包含可執行、確定性且可回放的准入路徑：

- **51/51**：分開凍結的參考路徑與預測路徑，關係向量完全一致。
- **51/51**：T0 結果完全一致。
- **17/17**：合法的 pre-tool 使用者轉移正確准入。
- **34/34**：注入式 tool-output 轉移在一般推理以前停止。
- 在固定切片的 17 筆合法控制中，False Stop 為 **0**。
- 在固定切片的 34 筆注入轉移中，False Admission 為 **0**。
- 上游 Commit、Git blob、來源 bytes、選取列、逐案比較、覆蓋、消融、回放與機器可讀收據均已固定。

這不是等待未來實現的概念。它是我從既有工程中抽出、完成可重現封裝、提交外部審查並正式獲錄取的最小公開層。

## 公開檔案

| 檔案 | 身分 | SHA-256 |
|---|---|---|
| [`paper/HF2007_CameraReady_MinorRevision_CLEAN.pdf`](paper/HF2007_CameraReady_MinorRevision_CLEAN.pdf) | 最終 Camera-ready 論文 | `ffca3677f1a36b38825f081ca9b3fa77ad1b2b66715ba7987b27531a6f8b34e4` |
| [`experiments/HF2007_Major_Revision_Experiment_Pack.zip`](experiments/HF2007_Major_Revision_Experiment_Pack.zip) | 審查採用的原始可重現實驗包 | `958d880c5d82f895c0687c18a55392040e66356b82b3a47f2a32195b10047118` |

一鍵重現方式見 [`REPRODUCE.md`](REPRODUCE.md)，來源與檔案身分見 [`PROVENANCE.md`](PROVENANCE.md)，已驗證範圍見 [`LIMITATIONS.md`](LIMITATIONS.md)。

## 與現行系統的關係

HF2007 是歷史上的公開驗證節點，不是完整私有系統，也不是 T0 工程的現行終點。論文只公開外部檢查與重現所需的那一層；T0、SCBKR、AICC 與 Runtime 整合仍持續向後落地。未來公開的完整版本會以新的版本與證據節點釋出，不會反向改寫這次已成立的紀錄。

## 出版狀態

本研究已通過正式審查並獲錄取，Camera-ready 檔案亦已獲主辦方確認收件。這個 Repository 是作者對獲錄取公開證據的自主釋出；不宣稱會議論文集出版已完成，也不宣稱已有 DOI、IEEE Xplore 或資料庫索引。精確狀態見 [`STATUS.md`](STATUS.md)。

## 權利與第三方資料

實驗包包含 InjecAgent 專案在 Commit `f19c9f2c79a41046eb13c03c51a24c567a8ffa07` 的固定來源資料。第三方檔案仍適用上游 MIT License；詳見 [`THIRD_PARTY_NOTICES.md`](THIRD_PARTY_NOTICES.md) 與 [`licenses/InjecAgent-MIT.txt`](licenses/InjecAgent-MIT.txt)。這不表示第三方對本研究背書。

作者內容與第三方資料分開管理，詳見 [`LICENSE.md`](LICENSE.md)。
