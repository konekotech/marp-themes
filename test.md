---
marp: true
size: 4:3
theme: google-test
paginate: true
---

<!--
_class: top
-->

# Python 機械学習プログラミング <br> 第 2 版

## 第 4 章 データの前処理 -- よりよい訓練データセットの構築

### 首藤 朗

---

# 4.1 欠損データへの対処

## 欠損値 (missing value)

データを収集する過程で誤りがあったり、不適切な計測があったり、アンケート調査で空欄のままになっている項目があることがある。

- データテーブルの**空欄**
- **`NaN`**（Not a Number）
- **`null`**（RDB において不明な値を表すのに使われる）

---

# 4.1.1 表形式のデータで欠損値を特定すごく長いタイトルすごく長いタイトルすごく長いタイトル

## 欠損値の特定

<div class="code-title">title.py</div>

```python
# フォントを操作する
import pandas as pd
from io import StringIO
csv_data = '''A,B,C,D
            1.0,2.0,3.0,4.0
            5.0,6.0,,8.0
            10.0,11.0,12.0,'''
df = pd.read_csv(StringIO(csv_data))
df.isnull().sum()
```

---

# aaa
