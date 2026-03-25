# policy-dashboard-assets

**Version: 1.0.0**

## 概要
Power BI用のテーマテンプレートやチャート・コンポーネントライブラリ、行政区域ポリゴンデータをまとめたリポジトリです。

以下のような用途を想定しています
- ダッシュボードの標準化・高速立ち上げ
- デザイン統一（カラーテーマ適用）
- 日本地図（都道府県・市区町村）を用いた可視化

## 含まれるアセット
- Power BIのデザインテンプレート（.pbit）
- カラーテーマ（JSON）
- 行政区域ポリゴンデータ

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
### デザインテンプレート(.pbit)およびカラーテーマ（JSON）の利用について

1. [`powerbi-templates/`](./powerbi-templates/) 配下のデザインテンプレート(.pbit)およびカラーテーマ（JSON）には、「[公共データ利用規約（第1.0版）](https://www.digital.go.jp/resources/open_data/public_data_license_v1.0)」（PDL1.0）が適用されます。
2. 1.にかかわらず、出典の記載については以下に準拠してください。
- 2-1. デザインテンプレート(.pbit)およびカラーテーマ（JSON）を編集・加工等して作成されたPower BIダッシュボード等を利用者のウェブサイト等で利用する場合、出典を明記する必要はありません。
- 2-2. デザインテンプレート(.pbit)およびカラーテーマ（JSON）を編集・加工等せずに利用し公開する場合は出典を記載してください。
- （出典記載例）出典：デジタル庁 ダッシュボードデザインの実践ガイドブックとチャート・コンポーネントライブラリ https://www.digital.go.jp/resources/dashboard-guidebook

### 行政区域ポリゴンデータの利用について

1. [`data/map/`](./data/map/) 配下の行政区域ポリゴンデータは、国土交通省「[国土数値情報ダウンロードサイト](https://nlftp.mlit.go.jp/ksj/)」のデータを加工して作成したものであり、 [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/legalcode.ja) に従って利用可能です。

## 連絡先

ご意見・ご要望がございましたら、以下のメールアドレスまでご連絡ください。

[info-fdu@digital.go.jp](mailto:info-fdu@digital.go.jp)