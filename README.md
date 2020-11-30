# Robosys2020_devicedriver

ロボットシステム学の演習で作ったデバイスドライバ  
  
## 動作環境  
  
以下の環境で動作確認を行っています。  
・Raspberry Pi 4 ModelB  
  ・Ubuntu 20.04LTS  
  
---  

## 実装内容  
  
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
  
  
### 実際の動画  
#### Aを入力した場合  
  
```sh
echo A > /dev/myled0  
```

上記のように'A'をデバイスファイルに入力すると、以下のように動作します。
<img src=https://github.com/Dansato1203/Robosys2020_devicedriver/blob/master/demo1.gif width=500px />
  
---

#### A以外を入力した場合

A以外を入力する場合（ここでは例として'a'）以下のように入力します。
```sh
echo a > /dev/myled0
```
  
この場合、以下のように動作します。  
<img src= https://github.com/Dansato1203/Robosys2020_devicedriver/blob/master/demo2.gif width=500px />  
  
---
  
### デモ動画  
  
<img src= https://github.com/Dansato1203/Robosys2020_devicedriver/blob/master/IMG_3674.PNG width=500px />
  
youtubeにあげたデモ動画は[こちら](https://www.youtube.com/watch?v=sgbnUssXj0Q)になります。

