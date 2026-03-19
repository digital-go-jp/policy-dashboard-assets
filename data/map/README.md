# data/map
Power BIやTableauで使用できる日本地図のファイル

## 行政区域地図

| 単位 | id | 説明 | JSON |
|---|---|---|---|
| 都道府県 | 都道府県コード2桁 | 47都道府県境界 | [ja_municipality_area.json](ja_prefecture_area.json) |
| 市区町村 | 地方公共団体コード5桁 | 1741市区町村境界 | [ja_municipality_area_with_pref_boundary.json](ja_municipality_area_with_pref_boundary.json) |
| 市区町村 | 地方公共団体コード5桁 | 1741市区町村境界（都道府県界含む） | [ja_prefecture_area.json](ja_prefecture_area.json) |

## Power BI Desktopへの適用方法
### データの準備
1. 都道府県コード2桁や地方公共団体コード5桁を用意し、使用するテーブルに追加

参照：[総務省 全国地方公共団体コード](https://www.soumu.go.jp/denshijiti/code.html)

### Power BI Desktopの準備(必要に応じて)
1. Power BI Desktopを開く
2. [ファイル] > [オプションと設定] > [オプション] > [プレビュー機能] を選択し、[図形マップのビジュアル] チェック ボックスをオンにする。
3. Power BI Desktop を再起動する。

### シェイプ マップ(Shape Map)ビジュアル
1. Power BI Desktopを開く
2. [視覚化] > [場所] に都道府県コード2桁または地方公共団体コード5桁を追加
3. [視覚化] > [ビジュアル] > [マップの設定] > [マップの種類] でカスタム マップを選択
4. [視覚化] > [ビジュアル] > [マップの設定] > [マップの種類を追加する] にJSONファイルを追加

参照：[マイクロソフト Power BI Desktop で図形マップの視覚エフェクトを作成する (プレビュー)](https://learn.microsoft.com/ja-jp/power-bi/visuals/desktop-shape-map)

## 加工処理のイメージ
### 行政区分
[国土数値情報の行政区域データ](https://nlftp.mlit.go.jp/ksj/gml/datalist/KsjTmplt-N03-2025.html)から取得したデータを元に、以下の処理を行っています。

1. ポリゴンの簡素化
2. 面積が小さいポリゴン(50000m²未満の小島や防波堤など)を省略
3. 基礎自治体単位(1741市区町村)単位でポリゴンを結合 (都道府県: 47都道府県単位)

## データ
このディレクトリに含まれるデータは、国土交通省「[国土数値情報ダウンロードサイト](https://nlftp.mlit.go.jp/ksj/)」のデータを加工して作成したものであり、 「国土数値情報ダウンロードサイトコンテンツ利用規約（政府標準利用規約準拠版）」および [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/legalcode.ja) に従って利用可能です。

出典：[国土交通省 国土数値情報ダウンロードサイト](https://nlftp.mlit.go.jp/)

## 注意点
- シェイプ マップはプレビュー機能であるため、Power BIのアップデートにより予期せぬ挙動をする可能性があります。
- このディレクトリに含まれるデータの拡張子は `.json` ですが、内部構造は TopoJSON 形式となっています。