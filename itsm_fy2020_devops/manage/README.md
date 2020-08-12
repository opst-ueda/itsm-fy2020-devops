# ITSM FY2020 DevOpsツール施策運営

## お上の一声
### メンバー
- オーナー
  - 1名 (福岡：1)
- 運営
  - 2名 (福岡：2)
- リーダー
  - 4名 (福岡：4)
-  メンバー
  - 16名 (福岡：11 / 東京：3 / 仙台：2)
- (新卒や中途入社で増員の可能性あり)
- 各人のスキルは様々
### 予算
- 4チーム * 5,000円 = 20,000円の予算
### 環境
- 施策メンバーにはWindowsやMacが混在
- AWS利用
### 環境
- テレビで　集まってワイワイする。　月２回する。
- タスクを振り分けれるように　タスク考える
- ある程度の答えを準備しておく（お題をだすなら）
- 来年に生かせるような工夫をする
- 途中参加の可能性も考慮する
- サービスに依存とかが分かるようにする
- 「説明をはしょるところ」があるなら、その旨をしーーかりとお伝え
- 別案があるなら言葉のヒントだけでも出しておく
- 参加できない場合もあることを考慮

## 各種リンク
- https://drive.google.com/drive/u/0/folders/1qSqU8DBtWLcbsqreuri-hFz9f13nKZ3G

---
## メンバーに達成して欲しいゴール
- 議論なし
- 上田的には
  - 初心者に優しく
  - 玄人にも気付きがあり
  - アンチパターンにどこまで踏み込むか
- ベンダーロックインしすぎないように気を付ける
  - 2つやれると理想
    - Git / SVN
    - TerraForm / Cloud Formation
      - https://qiita.com/jucky330/items/9868dca2b13366a6d074
    - Jenkins / CodePipeline
    - Ansible / Chef
---

## AMIで大枠ははしょる
- で、AMIの作成手順はgithubに残す
- opst_fy2020_devops
  - main
    - team
      - feature/Asan
      - feature/Bsan
- forkの方がいいかな？

## 議論したいこと
### githubのリポジトリ戦略
  - カンニングを許容するか
  - forkまで手を出すか
    - 初心者のハードルはあがる
    - JenkinsのPRガードの設定とかを各人で出来るようになるメリットはあるかと
  - private/public
  - organization
- リポジトリ名
  - itsm_fy2020_devops
    - ドキュメントやInfraのコード等を格納
    - 運営側以外はpushしないと思う
  - itsm_fy2020_devops_api
    - コードの変更検知をしてCIする場合
    - forkするならこのリポジトリ
  - itsm_fy2020_devops_front
    - 今期はいらない気がしてる
- PR書く → レビュー → マージの流れは実践してもらいたい
  - 1人ずつforkするとややこしいかな？
- 実は各自リポジトリ作った方がいいんだろうか？
  - githubのprガードを0から試してみる場合
  - 各自でforkすれば行ける？
- Lambdaや請求アラートの設定はCFn or シェル化したい

### DevOps入門ってホントのホントにしなくていいの？
- なぜ、そうするべきなのかが分からずにやっても意味ないんじゃ...

## 参画者の環境差異について
### 考えられる問題
- 個人の環境は様々
  - WindowsやMacが混在
  - 一時期のCPUではdocker動かない
  - Win10 HomeだとHyper-Vが
  - AndroidStudio(のちょっと古いバージョン)やVirtual Boxを使ってるとHyper-Vが無効化されてるはず。で、それだとDocker動かない...
  - 案件PCに色々インストールできない
  - 自宅にPC持ってない
### 解消法
- 極力Web上で完結するようにする
- Cloud9を利用
  - IDE
  - 利用料金について
    - 裏でEC2インスタンスが立ち上がる
      - 稼働中は当然課金される
      - 一定時間操作しなければ、自動で停止する
  - 停止されるだけでは保存したファイル等は作業は消えない
    - ストレージでの課金はある

## クラウドサービスの利用有無
- AWS、Azure、GCP
- AWS使う
- ルートユーザーは1つ
  - https://docs.aws.amazon.com/ja_jp/IAM/latest/UserGuide/id_root-user.html

## 言語選定
### 選定要件
- 学習コストが低いもの
#### FrontEnd
- 今期はSkip？
#### BackEnd
- DIしてモック化できること
- ビルドしやすいこと
  - Jenkins / Github Action / CodeBuild どれでも簡単にビルドできるやつ。あと、もちろんlocalでも
    - CodeBuild は、Java、Ruby、Python、Go、Node.js、Android、.NET Core、PHP、Docker
- カバレッジの収集が可能であること
- (ビルド速い奴が良い)

### 結論
- ★★★

## ドキュメントのコード化
- API Blue Print
  - drakov
  - dredd
  - aglio
- mermaid.js
  - 作図
  - https://qiita.com/caesar_cat/items/e8a116a585863633d15a
- draw.io
- reveal.js
  - パワポ

### Jenkins


gitのアクセスキーどうする？





- コンソール / cloud fomation / AWS CLI / Profile /

