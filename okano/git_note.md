#Gitその1

##コマンド

###設定

git config --global user.name "NAME"

ユーザー名を登録

git config --global user.email "ADRESS"

ユーザーアドレスを登録

git config --global core.autocrlf false

WinとUnixの改行コードを内部的に変換

git config --global color.ui auto

プロンプト表記を色つきにする

git config -l

設定内容を確認

###ローカルリポジトリ作業

git init

リポジトリを初期化する

git add

インデックスに変更を記録する

git add -p

インデックスに変更を部分的に記録する

git add -A

.gitignoreに記録されているファイル以外のリポジトリ内の変更をすべてインデックスに記録する

git commit -m "hoge"

ログメッセージを記述しながらコミットする

git diff

最後にgit addした時点から現在までの差分を表示

git diff HEAD

最後にgit commitした時点から現在までの差分を表示

git diff --cached

HEADと現在のインデックスの差分を表示

git status

現時点でgit commitした場合のプレビューを表示

git show

直近のコミットを確認する

git log

コミットログを参照する

git log -1 --pretty=short

コミットログの冒頭を1件参照する

+ -{数字}でさかのぼる件数

+ -pretty=shortでログの最初の1段落のみ

git log --grep="hoge"

コミットログの中から該当するキーワードを含むものを抜き出す(複数回記述でOR検索)

git blame hoge

ファイル内の1行ごとにどのコミットから更新されたかを確認する

##手順

git initでディレクトリを初期化

git add {ファイル名}でファイルを管理対象にする/インデックスに記録する

git commit -m "hoge"でログメッセージ"hoge"を記述してコミットする

git add -Aで.gitignoreに記述されたファイル以外をインデックスに記録する

git add -pで部分的にインデックスへ変更を記録する

##補足

git diffで最後にgit add(インデックスに記録)してからの差分を表示

git diff HEADで最後にgit commit(コミット)してからの差分を表示
+ HEADとは最新のコミットのこと

git diff --cachedでHEADとインデックスの差分を表示

##ログメッセージについて

コミットの時には必ずログメッセージを記述しなければいけない

###標準的な記述

1行目:変更の内容を要約

2行目:空白

3行目以降:変更の理由

##ログを確認する

git showで直近のコミットを確認

git logで以前の履歴を確認できるがオプションを指定しないと全てのログを引っ張ってきてしまう

git log
+ -{数字}で新しいものからその数字分までのログを表示する
+ --pretty=shortでログメッセージの最初の1段落だけを表示する
+ --grep="hoge"で文字列検索を使用できる。複数個続けてOR検索したり--all-matchオプションと併用してAND検索できる

git blame {ファイル名}でどのコミットから更新されたかを確認できる
+ 冒頭のオブジェクト名でコミットを特定できる
