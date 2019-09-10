---
name: Grove - Temperature&Humidity Sensor
category: Sensor
bzurl: https://jp.seeedstudio.com/Grove-Temp&Humi-Sensor-p-745.html
oldwikiname: Grove_-_Temperature&Humidity_Sensor
prodimagename: Grove-TempAndHumiSensor.jpg
bzprodimageurl: https://statics3.seeedstudio.com/images/101020011 1.jpg
surveyurl: https://www.research.net/r/Grove-TemperatureAndHumidity_Sensor
sku: 101020011
---
  
    
　　
<title>Grove-Temperature&Humidity sensor</title>
<meta name="description" content="Grove-温度や湿度センサーは校正されておくデジタル出力を提供します。相対湿度は独特な容量式センサーによって測定され、温度はNTCサーミスタによって測定されます。">
<meta name="author" content="minxuan">  　　  
  
    
      

![](https://github.com/SeeedDocument/Grove-TemperatureAndHumidity_Sensor/raw/master/img/main.jpg)

Grove-Temperature&Humidity sensor
Grove-温度や湿度センサーは校正されておくデジタル出力を提供します。相対湿度は独特な容量式センサーによって測定され、温度はNTCサーミスタによって測定されます。このセンサーは信頼できるデータを提供します。零度以下の環境では、このセンサーは動作できませんが、ご注意ください！

<p style=":center"><a href="https://jp.seeedstudio.com/Grove-Temperature-Humidity-Sensor-DHT1-p-745.html" target="_blank"><img src="https://raw.githubusercontent.com/SeeedDocument/Seeed-WiKi/master/docs/images/get_one_now_small.png" width="210" height="41"  border=0 /></a></p>



## 商品特性
--------

-   相対湿度や温度の測定ができる
-   全範囲の温度補償校正
-   デジタル信号
-   長持ちできる
-   長距離の送信できる(20メートル以上までも)
-   低電力消費

ヒント！
    Groveモジュールの詳細情報は [Grove System](http://wiki.seeedstudio.com/Grove_System/)でご覧ください。

## 実的応用
------------------

-   消費製品
-   気象観測
-   湿度調整器
-   エアコン


## 商品仕様
--------------

### 主な仕様

| 項目        |                     |
|--------------|------------------------|
| PCB サイズ     | 2.0cm*4.0cm            |
| インターフェース    | 2.0mm ピンヘッダー(pitch pin header) |
|　IO構造 | SIG,VCC,GND,NC         |
| RoHS         | √                   |

### 電気的特性

| 項目   |      条件     |    最小値     |     基準     |   最大値     |   単位       |
|---------|-------------|--------------|------------|-----------|-----------|
| VCC     |   -        | 3.3          |     -      |  5         |     Volts     |         
|    測定時電流  |    -      |     1.3      |    -       |    2.1       |   mA       | 
|   平均電流   |      -    |      0.5     |     -      |       1.1    |    mA      | 
|   測定範囲   |    湿度      |    20％       |    -       |     90%      |    RH      | 
|      |       温度   |     0      |     -      |     50      |   ℃       | 
|  精度    |       湿度   |     -      |       -    |      ±5%     |     RH     | 
|      |         温度 |           |           |      ±2     |      ℃    | 
|  感度　　　 |     湿度     |           |           |     1%      |    RH      | 
|      |       温度   |           |           |       1    |      ℃    | 
|   再現性   |   湿度       |           |           |     ±1%      |     RH     | 
|      |       温度   |           |           |      ±1   |     ℃     | 
|     耐用性 |          |           |           |    ±1%       |    RH/year      | 
|  信号収集間隔    |          |           |     2      |           |   s       | 




サポートされるプラットフォーム
------------------

| Arduino                                                                                             | Raspberry Pi                                                                                             | BeagleBone                                                                                      | Wio                                                                                               | LinkIt ONE                                                                                         |
|-----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|
| ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/arduino_logo.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/raspberry_pi_logo.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/bbg_logo_n.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/wio_logo.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/linkit_logo_n.jpg) |

ノート！
    以上のプラットフォームは代表的或いは理論的に互換性があるソフトウェアです。ほとんどの場合は、こちらはソフトウェアライブラリとコードの例を提供し、全部のMCUプラットフォームうにライブラリやデモのコードを提供するではありません。そのため、ライブラリを作ることが必要です。



入門ガイド


MCUからのトリガー信号をもらったら、センサーは低電力消費モードから活躍モードになって、MCUに応答信号を送信し、そして40bitの集められたデータを送信し、それからもう1つの信号が引き起こされます。（ノート：センサーからMCUに送信した40bitのデータはトリガー信号をもらった前に集められたものです。）1つのトリガー信号は毎回センサーから40bitのデータを受信します。単母線データはMCUとセンサーとの通信に用いられます。通信のプロセスは以下のようです。
![](https://raw.githubusercontent.com/SeeedDocument/Grove-TemperatureAndHumidity_Sensor/master/img/Twig-Temperature_Humidity.jpg)

毎回の通信には5 msがかかります。高次のデータがまず送信されます。信号データは40bitであり、16bitの湿度のデータ、16bitの温度のデータそして8bitのチェックサムが含まれます。以下はデータのフォーマットです。

    8bits integer part of humidity+8bits decimal part of humidity
    +8bits integer part of temperature+8bits decimal part of temperature
    +8bits checksum.

ノート！
    初めてArduinoを操作する場合は、 [Getting Started with Arduino](http://wiki.seeedstudio.com/Getting_Started_with_Arduino/) でご覧ください！



### Arduinoでは

#### ハードウェア

- **ステップ1**　以下の物が必要です。

| Seeeduino V4.2 | Base Shield| Temperature&Humidity Sensor|
|--------------|-------------|-----------------|
|![enter image description here](https://raw.githubusercontent.com/SeeedDocument/Grove_Light_Sensor/master/images/gs_1.jpg)|![enter image description here](https://raw.githubusercontent.com/SeeedDocument/Grove_Light_Sensor/master/images/gs_4.jpg)|![enter image description here](https://github.com/SeeedDocument/Grove-TemperatureAndHumidity_Sensor/raw/master/img/list.jpg)|
|[Get One Now](http://jp.seeedstudio.com/Seeeduino-V4.2-p-2517.html)|[Get One Now](https://jp.seeedstudio.com/Base-Shield-V2-p-1378.html)|[Get One Now](https://jp.seeedstudio.com/Grove-Temp%26Humi-Sensor-p-745.html)|


- **ステップ2**　Grove-温度や湿度センサーをGrove-Base ShieldのD2ポートに接続します。

- **ステップ3**　Grove - Base ShieldをSeeeduinoにインサートします。

- **ステップ4**　USBケーブルでSeeeduinoをコンピュータに接続します。
![](https://github.com/SeeedDocument/Grove-TemperatureAndHumidity_Sensor/raw/master/img/connect_arduino.jpg)


ノート！
	Grove-Base Shieldがない場合は、以下のようにGrove-温度や湿度センサーをSeeeduinoに接続します。


| Seeeduino       | Grove-温度や湿度センサー |
|---------------|-------------------------|
| 5V            | 赤                     |
| GND           | 黒                   |
| Not Conencted | 白                   |
| D2            | 黄                  |


#### ソフトウェア

- **ステップ1**　Githubで  [ Seeed DHT library](https://github.com/Seeed-Studio/Grove_Temperature_And_Humidity_Sensor)  をダウンロードします。

- **ステップ2**　ファイル [How to install library](http://wiki.seeedstudio.com/How_to_install_Arduino_Library) によってライブラリをArduinoにインストールします。

- **ステップ3**　Arduino IDEを再起動、このパス **(File → Examples → Grove_Humidity_Temperature_Sensor-master → DHTtester)**によって DHTtesterを開きます。このデモでは、周辺環境の相対湿度や温度が分かります。

![](https://github.com/SeeedDocument/Grove-Temperature_and_Humidity_Sensor_Pro/raw/master/img/path.png)


ノート！
    このライブラリはGrove-温度や湿度センサーと [Grove-温度や湿度センサー PRO](http://wiki.seeedstudio.com/Grove-Temperature_and_Humidity_Sensor_Pro/) に共有されます。どちらのセンサーを使うにもかかわらず、センサーのボードの定義ライン(definition line)を作用され、他のスペックの定義ラインをコメントアウトしてください。例えば、Grove-温度や湿度センサーはDHT11で、定義ラインは以下のようです。

```
#define DHTTYPE DHT11   // DHT 11
//#define DHTTYPE DHT22   // DHT 22  (AM2302)
//#define DHTTYPE DHT21   // DHT 21 (AM2301)
```

ライブラリのデフォールト設定は `DHT 22`で、`DHT 11` に変更してください。


- **ステップ4**　そのデモをアップロードします。アップロードが分からない場合、 [how to upload code](http://wiki.seeedstudio.com/Upload_Code/)でご覧ください。



- **ステップ5**　**Tool-> Serial Monitor**をクリックして、Arduino IDMの **シリアルモニター** を開きます。或いは ++ctrl+shift+m++ を同時に押します。間違いなければ、温度の結果は以下のように出てきます。


![](https://github.com/SeeedDocument/Grove-TemperatureAndHumidity_Sensor/raw/master/img/result_ar.png)

### Codecraftでは

#### ハードウェア

**ステップ1**　Grove-温度や湿度センサーをBase ShieldのD2ポートに接続します。

**ステップ2**　Base ShieldをSeeeduino或いはArduinoにインサートします。

**ステップ3**　USBブールでSeeeduino或いはArduinoをコンピュータに接続します。

#### ソフトウェア

**ステップ1**　[Codecraft](https://ide.chmakered.com/)を開き、Arduinoサポートを追加し、そしてメインプロシージャをワーキングエリアにドラッグします。

ノート！
    初めてCodecraftを操作する場合は、 [Guide for Codecraft using Arduino](http://wiki.seeedstudio.com/Guide_for_Codecraft_using_Arduino/)でご覧ください！

**ステップ2**以下のようにブロックをドラッグします。或いはcdcファイルを開きます。このページの終わりではcdcファイルがダウンロードできます。

![cc](https://raw.githubusercontent.com/SeeedDocument/Grove-TemperatureAndHumidity_Sensor/master/img/cc_Temperature_Humidity.png)

そのプログラムをSeeeduino/Arduinoにアップロードします。

完成！
    コードがアップロードさせたら、シリアルモニターでは湿度や温度が示されます！

### Raspberry Pi では(Grove Base Hat for Raspberry Piも必要)
#### ハードウェア

- **ステップ1**　以下の物が必要です。

| Raspberry pi | Grove Base Hat for RasPi| Grove - Temp & Hum Sensor|
|--------------|-------------|-----------------|
|![enter image description here](https://github.com/SeeedDocument/wiki_english/raw/master/docs/images/rasp.jpg)|![enter image description here](https://github.com/SeeedDocument/Grove_Base_Hat_for_Raspberry_Pi/raw/master/img/thumbnail.jpg)|![enter image description here](https://github.com/SeeedDocument/Grove-TemperatureAndHumidity_Sensor/raw/master/img/list.jpg)|
|[Get ONE Now](https://jp.seeedstudio.com/Raspberry-Pi-3-Model-B-p-2625.html)|[Get ONE Now](https://jp.seeedstudio.com/Grove-Base-Hat-for-Raspberry-Pi-p-3186.html)|[Get ONE Now](https://jp.seeedstudio.com/Grove-Temp%26Humi-Sensor-p-745.html)|


- **ステップ2**　Grove Base HatをRaspberryにインサートします。
- **ステップ3**　Grove-温度や湿度センサーをBase Hatの ポート12に接続します。
- **ステップ4**　USBケーブルでRaspberry Piをコンピュータに接続します。


![](https://github.com/SeeedDocument/Grove-TemperatureAndHumidity_Sensor/raw/master/img/Temp_Hum_Hat.jpg)


ノート！
    ステップ3では、Grove-温度や湿度センサーを **どちらのGPIOポート** に接続してもいけますが、それに伴い、マンドで相応しいポートナンバーに変更しなければなりません。


#### ソフトウェア

- **ステップ1**　[Setting Software](http://wiki.seeedstudio.com/Grove_Base_Hat_for_Raspberry_Pi/#installation) によって開発環境を構成します。
- **ステップ2**grove.py libraryのクローンによってソースファイルをダウンロードします。

```
cd ~
git clone https://github.com/Seeed-Studio/grove.py

```

- **ステップ3**　コードの実行のため、以下のコマンドを実行させます。

```
cd grove.py/grove
python grove_temperature_humidity_sensor.py 11 12

```

ノート！
    1.  そのプログラムを実行させるには、定義ラインを +++python grove_temperature_humidity_sensor.py DHT type pin+++　というようにしてください。このモジュールで、DHTタイプは11で、上の例では、Grove-温度や湿度センサーはピン12に接続されます。
    2. Grove-温度や湿度センサーとGrove-温度や湿度センサーPRO([Grove-Temperature and Humidity Sensor Pro](http://wiki.seeedstudio.com/Grove-Temperature_and_Humidity_Sensor_Pro/))は同じpythonコード( grove_temperature_humidity_sensor.py)を共有しますが、その違いはGrove-温度や湿度センサーPROのDHT タイプは22で、Grove-温度や湿度センサーのは11です。

以下はgrove_temperature_humidity_sensor.pyコード。

```python

import RPi.GPIO as GPIO
# from grove.helper import *
def set_max_priority(): pass
def set_default_priority(): pass
from time import sleep

GPIO.setmode(GPIO.BCM)
GPIO.setwarnings(False)

PULSES_CNT = 41

class DHT(object):
    DHT_TYPE = {
        'DHT11': '11',
        'DHT22': '22'
    }

    MAX_CNT = 320

    def __init__(self, dht_type, pin):        
        self.pin = pin
        if dht_type != self.DHT_TYPE['DHT11'] and dht_type != self.DHT_TYPE['DHT22']:
            print('ERROR: Please use 11|22 as dht type.')
            exit(1)
        self._dht_type = '11'
        self.dht_type = dht_type
        GPIO.setup(self.pin, GPIO.OUT)

    @property
    def dht_type(self):
        return self._dht_type

    @dht_type.setter
    def dht_type(self, type):
        self._dht_type = type
        self._last_temp = 0.0
        self._last_humi = 0.0

    def _read(self):
        # Send Falling signal to trigger sensor output data
        # Wait for 20ms to collect 42 bytes data
        GPIO.setup(self.pin, GPIO.OUT)
        set_max_priority()

        GPIO.output(self.pin, 1)
        sleep(.2)

        GPIO.output(self.pin, 0)
        sleep(.018)

        GPIO.setup(self.pin, GPIO.IN)
        # a short delay needed
        for i in range(10):
            pass

        # pullup by host 20-40 us
        count = 0
        while GPIO.input(self.pin):
            count += 1
            if count > self.MAX_CNT:
                # print("pullup by host 20-40us failed")
                set_default_priority()
                return None, "pullup by host 20-40us failed"

        pulse_cnt = [0] * (2 * PULSES_CNT)
        fix_crc = False
        for i in range(0, PULSES_CNT * 2, 2):
            while not GPIO.input(self.pin):
                pulse_cnt[i] += 1
                if pulse_cnt[i] > self.MAX_CNT:
                    # print("pulldown by DHT timeout %d" % i)
                    set_default_priority()
                    return None, "pulldown by DHT timeout %d" % i

            while GPIO.input(self.pin):
                pulse_cnt[i + 1] += 1
                if pulse_cnt[i + 1] > self.MAX_CNT:
                    # print("pullup by DHT timeout %d" % (i + 1))
                    if i == (PULSES_CNT - 1) * 2:
                        # fix_crc = True
                        # break
                        pass
                    set_default_priority()
                    return None, "pullup by DHT timeout %d" % i

        # back to normal priority
        set_default_priority()

        total_cnt = 0
        for i in range(2, 2 * PULSES_CNT, 2):
            total_cnt += pulse_cnt[i]

        # Low level ( 50 us) average counter
        average_cnt = total_cnt / (PULSES_CNT - 1)
        # print("low level average loop = %d" % average_cnt)
       
        data = ''
        for i in range(3, 2 * PULSES_CNT, 2):
            if pulse_cnt[i] > average_cnt:
                data += '1'
            else:
                data += '0'
        
        data0 = int(data[ 0: 8], 2)
        data1 = int(data[ 8:16], 2)
        data2 = int(data[16:24], 2)
        data3 = int(data[24:32], 2)
        data4 = int(data[32:40], 2)

        if fix_crc and data4 != ((data0 + data1 + data2 + data3) & 0xFF):
            data4 = data4 ^ 0x01
            data = data[0: PULSES_CNT - 2] + ('1' if data4 & 0x01 else '0')

        if data4 == ((data0 + data1 + data2 + data3) & 0xFF):
            if self._dht_type == self.DHT_TYPE['DHT11']:
                humi = int(data0)
                temp = int(data2)
            elif self._dht_type == self.DHT_TYPE['DHT22']:
                humi = float(int(data[ 0:16], 2)*0.1)
                temp = float(int(data[17:32], 2)*0.2*(0.5-int(data[16], 2)))
        else:
            # print("checksum error!")
            return None, "checksum error!"

        return humi, temp

    def read(self, retries = 15):
        for i in range(retries):
            humi, temp = self._read()
            if not humi is None:
                break
        if humi is None:
            return self._last_humi, self._last_temp
        self._last_humi,self._last_temp = humi, temp
        return humi, temp

Grove = DHT


def main():
    import sys
    import time

    if len(sys.argv) < 3:
        print('Usage: {} dht_type pin'.format(sys.argv[0]))
        sys.exit(1)

    typ = sys.argv[1]
    sensor = DHT(typ, int(sys.argv[2]))
    
    while True:
        humi, temp = sensor.read()
        if not humi is None:
            print('DHT{0}, humidity {1:.1f}%, temperature {2:.1f}*'.format(sensor.dht_type, humi, temp))
        else:
            print('DHT{0}, humidity & temperature: {1}'.format(sensor.dht_type, temp))
        time.sleep(1)


if __name__ == '__main__':
    main()



```

完成！
   間違いがなければ、結果が以下のように出てきます。
    
```python

pi@raspberrypi:~/grove.py/grove $ python grove_temperature_humidity_sensor.py 11 12
DHT11, humidity 31.0%, temperature 22.0*
DHT11, humidity 30.0%, temperature 23.0*
DHT11, humidity 29.0%, temperature 23.0*
^CTraceback (most recent call last):
  File "grove_temperature_humidity_sensor.py", line 192, in <module>
    main()
  File "grove_temperature_humidity_sensor.py", line 188, in main
    time.sleep(1)
KeyboardInterrupt


```


 ++ctrl+c++を押すと、このプログラムを終了することができます。


### Raspberry Piでは(GrovePi_Plusも必要)

#### ハードウェア

- **ステップ1**　以下の物が必要です。

| Raspberry pi | GrovePi_Plus | Temperature&Humidity Sensor|
|--------------|-------------|-----------------|
|![enter image description here](https://github.com/SeeedDocument/Grove_Ultrasonic_Ranger/raw/master/img/rasp.jpg)|![enter image description here](https://github.com/SeeedDocument/Grove_Ultrasonic_Ranger/raw/master/img/Grovepi%2B.jpg)|![enter image description here](https://github.com/SeeedDocument/Grove-TemperatureAndHumidity_Sensor/raw/master/img/list.jpg)|
|[Get One Now](https://jp.seeedstudio.com/Raspberry-Pi-3-Model-B-p-2625.html)|[Get One Now](https://jp.seeedstudio.com/GrovePi%2B-p-2241.html)|[Get One Now](https://jp.seeedstudio.com/Grove-Temperature%26Humidity-Sensor-Pro-p-838.html)|


- **ステップ2**　GrovePi_PlusをRaspberryにインサートします。
- **ステップ3**　Grove-温度や湿度センサーをGrovePi_Plusの **D4** ポートに接続します。

- **ステップ4**　USBケーブルでRaspberryをコンピュータに接続します。

![](https://github.com/SeeedDocument/Grove-TemperatureAndHumidity_Sensor/raw/master/img/connect_pi.jpg)


#### ソフトウェア
- **ステップ１**　[Setting Software](https://www.dexterindustries.com/GrovePi/get-started-with-the-grovepi/setting-software/) によって開発環境を構成します。

- **ステップ2**[Updating the Firmware](https://www.dexterindustries.com/GrovePi/get-started-with-the-grovepi/updating-firmware/)によって最新のGrovePiのファームウェアをアップデートします。



ヒント！
   このWikiページで、採用されたパスは **/home/pi/Desktop/GrovePi**ではなく、 **~/GrovePi/**ですが、ステップ2でのパスとステップ3のは同じようにご確認ください。

ノート！
    センサーがエラーをしないように、ファームウェアをアップデートしてください。

- **ステップ3**　GitでGithubリポジトリをコロンします。

```
cd ~
git clone https://github.com/DexterInd/GrovePi.git

```

-	**ステップ4**　コードをチェックしてください。
```python

cd ~/GrovePi/Software/Python
sudo nano grove_dht_pro.py

```

コードは以下のようです。
```python
import grovepi
import math
# Connect the Grove Temperature & Humidity Sensor Pro to digital port D4
# This example uses the blue colored sensor.
# SIG,NC,VCC,GND
sensor = 4  # The Sensor goes on digital port 4.

# temp_humidity_sensor_type
# Grove Base Kit comes with the blue sensor.
blue = 0    # The Blue colored sensor.
white = 1   # The White colored sensor.

while True:
    try:
        # This example uses the blue colored sensor.
        # The first parameter is the port, the second parameter is the type of sensor.
        [temp,humidity] = grovepi.dht(sensor,blue)  
        if math.isnan(temp) == False and math.isnan(humidity) == False:
            print("temp = %.02f C humidity =%.02f%%"%(temp, humidity))

    except IOError:
        print ("Error")

```

 ++ctrl+x++ を押して、nanoを終了します。
ノート！
    Grove-温度や湿度センサーとGrove-温度や湿度センサーPROは同じpythonコード(
    `grove_dht_pro.py`)を共有しますが、その違いはセンテンス： `[temp,humidity] = grovepi.dht(sensor,blue)`にあり、Grove-温度や湿度センサーの場合には、パラメータ
    `blue` が使われ、Grove-温度や湿度センサーPROの場合には、パラメータ `white` が使われます。
このセンサーのデフォールト値はblueで、変更する必要はありません。

-	**ステップ5**　以下のコマンドを実行させます
```
sudo python grove_dht_pro.py
```

結果は以下のようです。
```python

pi@raspberrypi:~/GrovePi/Software/Python $ sudo python grove_dht_pro.py
temp = 26.00 C humidity =40.00%
temp = 26.00 C humidity =40.00%
temp = 26.00 C humidity =40.00%
temp = 26.00 C humidity =40.00%
temp = 26.00 C humidity =40.00%
temp = 26.00 C humidity =40.00%
temp = 26.00 C humidity =40.00%
temp = 26.00 C humidity =40.00%
temp = 26.00 C humidity =40.00%
temp = 26.00 C humidity =40.00%
temp = 26.00 C humidity =40.00%
temp = 26.00 C humidity =40.00%

```



## 関連リソース


- **[Zip]** [温度や湿度センサー eagle ファイル(Temperature&Humidity Sensor eagle file)](https://raw.githubusercontent.com/SeeedDocument/Grove-TemperatureAndHumidity_Sensor/master/res/Temperature_Humidity.zip)

- **[Zip]** [温度や湿度センサー　ライブラリ(Temperature&Humidity Sensor Library)](https://github.com/Seeed-Studio/Grove_Temperature_And_Humidity_Sensor)

- **[Codecraft]** [CDCファイル (CDC File)](https://raw.githubusercontent.com/SeeedDocument/Grove-TemperatureAndHumidity_Sensor/master/res/Grove_Temperature_and_Humidity_Sensor_CDC_File.zip)


## プロジェクト

**トイレ管理システム(Toilet Management System)**：このシステムによっては、人がシングルのトイレを効率的に使用できます。

<iframe frameborder='0' height='327.5' scrolling='no' src='https://project.seeedstudio.com/taifur/toilet-management-system-8e2786/embed' width='350'></iframe>


## 技術サポート
何かご不明な点がございましたら、[フォーラム](http://forum.seeedstudio.com/)でお問い合わせ下さい。
<br /><p style="text-align:center"><a href="https://www.seeedstudio.com/act-4.html?utm_source=wiki&utm_medium=wikibanner&utm_campaign=newproducts" target="_blank"><img src="https://github.com/SeeedDocument/Wiki_Banner/raw/master/new_product.jpg" /></a></p>　　
　　
　　　　

　　※このページは英語バージョンのウィキに基づいて翻訳されたものです。何かご不明な点などございましたら、英語バージョンをご参考下さい。