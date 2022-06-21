# git_practice_for_tunnel
KINDAI Info-Tech HUB, トンネル施工プロジェクトのGit/GitHubを利用するのに練習です。

# Phase1 基本
Gitの基本操作と用途を明確にしよう

## Gitを使う意味
### Git/GitHubとは
Git バージョン管理システム ローカル環境で用いる

GitHub バージョン管理システムGitをネットワークを介して複数人で使用できるようにしたもの リモート環境で用いる
### 何のために
1. 変更内容を修正できるようにするため
-> バージョン管理ができるので、変更内容を変更前に戻すなどが可能
2. 一つのプロジェクトを複数人で同時進行するため
-> 共同で一つのプロジェクトを触ることが可能で、作業を分担して同時進行し後からそれを統合する等して効率的に進めることができる
3. 複数人の変更内容が被った際の対処などをしやすくするため
-> 同じ一つのファイルを複数人が変更してその内容が異なっている場合など、統合時にそれを解消することができる

## Gitの操作
Repository リポジトリ Gitの一つのプロジェクト単位

CLONE クローン ネットワーク上(GitHubなど)にあるリポジトリをローカル環境にコピーすること
```
git clone ***
```

ADD アッド 変更したファイルを変更内容に追加すること
```
git add file名
git add . 全部入れる
```

COMMIT コミット 変更内容にあるファイルの変更を登録すること
```
git commit -m "message"
```

PUSH プッシュ コミットをネットワーク上(リモートリポジトリ)の方に送信すること
```
git push
```

PULL プル ネットワークの方にある変更内容を取得して最新状態にすること
```
git pull
```

FETCH フェッチ ネットワークの方に変更内容がないかの確認をすること
```
git fetch
```


Branch ブランチ 開発の進行を河の流れに見立てて、ある段階から枝分かれした支流 支流での変更内容などを本流に合流させることもできる 複数人で支流に分けて開発をして支流ごとの開発目標が達成できたら支流を本流に合流させる

BRANCH 現在のブランチの確認
```
git branch
```

CHECKOUT チェックアウト 支流の切り替え
```
git checkout -b "ブランチ名"
```

Pull Request プルリクエスト 支流での変更内容を本流に合流させるための手続き。承認すれば合流し、否認すれば合流されない。ミスなどがあれば否認できる。変更内容にコンフリクトが起こる場合もある。

Conflict コンフリクト 衝突 複数の支流ごとに同じファイルを編集して、その変更内容が異なる場合などに発生する。プルリクの際にコンフリクトがあれば表示されるので、合流させるにはそれを解消させる必要がある

Fork フォーク 他の人のリポジトリを自分のところにコピーすること、自分のとこでの変更を大元に合流させることも可能

## 準備(リーダーだけがする)
1. GitHub Organizationを作成する
[設定のリンク](https://github.com/settings/organizations)から、「New organization」で「Free」なOrganizationを作成する。
名前はチーム名としてわかりやすければ何でも良い。
「KINDAI Info-Tech HUB トンネル施工プロジェクト」とか？

2. Organizationが作成できたら、そのページからPeople欄の「Invite member」で招待ができるのでメンバーのGitHubアカウントを招待する

3. 作成したOrganizationで[今回の練習用リポジトリ](https://github.com/Sane21/git_practice_for_tunnel) を Forkする

4. 次の1.の操作をする
5. developブランチを作る


## 操作しよう(全員)

1. https://github.com/作成したOrganization名/git_practice_for_tunnel を Fork する

2. README.mdをよく読む
3. クローンする
4. それぞれにブランチを作る
元はdevelopにする
ブランチ名は「feature/編集内容」とかにするかな
今回は「feature/PRAC_編集者名」とかにしよう
5. ブランチが切り替わってることを確認する
6. それぞれに「TGT_編集者名.md」のファイルを作成して、適当に今週の目標でも書いてみよう
7. add して commit して push する
8. https://github.com/自分のアカウント名/git_practice_for_tunnel でプルリクエストを 作成したOrganization宛に 投げる
9. リーダーはプルリクエストを承認する
10. それぞれに https://github.com/自分のアカウント名/git_practice_for_tunnel でfetch upstreamする
11. プルする
12. みんなの編集内容が自分のところに反映されてればOK

# Phase2 GitでUnityプロジェクトを管理
また次回以降に