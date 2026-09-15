# Seeed Studio XIAO ESP32S3 + GC9A01 Flight Radar

タッチパネルの無い丸型ディスプレイ(GC9A01, 240x240)向けの版です。
、**範囲内の全機体について常に**次の3つを表示します。

- ドット(機体位置)
- ドットから伸びる短い線(OpenSkyの`true_track`=進行方向)
- 便名(コールサイン。無ければICAO24)のラベル

## ハードウェア

- コントローラ: Seeed Studio XIAO ESP32S3
- ディスプレイ: 1.28インチ丸型 GC9A01 (240x240, SPI)

### 配線

| GC9A01 | Seeed Studio XIAO ESP32S3|
| --- | --- |
| VCC | 3V3 |
| GND | GND |
| SCL / SCK | D8 |
| SDA / MOSI | D10 |
| CS | D0 |
| DC | D1 |
| RST | D2 |

※ バックライト(BL)制御ピンが別に出ているモジュールの場合、配線表に含まれていなかったため、常時点灯前提にしています。もし個別制御が必要であれば教えてください。

## ライブラリ

LovyanGFXの素のLGFX_Deviceサブクラスを自分で定義して、GC9A01用のSPIピン設定(CS/DC/RST/SCLK/MOSI)を書きます。

## セットアップ

1. VSCode + PlatformIOで本フォルダを開く
2. ビルド&アップロード

```
pio run -t upload
pio device monitor
```

## 注意点
元になったのは、[Micro Radar](https://github.com/AnthonySturdy/micro-radar) で、ライセンスは MIT ライセンスなので、それを踏襲します。
