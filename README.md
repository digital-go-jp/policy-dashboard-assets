# policy-dashboard-assets

## 概要
Power BI用のテーマテンプレートやチャート・コンポーネントライブラリ、日本地図ファイルをまとめたリポジトリです。

以下のような用途を想定しています
- ダッシュボードの標準化・高速立ち上げ
- デザイン統一（カラーテーマ適用）
- 日本地図（都道府県・市区町村）を用いた可視化

## 含まれるアセット
- Power BIのチャート・コンポーネントライブラリ（.pbit）
- カラーテーマ（JSON）
- 行政区域ポリゴンデータ（TopoJSON）

## ディレクトリ構成
```
policy-dashboard-assets/
├── powerbi-templates/
│   ├── powerbi-theme-pbit/
│   └── powerbi-theme-json/
├── data/
│   └── map/
```

## ライセンス
### ソースコード
このディレクトリに含まれるソースコードは [MIT License](./LICENSE) の下で提供されています。