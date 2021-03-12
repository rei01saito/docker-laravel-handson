# docker-laravel-handson

quiitaの記事を見ながらdockerでLaravelの環境構築をやってみた。

## 大まかな流れ
1. アプリケーションサーバ（php）とWebサーバ(Nginx)とDBサーバ（MySQL）のDocker imageをpullする。
2. Dockerfileを編集する。(phpのライブラリやDBの設定など)
3. Docker-compose.ymlファイルを作成してポートフォロワーディングや共有ファイルの設定をする。
4. Docker-compose up -d --buildでDocker imageをビルドし、コンテナをまとめて起動する。

## やってみて思ったこと
Vagrant(Homestead)よりも起動時間が圧倒的に早い上に仮想環境の削除（コンテナの削除）がしやすかった。
もし仮にHomesteadではなくVagrantでVagrantboxを追加し、一からアプリケーションサーバやwebサーバ、DBサーバをaptやyumコマンドでインストールするとめちゃくちゃ時間がかかると思うのでより使いやすいなとは感じた。
Laravel公式のLaradockは余計なライブラリが多いとのことで不評の様なので、今回のこの環境はコンパクトなDocker環境を作れるのでいいと思う。
ただHomesteadの方が複数アプリを作成する、誰かと開発するとなった時にやりやすいのではないかと思うのだがどうなのだろう。
