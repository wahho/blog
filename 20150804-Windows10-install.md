# Windows10Proを入れてみた
* はまった点を適当にメモ
* PCはツクモBTOのエアロストリーム(マザーはMSI社P67A-C43のカスタム版)

### プロダクトキー
* DVDorUSBメモリからクリーンインストール時は「Windows10のプロダクトキーが必要」
* Win7or8.1からの無料アップグレードは初回のみ「現OSからアップグレードを実行しインターネットへ繋いでキー認証を受ける」
* 2回目以降は「プロダクトキーの入力をスキップしてインターネットへ繋ぐといつの間にか認証されている」

### 新しいSSDを用意してWin7をインストールしたら
* Win7単体ではマザーボードのNICを認識しなかった
* Win10のインストーラーは現在のプロダクトキーがインターネットで認証されるまでアップグレードを拒否する
* 最低でもマザーボードのWin7,8のNICドライバはWin10のDVDorUSBメモリに一緒に入れておくと吉
* realtek_pcielan_7_mb.zip

### UEFIインストールすると旧OSのドライブが見えない
* マザーボードのチップセットドライバを入れたら直った
* intel_chipset_6_mb.zip

### PCIe-eSATA*2ボードをWin10で認識させる
* AREA SD-PESA3ES2L (http://www.area-powers.jp/product/pcie/sata/pesa3es2l.html)
* ASMedia asm-106xチップセット使用  
http://www.necacom.net/index.php/asm/asm-106x-sata/9031-asmedia-106x-sata-6g-controller-driver-ver-3-0-2-0000-whql  
asmedia_106x_3.0.2.zip

----------

2015年8月4日 わっほー☆
