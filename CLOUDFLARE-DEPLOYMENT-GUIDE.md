# OBOSHI Art - Cloudflare Pages 移行ガイド

## 📦 このフォルダの内容

```
oboshi-website/
├── index.html          ← メインHTMLファイル（SEO最適化済み）
├── _redirects          ← リダイレクト設定
├── _headers            ← セキュリティヘッダー設定
└── README.md           ← このファイル
```

---

## 🚀 Cloudflare Pagesへのデプロイ手順

### ステップ1: Cloudflareアカウント作成

1. https://dash.cloudflare.com/sign-up にアクセス
2. メールアドレスとパスワードを入力
3. メール認証を完了

---

### ステップ2: Cloudflare Pagesにアクセス

1. https://dash.cloudflare.com/ にログイン
2. 左メニューから **「Workers & Pages」** をクリック
3. **「Create application」** をクリック
4. **「Pages」** タブを選択
5. **「Upload assets」** をクリック

---

### ステップ3: ファイルをアップロード

1. プロジェクト名を入力：`oboshi-art`
2. **「Create project」** をクリック
3. このフォルダ全体（`oboshi-website`）をドラッグ&ドロップ
4. **「Deploy site」** をクリック

**✅ これでサイトが公開されます！**

一時的なURL（例：`https://oboshi-art.pages.dev`）が発行されます。

---

### ステップ4: カスタムドメイン（oboshi.art）を接続

#### 4-1: Cloudflare Pagesでドメインを追加

1. デプロイされたプロジェクトを開く
2. **「Custom domains」** タブをクリック
3. **「Set up a custom domain」** をクリック
4. `oboshi.art` を入力
5. **「Continue」** をクリック

#### 4-2: DNS設定を確認

Cloudflareが自動的にDNS設定を検出します。

**パターンA: ドメインがCloudflareで管理されている場合**
- 自動的にDNSレコードが追加されます
- **「Activate domain」** をクリック
- ✅ 完了！

**パターンB: ドメインが他で管理されている場合**
- Cloudflareが表示するDNS設定をコピー
- ドメイン管理画面（例：Google Domains, Namecheap等）で以下を設定：

```
Type: CNAME
Name: @（またはoboshi.art）
Value: oboshi-art.pages.dev（Cloudflareが指定する値）
```

```
Type: CNAME
Name: www
Value: oboshi-art.pages.dev（Cloudflareが指定する値）
```

---

### ステップ5: SSL証明書の確認（自動）

Cloudflareが自動的にSSL証明書を発行します。
数分〜最大24時間で有効化されます。

---

## ✅ 確認事項

デプロイ後、以下を確認：

1. **メインURL**: https://oboshi.art
2. **WWW付き**: https://www.oboshi.art（自動的にwww無しにリダイレクト）
3. **Google Analytics**: ブラウザのデベロッパーツールで確認
4. **OGP**: https://www.opengraph.xyz/ でテスト

---

## 📝 今後の更新方法

### 方法1: 手動アップロード

1. Cloudflare Pagesのダッシュボードを開く
2. プロジェクト（oboshi-art）を選択
3. **「Create deployment」** をクリック
4. 更新したファイルをアップロード

### 方法2: GitHubと連携（推奨）

1. GitHubリポジトリを作成
2. このフォルダをプッシュ
3. Cloudflare PagesでGitHubを接続
4. 以降、GitHubにプッシュするだけで自動デプロイ

---

## 🎨 OGP画像の準備（重要！）

**まだ作成していない場合：**

### 必要な画像:
- **ファイル名**: `og-image.jpg`
- **サイズ**: 1200×630px
- **内容**: 代表作品または自分の写真
- **配置**: このフォルダのルートに配置

### 作成方法:
1. Canva等で1200×630pxのデザインを作成
2. `og-image.jpg` として保存
3. このフォルダに追加
4. 再度Cloudflare Pagesにアップロード

---

## 🔧 トラブルシューティング

### 問題1: サイトが表示されない
- DNS設定が反映されるまで最大48時間かかる場合があります
- 一時的なURL（`https://oboshi-art.pages.dev`）で確認してください

### 問題2: Google Analyticsが動作しない
- ブラウザの広告ブロッカーを無効化
- デベロッパーツールのコンソールでエラーを確認

### 問題3: OGP画像が表示されない
- `og-image.jpg` がアップロードされているか確認
- Facebook Sharing Debugger（https://developers.facebook.com/tools/debug/）でキャッシュをクリア

---

## 📊 費用

**完全無料**
- 帯域: 無制限
- ビルド回数: 月500回
- リクエスト数: 無制限
- カスタムドメイン: 無料
- SSL証明書: 無料

---

## 📞 サポート

問題が発生した場合：
- Cloudflare Docs: https://developers.cloudflare.com/pages/
- Cloudflare Community: https://community.cloudflare.com/

---

## 🎉 完了後

サイトが公開されたら：
1. Google Search Consoleに登録
2. Google Analyticsでトラッキング確認
3. SNSでシェアしてOGP表示を確認

---

**Good luck! 🚀**
