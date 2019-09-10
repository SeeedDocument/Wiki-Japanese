<title>Grove-PIRモーションセンサー(Grove - PIR Motion Sensor)</title>
<meta name="description" content="Grove-PIRモーションセンサーは一定範囲内の物体、一般的には人の動きが検出できます。使い方は簡単で、Groveベースシールドに接続して、そしてセンサーをプログラムします。範囲内の動きを検出したら、センサーはSIGピンにHighレベル信号を出力します。">
<meta name="author" content="minxuan">  　


![](https://github.com/SeeedDocument/Grove_PIR_Motion_Sensor/raw/master/img/Grove_-_PIR_Motion_Sensor.jpg)

このセンサーは一定範囲内の物体、一般的には人の動きが検出できます。使い方は簡単で、Groveベースシールドに接続して、そしてセンサーをプログラムします。範囲内の動きを検出したら、センサーはSIGピンにHighレベル信号を出力します。

<p style=":center"><a href="https://www.seeedstudio.co.jp/Grove-PIR-Motion-Sensor-p-802.html" target="_blank"><img src="https://raw.githubusercontent.com/SeeedDocument/Seeed-WiKi/master/docs/images/get_one_now_small.png" width="210" height="41"  border=0 /></a></p>

## 商品特性

- Groveと互換性があるインターフェース
- 検出範囲は調整可能
- ホールド時間は調整可能

!!!Tip
    Groveモジュールの詳細情報は [Grove System](http://wiki.seeedstudio.com/Grove_System/)をご覧ください。

## 商品仕様

|パラメーター	|数値/範囲
|---|---|
|動作電圧|	3V–5V
|動作電流(VCC = 3V)|	100uA
|動作電流(VCC = 5V)|	150uA
|検出範囲	|0.1 - 6m
|デフォルト検出範囲|	3m
|ホールド時間	|1 - 25s
|動作波長	|7 - 14um
|検出角度|	120 度まで

## サポートされるプラットフォーム


| Arduino                                                                                             | Raspberry Pi                                                                                             | BeagleBone                                                                                      | Wio                                                                                               | LinkIt ONE                                                                                         |
|-----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|
| ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/arduino_logo.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/raspberry_pi_logo.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/bbg_logo_n.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/wio_logo_n.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/linkit_logo_n.jpg) |

!!!Caution
    以上のプラットフォームは代表的或いは理論的に互換性があるソフトウェアです。ほとんどの場合は、こちらはソフトウェアライブラリとコードの例を提供し、全部のMCUプラットフォームうにライブラリやデモのコードを提供することではありません。そのため、ライブラリを作ることが必要です。

## 入門ガイド

!!!Note
    初めてArduinoを操作する場合は、 [Getting Started with Arduino](http://wiki.seeedstudio.com/Getting_Started_with_Arduino/) をご覧ください！

### Arduinoでは

#### ハードウェア


- **Step 1** 以下の物が必要です。

| Seeeduino V4.2 | Grove - PIR Motion Sensor | Base Shield |
|--------------|----------------------|-----------------|
|![enter image description here](https://raw.githubusercontent.com/SeeedDocument/Grove_Light_Sensor/master/images/gs_1.jpg)|![enter image description here](https://github.com/SeeedDocument/Grove_PIR_Motion_Sensor/raw/master/img/Grove%20-%20PIR%20Motion%20Sensor_s.jpg)|![enter image description here](https://raw.githubusercontent.com/SeeedDocument/Grove_Light_Sensor/master/images/gs_4.jpg)|
|[Get One Now](http://www.seeed.co.jp/Seeeduino-V4.2-p-2517.html)|[Get One Now](https://www.seeed.co.jp/Grove-PIR-Motion-Sensor-p-802.html)|[Get One Now](https://www.seeed.co.jp/Base-Shield-V2-p-1378.html)|


- **Step 2** Grove - PIRモーションセンサーをGrove-ベースシールドの **D2** ポートに接続します。

- **Step 3** Grove-ベースシールドをSeeeduinoにインサートします。

- **Step 4** USBケーブルでSeeeduinoをコンピュータに接続します。


![](https://github.com/SeeedDocument/Grove_PIR_Motion_Sensor/raw/master/img/connect_arduino.jpg)

!!!Note
	Grove-ベースシールドがない場合は、以下のようにGrove - PIRモーションセンサーをSeeeduinoに接続します。

| Seeeduino       | Grove - PIRモーションセンサー |
|---------------|-------------------------|
| 5V           | 赤                     |
| GND           | 黒                   |
| 接続なし | 白                   |
| D2            | 黄                  |



#### ソフトウェア

- Arduino IDEで以下のコードをコピーして、そしてアップロードします。アップロード方法が分からない場合、 [how to upload code](http://wiki.seeedstudio.com/Upload_Code/)をご覧ください。


```c
/*macro definitions of PIR motion sensor pin and LED pin*/
#define PIR_MOTION_SENSOR 2//Use pin 2 to receive the signal from the module


void setup()
{
    pinMode(PIR_MOTION_SENSOR, INPUT);
    Serial.begin(9600);  

}

void loop()
{
    if(digitalRead(PIR_MOTION_SENSOR))//if it detects the moving people?
        Serial.println("Hi,people is coming");
    else
        Serial.println("Watching");

 delay(200);
}

```


!!!Note
    ボードにポテンショメータを2つ追加すると、検出距離やホールド時間が調整できます。詳細は下記のV1.2 Eagleをご覧ください。Jumping Hatの変更によって、このモジュールは再トリガ可能もしくは再トリガ不可に設定することができます。


結果は以下のようです。


![](https://github.com/SeeedDocument/Grove_PIR_Motion_Sensor/raw/master/img/result_arduino.png)

### Codecraftでは

#### ハードウェア

**Step 1** Grove - PIRモーションセンサーをGrove-ベースシールドの D2 ポートに接続します。
**Step 2** Grove-ベースシールドをSeeeduino/Arduinoにインサートします。

**Step 3** USBケーブルで Seeeduino/Arduinoをコンピュータに接続します。

#### ソフトウェア

**Step 1** [Codecraft](https://ide.chmakered.com/)を開き、Arduino supportを追加して、そしてメインプロシージャをワーキングエリアにドラッグします。

!!!Note
    初めてCodecraftを操作する場合は、 [Guide for Codecraft using Arduino](http://wiki.seeedstudio.com/Guide_for_Codecraft_using_Arduino/)をご覧ください。

**Step 2** 以下のようにブロックをドラッグします。或いはcdcファイルを開きます。このページの終わりではcdcファイルがダウンロードできます。

![cc](https://raw.githubusercontent.com/SeeedDocument/Grove_PIR_Motion_Sensor/master/img/cc_PIR_Motion_Sensor.png)

そのプログラムをSeeeduino/Arduinoにアップロードします。

!!!Success
    コードがアップロードられたら、人が接近するとLEDが発光します。

### Raspberry Pi では(Grove Base Hat for Raspberry Piも必要)

#### ハードウェア

- **Step 1** 以下の物が必要です。

| Raspberry pi | Grove Base Hat for RasPi| Grove - PIR Motion Sensor |
|--------------|-------------|-----------------|
|![enter image description here](https://github.com/SeeedDocument/wiki_english/raw/master/docs/images/rasp.jpg)|![enter image description here](https://github.com/SeeedDocument/Grove_Base_Hat_for_Raspberry_Pi/raw/master/img/thumbnail.jpg)|![enter image description here](https://github.com/SeeedDocument/Grove_PIR_Motion_Sensor/raw/master/img/Grove%20-%20PIR%20Motion%20Sensor_s.jpg)|
|[Get ONE Now](https://www.seeedstudio.co.jp/Raspberry-Pi-3-Model-B-p-2625.html)|[Get ONE Now](https://www.seeedstudio.co.jp/Grove-Base-Hat-for-Raspberry-Pi-p-3186.html)|[Get ONE Now](https://www.seeedstudio.co.jp/Grove-PIR-Motion-Sensor-p-802.html)|


- **Step 2** Grove Base HatをRaspberryにインサートします。
- **Step 3** PIRモーションセンサーをBase Hatの D12ポートに接続します。
- **Step 4** USBケーブルでRaspberry Piをコンピュータに接続します。


![](https://github.com/SeeedDocument/Grove_PIR_Motion_Sensor/raw/master/img/Motion_Hat.jpg)


!!! Note
    step 3では、Ultrasonic RangerをどちらのGPIOポートに接続してもいけますが、それに伴い、ポートにマッチするコマンドを変更しなければなりません。


#### ソフトウェア

- **Step 1** [Setting Software](http://wiki.seeedstudio.com/Grove_Base_Hat_for_Raspberry_Pi/#installation) によって開発環境を構成します。
- **Step 2** grove.py libraryのクローンによってソースファイルをダウンロードします。 

```
cd ~
git clone https://github.com/Seeed-Studio/grove.py

```

- **Step 3** コードの実行のため、以下のコマンドを実行させます。

```
cd grove.py/grove
python grove_mini_pir_motion_sensor.py 12

```

以下は grove_mini_pir_motion_sensor.py コードです。

```python

import time
from grove.gpio import GPIO


class GroveMiniPIRMotionSensor(GPIO):
    def __init__(self, pin):
        super(GroveMiniPIRMotionSensor, self).__init__(pin, GPIO.IN)
        self._on_detect = None

    @property
    def on_detect(self):
        return self._on_detect

    @on_detect.setter
    def on_detect(self, callback):
        if not callable(callback):
            return

        if self.on_event is None:
            self.on_event = self._handle_event

        self._on_detect = callback

    def _handle_event(self, pin, value):
        if value:
            if callable(self._on_detect):
                self._on_detect()

Grove = GroveMiniPIRMotionSensor


def main():
    import sys

    if len(sys.argv) < 2:
        print('Usage: {} pin'.format(sys.argv[0]))
        sys.exit(1)

    pir = GroveMiniPIRMotionSensor(int(sys.argv[1]))

    def callback():
        print('Motion detected.')

    pir.on_detect = callback

    while True:
        time.sleep(1)


if __name__ == '__main__':
    main()

```

!!!success
    間違いがなければ、以下の結果が出てきます。

```python

pi@raspberrypi:~/grove.py/grove $ python grove_mini_pir_motion_sensor.py 12
Motion detected.
Motion detected.
Motion detected.
^CTraceback (most recent call last):
  File "grove_mini_pir_motion_sensor.py", line 84, in <module>
    main()
  File "grove_mini_pir_motion_sensor.py", line 80, in main
    time.sleep(1)
KeyboardInterrupt

```

++ctrl+c++を押すと、プログラムを終了することができます。




### Raspberry Piでは(GrovePi_Plusも必要)

#### ハードウェア

- **Step 1.** 以下の物が必要です。

| Raspberry pi | GrovePi_Plus | Grove - PIR Motion Sensor |
|--------------|-------------|-----------------|
|![enter image description here](https://github.com/SeeedDocument/Grove_Ultrasonic_Ranger/raw/master/img/rasp.jpg)|![enter image description here](https://github.com/SeeedDocument/Grove_Ultrasonic_Ranger/raw/master/img/Grovepi%2B.jpg)|![enter image description here](https://github.com/SeeedDocument/Grove_PIR_Motion_Sensor/raw/master/img/Grove%20-%20PIR%20Motion%20Sensor_s.jpg)|
|[Get One Now](https://www.seeedstudio.co.jp/Raspberry-Pi-3-Model-B-p-2625.html)|[Get One Now](https://www.seeedstudio.co.jp/GrovePi%2B-p-2241.html)|[Get One Now](https://www.seeedstudio.co.jp/Grove-PIR-Motion-Sensor-p-802.html)|


- **Step 2.** GrovePi_PlusをRaspberryにインサートします。

- **Step 3.** センサーをGrovePi_Plusの **D8** ポートに接続します。

- **Step 4.** USBケーブルでRaspberryをコンピュータに接続します。


![](https://github.com/SeeedDocument/Grove_PIR_Motion_Sensor/raw/master/img/connect_pi.jpg)

#### ソフトウェア


- **Step 1** [Setting Software](https://www.dexterindustries.com/GrovePi/get-started-with-the-grovepi/setting-software/) によって開発環境を構成します。

- **Step 2** [Updating the Firmware](https://www.dexterindustries.com/GrovePi/get-started-with-the-grovepi/updating-firmware/) によって最新のGrovePiのファームウェアをアップデートします。

!!!Tip
    このWikiページで、採用されたパスは **/home/pi/Desktop/GrovePi**ではなく、 **~/GrovePi/** ですが、Step 2でのパスとStep 3 でのは同じようにご確認ください。

!!!Note
    センサーがエラーをしないように、ファームウェアをアップデートしてください。


- **Step 3** GitでGithubリポジトリをコロンします。

```
cd ~
git clone https://github.com/DexterInd/GrovePi.git

```

- **Step 4** 以下のコマンドを実行させ、PIRモーションセンサーで人の動きが検出できます。

```
cd ~/GrovePi/Software/Python
sudo python grove_pir_motion_sensor.py
```

以下は grove_pir_motion_sensor.py コードです。

```python
import time
import grovepi

# Connect the Grove PIR Motion Sensor to digital port D8
# SIG,NC,VCC,GND
pir_sensor = 8

grovepi.pinMode(pir_sensor,"INPUT")

while True:
    try:
        # Sense motion, usually human, within the target range
        if grovepi.digitalRead(pir_sensor):
            print 'Motion Detected'
        else:
            print '-'

        # if your hold time is less than this, you might not see as many detections
        time.sleep(.2)

    except IOError:
        print "Error"
```

結果は以下のようです。

```python
pi@raspberrypi:~/GrovePi/Software/Python $ sudo python grove_pir_motion_sensor.py

-
-
-
Motion Detected
Motion Detected
Motion Detected
Motion Detected
Motion Detected
Motion Detected
Motion Detected
Motion Detected
Motion Detected
Motion Detected
Motion Detected
-
-

```

## よくあるご質問

**Q1: どうすれば検出距離が調整できますか？**

A1: R2は検出範囲調整に用いられ（AMP係数、2MΩ）。R6はホールド時間調整に用いられます（the trigger duty, 100KΩ）。

検出距離は6メートルから数センチメートルに調整できます。ポテンショメータが末端に設置されると、モジュールは感度が高すぎるから、周りに
人の移動がなくとも、物体などによってドリガーされるということがあります。ディレイタイム・ポテンショメータを使ってホールド時間の調整ができ、約25秒～1秒の範囲で調整できます。

R2とR6がはんだ付けをさせた場合、R13とR14は必ず何も入れられない状態のように確認してください。

!!!Note
    このように改造をすれば、ボードの損壊を起こす可能がありますから、慎重にお考えください。

![](https://github.com/SeeedDocument/Grove_PIR_Motion_Sensor/raw/master/img/Resistor.png)


## 関連リソース


- **[Eagle]** [Grove - PIRモーションセンサー Eagle File v1.2](https://github.com/SeeedDocument/Grove_PIR_Motion_Sensor/raw/master/res/Grove%20PIR%20Motion%20Sensor_v1_2.zip)
- **[PDF]** [Grove - PIRモーションセンサー v1.2 回路図](https://github.com/SeeedDocument/Grove_PIR_Motion_Sensor/raw/master/resources/Grove_PIR_Sensor_v1.2.pdf)
- **[PDF]** [Grove - PIRモーションセンサー Eagle V1.2 PCB](https://github.com/SeeedDocument/Grove_PIR_Motion_Sensor/raw/master/res/Grove%20-%20PIR%20motion%20sensor%20v1.1b%20PCB.pdf)
- **[Library]** [PIRモーションセンサー用のGithub repository](https://github.com/Seeed-Studio/PIR_Motion_Sensor)
- **[Datasheet]** [BISS0001 データシート](https://github.com/SeeedDocument/Grove_PIR_Motion_Sensor/raw/master/resources/Twig_-_BISS0001.pdf)
- **[Datasheet]** [Fresnel lens 8120 データシート](https://github.com/SeeedDocument/Grove_PIR_Motion_Sensor/raw/master/resources/Fresnel_lens_8120.pdf)
- **[Codecraft]** [CDC ファイル](https://raw.githubusercontent.com/SeeedDocument/Grove_PIR_Motion_Sensor/master/res/Grove_PIR_Motion_Sensor_CDC_File.zip)


## プロジェクト

**PIRモーションセンサー盗難警報機** : この文章はPIRモーションセンサー盗難警報機の動作原理についての内容を述べています。

<iframe frameborder='0' height='327.5' scrolling='no' src='https://www.hackster.io/pooja_baraskar/burglar-alarm-with-pir-motion-sensor-964c42/embed' width='350'></iframe>

## テクニカルサポート
何かご不明な点がございましたら、 [フォーラム](http://forum.seeedstudio.com/)でお問い合わせください。
<br /><p style="text-align:center"><a href="https://www.seeedstudio.com/act-4.html?utm_source=wiki&utm_medium=wikibanner&utm_campaign=newproducts" target="_blank"><img src="https://github.com/SeeedDocument/Wiki_Banner/raw/master/new_product.jpg" /></a></p>　　
　　
　　　
※このページは英語バージョンのウィキに基づいて翻訳されたものです。何かご不明な点などございましたら、英語バージョンをご参考下さい。