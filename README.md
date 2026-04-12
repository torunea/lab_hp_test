# new-web-site

研究室のプロジェクトを紹介するための[サイト](https://labshio.github.io/new-web-site/)です。

プロジェクトの追加・編集は **Google スプレッドシートのみ** で行います。HTMLファイルの編集は不要です。

---

## ディレクトリ構成

```
NEW-WEB-SITE/
├── css/
│   ├── footer.css          # フッター
│   ├── project-detail.css  # 詳細ページ
│   ├── projects.css        # メインページ・カード
│   └── style.css           # 共通スタイル
├── img/
│   └── logo.png            # ロゴ画像のみ
├── js/
│   └── sheets.js           # Google Sheets 連携（IDをここに設定）
├── footer.html             # 共通フッター
├── header.html             # 共通ヘッダー
├── index.html              # メインページ（カードをスプレッドシートから動的生成）
├── project.html            # 詳細ページ（スプレッドシートから動的生成）
└── README.md
```

---

## プロジェクトの追加方法

### 1. スプレッドシートを開く

管理用の Google スプレッドシートに新しい行を追加します。

### 2. 各列に入力する

| 列 | 内容 | 例 |
|---|---|---|
| **id** | URLに使う一意のID（半角英数字・ハイフンのみ） | `supertightcity` |
| **title** | タイトル | `SUPERTIGHTCITY` |
| **date** | 日付（YYYYMM形式） | `201907` |
| **tags** | カテゴリ（下記から1つ選択） | `Research` |
| **image_url** | Flickr などの画像直URL | `https://live.staticflickr.com/...` |
| **description** | 説明文（Ctrl+Enterで段落分け） | `一段落目の説明` |

**tags の選択肢：** `Design` / `Research` / `Thesis` / `Reading` / `Publication` / `Event`

### 3. 保存するだけで反映される

スプレッドシートを保存するとサイトに自動で反映されます。コードの編集は不要です。

---

## 初期設定（初回のみ）

### スプレッドシートをウェブに公開する

1. スプレッドシートを開き、**[ファイル] → [共有] → [ウェブに公開]** を選択
2. 「シート1」「カンマ区切りの値 (.csv)」を選んで **[公開]**
3. 表示されたURLの `/d/` と `/pub` の間の文字列がスプレッドシートIDです

### js/sheets.js にIDを設定する

```js
// js/sheets.js
const SPREADSHEET_ID = 'ここにスプレッドシートIDを貼り付ける';
```

---

## コードを変更したときのプッシュ手順

```bash
git pull origin main
# （ファイルを編集）
git add .
git commit -m "変更内容のメモ"
git push origin main
```
