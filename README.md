# 74th が RP2040 を手ではんだ付けしてみたくて作った開発ボード

<img src="rp2040-large/photo1.png" width=30%" /> <img src="rp2040-promicro/rp-promicro1-v2.0.0.jpg" width=30%" />

- [Raspberry PI PICO と同じピン配置で、Flush のサイズを変えたいために、作った開発ボード rp2040 large board](./rp2040-large/)
- [ProMicro ピンアウト開発ボード rp2040 pro micro](./rp2040-promicro/)
- [完成後のチェック用に使うファームウェア](rp2040-io-tester/) [rp2040-io-tester.uf2](rp2040-io-tester/rp2040-io-tester.uf2)
- [部品の調達先](./parts/)

## トラブルシューティング

トラブルシューティング
USB を接続する前に

```
1. ルーペで、USB ソケットと、RP2040 の接続部分を拡大して、はんだがブリッジしていないか、RP2040 とランドがただしく接続できているか確認してください。

2. GND と 5V の間の抵抗値を測り、0Ω になっていないことを確認してください
→ 0 Ω なら、USB ソケットの実装に問題がある可能性があります

3. 3V3 と RP2040 の 23 ピンの間の抵抗値を測り、0Ω になっていないことを確認してください
→ 0 Ω なら、22、23 ピンがブリッジ、44、45ピンがブリッジしている可能性が高いです

USB を接続して

4. レギュレータ AZ1117-3.3 で、GND と 5V、3.3V が計測できるか確認してください

5.GND と RP2040 44 ピンの電圧が 3.3V になっているか確認してください
→ だめなら、USB ソケットが実装に問題がある可能性があります

6. GND と RP2040 45 ピンでの電圧が 1.1V になっているか確認してください
→ 計測できなければ、内蔵レギュレータの入力の 44 ピンか、 出力の 46 ピンの実装に問題がある可能性があります

7. PC で USB 接続した時に RPI-RP2 ドライブがマウントされるか確認してください
→ RP2040 の クリスタルの入出力 20、21 ピンの実装に問題がある可能性があります
→ RP2040 の USB DM/DP 46、47 ピンの実装に問題がある可能性があります
→ クリスタルの実装に問題がある可能性があります

8. RPI-RP2 ドライブはマウントできるけれど、uf2 を入れても再度 RPI-RP2 がマウントされてしまう
→ RP2040 の SPI Flash の 51〜56 ピンの実装に問題がある可能性があります

私のところでは、以上のトラブルシューティングでなんとかなっています。
RP2040 のはんだ付けにトライして、失敗したら一度外してやり直しても良いと思います。
```

## 使用し、取り込んでいる Kicad ライブラリ

- https://datasheets.raspberrypi.com/rp2040/Minimal-KiCAD.zip

## LICENSE

MIT
