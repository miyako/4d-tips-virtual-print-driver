# 4d-tips-virtual-print-driver

### [doPDF 11.9 build 492](https://ja.dopdf.com)

> [!CAUTION]
> インストール中にエラーが発生しました。`PRINTERS LIST`に追加されません。

### [PrimoPDF 4.1](https://www.xlsoft.com/jp/products/primopdf/download.html) 

> [!CAUTION]
> インストール中にエラーが発生しました。`PRINTERS LIST`に追加されません。

### [PDF24 Creator 11.25.1](https://tools.pdf24.org/ja/creator#download)

> [!WARNING]
> 途中で警告が表示されましたが，インストールには成功しました。

<img src="https://github.com/user-attachments/assets/e4939ef6-e78d-487b-96b4-632dea2c10d2" width=400 height=auto />

`SET PRINT OPTION`が対応していないので，フリー版は印刷時にダイアログが表示されます。プロ版・OEM版であれば，強力なCLIツールが利用できます。

<img src="https://github.com/user-attachments/assets/3ae9b01e-96e1-40dc-8db1-eba5e81d0983" width=400 height=auto />

フリー版でも，設定アプリで保存フォルダーとファイルの命名規則を設定すれば，ダイアログを抑制できます。

<img src="https://github.com/user-attachments/assets/115c6dae-6f22-4658-a2df-10894e1f8e88" width=400 height=auto />

印刷は非同期なので，PDFの完成を待機する必要があります。

```4d
PRINTERS LIST($names)

SET CURRENT PRINTER("PDF24")
SET PRINT OPTION(Paper option; "A5")

$before:=Folder(fk desktop folder).files().query("extension == :1"; ".pdf").extract("fullName")

OPEN PRINTING JOB
$h:=Print form("test")
CLOSE PRINTING JOB

Repeat 
	$after:=Folder(fk desktop folder).files().query("extension == :1 except fullName in :2"; ".pdf"; $before).first()
	DELAY PROCESS(Current process; 6)
Until ($after#Null)

OPEN URL($after.platformPath)
```

### [PDF Creator 6.0.1 Free](https://www.pdfforge.org/pdfcreator/download)

> [!WARNING]
> 最新版を汎用的な仮想ドライバーとしてインストールすることはできますが，`SET PRINT OPTION`が対応していないので，フリー版は印刷時にダイアログが表示されます。プロ版・ビジネス版であれば，PowerShellまたはCOMインタフェース経由で制御できます。

<img src="https://github.com/user-attachments/assets/5d490305-132c-411a-9e8f-a12603cc7bbf" width=400 height=auto />
