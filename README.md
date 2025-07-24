![Developer Score](https://github-stats-eta-two.vercel.app/api/stats/yomi4486)

GitHubユーザーの公開統計情報を分析し、**コード行数を重視**した独自のスコアリングで開発者スキルを評価・可視化するリドミデコ

## ✨ 特徴

- 📊 GitHubユーザーの統計情報を総合分析
- � **コード行数重視**の独自スコアリング（40%の重み付け）
- 🏆 7段階のランクシステム（NEWCOMER → LEGENDARY）
- �🎨 美しいSVGグラフィックで表示
- 📱 レスポンシブデザイン
- 🔗 READMEやWebサイトに簡単埋め込み
- 📥 SVGファイルのダウンロード
- 🌐 RESTful API

## 📊 スコア計算システム

### 重み付け
- 📝 **コード行数 (40%)** - 実際に書いたコードの総行数
- 🌟 **スター数 (20%)** - リポジトリが獲得したスター数
- 👥 **フォロワー (15%)** - GitHubフォロワー数
- 💻 **コミット数 (15%)** - 総コミット数
- 📦 **リポジトリ数 (10%)** - パブリックリポジトリ数

### ランクシステム
- 👑 **LEGENDARY** (90-100) - 伝説級の開発者
- 🔥 **MASTER** (80-89) - マスタークラス
- ⭐ **EXPERT** (70-79) - エキスパート
- 💎 **ADVANCED** (60-69) - 上級者
- 🚀 **INTERMEDIATE** (50-59) - 中級者
- 🌱 **BEGINNER** (30-49) - 初心者
- 👶 **NEWCOMER** (0-29) - 新参者

## 📋 表示される情報

- 👤 **プロフィール画像** (GitHubアバター)
- 🎯 **開発者スコア** (0-100点、ランク付き)
- 📊 **スコア内訳** (各項目の詳細評価)
- 📝 総コード行数（推定）
- ⭐ 総スター数
- 🍴 総フォーク数
- 📦 パブリックリポジトリ数
- 💻 総コミット数（概算）
- 👥 フォロワー数
- 💬 使用言語トップ6
- 📅 GitHub登録年

## 使用方法

### Webインターフェース

1. ブラウザで `http://localhost:5173` にアクセス
2. GitHubユーザー名を入力
3. 「統計生成」ボタンをクリック
4. 生成されたSVGを確認・ダウンロード

### API エンドポイント

#### SVG形式で取得
```
GET /api/stats/{username}
```

#### JSON形式で取得
```
GET /api/stats/{username}?format=json
```

### 埋め込み例

#### README.mdに埋め込み
```markdown
![GitHub Developer Score](https://your-domain.com/api/stats/octocat)
```

#### HTMLに埋め込み
```html
<img src="https://your-domain.com/api/stats/octocat" alt="GitHub Developer Score">
```

#### 実例
```markdown
<!-- あなたのプロフィールに追加 -->
![My GitHub Stats](https://your-domain.com/api/stats/yourusername)
```

## 🎨 デザイン仕様

### レイアウト
- **サイズ**: 800×400px（横長、GitHub README最適化）
- **レイアウト**: 3列構成
  - **左列**: アバター + ユーザー情報 + スコア表示
  - **中列**: スコア内訳 + 詳細統計
  - **右列**: 使用言語トップ6
- **カラーテーマ**: ダークモダン
- **フォント**: Inter（フォールバック: システムフォント）

### 視覚要素
- **プロフィール画像**: 丸いアバター（GitHubアイコン）
- **グラデーション背景**: 深みのあるダークテーマ
- **グロー効果**: スコア数値の強調表示
- **プログレスバー**: 各評価項目の視覚化
- **カラーコード**: 言語別の色分け

## 🔬 技術的特徴

### コード行数の推定
- リポジトリサイズ（KB）から行数を推定
- 1KB ≈ 18行のコードと仮定
- フォークされたリポジトリは除外

### スコア正規化
- 対数スケールを使用して極端な値を調整
- 各項目0-100点で正規化
- 重み付けによる総合スコア算出

### パフォーマンス最適化
- SVGベースで軽量
- 1時間キャッシュ
- GitHub API率制限対応

## セットアップ

### 前提条件
- Node.js (v18以上)
- pnpm

### インストール

```bash
# リポジトリをクローン
git clone https://github.com/yomi4486/github_stats.git
cd github_stats

# 依存関係をインストール
pnpm install

# 開発サーバーを起動
pnpm dev
```

### 本番環境へのデプロイ

```bash
# ビルド
pnpm build

# プレビュー
pnpm preview
```

## 技術スタック

- **フレームワーク**: SvelteKit
- **言語**: TypeScript
- **スタイル**: CSS
- **API**: GitHub REST API
- **ビルドツール**: Vite

## API制限について

GitHub APIには以下の制限があります：

- **認証なし**: 1時間に60リクエスト
- **認証あり**: 1時間に5,000リクエスト

本格的な使用を想定する場合は、環境変数でGitHubトークンを設定することを推奨します。

## カスタマイズ

SVGの色やデザインは `src/routes/api/stats/[username]/+server.ts` の `generateSVG` 関数で変更できます。

## ライセンス

MIT License

## 貢献

プルリクエストやイシューは歓迎です！

## 作者

yomi4486
