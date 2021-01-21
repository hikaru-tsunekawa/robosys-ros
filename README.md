## 内容
* ROSのノードとトピックの関係を利用したPythonプログラムです
* カウントされた数字を元に，2倍・5倍の数字を表示します．

## 環境
* Rasberry Pi3 
* ubuntu20.04 lts(wsl2)  
* ROS Noetic

## 環境構築 

* ラズパイのIPアドレスを取得(コマンドプロンプトで`arp -a`を入力して検索等)して，ラズパイ環境内に入る  
`$ ssh ubuntu@[取得したIPアドレス] ` 

* gitがなかったらインストール  
`$ sudo apt install git`  

* robosys-rosをgitでダウンロード  
```
$ cd ~
$ git clone https://github.com//hikaru-tsunekawa/robosys-ros.git
```

* パッケージの環境構築  
```
$cd ..  
$catkin_make 
```

## 実行方法  
 
* 実行権限付与  
```
$ cd ~/catkin_ws/src/mypkg/scripts
$ chmod +x count.py twice.py five.py
```

* launchファイルのディレクトリに入る  
`$ cd ~/catkin_ws/src/mypkg/launch` 

* ROSパッケージ起動  
`$ roslaunch mypkg mypkg.launch` 

## 出力された数字を確認する(ノードの実行)

* "roslaunch"を実行したものとは別の端末を立ち上げる

* 2倍  
`端末2 $ rostopic echo /twice`

* 5倍  
`端末3 $ rostopic echo /five`

* ctrl + c を押すまでそれぞれ数字がカウントされる

## Youtube動画URL
https://youtu.be/_WqqCT6xSB8

## 参考URL

* ロボットシステム学  
https://github.com/ryuichiueda/robosys2020

* ROSで簡単な通信をする方法  
https://qiita.com/keinko/items/7d0f26c19414291660d9
