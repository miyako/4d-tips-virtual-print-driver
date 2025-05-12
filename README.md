# 4d-tips-virtual-print-driver

|ドライバー|印刷ダイアログの抑制|出力ファイル名の指定|備考|
|-|:-:|:-:|-|
|[clawPDF 0.9.31](https://github.com/miyako/4d-topic-clawpdf)|✅|✅|自動保存オプションをGUIで設定|
|[PDF24 Creator 11.25.1](https://github.com/miyako/4d-topic-pdf24)|⚠️|⚠️|自動保存オプションをGUIで設定・非同期処理|
|[doPDF 11.9 build 492](https://ja.dopdf.com)|❌|❌|インストール不可|
|[PrimoPDF 4.1.0.10](https://www.xlsoft.com/jp/products/primopdf/download.html)|❌|❌|インストール不可|
|[PDF Creator 6.0.1 Free](https://www.pdfforge.org/pdfcreator/download)|❌|❌|印刷ダイアログ抑制不可[^pdfcreator]

<img src="https://github.com/user-attachments/assets/5d490305-132c-411a-9e8f-a12603cc7bbf" width=400 height=auto />

[^pdfcreator]: 有償版とは違い，COMオブジェクトがインストールされません。ホームページにはフリー版もCOMに対応していると書かれていますが，それは起動中のアプリをVBAで制御できるという意味で，本格的なパラメーター制御ができるという意味ではありません。
