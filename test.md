---
marp: true
size: 4:3
theme: google-test
paginate: true
---

<!--
_class: top
-->

# Python 機械学習プログラミング PyTorch & scikit-learn編
## 第4章 データの前処理 -- よりよい訓練データセットの構築
### 首藤 朗

---

# 4.1 欠損データへの対処

## 欠損値 (missing value)

データを収集する過程で誤りがあったり、不適切な計測があったり、アンケート調査で空欄のままになっている項目があることがある。
- データテーブルの**空欄**
- **`NaN`**（Not a Number）
- **`null`**（RDBにおいて不明な値を表すのに使われる）

---

# 4.1.1 表形式のデータで欠損値を特定

## 欠損値の特定

```python