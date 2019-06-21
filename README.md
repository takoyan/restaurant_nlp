# restaurant_nlp
## Overview
  restaurantにおける,対話者からのメッセージ処理を行う.


## Description
rest.pyは対話者からのメッセージを処理行う。  
get_order.pyは回答者から受け取った文章に対して,オーダーを抜き出す。    

## Usage
```
roslaunch restaurant_nlp rest.launch
```
上記のコマンドを実行し,`rest_ctrl`にString型のメッセージを投げると起動する。

## Node
**`name` restaurant_nlp**

### Subscribe Topic

* **`rest_ctrl`** メインノードの立ち上げ（ std_msgs/String ）

* **`yes_no/recognition_result`** yes/noの音声認識結果の受け取り（ std_msgs/String ）

* **`sound_system/recognition/result`** 音声認識結果の受け取り（ std_msgs/String ）

* **`restaurant_nlp/finish_speaking`** 発話終了を受け取る( std_msgs/Bool )

### Publish Topic

* **`start_resume`** 音声認識開始 ( std_msgs/String )

* **`yes_no`** yes/noの音声認識開始（ std_msgs/Bool ）

<!--* **`help_me_carry/send_place`** 場所情報の送信（ std_msgs/String )-->

* **`/restaurant_nlp/speak`** 文章の発話( std_msgs/String )


**`name` speak.py**

### Subscribe Topic
* **`/restaurant/speak`** 発話するための文章を受け取る(std_msgs/Bool)

### Publish Topic
* **`restaurant_nlp/finish_speaking`** 発話終了を送信(std_msgs/String)
