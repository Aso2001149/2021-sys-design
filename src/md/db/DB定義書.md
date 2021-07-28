# DB定義書
## ER図
[ER図はこちら]( https://github.com/Aso2001149/2021-sys-design/blob/main/kaER.md "ER図はこちら" )
# DBテーブルカラム一覧詳細

### 顧客マスタ (d_purchase)
|和名|属性名|型|PK|NN|FK|
|:---|:---|:---|:---|:---|:---|
|名前|name|varchar(35)|○|○||
|価格|value|int||○||
|商品名|number|varchar(40)||○||

### 商品一覧 (m_custmers)
|和名|属性名|型|PK|NN|FK|
|:---|:---|:---|:---|:---|:---|
|名前|name|varchar(35)|○|○||
|住所|from|varchar(30)||○||
|電話番号|number|int||○||
|個人ID|id|int||○||
|パスワード|pass||○||
