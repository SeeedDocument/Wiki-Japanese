<title>micro:bit Grove 入門キット (Grove Inventor Kit for micro:bit)</title>
<meta name="description" content="BBC micro:bitはマイクロコンピュータの一種です。これを使えば、エレクトリックやコーディングに関する知識が少なくとも、使用者は創造性を生かすことがよくできます。しかし、創造性を生かすには、BBC micro:bitだけを使っては不十分です。そのため、BBC micro:bit に最適なGrove Inventor Kit をお薦めします。">
<meta name="author" content="minxuan">


![](https://github.com/SeeedDocument/Grove_kit_for_microbit/raw/master/img/zoro_im_kitbox.jpg)
 　　
      
      
　BBC micro:bitはマイクロコンピュータの一種です。これを使えば、エレクトリックやコーディングに関する知識が少なくとも、使用者は創造性を生かすことがよくできます。BBC micro:bitはいろんな創造の可能性を提供しており、ロボットから楽器までのほうにも創造的なことが出きます。しかし、創造性を生かすには、BBC micro:bitだけを使っては不十分です。そのため、BBC micro:bit に最適なGrove Inventor Kit をお薦めします。


　Grove Inventor Kitはユーザにmicro:bitの無限の可能性を与えられます。キットのコアボードはmicro:bitに適用するGrove拡張ボードであり、それによって、センサー、ディスプレー装置やアクチュエータなど多種のGroveモジュラーはmicro:bitとのインタコネクトができます。たとえGroveを使ったことがない、或いはそのことが分からなくても心配する必要がありません。Groveの使いには溶接やジャンパー線の必要がなく、プロトタイピングのことも簡単、便利であることだけです。　　

　Micro:bitのご使用になるため、こちらはGroveモジュールを８つ用意します。これらのGroveモジュールを合わせて使うと、距離測定とその表示、手振りで音楽放送、部屋で電子警備装置の放置などもできます。必要なパッケージも無料で提供しています。また、Micro:bit初心者には、学習材料とする12のプロジェクトも提供します。エキスパートに対しては、このキットを手際よく活かせることができます。

注意！
    　Micro:bitの輸出電圧は約3.0Ｖで、Micro:bit或いは単3電池を電源とすると、高入力電圧と駆動電流が必要なGroveモジュール（例えばGrove-Ultrasonic Ranger）には故障を起こる可能がありますので、Groveモジュールの通常動作のため、Grove拡張ボードのMicro USBを使ってシステムに電力供給してください。





[![](https://github.com/SeeedDocument/Seeed-WiKi/raw/master/docs/images/300px-Get_One_Now_Banner-ragular.png)](https://jp.seeedstudio.com/Grove-Inventor-Kit-for-micro%3Abit-p-2891.html)

## 商品特性
  
  - 外形綺麗な拡張ボードに多種の周辺機器を便利に接続
  - Micro:bit最適のGroveモジュールが10つあり
  - ゼロから学習用プロジェクトが12つあり
  - 詳細な取扱説明書

## ハードウェア概要


![](https://github.com/SeeedDocument/Grove_kit_for_microbit/raw/master/img/first_im.jpg)



### 部品一覧


| 部品 | 数量 |
|--------------------------|-----|
|Micro:bit用のGrove拡張ボード(Grove Shield for micro:bit)|  1  |
|Grove - Rotary Angle Sensor(P)| 1 |
|Grove-スピーカー(Grove - Speaker) | 1 |
|Grove-超音波レンジャー(Grove - Ultrasonic Ranger)| 1 |
|Grove-ライトセンサー v1.2(Grove - Light Sensor v1.2)| 1 |
|Grove-WS2812防水LED Strip-30 LEDs　1m(Grove - WS2812 Waterproof LED Strip - 30 LEDs 1 meter)| 1 |
|Grove - Gesture | 1 |
|Grove -  4-Digitディスプレー(Grove - 4-Digit Display)| 1 |
|Grove - 赤LED(Grove - Red LED)| 1 |
|(Micro USB ケーブル 48cm)Micro USB Cable - 48cm| 1 |
|プロジェクトのマニュアル(12 Projects Manual)| 1 |
|Alligator ケーブル(Alligator Cable)| 10 |
|Grove　ケーブル(Grove Cable)| 7 |


## ご使用の案内

### Micro:bitについての基本知識

初めて使う場合には、Micro:bitに関わる基本知識が必要です。 [ **こちら** ](https://microbit.org/code/) へMicro:bitの詳細情報をご覧ください。

Micro:bitは、JavaScriptブロックエディターや、Python Editorという2種類のエディターでプログラムすることができます。JavaScriptブロックエディターはグラフィカルプログラミングができ、簡単で、学びやすいです。それで、以下はJavaScriptブロックエディターについての学習内容です。

簡単ですが、以下の2つのステップを注意してください、その2つのステップが終わったらす、Micro:bitを自由に活用させることができます。


####  ステップ1　エディタを開く


 **[JavaScriptブロックエディター](https://makecode.microbit.org/)**をクリックして 、グラフィカルプログラミングのページに行きます。


#### ステップ2　Grove パッケージの追加

  -右上のギヤをクリックして、 **「Add Package」**を選んでください。

  ![](https://github.com/SeeedDocument/Grove_kit_for_microbit/raw/master/img/0-1.png)

  - 以下のURL: **github.com/seeed-studio/pxt-grove**を入力します。

  ![](https://github.com/SeeedDocument/Grove_kit_for_microbit/raw/master/img/0-2.png)

  - それからツールバーでは **Grove** が見えます
  ![](https://github.com/SeeedDocument/Grove_kit_for_microbit/raw/master/img/0-3.png)


###デモ1　ジェスチャー認識


ジェスチャーセンサーは九種のジェスチャーが識別できます。このデモを通じて、Micro:bitでジェスチャー名称を表示することができます


####器材リスト


|器材|数量|
|---|---|
|Grove - Gesture|1|
|Micro:bit用のGrove拡張ボード(Grove Shield for micro:bit)|1|
|micro:bit|1|
|Grove ピンが4つあるケーブル(Grove Universal 4 pin cable)|1|
|Micro-USB ケーブル(Micro-USB cable)|1|  
   
   
 
#### 接続

  -  **micro:bit**を **Grove Shield for micro:bit**にインサートします。
  - Grove ケーブルでGrove-GestureをMicro:bitの **I2C** ポートに接続します。
  - Micro-USB ケーブルでmicro:bitをパソコンに接続します。

注意！
  
  micro:bitを壊しないように、micro:bitをインサートする時は、LED配列は外へ向けてください。

![](https://github.com/SeeedDocument/Grove_kit_for_microbit/raw/master/img/Gesture%20Recognition.png)


#### ソフトウェア部分

  - ステップ1

  Gesture sensorの追加
  ![](https://github.com/SeeedDocument/Grove_kit_for_microbit/raw/master/img/1-1.png)

  -ステップ2

  センサーが手の右から左への移動方向を識別できるように、 Right を選んでください。

  ![](https://github.com/SeeedDocument/Grove_kit_for_microbit/raw/master/img/1-2.png)

  - ステップ3

 「Basic」での **show string** を追加し、それを「Gesture」に挿入します。「Hello!」をダブルクリックして、それを「Right」に変更します。

  ![](https://github.com/SeeedDocument/Grove_kit_for_microbit/raw/master/img/1-3.png)

  - ステップ4

 ステップ3と同じように、「Left」や「Clockwise」を追加して、 **「show icon」** を「Clockwise」に挿入します。

  ![](https://github.com/SeeedDocument/Grove_kit_for_microbit/raw/master/img/1-4.png)

  - ステップ5

  以上の操作が完了すると、プロジェクトの名前を「gesture」にリネームします。そして、このプロジェクトをボードにダウンロードします。左下の **「Download」** をクリックして、ファイル **「microbit-gesture.hex」**をMICROBITでの「flash」にダウンロードします。

  ![](https://github.com/SeeedDocument/Grove_kit_for_microbit/raw/master/img/1-5.png)

 完成！


ヒント!!!
    色によってブロックを探すのは便利ですよ。例えば、「show icon」の所在が分からないけれど、そのブロックが青色で、それから青色のモジュール「Basic」で「show icon」が見つかります。便利で効率ウップではありませんか？


### デモ2　超音波メーター

このデモを通じて、超音波メーターで距離測定とその表示ということができます。

#### 器材リスト


|器材|数量|
|---|---|
|Grove-超音波レンジャー(Grove - Ultrasonic Ranger)|1|
|Grove - 4-DigitディスプレーGrove - 4-Digit Display|1|
|Micro:bit用のGrove拡張ボード(Grove Shield for micro:bit)|1|
|micro:bit|1|
|Grove ピンが4つあるケーブル(Grove Universal 4 pin cable)|2|
|Micro-USB ケーブル(Micro-USB cable)|1|

#### 接続

  -  **micro:bit** を **Grove Shield for micro:bit**にインサートします。

注意!!!
    micro:bitを壊しないように、micro:bitをインサートする時は、LED配列は外へ向けてください。

  - Grove ケーブルでGrove - Ultrasonic Rangerをmicro:bitの**P0/P14** ポートに接続します。
  - GroveケーブルでGrove - 4-Digit Displayをmicro:bitの **P1/P15** ポートに接続します。
  - Micro-USBケーブルでmicro:bitをコンピュータに接続します。

  ![](https://github.com/SeeedDocument/Grove_kit_for_microbit/raw/master/img/Ultrasonic_Meter.png)

#### ソフトウェア部分

  -ステップ1

  Basic block **「on start」**を追加して、そしてvariable blocks **「set item to 0」**を追加します。「item」を「Display」にリネームします。または「0」を「Grove block 4-Digit Display at P1 and P15」に取り替えます。

  ![](https://github.com/SeeedDocument/Grove_kit_for_microbit/raw/master/img/2-1.png)

  ![](https://github.com/SeeedDocument/Grove_kit_for_microbit/raw/master/img/2-2.png)

  - ステップ2
  Basic block「forever」を追加して、そしてGrove block「item show number 0」を追加します。「item」を「Display」にリネームします。または「0」を「Grove block Ultrasonic Sensor (in cm) at P0」に取り替えます。

  - ステップ3

  Basic block「pause (ms) (100)」を追加します。

  ![](https://github.com/SeeedDocument/Grove_kit_for_microbit/raw/master/img/2-3.png)

  - ステップ4

  このプロジェクトを「Ultrasonic Meter」にリネームして、ダウンロードします。Enjoy！


## 関連リソース

  [**Grove Shield for microbit_eagle file.zip**](https://github.com/SeeedDocument/Grove_kit_for_microbit/blob/master/res/Guide-Grove%20kit%20for%20microbit.pdf)

  [**micro:bit Getting Started Videos**](http://microbit.org/start/)

  [**About micro:bit**](http://microbit.org/about/)

  [**micro:bit Hardware**](http://microbit.org/guide/hardware/)

  [**micro:bit Apps**](http://microbit.org/code/)

  [**Grove Shield for microbit_eagle file.zip**](https://github.com/SeeedDocument/Bazzar_Attachment/raw/master/103030195/202001587_Grove%20Shield%20for%20BBC%20microbit%20V1.2_eagle%20file.zip)

## 技術サポート
何かご不明な点がございましたら、 [フォーラム](http://forum.seeedstudio.com/)でお問い合わせ下さい。 <br /><p style="text-align:center"><a href="https://www.seeedstudio.com/act-4.html?utm_source=wiki&utm_medium=wikibanner&utm_campaign=newproducts" target="_blank"><img src="https://github.com/SeeedDocument/Wiki_Banner/raw/master/new_product.jpg" /></a></p>
  
  ※このページは英語バージョンのウィキに基づいて翻訳されたものです。何かご不明な点などございましたら、英語バージョンをご参考下さい。