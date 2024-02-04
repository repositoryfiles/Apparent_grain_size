## 概要
GrainSize.pyは、結晶粒界が現出している組織画像について、JIS G0551の切断法に準じて結晶番号を求めるプログラムです。ここで、結晶粒界が現出している組織画像とは次のようなものをいいます。

![435_500_10](https://github.com/repositoryfiles/Apparent_grain_size-/assets/91704559/c4162f93-4bd4-4529-abff-7e7e016b1674)

機械構造用合金鋼SCM435の組織画像（AGS腐食液でエッチング、幅142mmで表示したときに倍率500倍）

## 動作環境
GrainSize.pyは、Pythonがインストールされたパソコンで動作します。このプログラムの実行には、画像処理のライブラリOpenCVが必要です。

## 使い方
1. **GrainSize.py** を適当なフォルダに置きます。
2. **GrainSize.py** の18～20行目を設定します。
- **PictureWidth** には、画像の幅（単位：mm）を入力します。
- **Magnification** には、顕微鏡で撮影した倍率を入力します。<br>
※プログラムの初期値は、画像を幅142mmで表示すると、倍率1000倍の組織画像になるという設定になっています。
-. **miniGraSize** には、画像の幅に対して画像処理で認識させる結晶粒（輪郭）の最小サイズを入力します。
3. **GrainSize.py** の93行目の **iDir** には、ダイアログ「画像ファイルを選んでください」で最初に表示させたいフォルダを設定します。<br>
上記の **iDir** に設定したフォルダに **SUJ2_Mag1000_width142mm.jpg** のような組織画像を格納して、**GrainSize.py** を実行します。**GrainSize.py** と組織画像を格納したフォルダは全角文字を含まない名前としてください。<br>
4. プログラムを実行すると最初にダイアログ「画像ファイルを選んでください」が表示されるので、調べたい組織画像を選択します。少し待つと、同心円が三個描画された組織画像が表示されます。同心円上の丸い点は同心円を横切る結晶粒界の位置を示しています。また、コンソールには<br>
Number of grain boundaries : 69<br>
Number of grain boundaries per 1 mm : 138.0<br>
Apparent grain size : 10.9<br>
が表示されます。<br>
これらは、同心円を横切る結晶粒界の個数、同心円の長さ1mm当たりの結晶粒界の数、粒度番号　を表しています。
5. 同心円状の丸い点はマウスの左クリックで追加、右クリックで削除できます。それに伴い、コンソールに表示される数値も更新されます。<br>
表示されているwindowの大きさは自由に変更できます。また、windowに表示されている画像はいつでも保存できます。
6. 画像を閉じるか、任意のキーを押すと、プログラムは終了します。終了方法は、プログラムの最後の部分を書き換えれば変更できます。

## 画像ファイルについて
- SCM435_Mag1000_width142mm.jpg 機械構造用合金鋼SCM435の金属組織
- SUJ2_Mag1000_width142mm.jpg 高炭素クロム軸受鋼SUJ2の金属組織
いずれもAGS腐食液でエッチングしたもので、幅142mmで表示したときに倍率1000倍となります。これらの画像はプログラム **GrainSize.py** の **PictureWidth** と **Magnification** は変更せずに粒度番号を求めることができます。

## ご利用に関して
- このプログラムでは、結晶粒界が明瞭に現出されている組織画像に対して、結晶粒界を判別することができます。粒界が不明瞭なものについては粒界の検出ができません。
- **PictureWidth** と **Magnification** を組織画像に合わせて設定しないと結晶粒度が正しく求まりませんのでご注意ください。
- このプログラムは、JIS G0551の線分法を完全には対応しておりません。JIS G0551の内容をご理解の上、ご利用ください。
- ご利用結果について当方は責任は負いません。

## 開発環境
- Windows11
- VSC 1.85.2
- Python 3.9.18
- OpenCV 4.5.0
