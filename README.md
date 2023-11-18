## ZBI2.0を用いてBluetooth経由でスキャナから直接ラベル印刷をする方法

本ガイドはDS8178をベースに説明をする。
他スキャナを利用の際は設定が一部異なる可能性があることをご了承頂きたい。

</br>

1. プリンタとスキャンを工場出荷状態に戻す。

    > 参考資料  
    > Scanner Facrory Reset.pdf

1. プリンタに対して用紙の設定をする。

1. ZBIをActivateする。

    Activating ZBI (Zebra Basic Interpreter)
    Article ID:000015434  •  February 15, 2022  
    https://supportcommunity.zebra.com/s/article/Activating-and-deactivating-ZBI-Zebra-Basic-Interpreter?language=en_US

1. 下記ファイルをZebra Setup Utilitiesを用いてプリンタに送信する。

- DEMOZBI.ZPL
- DEMOZBI.prn

1. 下記scncfgファイルを用いて、123ScanでADFの設定をする。

    > 参考設定  
    > "Config File_DS8178_Add-Enter_2023.11.18.scncfg"

1. 123Scanを終了。

1. Notepadを開く。バーコードをスキャンした結果として、スキャンデータ読み取り後にエンターが追加されていればOK。

        4904910024940
        4904910024940
        4904910024940


1. DEMOZBI.ZBIを実行する。

        ^XA^JIE:DEMOZBI.BAS,N,N,50K^FS^XZ

        ※液晶メニューからの実行でもOK。


1. プリンタとスキャナをBluetooth接続する。

    > Zebra BlutoothスキャナとZebra プリンタと直接接続する方法  
    > https://github.com/shimauma-giken/Zebra-Scanner-How-to-direct-connect-bluetooth-scanner-to-printer

1. JANコードなどのバーコードをスキャンする。スキャンした内容に応じたバーコードがプリンタから出力されれば設定は完了。

