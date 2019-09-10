<title>Grove-ダストセンサー(Grove-Dust Sensor)</title>
<meta name="description" content="Grove-ダストセンサーは空気中粉塵濃度の測定によって、空気質を反映するモジュールです。直径 1μmの微粒子までも検出でき、空気清浄機システムに信頼できるデータを提供できます。">
<meta name="author" content="minxuan">  　　  
  
    
  

![](https://github.com/SeeedDocument/Grove_Dust_Sensor/raw/master/img/Dust1.JPG)

Grove-Dust Sensor 

Grove-ダストセンサーは空気中粉塵濃度の測定によって、空気質を反映するモジュールです。一定時間内のLowパルスの占有時間（Low Pulse Occupancy time:LPO time）によりParticulate Matterレベル(PMレベル)が分かります。PM濃度はLPO timeに正比例します。Grove-ダストセンサーは直径 1μmの微粒子までも検出でき、空気清浄機システムに信頼できるデータを提供できます。


<iframe width="800" height="450" src="https://www.youtube.com/embed/4df5kaaKa6I" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

!!!Tip
    - このセンサーはダストの重さを測ることではなく、ダストの飛散量を計測ことによりダスト濃度を測定します。計算単位はpcs/L 或いは pcs/0.01cfです。
    
   
   - ご使用になる場合のご注意！
        - 使っている時はセンサーを直立させてください。
        - 初めて使う時には、3分間の予熱時間が必要です。
        - 不注意な操作で故障を起こることは可能です。
        - 以下の小さな部件(赤長方形で)は工場設定用で、デフォルト設定を変更 **しないでください。** 


<p style=":center"><a href="https://jp.seeedstudio.com/Grove-Dust-Sensor-p-1050.html" target="_blank"><img src="https://github.com/SeeedDocument/wiki_english/raw/master/docs/images/get_one_now_small.png" width="200" height="38"  border=0 /></a></p>

## バージョン

| バージョン              | 変更                                   | 発行日 |
|------------------------------|-------------------------------------------|---------------|
|Grove-Dust Sensor V1.0        | オリジナル                                   | 2012年      |     


## 商品特性

- タバコ煙濃度や室内の粉塵濃度を敏感に正確に反映できます。
- 内蔵の空気加熱装置で自動的に空気を集めることができます。
- メンテナンスは容易で、高感度は長持ちします。
- アウトプットが二つあり、 1μm以上と、2.5μm以上の微粒子濃度を同時に出力できます。
- 軽便で、組み立ては簡単です。

!!!Tip
    Groveモジュールの詳細情報は[Grove System](http://wiki.seeedstudio.com/Grove_System/)でご覧ください。

## 商品仕様


|項目|	基準|	単位 |
|----|-----|-------|
|VCC |	4.75~5.75|	V    |
|待機電流|	90|	mA|
|濃度測定範囲|	0~28,000 / 0 ~ 8000	|	pcs/liter / pcs/0.01cf|
|操作温度|	0~45|	°C|
|出力|	負ロジック、デジタル出力、高電圧：4.0V以上(Rev.2)、低電圧：0.7V以下|-|
|微粒子測定直径|	>1 |μm|
|商品サイズ|	59(W) × 45(H) × 22(D) |mm|
|湿度範囲|	95％rh以下|-|


!!!Tip
    最新バージョンの商品は、出力電圧は4.0Vから4.5Vになります。


## サポートされるプラットフォーム
| Arduino                                                                                             | Raspberry Pi                                                                                             | BeagleBone                                                                                      | Wio                                                                                               | LinkIt ONE                                                                                         |
|-----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|
| ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/arduino_logo.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/raspberry_pi_logo.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/bbg_logo_n.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/wio_logo_n.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/linkit_logo_n.jpg) |

!!!Tip
    以上のプラットフォームは代表的或いは理論的に互換性があるソフトウェアです。ほとんどの場合は、こちらはソフトウェアライブラリとコードの例を提供し、全部のMCUプラットフォームうにライブラリやデモのコードを提供するではありません。そのため、ライブラリを作ることが必要です。


## 実的応用

- 空気清浄機
- 空気質の監視、測定
- クーラー
- ベンチレーター

## 入門ガイド

!!!Tip
   初めてArduinoを操作する場合は、 [Getting Started with Arduino](http://wiki.seeedstudio.com/Getting_Started_with_Arduino/) でご覧ください！


### Arduinoでは

**ハードウェア部分**

- **ステップ1** 以下の物が必要です。

| Seeeduino V4.2 | Base Shield|  Grove-Dust Sensor |
|--------------|-------------|-----------------|
|![enter image description here](https://github.com/SeeedDocument/wiki_english/raw/master/docs/images/seeeduino_v4.2.jpg)|![enter image description here](https://github.com/SeeedDocument/wiki_english/raw/master/docs/images/base_shield.jpg)|![enter image description here](https://github.com/SeeedDocument/Grove_Dust_Sensor/raw/master/img/Dust_sensor%20-_s.JPG)|
|[Get One Now](http://jp.seeedstudio.com/Seeeduino-V4.2-p-2517.html)|[Get One Now](https://jp.seeedstudio.com/Base-Shield-V2-p-1378.html)|[Get One Now](https://jp.seeedstudio.com/Grove-Dust-Sensor-p-1050.html)|

- **ステップ2** Grove-ダストセンサーをGrove-Base ShieldのD8ポートに接続します。
- **ステップ3** Grove - Base ShieldをSeeeduinoにインサートします。
- **ステップ4** USBケーブルでSeeeduinoをコンピュータに接続します。

![](https://github.com/SeeedDocument/Grove_Dust_Sensor/raw/master/img/seeeduino_dust.jpg)

!!!Tip
	Grove-Base Shieldがない場合は、以下のようにGrove-ダストセンサーをSeeeduinoに接続します。

| Seeeduino |  Grove-ダストセンサー |
|-----------|-----------------|
| 5V        | 赤             |
| GND       | 黒           |
| NC        | 白           |
| D8        | 黄          | 

**ソフトウェア部分**

- **ステップ1** Arduio IDEで以下のコードをコピーして、Arduioにアップロードします。アップロード方法が分からない場合、 [how to upload code](http://wiki.seeedstudio.com/Upload_Code/)でご覧ください。


```
int pin = 8;
unsigned long duration;
unsigned long starttime;
unsigned long sampletime_ms = 30000;//sampe 30s ;
unsigned long lowpulseoccupancy = 0;
float ratio = 0;
float concentration = 0;

void setup() 
{
    Serial.begin(9600);
    pinMode(pin,INPUT);
    starttime = millis();//get the current time;
}

void loop() 
{
    duration = pulseIn(pin, LOW);
    lowpulseoccupancy = lowpulseoccupancy+duration;

    if ((millis()-starttime) > sampletime_ms)//if the sampel time == 30s
    {
        ratio = lowpulseoccupancy/(sampletime_ms*10.0);  // Integer percentage 0=>100
        concentration = 1.1*pow(ratio,3)-3.8*pow(ratio,2)+520*ratio+0.62; // using spec sheet curve
        Serial.print(lowpulseoccupancy);
        Serial.print(",");
        Serial.print(ratio);
        Serial.print(",");
        Serial.println(concentration);
        lowpulseoccupancy = 0;
        starttime = millis();
    }
}

```

- **ステップ2** このプリグラムで、Seeeduinoは30秒での低ロジック(logic low)	の持続時間をサンプルします。その持続時間は環境のダスト濃度を反映できます。シリアルモニターを開き、コンピュータのシリアルポートを通じて空気質の測定数値が獲得できます。

![](https://github.com/SeeedDocument/Grove_Dust_Sensor/raw/master/img/Serial.png)

**専門語：**

- **Lowpulseoccupancy：** 30秒で測定した低パルスの占有時間(LPO timeの占有時間)を示します。単位はマイクロ秒(µs)。

- **Ratio：** サンプリング時間に占有するLPOタイム(LPO time)のレベルの示し方です。

- **Concentration：** 物理学の意味がある数値記号であり、低パルス時間(LPO time)と以下の特性グラフによって計測されます。
![](https://raw.githubusercontent.com/SeeedDocument/Grove_Dust_Sensor/master/image/600px-Characteristics.jpg)

- これはオフィスで測定したダスト濃度のグラフです。

![](https://raw.githubusercontent.com/SeeedDocument/Grove_Dust_Sensor/master/image/600px-Dust_sensor_4.jpg)

グラフによって、夜のダスト濃度は非常に低く、午後では高いということが分かります。濃度がある数値を超える場合は、閾値の設定ができます。また、センサーに扇風機をつけ、ピン5とGroundとの間で10kΩの抵抗器を追加すると、センサーはより敏感になります。詳細情報は [blog of A.J](https://indiaairquality.com/2014/12/14/measuring-the-pickle-jr-a-modified-ppd42-with-an-attached-fan/)　でご覧ください。



### Raspberry Piでは

**ハードウェア部分**

- **ステップ1** 以下の物が必要です。

| Raspberry pi | GrovePi_Plus | Grove-Dust Sensor |
|--------------|-------------|-----------------|
|![enter image description here](https://github.com/SeeedDocument/wiki_english/raw/master/docs/images/rasp.jpg)|![enter image description here](https://github.com/SeeedDocument/wiki_english/raw/master/docs/images/Grovepi%2B.jpg)|![enter image description here](https://github.com/SeeedDocument/Grove_Dust_Sensor/raw/master/img/Dust_sensor%20-_s.JPG)|
|[Get One Now](https://jp.seeedstudio.com/Raspberry-Pi-3-Model-B-p-2625.html)|[Get One Now](https://jp.seeedstudio.com/GrovePi%2B-p-2241.html)|[Get One Now](https://jp.seeedstudio.com/Grove-Dust-Sensor-p-1050.html)|


- **ステップ2** GrovePi_PlusをRaspberryにインサートします。
- **ステップ3** Grove-ダストセンサーをGrovePi_PlusのD2ポートに接続します。
- **ステップ4** USBケーブルでSRaspberryをコンピュータに接続します。


![](https://github.com/SeeedDocument/Grove_Dust_Sensor/raw/master/img/rpi_dust.jpg)

**ソフトウェア部分**

- **ステップ1** [Setting Software](https://www.dexterindustries.com/GrovePi/get-started-with-the-grovepi/setting-software/) によって、開発環境を構成します。
- **ステップ2** GitでGithubリポジトリをコピーします。

```
cd ~
git clone https://github.com/DexterInd/GrovePi.git

```

- **ステップ3** 以下のコマンドを実行させます。


```python
cd ~/GrovePi/Software/Python
python grove_dust_sensor.py
```

以下は　the grove_dust_sensor.pyコードです。

```python
import time
import grovepi
import atexit

atexit.register(grovepi.dust_sensor_dis)

print("Reading from the dust sensor")
grovepi.dust_sensor_en()
while True:
    try:
		[new_val,lowpulseoccupancy] = grovepi.dustSensorRead()
		if new_val:
			print(lowpulseoccupancy)
		time.sleep(5) 

    except IOError:
        print ("Error")

```

- **ステップ4** 以下のようなダスト測定結果が出てきます。

```python
pi@raspberrypi:~/GrovePi/Software/Python $ python grove_dust_sensor.py 
Reading from the dust sensor
14029
2621
1725
1978
2533
1619
```

## 関連プロジェクト

Grove-ダストセンサーを使ってプロジェクトをスタートすることに興味を持つなら、以下のプロジェクトは参考になります。

**空気質測定箱(Air Quality Box)**

![](https://raw.githubusercontent.com/SeeedDocument/Grove_Dust_Sensor/master/image/600px-Overview0.png)

これはSeeeduinoと[Grove](http://jp.seeedstudio.com/wiki/Grove_System)　によって作られたIoTデモです。

空気中の微粒子が人に悪い影響を与えるため、現在、周辺の空気質は注目されます。常に我々は政府機関から環境情報をもらいますが、その情報は一定地域の平均水準を反映するだけで、身近な周辺環境の環境情報ではありません。

[![](https://raw.githubusercontent.com/SeeedDocument/Grove_Dust_Sensor/master/image/200px-Wiki_makeitnow_logo.png)](http://www.instructables.com/id/Air-Quality-Test-Box/?ALLSTEPS)


## FAQs

**Q1：Seeeduino Stalker (3.3V logic)と合わせてGrove-ダストセンサーを操作したいんですが、どうしましょうか？**

A1：Seeeduino Stalkerなど他のボードと合わせて使うには、Grove-ダストセンサーの出力信号を3.3V logicに設定します。Grove-ダストセンサーの出力は低ロジック(Logic Low)で0.7V、高ロジック(Logic High)では4.0Vです。3.3V logicと互換性にある状態になるには、分圧回路或いはTTL logic レベル変換機を使ってください。
## 関連リソース

- **[データシート]** [Grove-ダストセンサー　データシート](https://github.com/SeeedDocument/Grove_Dust_Sensor/raw/master/resource/Grove_-_Dust_sensor.pdf)
- **[データシート]** [De-construction of the Shinyei PPD42NS dust sensor Made by Tracy Allen](https://github.com/SeeedDocument/Grove_Dust_Sensor/raw/master/resource/ShinyeiPPD42NS_Deconstruction_TracyAllen.pdf)
- **[デモ]** [安いネットワーキングPM2.5モニターを作る(Building a low-cost networked PM2.5 monitor )](https://indiaairquality.com/2014/12/14/building-pickle-jr-the-low-cost-networked-pm2-5-monitor-part-2/) -- Made by A.J.
- **[デモ]** [Measuring the Pickle Jr. – a modified PPD42 with an attached fan.](https://indiaairquality.com/2014/12/14/measuring-the-pickle-jr-a-modified-ppd42-with-an-attached-fan/) -- Made by A.J.
- **[デモ]** [Testing the Shinyei PPD42NS](http://irq5.io/2013/07/24/testing-the-shinyei-ppd42ns/) -- Made by darell tan
- **[デモ]** [空気質モニター(Air Quality Monitoring)](http://www.howmuchsnow.com/arduino/airquality/grovedust/) -- Made by Chris Nafis


## Projects

**Air Quality Box** :Monitor air quality around you

<iframe frameborder='0' height='327.5' scrolling='no' src='https://www.hackster.io/ye-xiaobo/air-quality-box-d7658a/embed' width='350'></iframe>

**loTを応用してきた知能農業(Smart Crops: Implementing IoT in Conventional Agriculture)** ：モニターリングなど技術の応用によって、Heliumを使って自然保護するために力を注ぎましょう。

<iframe frameborder='0' height='327.5' scrolling='no' src='https://www.hackster.io/gabogiraldo/smart-crops-implementing-iot-in-conventional-agriculture-3674a6/embed' width='350'></iframe>

**LoRa loTea** ：茶園に応用してきた自動的情報収集システムで、知能農業の一部分であります。

<iframe frameborder='0' height='327.5' scrolling='no' src='https://www.hackster.io/SeeedStudio/seeed-lora-iotea-solution-b5ee95/embed' width='350'></iframe>

## 技術サポート
何かご不明な点がございましたら、  [フォーラム](http://forum.seeedstudio.com/)でお問い合わせ下さい。 <br /><p style="text-align:center"><a href="https://www.seeedstudio.com/act-4.html?utm_source=wiki&utm_medium=wikibanner&utm_campaign=newproducts" target="_blank"><img src="https://github.com/SeeedDocument/Wiki_Banner/raw/master/new_product.jpg" /></a></p>　　
　　
　　　　
　　※このページは英語バージョンのウィキに基づいて翻訳されたものです。何かご不明な点などございましたら、英語バージョンをご参考下さい。 