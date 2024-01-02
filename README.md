![test](https://github.com/YusukeFujikawa537/mypkg/actions/workflows/test.yml/badge.svg)

# mypkg

千葉工業大学未来ロボティクス学科のロボットシステム学の講義で作成したリポジトリである。
このレポジトリではros2を用いて、talkerとlistenerという名前のノードが通信するのを確認することができる。

## ノード

### talker.py

* 機能
実行すると0.5秒おきにメッセージを送信する。メッセージは自然数で、１ずつ増えていく。

* 使い方
`` $ ros2 run mypkg talker ``

### listener.py

* 機能
トピックからのメッセージを受信し、talker.py　が送ってきた順番に標準出力する。

* 使い方
`` $ ros2 run mypkg listener ``

* 実行結果
```
[INFO] [1703700061.717145198] [listener]: Listen: 184
[INFO] [1703700062.097893330] [listener]: Listen: 185
[INFO] [1703700062.596147427] [listener]: Listen: 186
[INFO] [1703700063.097135328] [listener]: Listen: 187
[INFO] [1703700063.595263053] [listener]: Listen: 188
[INFO] [1703700064.107682698] [listener]: Listen: 189
[INFO] [1703700064.598444966] [listener]: Listen: 190
[INFO] [1703700065.096480596] [listener]: Listen: 191
[INFO] [1703700065.597302148] [listener]: Listen: 192
[INFO] [1703700066.094473505] [listener]: Listen: 193
[INFO] [1703700066.596135984] [listener]: Listen: 194
[INFO] [1703700067.095569733] [listener]: Listen: 195
```

## launchファイル
talkerとlistnerを同時に実行することができる。

* 使い方
```
$ ros2 launch mypkg talk_listen.launch.py
```

* 実行結果
```
[INFO] [launch]: All log files can be found below /home/asd/.ros/log/2023-12-29-12-54-06-049433-NW-55439
[INFO] [launch]: Default logging verbosity is set to INFO
[INFO] [talker-1]: process started with pid [55441]
[INFO] [listener-2]: process started with pid [55443]
[listener-2] [INFO] [1703822047.081884789] [listener]: Listen: 0
[listener-2] [INFO] [1703822047.557188687] [listener]: Listen: 1
[listener-2] [INFO] [1703822048.057192999] [listener]: Listen: 2
[listener-2] [INFO] [1703822048.557394631] [listener]: Listen: 3
```

## 必要なソフトウェア
* Python 
* ROS2 foxy
  
## テスト環境
GitHubActionsでのテスト環境構築に以下のコンテナを使用した.
https://hub.docker.com/repository/docker/ryuichiueda/ubuntu22.04-ros2
* ROS2 foxy    
* ubuntu 20.04 
上記ヴァージョンにて動作確認済み

## ライセンス
* このソフトウェアパッケージは、3条項BSDライセンスの下、再頒布および使用が許可されています。
* © 2024 Yusuke Fujikawa
