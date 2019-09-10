<title>Grove - Ultrasonic Ranger</title>
<meta name="description" content="Grove -超音波レンジャーは40KHzで作業する、非接触式の距離測定モジュールです。">
<meta name="author" content="minxuan">  　　
　　
　　

![](https://github.com/SeeedDocument/Grove_Ultrasonic_Ranger/raw/master/img/Ultrasonic.jpg)



Grove - Ultrasonic Ranger

Grove -超音波レンジャーは40KHzで作業する、非接触式の距離測定モジュールです。信号ピンで10uS以上のパルス　トリガ信号を発送したら、Grove - Ultrasonic Rangerは８サイクルの40KHz超音波を送り、物体からのエコーを受信します。エコーのパルス幅と距離とには比例した相関関係があります。計算公式：距離＝エコーのかかった時間＊音声速度（３４０メートル/秒）/2。 Grove-Ultrasonic Rangerのトリガー(Trig) のSIGピンとエコー信号のは同じです。

注意！！
	センサー損壊のないように、Grove-Ultrasonic Rangerのホットプラグはしないでください。距離測定には、測定地域は面積が0.5平方メートル以上、面が平滑であるというように。

<p style=":center"><a href="https://jp.seeedstudio.com//Grove-Ultrasonic-Ranger-p-960.html" target="_blank"><img src="https://raw.githubusercontent.com/SeeedDocument/Seeed-WiKi/master/docs/images/get_one_now_small.png" width="210" height="41"  border=0 /></a></p>




## バージョン

| バージョン              | 変更                                                                                                                                                                                    | 発行日 |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------|
| Grove-Ultrasonic ranger V1.0 | オリジナル版|２０１２年５月 |
| Grove-Ultrasonic ranger V2.0 | 低電圧ボードの採用と以下の変更（1：電気容量C14の追加。2：よりきれいなレイアウト。3：3.3V電圧で働くシステムとも互換性がある。）によって、電源はより穏やかになる。 | ２０１７年７月     |



## 商品仕様

|パラメーター|	数値/範囲|
|:------|:------------------|
|動作電圧|	3.2~5.2V|
|動作電流|	8mA|
|超音波頻度|	40kHz|
|測定範囲|	2-350cm|
|精度|	1cm|
|出力|PWM|
|サイズ|50mm X 25mm X 16mm|
|重さ|13g|
|測定角度|15度に至る|
|動作温度|-10~60℃|
|トリガー信号|10uS TTL|
|エコー信号|TTL|


ヒント!!!
        Groveモジュールの詳細情報は [Grove System](http://wiki.seeedstudio.com/Grove_System/)でご覧ください

## サポートされるプラットフォーム

| Arduino                                                                                             | Raspberry Pi                                                                                             | BeagleBone                                                                                      | Wio                                                                                               | LinkIt ONE                                                                                         |
|-----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|
| ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/arduino_logo.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/raspberry_pi_logo.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/bbg_logo_n.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/wio_logo.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/linkit_logo_n.jpg) |

注意！
    以上のプラットフォームは代表的或いは理論的に互換性があるソフトウェアです。ほとんどの場合は、こちらはソフトウェアライブラリとコードの例を提供し、全部のMCUプラットフォームうにライブラリやデモのコードを提供するではありません。そのため、ライブラリを作ることが必要です。


## 入門ガイド

ノート!!!
        初めてArduinoを操作する場合は、 [Getting Started with Arduino](http://wiki.seeedstudio.com/Getting_Started_with_Arduino/) でご覧ください。



### Arduinoでは

#### ハードウェア部分

- **ステップ1**　以下の物は必要です。

| Seeeduino V4.2 | Base Shield|  Grove - Ultrasonic Ranger |
|--------------|-------------|-----------------|
|![enter image description here](https://raw.githubusercontent.com/SeeedDocument/Grove_Light_Sensor/master/images/gs_1.jpg)|![enter image description here](https://raw.githubusercontent.com/SeeedDocument/Grove_Light_Sensor/master/images/gs_4.jpg)|![enter image description here](https://github.com/SeeedDocument/Grove_Ultrasonic_Ranger/raw/master/img/Ultrasonic_small.jpg)|
|[Get One Now](http://jp.seeedstudio.com/Seeeduino-V4.2-p-2517.html)|[Get One Now](https://jp.seeedstudio.com/Base-Shield-V2-p-1378.html)|[Get One Now](https://jp.seeedstudio.com/Grove-Ultrasonic-Ranger-p-960.html)|

- **ステップ2** Ultrasonic RangerをGrove-Base ShieldのD7ポートに接続します。
- **ステップ3** SeeeduinoにGrove-Base Shieldをインサートします。
- **ステップ4** USBケーブルでSeeeduinoをコンピュータに接続します。

![](https://github.com/SeeedDocument/Grove_Ultrasonic_Ranger/raw/master/img/arduino%20connection.jpg)



ノート!!!
        Grove-Base Shieldがない場合は、以下のようにGrove - Ultrasonic RangerをSeeeduinoに接続します。



| Seeeduino       | Grove-Ultrasonic Ranger |
|---------------|-------------------------|
| 5V           | 赤                     |
| GND           | 黒                   |
| 接続なし | 白                   |
| D7            | 黄                  |



#### ソフトウェア部分

- **ステップ1** 　Githubから  [ UltrasonicRanger Library](https://github.com/Seeed-Studio/Grove_Ultrasonic_Ranger/archive/master.zip) をダウンロードします。
- **ステップ2** 　ファイル [How to install library](http://wiki.seeedstudio.com/How_to_install_Arduino_Library) によってライブラリをArduinoにインストールします。
- **ステップ3** 　Arduinoで以下のコードをコピーして、そしてアップロードします。アップロード方法が分からない場合、 [how to upload code](http://wiki.seeedstudio.com/Upload_Code/)でご覧ください。

```C
#include "Ultrasonic.h"

Ultrasonic ultrasonic(7);
void setup()
{
	Serial.begin(9600);
}
void loop()
{
	long RangeInInches;
	long RangeInCentimeters;

	Serial.println("The distance to obstacles in front is: ");
	RangeInInches = ultrasonic.MeasureInInches();
	Serial.print(RangeInInches);//0~157 inches
	Serial.println(" inch");
	delay(250);

	RangeInCentimeters = ultrasonic.MeasureInCentimeters(); // two measurements should keep an interval
	Serial.print(RangeInCentimeters);//0~400cm
	Serial.println(" cm");
	delay(250);
}
```

- **ステップ4** そして距離数値は以下のようにターミナルで表示されます。

```C
The distance to obstacles in front is:
2 inches
6 cm
The distance to obstacles in front is:
2 inches
6 cm
The distance to obstacles in front is:
2 inches
6 cm
```

### Codecraftでは

#### ハードウェア部分

**ステップ1** 　Grove-Ultrasonic RangerをBase ShieldのD7ポートに接続します。
**ステップ2** 　Seeeduino/ArduinoにGrove-Base Shieldをインサートします。

**ステップ3** 　USBケーブルでSeeeduino/Arduinoをコンピュータに接続します。

#### ソフトウェア部分

**ステップ1** 　[Codecraft](https://ide.chmakered.com/)　を開き、Arduino supportを追加して、そしてメインプロシージャをワーキングエリアにドラッグします。
ノート！！
   初めてCodecraftを操作する場合は、 [Guide for Codecraft using Arduino](http://wiki.seeedstudio.com/Guide_for_Codecraft_using_Arduino/)でご覧ください！

**ステップ2** 以下のようにブロックをドラッグします。或いはcdcファイルを開きます。このページの終わりではcdcファイルがダウンロードできます。


![cc](https://raw.githubusercontent.com/SeeedDocument/Grove_Ultrasonic_Ranger/master/img/cc_Ultrasonic_Ranger.png)

そのプログラムをSeeeduino/Arduinoにアップロードします。

できた！
   コードがアップロードられたら、シリアルモニターでは距離数値が表示されます！

### Raspberry Pi では(Grove Base Hat for Raspberry Piも必要)

####ハードウェア部分

- **ステップ1**　以下の物が必要です。

| Raspberry pi | Grove Base Hat for RasPi| Grove - Ultrasonic Ranger |
|--------------|-------------|-----------------|
|![enter image description here](https://github.com/SeeedDocument/wiki_english/raw/master/docs/images/rasp.jpg)|![enter image description here](https://github.com/SeeedDocument/Grove_Base_Hat_for_Raspberry_Pi/raw/master/img/thumbnail.jpg)|![enter image description here](https://github.com/SeeedDocument/Grove_Ultrasonic_Ranger/raw/master/img/Ultrasonic_small.jpg)|
|[Get ONE Now](https://jp.seeedstudio.com/Raspberry-Pi-3-Model-B-p-2625.html)|[Get ONE Now](https://jp.seeedstudio.com/Grove-Base-Hat-for-Raspberry-Pi-p-3186.html)|[Get ONE Now](https://jp.seeedstudio.com/Grove-Ultrasonic-Ranger-p-960.html)|



- **ステップ2**　Grove Base HatをRaspberryにインサートします。
- **ステップ3**　Grove - Ultrasonic RangerをBase Hatの D5ポートに接続します。
- **ステップ4**　USBケーブルでRaspberry Piをコンピュータに接続します。

![](https://github.com/SeeedDocument/Grove_Base_Hat_for_Raspberry_Pi/raw/master/img/connect2.jpg)


ノート！
   ステップ3では、Ultrasonic Rangerを **どちらのGPIOポート** に接続してもいけますが、それに伴い、ポートにマッチするコマンドを変更しなければなりません。

#### ソフトウェア部分

- **ステップ1**　[Setting Software](http://wiki.seeedstudio.com/Grove_Base_Hat_for_Raspberry_Pi/#installation) によって開発環境を構成します。
- **ステップ２**　grove.py libraryのクローンによってソースファイルをダウンロードします。

```
cd ~
git clone https://github.com/Seeed-Studio/grove.py

```

- **ステップ3**コードの実行のため、以下のコマンドを実行させます。


```
cd grove.py/grove
python grove_ultrasonic_ranger.py 5 6

```

以下はgrove_ultrasonic_ranger.pyコード。

```python

import sys
import time
from grove.gpio import GPIO

usleep = lambda x: time.sleep(x / 1000000.0)

_TIMEOUT1 = 1000
_TIMEOUT2 = 10000

class GroveUltrasonicRanger(object):
    def __init__(self, pin):
        self.dio =GPIO(pin)

    def _get_distance(self):
        self.dio.dir(GPIO.OUT)
        self.dio.write(0)
        usleep(2)
        self.dio.write(1)
        usleep(10)
        self.dio.write(0)

        self.dio.dir(GPIO.IN)

        t0 = time.time()
        count = 0
        while count < _TIMEOUT1:
            if self.dio.read():
                break
            count += 1
        if count >= _TIMEOUT1:
            return None

        t1 = time.time()
        count = 0
        while count < _TIMEOUT2:
            if not self.dio.read():
                break
            count += 1
        if count >= _TIMEOUT2:
            return None

        t2 = time.time()

        dt = int((t1 - t0) * 1000000)
        if dt > 530:
            return None

        distance = ((t2 - t1) * 1000000 / 29 / 2)    # cm

        return distance

    def get_distance(self):
        while True:
            dist = self._get_distance()
            if dist:
                return dist


Grove = GroveUltrasonicRanger


def main():
    if len(sys.argv) < 2:
        print('Usage: {} pin_number'.format(sys.argv[0]))
        sys.exit(1)

    sonar = GroveUltrasonicRanger(int(sys.argv[1]))

    print('Detecting distance...')
    while True:
        print('{} cm'.format(sonar.get_distance()))
        time.sleep(1)

if __name__ == '__main__':
    main()



```

完成！！
    間違いがなければ、以下の結果が出てきます。
    
```python

pi@raspberrypi:~/grove.py/grove $ python grove_ultrasonic_ranger.py 5 6
Detecting distance...
121.757901948 cm
246.894770655 cm
2.60205104433 cm
0.205533257846 cm
0.657706425108 cm
247.433267791 cm
122.485489681 cm
^CTraceback (most recent call last):
  File "grove_ultrasonic_ranger.py", line 110, in <module>
    main()
  File "grove_ultrasonic_ranger.py", line 107, in main
    time.sleep(1)
KeyboardInterrupt


```

++ctrl+c++を押すと、このプログラムを終了することができます。




### Raspberry Piでは(GrovePi_Plusも必要)
#### ハードウェア部分

- **ステップ1**　以下の物が必要です。

| Raspberry pi | GrovePi_Plus | Grove - Ultrasonic Ranger |
|--------------|-------------|-----------------|
|![enter image description here](https://github.com/SeeedDocument/Grove_Ultrasonic_Ranger/raw/master/img/rasp.jpg)|![enter image description here](https://github.com/SeeedDocument/Grove_Ultrasonic_Ranger/raw/master/img/Grovepi%2B.jpg)|![enter image description here](https://github.com/SeeedDocument/Grove_Ultrasonic_Ranger/raw/master/img/Ultrasonic_small.jpg)|
|[Get One Now](https://jp.seeedstudio.com/Raspberry-Pi-3-Model-B-p-2625.html)|[Get One Now](https://jp.seeedstudio.com/GrovePi%2B-p-2241.html)|[Get One Now](https://jp.seeedstudio.com/Grove-Ultrasonic-Ranger-p-960.html)|


- **ステップ2** GrovePi_PlusをRaspberryにインサートします。
- **ステップ3** Grove-Ultrasonic rangerをGrovePi_PlusのD4ポートに接続します。
- **ステップ4** USBケーブルでRaspberryをコンピュータに接続します。
![](https://github.com/SeeedDocument/Grove_Ultrasonic_Ranger/raw/master/img/pi%20connection.jpg)

#### ソフトウェア部分

- **ステップ１**　[Setting Software](https://www.dexterindustries.com/GrovePi/get-started-with-the-grovepi/setting-software/) によって開発環境を構成します。
- **ステップ2**　GitでGithubリポジトリをコピーします。

```
cd ~
git clone https://github.com/DexterInd/GrovePi.git

```

- **ステップ3** ultrasonic_rangerで距離測定のため、以下のコマンドを実行させます。



```python
cd ~/GrovePi/Software/Python
python grove_ultrasonic.py
```

以下はgrove_ultrasonic.pyコードです。

```python
# GrovePi + Grove Ultrasonic Ranger

from grovepi import *

# Connect the Grove Ultrasonic Ranger to digital port D4
# SIG,NC,VCC,GND

ultrasonic_ranger = 4

while True:
    try:
        # Read distance value from Ultrasonic
        print ultrasonicRead(ultrasonic_ranger)

    except TypeError:
        print "Error"
    except IOError:
        print "Error"
```

- **ステップ4**　ターミナルで距離数値は以下のように出てきます。

```python
pi@raspberrypi:~/GrovePi/Software/Python $ python grove_ultrasonic.py
9
9
9
9
9
9
9
9
9
9
9

```

## よくある質問


**Q1：Grove-Ultrasonic sensorはどのように距離を測定しますか？**

- A1：信号ピンで10uS以上のパルス　トリガ信号を発送したら、Grove - Ultrasonic Rangerは８サイクルの40KHz超音波を送り、物体からのエコーを受信します。エコーのパルス幅と距離とには比例した相関関係があります。計算公式：距離＝エコーのかかった時間＊音声速度（３４０メートル/秒）/2。



**Q2：ほかのultrasonic sensor TrigとEcho pinsに比べると、なぜGrove-Ultrasonic sensorには信号ピンが1つだけありますか？**

- A2：Grove-Ultrasonic RangerのTrig のSIGピンとエコー信号のは同じですから。


**Q3：ほかの問題があればどうしましょうか？**

- A3：techsupport@seeed.ccまで送信してください。

**Q4：１つのArduinoに複数のultrasonic sensorを接続してもいいですか？**

- A4：OKです。例として、１つのセンサーはD2ポートに接続し、ほかのはD3ポートに接続します。

```c++
#include "Ultrasonic.h"

Ultrasonic ultrasonic1(2);
Ultrasonic ultrasonic2(3);
void setup()
{
    Serial.begin(9600);
}
void loop()
{
    long RangeInCentimeters1;
    long RangeInCentimeters2;

    RangeInCentimeters1 = ultrasonic1.MeasureInCentimeters(); // two measurements should keep an interval
    Serial.print(RangeInCentimeters1);//0~400cm
    Serial.println(" cm");
    
    RangeInCentimeters2 = ultrasonic2.MeasureInCentimeters(); // two measurements should keep an interval
    Serial.print(RangeInCentimeters2);//0~400cm
    Serial.println(" cm");
    
    delay(250);
}

```

## FAQs

**Q1：Grove-Ultrasonic sensorはどのように距離を測定しますか？**

A1：信号ピンで10uS以上のパルス　トリガ信号を発送したら、Grove - Ultrasonic Rangerは８サイクルの40KHz超音波を送り、物体からのエコーを受信します。エコーのパルス幅と距離とには比例した相関関係があります。計算公式：距離＝エコーのかかった時間＊音声速度（３４０メートル/秒）/2。

**Q2：ほかのultrasonic sensor TrigとEcho pinsに比べると、なぜGrove-Ultrasonic sensorには信号ピンが1つだけありますか？**

A2：Grove-Ultrasonic RangerのTrig のSIGピンとエコー信号のは同じですから。


## 関連リソース

- **[PDF]** [WikiのPDFのダウンロード(Download Wiki PDF)](https://github.com/SeeedDocument/Grove_Ultrasonic_Ranger/raw/master/res/Grove-Ultrasonic_Ranger_WiKi.pdf)
- **[PDF]** [Grove_Ultrasonic Ranger回路図(Grove_Ultrasonic Ranger Schematic)](https://github.com/SeeedDocument/Grove_Ultrasonic_Ranger/raw/master/res/Grove_Ultrasonic%20Ranger%20Schematic.pdf)
- **[PDF]** [セラミックUltrasonic Sensor NU40C16T/R-1(Ceramic Ultrasonic Sensor NU40C16T/R-1)](https://github.com/SeeedDocument/Grove_Ultrasonic_Ranger/blob/master/res/NU40C16T-R-1.pdf)
- **[Library]** [Grove_Ultrasonic Ranger library](https://github.com/Seeed-Studio/Grove_Ultrasonic_Ranger/archive/master.zip)
- **[Codecraft]** [CDCファイル(CDC File)](https://raw.githubusercontent.com/SeeedDocument/Grove_Ultrasonic_Ranger/master/res/Grove_Ultrasonic_Ranger_CDC_File.zip)
- **[Project]** [カラーへリックス(The Color Helix)](https://community.seeedstudio.com/project_detail.html?id=138)
- **[Project]** [インドアの雲状照明(Indoor Lightning Cloud)](https://community.seeedstudio.com/project_detail.html?id=182)
- **[Project]** [自動的の水位コントローラ(Automatic Water Level Controller)](https://community.seeedstudio.com/project_detail.html?id=241)
- **[Example]** [距離測定とLEDディスプレの例(Example_Measure_distance_and_led_display)](https://github.com/SeeedDocument/Grove_Ultrasonic_Ranger/raw/master/res/Example_Measure_distance_and_led_display.zip)
- **[Example]** [距離測定とその表示の例(Example_Measure_and_display_the_distance)。](https://github.com/SeeedDocument/Grove_Ultrasonic_Ranger/raw/master/res/Example_Measure_and_display_the_distance.zip)

## プロジェクト

**Seeed Officeでの面白い段階**：段階を楽しく、インタラクティブにしましょう。また、”STAFF ONLY”という文字を展示することもできます！

<iframe frameborder='0' height='327.5' scrolling='no' src='https://www.hackster.io/stairs-hackers/hacking-the-stairs-at-seeed-s-new-office-9ef30b/embed' width='350'></iframe>






## 技術サポート

何かご不明な点がございましたら、 [フォーラム](http://forum.seeedstudio.com/)でお問い合わせ下さい。

<br />

<p style="text-align:center"><a href="https://www.seeedstudio.com/act-4.html?utm_source=wiki&utm_medium=wikibanner&utm_campaign=newproducts" target="_blank"><img src="https://github.com/SeeedDocument/Wiki_Banner/raw/master/new_product.jpg" /></a></p>　　
　　
　　
　　
※このページは英語バージョンのウィキに基づいて翻訳されたものです。何かご不明な点などございましたら、英語バージョンをご参考下さい。


PCBA

<div class="altium-ecad-viewer" data-project-src="%https://github.com/SeeedDocument/Grove-3-Axis_Analog_Accelerometer-20g-ADXL356B/raw/master/res/Grove%20-%203-Axis%20Analog%20Accelerometer%20%C2%B120g%20(ADXL356B).zip%" style="border-radius: 0px 0px 4px 4px; height: 500px; border-style: solid; border-width: 1px; border-color: rgb(241, 241, 241); overflow: hidden; max-width: 1280px; max-height: 700px; box-sizing: border-box;" />