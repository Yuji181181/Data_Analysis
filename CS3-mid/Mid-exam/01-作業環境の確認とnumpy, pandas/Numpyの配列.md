# Numpyの基本

Numpyは、Pythonで数値計算を効率的に行うためのライブラリです。  
多次元配列（ndarray）を中心に、高速な計算や便利な機能を提供します。

## 主な特徴

- 多次元配列（ndarray）によるデータ管理
- 配列同士の高速な演算
- 行列計算や統計処理などの数学関数が豊富
- 他の科学技術系ライブラリ（pandas, matplotlibなど）と連携しやすい

## 配列の作成例

```python
import numpy as np

# リストからndarrayを作成
lst = [1, 2, 3]
a = np.array(lst)  # 1次元配列

# 2次元リストからndarrayを作成
b = np.array([[1, 2, 3], [4, 5, 6]])  # 2次元配列

# 0で初期化された配列
zeros = np.zeros((2, 3))

# 1で初期化された配列
ones = np.ones((3, 3))

# 連番の配列
arange = np.arange(0, 10, 2)
```

## 配列の演算例

```python
x = np.array([1, 2, 3])
y = np.array([4, 5, 6])

# 要素ごとの加算
z = x + y  # [5, 7, 9]

# 要素ごとの乗算
w = x * y  # [4, 10, 18]
```