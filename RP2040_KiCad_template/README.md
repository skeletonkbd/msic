# RP2040_KiCad_template

※ 現時点ではまだ基板を製造しての実機確認は行っていません。もしご利用される場合は自己責任でお願いいします。

## これはなに？

RP2040周りの回路図をKiCadで作成したものです。プロジェクトテンプレートとして使用することを想定しています。

JLCPCBでPCBAをするための部品の選定も行っています。

## 使用方法

### ユーザーテンプレートフォルダのパスの確認・変更
KiCadで<code>設定</code>から<code>パスを設定</code>を開きます。

<code>KICAD_USER_TEMPLATE_DIR</code>のパスを確認、必要に応じて変更します。

このディレクトリを配置します。

### テンプレートから新規プロジェクトを作成

<code>ファイル</code>から<code>テンプレートから新規プロジェクト</code>を開きます。

ユーザーテンプレートに「RP2040 Template」という表示が現れますので、それを選択してOKをクリックします。

## BOM

| MNP              | メーカー                      | 用途・概要                        | LCSC     | 数量 | Basic Parts |
|------------------|-------------------------------|-----------------------------------|----------|------|-------------|
| RP2040           | Raspberry Pi                  | マイコン (メイン MCU)             | C2040    | 1    |             |
| TYPE-C-31-M-12   | Korean Hroparts Elec          | USB Type-C レセプタクル           | C165948  | 1    |             |
| USBLC6-2SC6      | TECH PUBLIC                   | USB 信号ライン用 ESD 保護 IC      | C2827654 | 1    |             |
| W25Q32JVUUIQ     | Winbond Elec                  | SPI フラッシュメモリ (4MB)        | C2999380 | 1    |             |
| XC6206P332MR-G   | Torex Semicon                 | LDO レギュレータ (3.3V 出力)      | C5446    | 1    | 👍️          |
| nSMD050-24V      | TECHFUSE                      | リセッタブルヒューズ (ポリヒューズ)| C70076   | 1    |             |
| X322512MSB4SI    | YXC Crystal Oscillators       | 水晶発振子 12MHz                   | C9002    | 1    | 👍️          |
| TS-1187A-B-A-B   | XKB Connection                | タクトスイッチ            | C318884  | 2    | 👍️          |
| ESD5Z5V0         | MDD (Microdiode Semiconductor)| 電源ライン用 ESD 保護ダイオード   | C502546  | 1    |             |
| CL10C220JB8NNNC  | Samsung Electro-Mechanics     | コンデンサ 22pF     | C1653    | 2    | 👍️          |
| CL05B104KO5NNNC  | Samsung Electro-Mechanics     | コンデンサ 100nF  | C1525    | 10   | 👍️          |
| CL05A105KA5NQNC  | Samsung Electro-Mechanics     | コンデンサ 1µF       | C52923   | 4    | 👍️          |
| CL05A106MQ5NUNC  | Samsung Electro-Mechanics     | コンデンサ 10µF       | C15525   | 1    | 👍️          |
| 0603WAF1001T5E   | UNI-ROYAL (Uniroyal Elec)     | 抵抗 1kΩ            | C21190   | 2    | 👍️          |
| 0603WAF5101T5E   | UNI-ROYAL (Uniroyal Elec)     | 抵抗 5.1kΩ          | C23186   | 2    | 👍️          |
| 0603WAF270JT5E   | UNI-ROYAL (Uniroyal Elec)     | 抵抗 27Ω     | C25190   | 2    |             |

## 参考資料

### RP2040を使用したハードウェア設計
https://datasheets.raspberrypi.com/rp2040/hardware-design-with-rp2040-JP.pdf

「2.1.2. バイパスコンデンサー」のサンプル回路を参考に、コンデンサーの個数を決定しています。配置については回路図内に注記しています。

### Hardware design for the RP2040
https://github.com/calliah333/RP2040-designguide/tree/main

主要なパーツの選定の参考にしています。

### Xiao RP2040 回路図
https://files.seeedstudio.com/wiki/XIAO-RP2040/res/Seeed-Studio-XIAO-RP2040-v1.3.pdf

ResetとBootの2つのスイッチを配置する方式はXiao RP2040の設計を参考にしています。