```uml

@startuml

/'
  図の中で目立たせたいエンティティに着色するための
  色の名前（定数）を定義できます。
  https://plantuml.com/ja/skinparam
'/

!define MASTER_MARK_COLOR Orange 
!define TRANSACTION_MARK_COLOR DeepSkyBlue

'グラデーションさせる場合 #xx-xx
!define MAIN_ENTITY #MintCream-MistyRose

/'
  デフォルト色を"skinparam class"で設定します。
'/
skinparam class {
    '図の背景
    BackgroundColor Snow
    '図の枠
    BorderColor Black
    'リレーションの色
    ArrowColor Black
}

package "ECサイト" as target_system {
    /'
      マスターテーブルを M、トランザクションを T などで表記
      １文字なら "主" とか "従" まど日本語でも記載可能
     '/

    entity "顧客マスタ" as customer <m_customers> <<M,MASTER_MARK_COLOR>> {
        + customer_code [PK]
        --
        name
        from
        numbers
        ID
        pass
    }

    entity "商品一覧" as order <d_purchase> <<T,TRANSACTION_MARK_COLOR>> MAIN_ENTITY {
        + order_id [PK]
        --
        name
        value
        number
    }


    

}

/'
  テーブルのつながりの記載方法
  https://qiita.com/murakami-mm/items/4c50d1949a8b10016ef7

    ------   :1
    ----||   :1 and only 1
    ----o|   :0 or 1
    -----{   :many
    ----|{   :1 or more (1以上)
    ----o{   :0 or many (0以上)

これだと縦につながる
customer       |o--o{     order

 left    le
 right   ri
 up      up
 down    do


'/
customer       |o-ri-o{     order



@enduml

```
