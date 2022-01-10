# 操作変数法（method of instrumental variables, IV）
## 目的
- 操作変数法の理論体系について理解する
- 操作変数法をpythonで実装する
- 論文を理解する
---
## ディレクトリ構成
- ```./data```: データ保管用ディレクトリ
- ```./docs```: 文書，論文用のディレクトリ
- ```./notebooks```: まとまったnotebooksを保存するディレクトリ
- ```./scripts```: 一時作業用ディレクトリ
- ```./src```: 自作モジュール

---
## 使用ライブラリ
- ```pandas=1.3.5```
- ```numpy=1.22.0```
- ```statsmodels=0.13.1```
- ```linearmodels=4.25```

---
## 計算したい統計量，したいこと
- OLS推定量，GMM推定量（2SLS）
- J検定統計量とp値
- Newey-West procedureのstdev（不均分散，系列相関に対して頑健，HAC標準誤差とも呼ばれる）
  - ```linearmod```の```fit()``` メソッドで引数に```cov_type="kernel", kernel="bartlett```と指定すればいい（[参考文献](https://bashtage.github.io/linearmodels/system/examples/examples.html)）
- Hausman検定統計量（論文にはないけど）
  - 論文では diff_coef / stdev_NWをt検定することで代用（いいのかな？）
- 2SLS, 1段階目回帰のF統計量
- Lasso回帰