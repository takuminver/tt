# スマホだけでAPKを作る手順（GitHub Actions）

このZIPにはAndroidアプリのソースコードと、GitHub上でAPKを自動ビルドする設定が入っています。
PCは不要ですが、GitHubアカウントとブラウザ操作が必要です。

## 手順

1. Androidのブラウザで https://github.com/new を開き、GitHubアカウントでログインします。
2. Repository name に `AICommentatorAndroid` と入力し、Public または Private を選んで Create repository。
3. リポジトリ画面の `Add file` → `Upload files` を選びます。
4. このZIPをスマホで展開し、中にあるファイルとフォルダをすべてアップロードします。
   - `.github` フォルダも必要です。隠しフォルダが表示されない場合は、ファイル管理アプリの「隠しファイルを表示」を有効にしてください。
   - ZIPファイル自体をアップロードするのではなく、展開した中身をアップロードしてください。
5. `Commit changes` を押します。
6. リポジトリ上部の `Actions` を開き、`Build Android APK` を選びます。
7. `Run workflow` → もう一度 `Run workflow` を押します。
8. ビルドが完了したら実行結果を開き、下部の `Artifacts` にある `AICommentator-debug-apk` をダウンロードします。
9. ダウンロードしたArtifact ZIPを展開し、`app-debug.apk` を開いてインストールします。
   Androidが確認を求めた場合は、ダウンロード元アプリからのインストールを許可してください。

## 注意
- GitHub Actionsの無料利用枠には制限があります。Publicリポジトリでは通常の標準ランナー利用に無料枠の扱いがありますが、アカウント設定・GitHubの最新ポリシーを確認してください。
- これは未実機検証の試作版です。ビルドが通っても、すべてのAndroid機種やゲームで画面キャプチャ・実況音声の配信取り込みが動く保証はありません。
- この試作版は汎用画像ラベル認識と簡易コメント生成です。敵・勝敗・HPを正確に理解する本格的なAI実況ではありません。
- GitHubにアップロードするのはソースコードだけです。パスワードやAPIキーは入力・公開しないでください。
