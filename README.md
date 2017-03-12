DeepAA
====

本レポジトリについての記事を書きました。
よろしければご覧ください。
[ディープラーニングでアスキーアートを作る](http://qiita.com/OsciiArt/items/325714d8ab3f2b482ced)
This is an article about this repository. Sorry, it's only in Japanese, but you can see some sample outputs here.

## 概要
ディープラーニング技術を用いて画像をアスキーアートに変換します。

## 前提
動作にはPythonの実行環境が必要です。

以下の環境でテスト済みです。

+ Python 3.5 (64bit)

## 依存パッケージ
本ツールは以下のパッケージに依存しています。

+ TensorFlow
+ Keras
+ NumPy
+ Pillow (PIL Fork)

## 使用方法
`deepaa_output.py ` の17行目

```
image_path = 'test_image.png' # 変換する画像を指定
```
の画像パスを任意のものに置き換えて実行してください。
画像は白黒の線画を用いてください。
細線化された画像の方が良い結果が得られやすいです。

現段階では学習済みモデルによる出力を行うコードのみ公開しています。
学習データの前処理、学習のコードは今後公開の予定です。

## 実行例
![実行例](http://i.imgur.com/rasaYQi.png)

## 学習
注) 現在アップしているデータセットは実際に学習に用いたものではありません
### Steps
1. **データの前処理**
    ```bash
    python process_data.py
    ```
    アスキーアートのデータを保存しているテキストファイル (data/aa_sample.ast) を学習データに変換します。データはdata/traindata/に出力されます。
    <br>

2. モデルの学習
    ```bash
    python deepaa_train.py
    ```
    モデルの学習を実行します。学習したモデルはmodel/model_test/に保存されます。

## ライセンス
本ライブラリのライセンスは `MIT License` になります。