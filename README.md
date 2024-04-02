# libjpeg
GNU Emacs30.0.50に含まれる`java/INSTALL`にしたがってパッチを適用したlibjpegモジュールのレポジトリ。

# 作成した手順

1. [Google Gitのlibjpeg-turbo](https://android.googlesource.com/platform/external/libjpeg-turbo)をclone


```bash
$: git clone https://android.googlesource.com/platform/external/libjpeg-turbo
```

2. `nougat-release`ブランチから修正用ブランチ`my/nougat-release`をcheckout

```bash
$: cd libjpeg-turbo
$: git checkout nougat-release
$: git checkout -b my/nougat-release
```

3. `java/INSTALL`にしたがいpatchを適用

```bash
$: patch -p1 < PATCH_FOR_JPEG.patch
```

4. 上記patch ファイルとpatch適用後ファイルをcommitして空レポジトリにpush

```bash
$: git add -A
$: git commit -m 'nanika commit messages...'
$: gh repo create my-libjpeg-turbo --public
$: git remote add mine https://github.com/JIBUN/my-libjpeg-turbo.git
$: git branch -M my/nougat-release
$: git push -u mine my/nougat-release
```
