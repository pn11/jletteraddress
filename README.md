# jletteraddress.cls + VS Code devcontainer

[ueokande/jletteraddress](https://github.com/ueokande/jletteraddress) に [korosuke613/texlive-ja-devcontainer-template](https://github.com/korosuke613/texlive-ja-devcontainer-template) を加えて簡単に使えるようにしました。

## 使用方法1 (Webブラウザで完結)

1. このリポジトリを fork する
2. `example.tex` または `addresses.json` を編集し、コミットする
3. GitHub Actions が動き `example.pdf` または `out.pdf` が生成される

## 使用方法2 (Docker Compose を使う)

### 前提条件

- Docker がインストールされている

### 動かし方

まず以下のコマンドでリポジトリをクローンする。

```sh
git clone https://github.com/pn11/jletteraddress.git
cd jletteraddress
code .
```

クローンしたら  `example.tex` または `addresses.json` を編集する。その後、以下のコマンドを実行する。

```sh
docker compose -f .devcontainer/docker-compose.yml up -d
docker compose -f .devcontainer/docker-compose.yml exec ubuntu-texlive-ja latexmk
```

実行が終わると `example.pdf` または `out.pdf` が生成される。

## 使用方法3 (VS Code devcontainer を使う)

### 前提条件

- Docker がインストールされている
- VS Code に devcontainer 拡張機能がインストールされている

### 動かし方

以下のコマンドを実行して VS Code でこのリポジトリを開く

```sh
git clone https://github.com/pn11/jletteraddress.git
cd jletteraddress
code .
```

その後、 `example.tex` または `addresses.json` を編集し、以下の手順を実行する

1. 左下の><アイコンを押して、Reopen in container を実行する
2. Docker Image がビルドされるので待つ
3. ワークスペースが開いたら、terminalを開き、`latexmk` を実行する
4. `example.pdf` または  `out.pdf`  が生成される

スタイルファイルの使い方は[README_org.md](README_org.md) または[フォーク元](https://github.com/ueokande/jletteraddress)を参照。
