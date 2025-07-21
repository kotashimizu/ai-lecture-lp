# デプロイ手順

## GitHub Pagesでの公開方法

### 1. GitHubリポジトリの作成と初期設定

```bash
# プロジェクトディレクトリで実行
git init
git add .
git commit -m "Initial commit: Add AI lecture landing page"
git branch -M main
git remote add origin https://github.com/[あなたのユーザー名]/ai-lecture-lp.git
git push -u origin main
```

### 2. GitHub Pages設定

1. GitHubのリポジトリページで「Settings」タブをクリック
2. 左メニューから「Pages」を選択
3. Source設定:
   - **Deploy from a branch** を選択
   - **Branch**: `main`
   - **Folder**: `/ (root)`
4. 「Save」をクリック

### 3. 公開URL
設定完了後、以下のURLでアクセス可能になります：
```
https://[あなたのユーザー名].github.io/ai-lecture-lp/
```

### 4. 独自ドメインの設定（オプション）

1. `CNAME`ファイルをルートディレクトリに作成
2. ファイル内に独自ドメインを記述
3. DNS設定でCNAMEレコードを追加

## 注意事項

- デプロイ完了まで数分かかる場合があります
- ファイル更新後、反映まで少し時間がかかることがあります
- HTTPSが自動で有効になります