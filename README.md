# ロボットシステム学 2019 課題1  
## 概要  
LEDの点滅を用いてFizzBuzzを行うデバイスドライバ(1~50まで)  
各LEDは以下の法則で点滅を行う．  
* 赤LED：カウント用  
* 青LED：3の倍数  
* 緑LED：5の倍数  

## インストール方法  
```
$ git clone https://github.com/takahara3/myled.git
```

## 実行方法  
以下のコマンドを実行し，コンパイル，インストール，パーミッションの変更を行う．
```
$ cd myled
$ make  
$ sudo insmod myled.ko
$ sudo chmod 666 /dev/myled0  
```  
デバイスファイルに`1`を書き込むことでFizzBuzzが行われる．  
```
$ echo 1 > /dev/myled0
```  
**後処理**  
以下のコマンドを実行し，デバイスファイルを削除する．
```
$ sudo rmmod myled
```
