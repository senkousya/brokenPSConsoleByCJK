# Powershellコンソールに日本語等がある時にカーソルを動かすと表示がぶっこわれる問題

Powershellのコンソールで日本語を入力した後にカーソルを動かすと、下記リンク先で報告されるようにコンソールの表示がぶっ壊れる問題が今まで発生していました。

▶下記のissueページにあるような感じ  
[Broken rendering for CJK on Windows #4964](https://github.com/PowerShell/PowerShell/issues/4964)

この問題はいつの間にか標準で導入されるようになっていた、psreadlineというモジュール(Powershellコンソールをハイライトしてくれる)が引き金となっていたようです。

powershellでカーソル位置がぶっこわれる度に、psreadlineを削除する以外で何か解決方法が無いか検索していたら。

psreadlineのissueページになんか対応したっぽい宣言があることに気が付きました。

[Make PSReadLine more portable #561](https://github.com/lzybkr/PSReadLine/pull/561)

>The PR includes a few internationalization fixes - cursor placement for CJK, plus improved handling of key bindings for less common keyboard layouts.

おー。

psreadlineのv2.0ベータ版から表題の問題が修正されているようです。(2018年2月現在のバージョンは1.2)

さっそくベータ版のpsreadlineのインストール方法を調べていたらそのものズバリのブログ記事が。

[PowerShellGetをアップデートしよう - PSReadline 2.0 Betaをインストールしてみる](http://blog.shibata.tech/entry/2017/12/18/004105)

上記ページにある通りに、psreadlineを2.0 Betaにアップグレードした所、無事Powershellコンソールで壊れなくなりました。

素敵。
