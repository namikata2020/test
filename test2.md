# FreeRTOS version 10.4.1 for Renesas RX210 MPU

ルネサスエレクトロニクス製MPU RX210用のFreeRTOSの実装です。
## OSバージョン
　v10.4.1
 
## ターゲットボード
　[秋月電子通商製](https://akizukidenshi.com/catalog/default.aspx)マイコンボード[AE-RX210](https://akizukidenshi.com/catalog/g/gK-08207/)　

## 開発環境
　IDE [e2-studio](https://www.renesas.com/jp/ja/products/software-tools/tools/ide/e2studio.html)　Version: 2020-07 (20.7.0)
 
　Compiler Renesas [CC-RX](https://www.renesas.com/jp/ja/products/software-tools/tools/compiler-assembler/compiler-package-for-rx-family.html) V2.08.01
 
## 追加機能
シリアルポートを利用して標準入出力(stdio.h,printf(),scanf())関数が動作します。設定は"FreeRTOS/FreeRTOSConfig.h"ファイルを書き換えて行います。

'''
''' /* Board specifics. */
''' /* use serial console */
#define		USE_SERIAL_CONSOLE

#ifdef USE_SERIAL_CONSOLE
/* serial port SCI0 or SCI1 */
#define		USE_SCI_PORT	0

/* serial baud rate
   8bit: stop bit 1: Parity none
*/
#define		SERIAL_BAUD_RATE	38400

#endif /* USE_SERIAL_CONSOLE */
'''
