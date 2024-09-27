# LaTeXEnv_docker

## Overview
texliveを使ってlatexmkrcからいい感じに日本語LaTeXをタイプセットできるdockerfileおよびVSCodeのワークスペース設定です。

また、千葉工業大学 応用知能システム 今野研究室で用いるために整備しているため知能メデイア工学科の卒業論文および卒論予稿（概要）のテンプレートが含まれています。

## Requirements
### 必要環境
- Docker Desktop
- VSCode
    - 拡張機能としてLaTeX WorkShopが導入されていること

## Usage
### gitからcloneもしくはダウンロード
```
git clone https://github.com/aais-lab/LaTeXEnv_docker.git --depth 1
```

[ダウンロード(zip)](https://github.com/aais-lab/LaTeXEnv_docker/archive/refs/heads/main.zip)

### docker imageのビルド
```
cd LaTeXEnv_docker/dev
docker image build -t latex-docker .
```

dockerイメージのビルドは、10〜20分で終わります。

### タイプセットのテスト
LaTeX WorkShopをインストールして有効化したVSCodeで、LaTeXEnv_docker/testを開く。

thesis_template.texを開き、Ctrl+S(保存)をすると自動でタイプセットされます。
生成されるoutフォルダ下のthesis_template.pdfがtestフォルダ直下に配置されているthesis_template.pdfと同一であれば正常にタイプセットされています。

中間ファイルやpdfはoutフォルダ下に出力されるように設定しています。この設定は.vscodeフォルダ内のsettings.jsonで変更可能です。

### 任意のディレクトリにTeXファイルを配置してタイプセットする
template/workspace直下に入っている.vscodeおよび.latexmkrcを任意のディレクトリに移動させてください。

.vscodeディレクトリにはワークスペースの設定が、.latexmkrcにはタイプセットに必要なコマンドの情報が記載されています。
どちらかが不足している場合、正常にタイプセットされません。

### Windowsで使用する際の注意点
template/abst/abst_template.texでは相対参照による図の参照を行なっています。
コメントアウトでWindows用のパスも記載しているので、タイプセットの際にはコメントアウトをはずし、MacやLinuxで使用するコマンド部分をコメントアウトしてください。

## Author
[Nao Yamanouchi](https://github.com/ClairdelunaEve)
