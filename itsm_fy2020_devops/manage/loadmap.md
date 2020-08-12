# 運営ロードマップ
## 施策コンテンツの方針決定
- ～ 2020/07
- ～ 2020/07
- ～ 2021/**

## 施策開始前

## 運営が事前準備すべきもの
- AWSアカウント
  - ルートアカウントを一つだけ
    - 要クレカ
- 各メンバー分のIAM
  - 基本的にフル権限与える
  
- AWSアカウント
  - 全メンバーで1アカウント共用
    - あくまで請求的な意味合いで
    - IAMは分ける
  - 招待作業が必要
  - 不要なインスタンスの停止Lambda
- 施策用Slack
  - 主目的はアプリからの通知の為
    - 福岡メンバー以外も参画するので
    - しかもメッセージが流れまくるので1万件まで
  - 招待作業が必要
- githubアカウント
  - 招待作業が必要

### Gitアカウント作成
- オーナー(？)がprivateリポジトリを作成
  - masterブランチを作成
  - masterブランチを保護 (PRのみ許容)
    - https://github.com/ebook-japan/{リポジトリ名}/settings/branches の対象ブランチで `Require pull request reviews before merging` にチェック
  - リポジトリに管理権限で各リーダーを追加
    - (辛くないなら全メンバー追加)
- 各リーダーがmasterブランチからteam-xxブランチを作成
  - team-xxブランチを保護 (PRのみ許容)
  - リポジトリに管理権限で各メンバーを追加
    - (オーナーが追加してる場合は不要)
- 各メンバーはteam-xxブランチからteam-xx-nameブランチを作成

## AWSアカウント作成
- オーナー1名がAWSのルートアカウントを作成
  - 要・クレジットカード登録
  - 請求のアラートを付ける
- オーナー1名がリーダー2 + 4名分のIAMアカウントを作成
  - AdminFull + billing 権限？ (可能ならちゃんと選定して絞りたいが...)
  -  (辛くないなら全メンバー追加)
- 各リーダーが招待メールを承認 → ログイン
- 各リーダーが各メンバー分のIAMアカウントを作成
  - AdminFull + billing 権限
  - (オーナーが追加してる場合は不要)
- 各メンバーが招待メールを承認 → ログイン

## AWS仕込み
- ConsoleのURL決め
  - https://docs.aws.amazon.com/ja_jp/IAM/latest/UserGuide/console_account-alias.html
- 請求アラーム
  - https://docs.aws.amazon.com/ja_jp/AmazonCloudWatch/latest/monitoring/monitor_estimated_charges_with_cloudwatch.html
- 上限緩和申請 (AWS Service Quotas)
  - https://console.aws.amazon.com/servicequotas/
- EC2の強制停止をCloudWatch + Lambdaで仕込む
  - https://aws.amazon.com/jp/premiumsupport/knowledge-center/start-stop-lambda-cloudwatch/

## Team分け
- Done

## サンプルアプリケーションの作成

## KickOffの仕込み

## KickOffタイミング
### 各メンバーのGitことはじめ
- 各メンバーがGitアカウントを用意
  - アカウントを運営に通達 (アンケート？
  - Organization

### 各メンバーのAWSことはじめ
- IAMログイン
- VPCを作成
  - 全メンバーDefault VPCで作業することも可能だが...
  - 間違って他の人のリソースを触ることによって混乱するかもしれないので分けたが良いと思う
  - VPC自体は課金対象外
- Cloud9インスタンスを作成

### 来期以降に
- Slack通知まわり
- Dockerとか
- GitHubの初期設定
- AWSの初期設定
- Gitのリポジトリガード
- Selenium