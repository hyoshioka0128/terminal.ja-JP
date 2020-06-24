---
title: Windows ターミナルのコマンドライン引数
description: Windows ターミナルのコマンドライン引数を作成する方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 06/18/2020
ms.topic: how-to
ms.service: terminal
ms.openlocfilehash: d40b0527bab94289457cf8c8a88931f4df943496
ms.sourcegitcommit: 91a802863cd0730d2e364377ffe44f819a66ff2a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84994384"
---
# <a name="using-command-line-arguments-for-windows-terminal"></a>Windows ターミナルにコマンド ライン引数を使用する

`wt.exe` を使用すると、コマンド ラインから Windows ターミナルの新しいインスタンスを開くことができます。 代わりに、実行エイリアス `wt` を使用することもできます。

> [!NOTE]
> [GitHub](https://github.com/microsoft/terminal) のソース コードから Windows ターミナルをビルドした場合、`wtd.exe` または `wtd` を使用してそのビルドを開くことができます。

![分割ペインの Windows ターミナル コマンドライン引数](./images/terminal-command-args.gif)

## <a name="command-line-syntax"></a>コマンド ライン構文

`wt` コマンド ラインでは、**オプション** と **コマンド** の 2 種類の値が受け付けられます。 **オプション** は、`wt` コマンド ライン全体の動作を制御できるフラグとその他のパラメーターのリストです。 **コマンド** では、実装する必要がある 1 つのアクション、またはセミコロンで区切られたアクションのリストを提供します。 コマンドを指定しないと、コマンドは既定で `new-tab` と見なされます。

```bash
wt [options] [command ; ]
```

使用可能なコマンドライン引数を一覧表示するヘルプ メッセージを表示するには、`wt -h`、`wt --help`、`wt -?`、`wt /?` と入力します。

## <a name="options-and-commands"></a>オプションとコマンド

`wt` コマンド ラインでサポートされているコマンドとオプションの完全な一覧を次に示します。

| オプション | 説明 |
| ------ | ----------- |
| `--help`、`-h`、`-?`、`/?` | ヘルプ メッセージを表示します。 |
| `--maximized`、`-M` | ターミナルを最大化して起動します。 |
| `--fullscreen`、`-F` | ターミナルを全画面で起動します。 |

> [!IMPORTANT]
> `--maximized`、`-M` と `--fullscreen`、`-F` は、[Windows ターミナル プレビュー](https://aka.ms/terminal-preview/)でのみ使用できます。

| コマンド | パラメーター | 説明 |
| ------- | ---------- | ----------- |
| `new-tab` | `--profile, -p profile-name`、`--startingDirectory, -d starting-directory`、`commandline`、`--title` | 新しいタブを作成します。 |
| `split-pane` | `-H, --horizontal`、`-V, --vertical`、`--profile, -p profile-name`、`--startingDirectory, -d starting-directory`、`commandline`、`--title` | 新しいペインを分割します。 |
| `focus-tab` | `--target, -t tab-index` | 特定のタブにフォーカスを設定します。 |

> [!IMPORTANT]
> `--title` は、[Windows ターミナル プレビュー](https://aka.ms/terminal-preview/)でのみ使用できます。

## <a name="command-line-argument-examples"></a>コマンド ライン引数の例

コマンドは、使用しているコマンド ラインによって多少異なる場合があります。

### <a name="open-a-new-profile-instance"></a>新しいプロファイル インスタンスを開く

新しいターミナル インスタンスを開くには、次のように入力します。このコマンドでは、"Ubuntu-18.04" という名前のプロファイルが開かれます。

<!-- Start tab selectors. -->
#### <a name="command-prompt"></a>[コマンド プロンプト](#tab/windows)

```bash
wt -p "Ubuntu-18.04"
```

#### <a name="powershell"></a>[PowerShell](#tab/powershell)

```powershell
wt -p "Ubuntu-18.04"
```

#### <a name="linux"></a>[Linux](#tab/linux)

```bash
cmd.exe /c "wt.exe" -p "Ubuntu-18.04"
```

実行エイリアスは、WSL ディストリビューションでは機能しません。 WSL コマンド ラインから wt.exe を使用する場合は、`cmd.exe` を実行することにより、CMD から直接生成することができます。 `/c` オプションは、実行後に終了するよう CMD に指示します。

---
<!-- End tab selectors.  -->

 `-p` フラグを使用して、開く必要がある Windows ターミナル プロファイルを指定します。 "Ubuntu-18.04" を、インストールされているターミナル プロファイルの名前に置き換えます。 このようにすると、常に新しいウィンドウが開きます。 Windows ターミナルでは、既存のインスタンスで新しいタブまたはペインを開くことはまだできません。

### <a name="target-a-directory"></a>ディレクトリをターゲットにする

コンソールの開始ディレクトリとして使用するフォルダーを指定するには、次のように入力します。この場合は d:\ ディレクトリです。

<!-- Start tab selectors. -->
#### <a name="command-prompt"></a>[コマンド プロンプト](#tab/windows)

```bash
wt -d d:\
```

#### <a name="powershell"></a>[PowerShell](#tab/powershell)

```powershell
wt -d d:\
```

#### <a name="linux"></a>[Linux](#tab/linux)

```bash
cmd.exe /c "wt.exe" -d d:\
```

実行エイリアスは、WSL ディストリビューションでは機能しません。 WSL コマンド ラインから wt.exe を使用する場合は、`cmd.exe` を実行することにより、CMD から直接生成することができます。 `/c` オプションは、実行後に終了するよう CMD に指示します。

---
<!-- End tab selectors.  -->

### <a name="multiple-tabs"></a>複数のタブ

複数のタブを持つ新しいターミナル インスタンスを開くには、次のように入力します。

<!-- Start tab selectors. -->
#### <a name="command-prompt"></a>[コマンド プロンプト](#tab/windows)

```bash
wt ; ;
```

#### <a name="powershell"></a>[PowerShell](#tab/powershell)

```powershell
wt `; `;
```

PowerShell では、ステートメントを区切るためにセミコロン ; を使用します。 wt コマンドライン引数でセミコロン ; がコマンド区切り記号として解釈されるためには、バッククォートを使用してセミコロン文字をエスケープする必要があります。 また、PowerShell には、解析停止演算子 (--%) もあります。これにより、それより後のすべての解釈が停止され、逐語的にただ渡されます。

#### <a name="linux"></a>[Linux](#tab/linux)

```bash
cmd.exe /c "wt.exe" \; \;
```

実行エイリアスは、WSL ディストリビューションでは機能しません。 WSL コマンド ラインから wt.exe を使用する場合は、`cmd.exe` を実行することにより、CMD から直接生成することができます。 `/c` オプションは、実行後に終了するよう CMD に指示します。

---
<!-- End tab selectors.  -->

複数のタブを持つ新しいターミナル インスタンスを開くには、次のように入力します。この場合はコマンド プロンプト プロファイルと PowerShell プロファイルです。

<!-- Start tab selectors. -->
#### <a name="command-prompt"></a>[コマンド プロンプト](#tab/windows)

```bash
wt -p "Command Prompt" ; new-tab -p "Windows PowerShell"
```

#### <a name="powershell"></a>[PowerShell](#tab/powershell)

```powershell
wt -p "Command Prompt" `; new-tab -p "Windows PowerShell"
```

PowerShell では、ステートメントを区切るためにセミコロン ; を使用します。 wt コマンドライン引数でセミコロン ; がコマンド区切り記号として解釈されるためには、バッククォートを使用してセミコロン文字をエスケープする必要があります。 また、PowerShell には、解析停止演算子 (--%) もあります。これにより、それより後のすべての解釈が停止され、逐語的にただ渡されます。

#### <a name="linux"></a>[Linux](#tab/linux)

```bash
cmd.exe /c "wt.exe" -p "Command Prompt" \; new-tab -p "Windows Powershell"
```

実行エイリアスは、WSL ディストリビューションでは機能しません。 WSL コマンド ラインから wt.exe を使用する場合は、`cmd.exe` を実行することにより、CMD から直接生成することができます。 `/c` オプションは実行後に終了するよう CMD に指示するものであり、`\;` (スラッシュ + セミコロン) はコマンド間の区切りです。

---
<!-- End tab selectors.  -->

### <a name="multiple-panes"></a>複数のペイン

コマンド プロンプト プロファイル、PowerShell プロファイル、および WSL コマンド ラインを実行する既定のプロファイルが実行されている 3 つのペインが含まれる 1 つのタブを持つ新しいターミナル インスタンスを開くには、次のように入力します。

<!-- Start tab selectors. -->
#### <a name="command-prompt"></a>[コマンド プロンプト](#tab/windows)

```bash
wt -p "Command Prompt" ; split-pane -p "Windows PowerShell" ; split-pane -H wsl.exe
```

#### <a name="powershell"></a>[PowerShell](#tab/powershell)

```powershell
wt -p "Command Prompt" `; split-pane -p "Windows PowerShell" `; split-pane -H wsl.exe
```

PowerShell では、ステートメントを区切るためにセミコロン ; を使用します。 wt コマンドライン引数でセミコロン ; がコマンド区切り記号として解釈されるためには、バッククォートを使用してセミコロン文字をエスケープする必要があります。 また、PowerShell には、解析停止演算子 (--%) もあります。これにより、それより後のすべての解釈が停止され、逐語的にただ渡されます。

#### <a name="linux"></a>[Linux](#tab/linux)

```bash
cmd.exe /c "wt.exe" -p "Command Prompt" \; split-pane -p "Windows PowerShell" \; split-pane -H wsl.exe
```

実行エイリアスは、WSL ディストリビューションでは機能しません。 WSL コマンド ラインから wt.exe を使用する場合は、`cmd.exe` を実行することにより、CMD から直接生成することができます。 `/c` オプションは実行後に終了するよう CMD に指示するものであり、`\;` (スラッシュ + セミコロン) はコマンド間の区切りです。

---
<!-- End tab selectors.  -->

`-H` フラグ (または `--horizontal`) は、ペインを水平方向に分割するように指定します。 `-V` フラグ (または `--vertical`) は、ペインを垂直方向に分割するように指定します。

### <a name="tab-title-preview"></a>タブ タイトル ([プレビュー](https://aka.ms/terminal-preview/))

カスタム タブ タイトルを使用して新しいターミナル インスタンスを開くには、`--title` 引数を使用します。 2 つのタブを開くときに各タブのタイトルを設定するには、次のように入力します。

<!-- Start tab selectors. -->
#### <a name="command-prompt"></a>[コマンド プロンプト](#tab/windows)

```bash
wt --title tabname1 ; new-tab -p "Ubuntu-18.04" --title tabname2
```

#### <a name="powershell"></a>[PowerShell](#tab/powershell)

```powershell
wt --title tabname1 `; new-tab -p "Ubuntu-18.04" --title tabname2
```

#### <a name="linux"></a>[Linux](#tab/linux)

```bash
cmd.exe /c "wt.exe" --title tabname1 \; new-tab -p "Ubuntu-18.04" --title tabname2
```

実行エイリアスは、WSL ディストリビューションでは機能しません。 WSL コマンド ラインから wt.exe を使用する場合は、`cmd.exe` を実行することにより、CMD から直接生成することができます。 `/c` オプションは実行後に終了するよう CMD に指示するものであり、`\;` (スラッシュ + セミコロン) はコマンド間の区切りです。

---
<!-- End tab selectors.  -->

> [!IMPORTANT]
> この機能は、[Windows ターミナル プレビュー](https://aka.ms/terminal-preview/)でのみ使用できます。

### <a name="tab-focus"></a>タブ フォーカス

特定のタブにフォーカスを設定して新しいターミナル インスタンスを開くには、`-t` フラグ (または `--target`) とタブ インデックス番号を使用します。 1 番目のタブで既定のプロファイルを開き、2 番目のタブ (`-t 1`) で "Ubuntu-18.04" プロファイルを開いてフォーカスを設定するには、次のように入力します。

<!-- Start tab selectors. -->
#### <a name="command-prompt"></a>[コマンド プロンプト](#tab/windows)

```bash
wt ; new-tab -p "Ubuntu-18.04" ; focus-tab -t 1
```

#### <a name="powershell"></a>[PowerShell](#tab/powershell)

```powershell
wt `; new-tab -p "Ubuntu-18.04" `; focus-tab -t 1
```

#### <a name="linux"></a>[Linux](#tab/linux)

```bash
cmd.exe /c "wt.exe" \; new-tab -p "Ubuntu-18.04" \; focus-tab -t 1
```

実行エイリアスは、WSL ディストリビューションでは機能しません。 WSL コマンド ラインから wt.exe を使用する場合は、`cmd.exe` を実行することにより、CMD から直接生成することができます。 `/c` オプションは実行後に終了するよう CMD に指示するものであり、`\;` (スラッシュ + セミコロン) はコマンド間の区切りです。

---
<!-- End tab selectors.  -->

## <a name="examples-of-multiple-commands-from-powershell"></a>PowerShell からの複数のコマンドの例

Windows ターミナルでは、`wt` コマンド ラインのコマンドを区切るための区切り記号として、セミコロン文字 `;` を使用します。 残念ながら、PowerShell では、コマンドの区切り記号としても `;` を使用します。 これを回避するには、次の方法を使用して、PowerShell から複数の `wt` コマンドを実行できます。 以下のすべての例では、3 つのペインから成る新しいターミナル ウィンドウが作成されます。コマンド プロンプトを実行するペイン、PowerShell のペイン、WSL を実行するペインです。

次の例では、`Start-Process` コマンドを使用して `wt` を実行します。 ターミナルで `Start-Process` を使用する理由について詳しくは、後の「[start を使用する](#using-start)」をご覧ください。

### <a name="single-quoted-parameters"></a>単一引用符で囲まれたパラメーター

この例では、`wt` パラメーターは単一引用符 (`'`) でラップされています。 この構文は、何も計算されていない場合に役に立ちます。

```powershell
start wt 'new-tab "cmd" ; split-pane -p "Windows PowerShell" ; split-pane -H wsl.exe'
```

### <a name="escaped-quotes"></a>エスケープされた引用符

変数に格納されている値を `wt` のコマンド ラインに渡す場合は、次の構文を使用します。

```powershell
$ThirdPane = "wsl.exe"
start wt "new-tab cmd ; split-pane -p `"Windows PowerShell`" ; split-pane -H $ThirdPane"
```

`split-pane` パラメーターに対する `-p` パラメーターの "Windows PowerShell" を囲む二重引用符 (`"`) をエスケープするために、`` ` `` が使用されていることに注意してください。

### <a name="using-start"></a>`start` を使用する

上記の例ではすべて、ターミナルを起動するために `start` が明示的に使用されています。

次の例では、`start` を使用しないでコマンド ラインを実行しています。 代わりに、コマンド ラインをエスケープする方法が他に 2 つあります。

* `PowerShell` によってセミコロンが無視され、`wt` にそのまま渡されるように、セミコロンだけをエスケープします。
* コマンド ラインの残りの部分が PowerShell によってアプリケーションへの引数として扱われるように、`--%` を使用します。

```powershell
wt new-tab "cmd" `; split-pane -p "Windows PowerShell" `; split-pane -H wsl.exe
```

```powershell
wt --% new-tab cmd ; split-pane -p "Windows PowerShell" ; split-pane -H wsl.exe
```

どちらの例でも、新しく作成される Windows ターミナル ウィンドウでは、指定したすべてのコマンドライン引数が正しく解析されてウィンドウが作成されます。

ただし、新しく作成されたターミナル ウィンドウが閉じられるまで待ってから、PowerShell に制御が返されるため、現在は、これらの方法は推奨 "_されません_"。 既定では、PowerShell は常に、Windows ストア アプリケーション (Windows ターミナルなど) が終了するまで待ってからプロンプトに戻ります。 これは、すぐにプロンプトに戻るコマンド プロンプトの動作とは異なることに注意してください。
