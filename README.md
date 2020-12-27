# git bisect sample

## 準備

- npmをインストールします
- このリポジトリをクローンします
- プロジェクトルートで`npm install`を実行します
- `npm test`を実行し、テストが失敗することを確認します。これは最新コミットにはバグが含まれることを表現しています。

## 実行

- `git bisect start`
- `git bisect bad` 現在のコミットが"bad"である、つまりテストが失敗する状態であることをgitに伝えます。
- `git bisect good 88e5877` コミット`88e5877`が"good"である、つまりこのコミットの時点ではテストが成功していたことをgitに伝えます。
- `git bisect run npm test` 初めて`npm test`が失敗するようになったコミットを二分探索で特定するようにgitに伝えます。
- `git bisect reset` git bisect startした時点の状態に戻します。
