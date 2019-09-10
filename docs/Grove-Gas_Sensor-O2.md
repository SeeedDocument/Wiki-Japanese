<title>Grove-酸素センサー(Grove-Gas Sensor O2)</title>
<meta name="description" content="Grove-Gas Sensor O2は電気化学セルという原理によって、空気中酸素濃度の測定に用いられるセンサーです。空気中酸素濃度に比例する電圧値を出力したら、酸素濃度線形特性グラフによると、実時間の酸素濃度が分かります。所在環境酸素濃度の測定に最適なセンサーの一種です。">
<meta name="author" content="minxuan">  　  
  
    
      
        

![enter image description here](https://raw.githubusercontent.com/SeeedDocument/Grove_Gas_Sensor_O2/master/images/cover.jpg)
  

Grove-Gas Sensor O2は電気化学セルという原理によって、空気中酸素濃度の測定に用いられるセンサーです。空気中酸素濃度に比例する電圧値を出力したら、酸素濃度線形特性グラフによると、実時間の酸素濃度が分かります。所在環境酸素濃度の測定に最適なセンサーの一種です。Grove-Gas Sensor O2は有機反応に基づくモジュールであり、空気中のガスとの化学反応で電流が発生するので、外部電流供給の必要はなく、その出力電圧も環境の変化によって実時間に変化します。


<iframe width="800" height="450" src="https://www.youtube.com/embed/4df5kaaKa6I" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

[![](https://github.com/SeeedDocument/BeagleBone_Green_Wireless/blob/master/images/get_one_now.png?raw=true)](http://jp.seeedstudio.com/grove-gas-sensoro2-p-1541.html)

!!!Tip
     [Seeed Gas Sensor 選択ガイド](http://wiki.seeedstudio.com/Seeed_Gas_Sensor_Selection_Guide/)へ、最適なセンサーを選びましょう！

## 商品特性  

* 高精度
* 高感度
* 広い線形範囲
* 強い防干渉能力
* 穏やかで、信頼できる

!!!Tip
   Groveモジュールの詳細情報は[Grove System](http://wiki.seeedstudio.com/Grove_System/)でご覧ください。　　
   
## 商品仕様

|項目	| パラメーター |
|-------|---------------|
|測定範囲	| 0-25% |
|耐用年数	| 2年 |
|感度	| 0.05~0.15 mA(空気中) |
|使用温度範囲 |	-20℃～50℃ |
|予熱時間	| 20分間|
|入力電圧|3.3V / 5V|


## ハードウェア部分

**電圧変換機**

![](https://github.com/SeeedDocument/Grove_Gas_Sensor_O2/raw/master/images/Converter.png)

XC6206332MRは入力電圧3.3V / 5Vを3.3Vに変換します。

**ME2-O2電流電源（ME2-O2 current source）**

![](https://github.com/SeeedDocument/Grove_Gas_Sensor_O2/raw/master/images/ME2-O2.png)
　　
電流電源はME2-O2で、ラベル＃3ポイントの電圧はR7 *電流(ME2-O2)です。


**アンプ（Amplifer）**

![](https://github.com/SeeedDocument/Grove_Gas_Sensor_O2/raw/master/images/Amplifer.png)

アンプで獲得数値は121で、SIGAの電圧はラベル＃3の121倍です。

![](https://github.com/SeeedDocument/Grove_Gas_Sensor_O2/raw/master/images/concentration_current.png)

これはME2-O2出力電流と酸素濃度との相関関係であり、20％の酸素濃度には、電流数値は約120uAです。そのため、Grove SIGA電圧 @ 濃度20% = R7 * 電流(ME2-O2) * 121 = 100 * 120uA * 121 = 1.452V。

!!!Warning
    個体差によってME2-O2の電流範囲は80uA～160uAで、センサーの出力電圧も伴って変化します。初めにはセンサーを空気中に置いており、参考数値とする出力電圧を獲得できるようにしてください。初めには、 [この例](https://github.com/SeeedDocument/Grove_Gas_Sensor_O2/raw/master/resources/Read_O2_value.zip) に照らし合わせて校正し、それからセンサーの表示数値を読み取ります。

## サポートされるプラットフォーム

| Arduino                                                                                             | Raspberry Pi                                                                                             | BeagleBone                                                                                      | Wio                                                                                               | LinkIt ONE                                                                                         |
|-----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|
| ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/arduino_logo.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/raspberry_pi_logo_n.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/bbg_logo_n.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/wio_logo_n.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/linkit_logo_n.jpg) |

!!!Tip
    以上のプラットフォームは代表的或いは理論的に互換性があるソフトウェアです。ほとんどの場合は、こちらはソフトウェアライブラリとコードの例を提供し、全部のMCUプラットフォームうにライブラリやデモのコードを提供することではありません。そのため、ライブラリを作ることが必要です。


## 入門ガイド

!!!Note 本章節の内容はWin10とArduino IDE 1.6.9に基づいて展開されます。

このモジュールの操作が簡単で、コントローラのADCインプットに信号ピン（Groveケーブルの黄色ピン）を接続したらOKです。コントローラに内部ADCがない場合は、製品 [Grove - I2C ADC](http://jp.seeedstudio.com/Grove-I2C-ADC-p-1580.html) がお薦めです。 

ここでは簡単なデモでGrove-ガスセンサーの操作を紹介します。まず、以下の物が必要です。

| Seeeduino V4 | Grove - Gas Sensor(O2) | Base Shield |
|--------------|----------------------|-----------------|
|![enter image description here](https://raw.githubusercontent.com/SeeedDocument/Grove_Light_Sensor/master/images/gs_1.jpg)|![enter image description here](https://raw.githubusercontent.com/SeeedDocument/Grove_Gas_Sensor_O2/master/images/gas_sensor_210.jpg)|![enter image description here](https://raw.githubusercontent.com/SeeedDocument/Grove_Light_Sensor/master/images/gs_4.jpg)|
|[Get ONE Now](http://jp.seeedstudio.com/Seeeduino-V4.2-p-2517.html)|[Get ONE Now](http://jp.seeedstudio.com/grove-gas-sensoro2-p-1541.html)|[Get ONE Now](http://jp.seeedstudio.com/Grove-Universal-4-Pin-20cm-Unbuckled-Cable-%285-PCs-Pack%29-p-749.html)|



### 接続

Groveシリーズ　モジュールでは、溶接やブレードボード作りの必要はなく、ベースシールドにモジュールを正確に接続したらOKです。このデモでは、Groveモジュールが１つだけあります。

* このデモでは、アナログ出力モジュールであるGrove-音声センサーを **A0** に接続します。

![enter image description here](https://raw.githubusercontent.com/SeeedDocument/Grove_Gas_Sensor_O2/master/images/connection.jpeg)


### Arduinoにコードをアップロードする

以下のコードをArduino IDEにコピーします。


```
// Grove - Gas Sensor(O2) test code
// Note:
// 1. It need about about 5-10 minutes to preheat the sensor
// 2. modify VRefer if needed

const float VRefer = 3.3;       // voltage of adc reference

const int pinAdc   = A0;

void setup() 
{
    // put your setup code here, to run once:
    Serial.begin(9600);
    Serial.println("Grove - Gas Sensor Test Code...");
}

void loop() 
{
    // put your main code here, to run repeatedly:
    float Vout =0;
    Serial.print("Vout =");

    Vout = readO2Vout();
    Serial.print(Vout);
    Serial.print(" V, Concentration of O2 is ");
    Serial.println(readConcentration());
    delay(500);
}

float readO2Vout()
{
    long sum = 0;
    for(int i=0; i<32; i++)
    {
        sum += analogRead(pinAdc);
    }
    
    sum >>= 5;
    
    float MeasuredVout = sum * (VRefer / 1023.0);
    return MeasuredVout;
}

float readConcentration()
{
    // Vout samples are with reference to 3.3V
    float MeasuredVout = readO2Vout();
    
    //float Concentration = FmultiMap(MeasuredVout, VoutArray,O2ConArray, 6);
    //when its output voltage is 2.0V,
    float Concentration = MeasuredVout * 0.21 / 2.0;
    float Concentration_Percentage=Concentration*100;
    return Concentration_Percentage;
}

```

そして正確のBoardとCOMポートを選んで、アップロード　ボタンをクリックします。このプロセスは何秒の時間がかかります。

### データ獲得

Arduino IDEのシリアルモニターを開くと、データが獲得できます。

!!!Tip
    高精度のデータを獲得するためには、20～30分間の予熱時間が必要です。
    
![enter image description here](https://raw.githubusercontent.com/SeeedDocument/Grove_Gas_Sensor_O2/master/images/data.png)






## 関連リソース

* [ME2-O2データシート（ME2-O2 Datasheet）](https://github.com/SeeedDocument/Grove_Gas_Sensor_O2/raw/master/resources/ME2-O2-D20%200-25%25%20Manual%20%28ver1.2%29.pdf)
* [Eagleファイルでの回路図（Schematic in Eagle File）](https://github.com/SeeedDocument/Grove_Gas_Sensor_O2/raw/master/resources/Schematics_O2.zip)
* [ドキュメントでのGithubリポジトリ（Github Repository of this Document）](https://github.com/SeeedDocument/Grove_Gas_Sensor_O2)


## プロジェクト

**LoRa IoTea**：茶園に応用してきた自動的情報収集システムで、知能農業の一部分であります。

<iframe frameborder='0' height='327.5' scrolling='no' src='https://www.hackster.io/SeeedStudio/seeed-lora-iotea-solution-b5ee95/embed' width='350'></iframe>

**雨降りや照明付けの鉢植え** ：すばらしいデザインで水をやります。

<iframe frameborder='0' height='327.5' scrolling='no' src='https://www.hackster.io/team-seeed-ae/a-plant-box-with-lighting-and-raining-bfc59b/embed' width='350'></iframe>

## 技術サポート
何かご不明な点がございましたら、 [フォーラム](http://forum.seeedstudio.com/)でお問い合わせ下さい<br /><p style="text-align:center"><a href="https://www.seeedstudio.com/act-4.html?utm_source=wiki&utm_medium=wikibanner&utm_campaign=newproducts" target="_blank"><img src="https://github.com/SeeedDocument/Wiki_Banner/raw/master/new_product.jpg" /></a></p>　　
　　
　　
　　※このページは英語バージョンのウィキに基づいて翻訳されたものです。何かご不明な点などございましたら、英語バージョンをご参考下さい。