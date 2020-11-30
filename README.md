# Robosys2020_devicedriver

ロボットシステム学の演習で作ったデバイスドライバ  
  
---

## 実装内容  
  
こちらは、講義内で作成した[デバイスドライバ](https://github.com/ryuichiueda/robosys_device_drivers/blob/master/myled.c)に変更を加え作成しています。  
・Aを入力した場合2つのLEDを交互に点滅、光に合わせてブザーがなります。  
・A以外を入力した場合、エラーとしてLEDとブザーが3回点滅して警告します。  
  
---
  
## 用意する物
  
・Raspberry Pi 4 ModelB
・ブレッドボード  
・LED *2  
・電子ブザー  
・抵抗　220Ω *2  
・ジャンパー線 オス−メス *3  
  
---
  
### 回路
  
以下のように回路を組みました。  

<img src=https://github.com/Dansato1203/Robosys2020_devicedriver/blob/master/13118597806544.jpg width=500px />  
  
LEDはそれぞれのアノードがGPIO25,GPIO26に、電子ブザーはプラス側をGPIO12に接続しています。GNDはどこでも構いません。  
  
---
  
### ビルド
  
実行する場合、以下のように行ってください。  
```sh
$ git clone https://github.com/Dansato1203/Robosys2020_devicedriver  
$ cd Robosys2020_devicedriver  
$ make  
$ sudo insmod myled.ko  
$ sudo chmod 666 /dev/myled0  
```
  
### 実行した場合  
#### Aを入力した場合  
  
```sh
$ echo A > /dev/myled0  
```

上記のように'A'をデバイスファイルに入力すると、以下のように動作します。
<img src=https://github.com/Dansato1203/Robosys2020_devicedriver/blob/master/demo1.gif width=500px />
  
---

#### A以外を入力した場合

A以外を入力する場合（ここでは例として'a'）以下のように入力します。
```sh
$ echo a > /dev/myled0
```
  
この場合、以下のように動作します。  
<img src= https://github.com/Dansato1203/Robosys2020_devicedriver/blob/master/demo2.gif width=500px />  
  
---
  
### デモ動画  
  
<img src= https://github.com/Dansato1203/Robosys2020_devicedriver/blob/master/IMG_3674.PNG width=500px />
  
youtubeにあげたデモ動画は[こちら](https://www.youtube.com/watch?v=sgbnUssXj0Q)になります。
  
---
  
### ライセンス
[GNU General Public License v3.0](https://github.com/Dansato1203/Robosys2020_devicedriver/blob/master/COPYING)  
