### データフレームのマージ

~~~
変数 = pd.merge(左データフレーム, 右データフレーム, how='マージ方式', left_on='左データフレームの列名', right_on='右データフレームの列名)
~~~

---

### インポート

~~~
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans
from sklearn.preprocessing import scale
~~~

---
### クラスタリング用データ抽出

~~~
(2指標の場合)

変数 = df[['列名1', '列名2']]
~~~

---

### データの標準化

~~~
変数 = scale(標準化前の変数)
~~~

### データフレームに直す

~~~
変数_df = pd.DataFrame(変数, columns=['列名1', '列名2'])
~~~

---

### 散布図の描画

~~~
plt.scatter(変数_df['列名1'], 変数_df['列名2'])
plt.xlabel('col1')
plt.ylabel('col2')
plt.show()
~~~

---

### クラスタリングの実行

~~~
オブジェクト = KMeans(n_clusters=クラスタ数, n_init=10, random_state=適当な整数)

クラスタリング結果 = オブジェクト.fit_predict(入力データ)
~~~

---

### 散布図の描画(カラーバー付き)

~~~
df['cluster'] = クラスタリング結果

plt.scatter(df['列名1'], df['列名2'], c=df['cluster'])
plt.colorbar()
plt.xlabel('col1')
plt.ylabel('col2')
plt.show()
~~~

---

### クラスタごとの平均値

~~~
df.groupby('cluster')[['列名1', '列名2']].mean()
~~~

---

### エルボー法による妥当なクラスタ数の見積もり

~~~
distortions = []
for k in range(1, 10):  
    model = KMeans(n_clusters=k, n_init=10, random_state=0)
    model.fit(X_scaled)
    distortions.append(model.inertia_)

plt.plot(range(1, 11), distortions, marker='o') 
plt.xlabel('クラスタ数')
plt.ylabel('Distortion')
plt.show()
~~~