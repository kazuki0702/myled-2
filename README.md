# ロボットシステム学 2019 課題1  
## 概要  
LEDの点滅を用いてFizzBuzzを行うデバイスドライバ(1~30まで)  
各LEDは以下の法則で点滅を行います．  
* 赤LED：カウント用  
* 青LED：3の倍数  
* 緑LED：5の倍数  

## 動作環境  
以下の環境で開発，動作確認を行っています．  
* Raspberry Pi  
  - Raspberry Pi Model 3B+  
* OS  
  - Ubuntu 16.04
* 各LED 
  - 赤（小）：16番ピン（GPIO23）　　
  - 赤（大）：22番ピン（GPIO25）  
  - 緑　　　：26番ピン（GPIO7）
## インストール方法  
```
$ git clone https://github.com/takahara3/myled.git
```
## 実行方法  
以下のコマンドを実行し，コンパイル，インストール，パーミッションの変更を行います．
```
$ cd myled
$ make  
$ sudo insmod myled.ko
$ sudo chmod 666 /dev/myled0  
```  
デバイスファイルに`1`を書き込むことでFizzBuzzが行われます．  
```
$ echo 1 > /dev/myled0
```  
**後処理**  
以下のコマンドを実行し，デバイスファイルを削除します．
```
$ sudo rmmod myled
```  

## デモ動画  
https://youtu.be/jQUBy71M9K0

## LICENSE  
This repository is licensed under the GPLv3 license, see COPYING.
