# sidtool

## 概要
DokiDokiLiveの動画を保存するためのスクリプトです。2025年当時は動いていましたが、更新しておらず、サーバーの仕様変更等もあり得るため、現在の動作は保証できません。

## 使用技術
- Python3
- Flet（GUI版のみ）

## 実行方法
### このツールを利用するには、CUI版、GUI版ともにFFmpegをインストールし、必要に応じてパスを通す必要があります。Debianユーザーであれば```sudo apt install ffmpeg```でOKです。Windowsユーザーは環境変数の設定などお願いします。
CUI版
```bash
python3 sidtool.py
```
GUI版
- Windows  
WindowsのGUI版のみ[Release](https://github.com/erga0131/sidtool/releases/latest)にビルドがあります。zipファイルを解凍して、中のdokisidpy.exeを起動してください。
- Windows / Linux 等
```bash
pip install flet
flet run GUI_test.py 
```

### 既知の問題点
- 何らかの要因により途中でtsの番号が飛び、ダウンロード完了を誤検知する場合があります。  
→どうしてもうまく行かないときは手動でtsの抜けた分をダウンロードした上で、sidtoolをimportして必要部分の関数のみを利用するpythonスクリプトを組むなどの対策が考えられます。GUI版では各ボタンで関数を呼び出せるようになっているので便利です。

### 技術仕様
- sidtool.py  
DokiDokiLiveのsidからUNIX時間の日付を計算してm3u8のURLを表示した後、連番の.tsのダウンロードとffmpegによるmp4への結合を一括でできるようにしています。
- GUI_test.py  
Fletで作ったsidtoolのGUI版です。
