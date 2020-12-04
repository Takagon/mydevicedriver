# robosys2020 課題
## ロボットシステム学2020第7~8回課題内容
raspberry pi3B+ を用いてモータードライバ(TA7291P)を２つ制御するデバイスドライバを作成しキャタピララジコンを作成しました。
![IMAGE OF ROBOT](./robosys.JPG)
# 実行環境

|||
|:-:|:-:|
| OS | Ubuntu20.04 server |
|Raspberry Pi|Raspberry Pi Model3B+|
# 実行手順

## ドライバーのインストール

`` `
$git clone http://github.com/Takagon/mydevicedriver.git  

$cd mydevicedriver
`` `

## ドライバーのビルド

`` `
$make  

$sudo insmod myled.ko  

$sudo chmod 666 /dev/myled0
`` `

## 実行
ロボットの前進
```
echo s > /dev/myled0
```
ロボットの後退
```
echo b > /dev/myled0
```
ロボットの左折
```
echo l > /dev/myled0
```
ロボットの右折
```
echo r > /dev/myled0
```
ロボットの停止
```
echo 0 > /dev/myled0
```

## ドライバーのアンインストール
```
$sudo rmmod myled
```
# ピン配置
## 東芝製モータードライバTA7291Pについて
モーターの正転、逆転を制御するために東芝製モータードライバTA7291Pを使用する。以下のようにTA7291PとRaspberryPiを接続する。
|GPIO|Motor driver|
|:--:|:--:|
|GPIO22|motor left TA7291P IN1|
|GPIO23|motor left TA7291P IN2|
|GPIO24|motor right TA7291P IN1|
|GPIO25|motor right TA7291P IN2|
