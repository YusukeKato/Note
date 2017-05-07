---
---
---
---
---
## ＜ 通信方法 ＞
#### `Node` : 一つのプロセスのこと
#### `Publisher` （ 送信者 ） と `Subscriber` （ 受信者 ）、`Node` 間で行う
#### `Topic` : `Node` が送受信するデータ（ 非同期 ）
#### `Service` : 同期する
#### `Paramerter` : YAML形式、データの蓄積・操作を行う
---
## ＜ rosbash ＞
```
roscd : cd
rosls : ls
$ rosed [package_name] [filename]
$ rosed roscpp Logger.msg
```
---
## ＜ メッセージとサービス ＞
#### msgファイルは、ROSメッセージの型を説明するテキストファイル
```
int64 num
```
#### srvファイルは、サービスを記述
```
int64 a
int64 b
---
int64 c
```
```
$ rosmsg show [message type]
$ rossrv show <service type>
```
---
## ＜ オプション ＞
```
-h : help （ ヘルプ ）
-v : verbose （ 詳細 ）
```
```
$ rostopic -h
$ rostopic list -v
```
---
## ＜ ROSを始める ＞
```
$ roscore
```
---
## ＜ rosrun ＞
##### `package` の中にある `node` を起動する
```
$ rosrun [package_name] [node_name]
```
```
$ rosrun turtlesim turtlesim_node
```
---
# ＜ Node の関係をみる ＞
```
$ rqt_graph
```
---
## ＜ topic から送信されるデータを表示する ＞
```
$ rostopic echo [topic]
```
```
$ rostopic echo /turtle1/cmd_vel
```
---
## ＜ topic で送受信されるデータの型を確認する ＞
```
$ rostopic type [topic]
```
```
$ rostopic type /turtle1/cmd_vel
```
---
## ＜ topic へデータを送信する ＞
```
$ rostopic pub [topic] [msg_type] [args]
```
```
rostopic pub -r 1 /turtle1/cmd_vel geometry_msgs/Twist -- '[2.0, 0.0, 0.0]' '[0.0, 0.0, 1.8]'
```
---
## ＜ 型の詳細を知る ＞
```
$ rosmsg show [type]
```
```
$ rosmsg show geometry_msgs/Twist
```
#### パイプでつなぐ
```
$ rostopic type [topic] | rosmsg show
```
```
$ rostopic type /turtle1/cmd_vel | rosmsg show
```
---
## ＜ 引数と返り値を知る ＞
```
$ rosservice list
$ rosservice type [service] | rossrv show
```
---
## ＜ service を呼び出す ＞
```
$ rosservice call [service] [args]
```
```
$ rosservice call clear
$ rosservice call /spawn 2 3 1 ""
```
---
## ＜ rosparam ＞
```
$ rosparam get [param_name]
$ rosparam set [param_name]
```
```
$ rosparam get background_r
$ rosparam set background_r 150
```
---
---
---
---
---

