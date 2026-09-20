# negotimer for Windows — 配布リポジトリ

オンラインの交流会・商談で、**タイマーを参加者のタイルとして見せる** Windows アプリ
「negotimer」のインストーラを配布しています。

**このリポジトリにソースコードはありません。** 配布物（Releases）だけを置いています。

- 製品ページ: https://shikumill.com/negotimer/windows/
- negotimer（iPhone / Android）: https://shikumill.com/negotimer/

## ダウンロード

[**Releases**](https://github.com/OzakiSatoshi/negotimer-dist/releases/latest) から
`negotimer-setup-x.y.z.exe` を取得してください。

- 対応 OS: **Windows 11 以降**（アプリをカメラとして登録する仕組みが Windows 11 で
  追加されたものであるため）
- インストールには**管理者権限**が必要です（タイマーをカメラとして登録するため）。
  アンインストール時に登録も消えます

## 「Windows によって PC が保護されました」と出ます

出ます。**故障ではありません。**

negotimer は**コード署名証明書を使っていません**。証明書は年額で費用がかかるもので、
小さなアプリでそこに費用をかけるより、その分を機能に回す判断をしています。
署名が無いアプリは、Windows がこの画面を出します。

1. **「詳細情報」**をクリック
2. 下に出る**「実行」**をクリック

気になる場合は、ダウンロードしたファイルのハッシュが各 Release に記載の SHA-256 と
一致することを確かめてから実行してください。

```powershell
Get-FileHash .\negotimer-setup-x.y.z.exe -Algorithm SHA256
```

手順の詳しい説明は https://shikumill.com/negotimer/windows/ にあります。

## サポート・プライバシー

- サポート: https://ozakisatoshi.github.io/negotimer-legal/support.html
- プライバシーポリシー: https://ozakisatoshi.github.io/negotimer-legal/

提供：[合同会社シクミル](https://shikumill.com/)

## `latest.json` について

アプリが起動時に見に行く、最新版の情報です。

```
https://raw.githubusercontent.com/OzakiSatoshi/negotimer-dist/main/latest.json
```

Windows 版はストアを通さない自社配布で、**自動更新の仕組みがありません**。
放っておくと古いまま使われるので、アプリが起動ごとに 1 回だけここを見て、
新しい版があれば「新しい版があります」と知らせます。
**自動では落としませんし、入れません**（署名していないインストーラを黙って
落とすのは、やってはいけないことに近いため）。押されたら製品ページを開くだけです。

**リリースを出したら、必ずこのファイルも更新してください。**
更新を忘れると、誰にも新しい版が届きません。

| 項目 | 意味 |
|---|---|
| `version` | 最新版。アプリは自分の版と数字で比べます（`1.2.10` > `1.2.9`） |
| `url` | インストーラの URL。**https 以外はアプリが受け付けません** |
| `sha256` | 配布物のハッシュ。製品ページの表記と揃えてください |
| `notes` | 帯に 1 行で出る説明。長くしないこと |
