## VScode のインストール

## OTF パッケージのインストール

そもそも和文の LaTEX には，本文用の明朝体と見出し用のゴシック体しかない．
さらにめんどくさいことに，太字とかにすることができない（？）
これらを解消するのが，OTF パッケージ．
以下インストール方法

- Mac

```
# tlmgr（latexのパッケージ管理ツール） に新しくリポジトリを追加
sudo tlmgr repository add http://contrib.texlive.info/current tlcontrib
# よくわからん
sudo tlmgr pinning add tlcontrib '*'
# 4つのフォントをインストール
sudo tlmgr install japanese-otf-nonfree ptex-fontmaps-macos cjk-gs-integrate-macos

# 一旦シンボリックリンクを clean up
sudo cjk-gs-integrate --link-texmf --cleanup
# シンボリックリンクの追加
sudo cjk-gs-integrate-macos --link-texmf
# ファイルのキャッシュクリア
sudo mktexlsr

# ヒラギノフォントを使うように map ファイルを更新
sudo kanji-config-updmap-sys --jis2004 hiragino-highsierra-pron
```

## 使用上の注意

- 画像
  - ファイル名に英数字以外を記入してはいけない
