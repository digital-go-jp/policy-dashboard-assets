# 行政区域ポリゴンデータ

Power BIやTableauなどのBIツールで前処理無しで簡単に使用できるTopoJSON形式の日本の行政区域ポリゴンデータを公開しています。

## ポリゴンデータ一覧

| 単位 | id | 説明 | TopoJSONファイル |
|---|---|---|---|
| 都道府県 | 都道府県コード2桁 | 47都道府県の境界 | [ja_prefecture_area.json](ja_prefecture_area.json) |
| 市区町村 | 地方公共団体コード5桁 | 1741市区町村の境界 | [ja_municipality_area.json](ja_municipality_area.json) |
| 市区町村 | 地方公共団体コード5桁 | 1741市区町村の境界（都道府県界の強調あり） | [ja_municipality_area_with_pref_boundary.json](ja_municipality_area_with_pref_boundary.json) |

## ポリゴンデータの加工について

[国土数値情報 行政区域データ](https://nlftp.mlit.go.jp/ksj/gml/datalist/KsjTmplt-N03-2025.html)の2025年（令和7年）| 全国地域から取得したデータを元に、以下の処理を行っています。

1. ポリゴンの簡素化及び量子化による軽量化
2. 面積が小さいポリゴン(50000m²未満の小島や防波堤など)を省略
3. 基礎自治体単位(1741市区町村)でポリゴンを結合 (都道府県: 47都道府県単位)
    - 政令指定都市については、行政区（例：札幌市中央区）を政令指定都市単位（例：札幌市）に結合しています。

## ライセンス

### 原データについて

出典：[「国土数値情報（行政区域データ）」（国土交通省）](https://nlftp.mlit.go.jp/ksj/gml/datalist/KsjTmplt-N03-2025.html)
ライセンス: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/legalcode.ja)

### 本データセットのライセンス

本データセットは、上記原データを加工して作成した派生データです。  
原データのライセンスに従い、本データセットも [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/legalcode.ja) の下で公開します。
CC BY 4.0 の条件に従い、出典を表示することで、改変・再配布が可能です。

### 出典表示例

> 「国土数値情報（行政区域データ）」（国土交通省）を加工して作成

## Power BI Desktopでの使用方法

### 1. データの準備

都道府県コード2桁や地方公共団体コード5桁を用意し、使用するテーブルに追加。

参照：[総務省 全国地方公共団体コード](https://www.soumu.go.jp/denshijiti/code.html)

### 2. (必要に応じて)Power BI Desktopの設定確認

1. Power BI Desktopを開く。
2. [ファイル] > [オプションと設定] > [オプション] > [プレビュー機能] を選択し、[図形マップのビジュアル] チェック ボックスをオンにする。
3. Power BI Desktop を再起動する。

### 3. シェイプ マップ(Shape Map)ビジュアルの作成

1. Power BI Desktopを開く。
2. [視覚化] > [場所] に都道府県コード2桁または地方公共団体コード5桁を追加。
3. [視覚化] > [ビジュアル] > [マップの設定] > [マップの種類] で「カスタム マップ」を選択。
4. [視覚化] > [ビジュアル] > [マップの設定] > [マップの種類を追加する] にTopoJSONファイルを追加。

参考：[マイクロソフト Power BI Desktop で図形マップの視覚エフェクトを作成する (プレビュー)](https://learn.microsoft.com/ja-jp/power-bi/visuals/desktop-shape-map)

### 注意点

- シェイプ マップはプレビュー機能であるため、Power BIのアップデートにより予期せぬ挙動をする可能性があります。
