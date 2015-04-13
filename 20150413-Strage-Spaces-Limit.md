﻿# Windows8.1で記憶域プールから作成したドライブの容量上限は15.8TiB(=17.5*10^12B)
* eSATA2ポートのPCIeカード2枚に[MARSHAL社HDD TOWER4](http://www.marshal-no1.jp/products/MAL-3035SBKU3.html)を4台(HDDにして16台)繋げ大容量のドライブを作ろうとしたら嵌りましたのでメモです。
* [NT File System - Wikipedia](http://ja.wikipedia.org/wiki/NT_File_System)によれば
> なお、2010年時点でのNTFSの実装では、クラスタ数は2^32-1までとなっている。このため、16 TiBを超えるボリュームは、4 KiBを超えるアロケーション ユニット サイズを指定しなければならない。
* 上記制限のため何も考えずに記憶域プールからドライブを作ると15.8TiBが上限となる。
* もう一つアロケーションユニットサイズが大きな(自分は16KiB)ドライブを作って死ぬ気でコピーかければ良いのですけどね。
* 単体のHDDドライブでも17.5TBを超えると同様の問題が起こるはずなので注意しよう。(OSが自動でアロケーションユニットサイズを変更しそうですが)

2015年4月13日 わっほー☆