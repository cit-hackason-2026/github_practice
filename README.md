# github_practice

GitHubの操作を練習するためのリポジトリです。

## 目的

このリポジトリは、Gitの基本操作やGitHubでの共同開発フローを実際に手を動かして学ぶための練習場所です。安心して試行錯誤してください。

---

## 初心者向けGit/GitHubガイド

### ローカル と リモート の違い

Gitには「ローカル」と「リモート」の2つの世界があります。

- **ローカル (local)**: 自分のPCの中にあるリポジトリ。ここで編集・コミットを行う。
- **リモート (remote)**: GitHub上にあるリポジトリ。チーム全員で共有する場所。

```
[自分のPC (ローカル)]  <----push/pull---->  [GitHub (リモート)]
```

ローカルで作業した内容は `push` でリモートに送り、リモートの最新内容は `pull` でローカルに持ってきます。

---

### よく使うコマンドまとめ

#### 1. クローン（最初の1回）

リモートのリポジトリを自分のPCにコピーしてくる。

```bash
git clone https://github.com/cit-hackason-2026/github_practice.git
cd github_practice
```

#### 2. 最新の状態を取り込む（pull）

作業を始める前に、リモートの最新状態をローカルに取り込みます。

```bash
git pull origin main
```

> 💡 **ポイント**: 作業を始める前には必ず `git pull` をしてから始めると、コンフリクト（衝突）が起きにくくなります。

#### 3. 作業ブランチを切る

新しい作業を始める時は、`main` ブランチから新しいブランチを作成します。

```bash
git checkout -b 作業ブランチ名
```

**ブランチの命名ルール**:

| 種類 | プレフィックス | 例 |
|------|--------------|-----|
| 機能追加 | `feature/` | `feature/login-page` |
| バグ修正 | `fix/` | `fix/header-bug` |
| 練習用 | `practice/` | `practice/your-name` |

```bash
# 機能追加の例
git checkout -b feature/add-profile

# バグ修正の例
git checkout -b fix/typo-in-readme
```

#### 4. ファイルを編集する

エディタで好きなようにファイルを編集します。

#### 5. 変更をステージに追加する（add）

コミットする前に、どのファイルをコミットに含めるかを指定します。

```bash
# 変更した全部のファイルを追加
git add .

# ファイルを1つずつ追加
git add ファイル名
git add members/your-name.md
```

> 💡 **ポイント**: `git add .` は楽ですが、不要なファイルまで含めないように `git status` で確認するクセをつけましょう。

#### 6. コミットする（commit）

ステージに追加した変更を「ひとまとまりの作業」として記録します。

```bash
git commit -m "どういうことをしたかのメッセージ"
```

`-m` の後の `""` の中に、**何をしたかをわかりやすく書く** のが大事です。

```bash
# 良い例
git commit -m "ログイン画面のレイアウトを追加"
git commit -m "READMEのタイポを修正"

# 悪い例（何をしたかわからない）
git commit -m "更新"
git commit -m "fix"
```

#### 7. リモートにプッシュする（push）

ローカルのコミットをリモート（GitHub）に送ります。

```bash
git push origin 作業ブランチ名
```

例:
```bash
git push origin feature/add-profile
```

#### 8. Pull Request を作成する

GitHubのページにアクセスして、「Compare & pull request」ボタンから Pull Request を作成します。レビューしてもらった後、`main` にマージします。

---

### よく使うコマンド早見表

| やりたいこと | コマンド |
|------------|---------|
| リポジトリをコピーしてくる | `git clone <URL>` |
| 最新の状態を取得する | `git pull origin main` |
| 今の状態を確認する | `git status` |
| 変更内容を確認する | `git diff` |
| ブランチを新しく作って切り替え | `git checkout -b ブランチ名` |
| ブランチを切り替える | `git checkout ブランチ名` |
| ブランチ一覧を見る | `git branch` |
| 全部のファイルをステージに追加 | `git add .` |
| 1ファイルずつステージに追加 | `git add ファイル名` |
| コミットする | `git commit -m "メッセージ"` |
| リモートにアップロード | `git push origin ブランチ名` |
| 今までのコミット履歴を見る | `git log` |

---

### 一連の流れ（チートシート）

```bash
# 1. 最新を取得
git checkout main
git pull origin main

# 2. 作業ブランチを切る
git checkout -b feature/my-task

# 3. ファイルを編集...

# 4. 状態を確認
git status

# 5. 変更を追加
git add .

# 6. コミット
git commit -m "プロフィール画面を追加"

# 7. プッシュ
git push origin feature/my-task

# 8. GitHubでPull Requestを作成 → レビュー → マージ
```

---

## 練習できること

- `git clone` / `git pull` / `git push` などの基本操作
- ブランチの作成・切り替え (`git checkout -b`)
- コミット (`git add` / `git commit`)
- マージ (`git merge`)
- Pull Request の作成・レビュー・マージ
- Issue の作成・コメント・クローズ
- コンフリクトの解消

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
