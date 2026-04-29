# github_practice

GitHubの操作を練習するためのリポジトリです。

## 目的

このリポジトリは、Gitの基本操作やGitHubでの共同開発フローを実際に手を動かして学ぶための練習場所です。安心して試行錯誤してください。

## 練習できること

- `git clone` / `git pull` / `git push` などの基本操作
- ブランチの作成・切り替え (`git branch` / `git checkout` / `git switch`)
- コミット (`git add` / `git commit`)
- マージ・リベース (`git merge` / `git rebase`)
- Pull Request の作成・レビュー・マージ
- Issue の作成・コメント・クローズ
- コンフリクトの解消

## 基本的な使い方

```bash
# リポジトリをクローン
git clone https://github.com/cit-hackason-2026/github_practice.git
cd github_practice

# 自分用のブランチを切る
git switch -c practice/your-name

# ファイルを編集してコミット
git add .
git commit -m "練習: 自己紹介を追加"

# リモートにプッシュ
git push -u origin practice/your-name
```

その後、GitHub上で Pull Request を作成してみましょう。

## おすすめの練習フロー

1. このリポジトリをクローンする
2. `practice/自分の名前` のブランチを作る
3. `members/` ディレクトリに自己紹介ファイル（例: `members/your-name.md`）を追加する
4. コミットしてプッシュする
5. Pull Request を作成する
6. レビューしてマージする

## 注意

- 練習用のリポジトリなので、壊しても大丈夫です
- わからないことがあればチームメンバーに聞いてみましょう
