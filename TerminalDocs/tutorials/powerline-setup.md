---
title: Windows ターミナル Powerline のセットアップ
description: このチュートリアルでは、Windows ターミナルで Powerline を設定する方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: tutorial
ms.service: terminal
ms.openlocfilehash: 2896ede288e0e466f68323a87e5a4b07bd509d3c
ms.sourcegitcommit: bae07a8dd2010a95de4d53b1465abe226e4ad18e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2020
ms.locfileid: "83856350"
---
# <a name="tutorial-set-up-powerline-in-windows-terminal"></a>チュートリアル: Windows ターミナルで Powerline をセットアップする

Powerline は、Git 状態の色分けとプロンプトを提供する、カスタマイズされたコマンド プロンプト エクスペリエンスを提供します。

![Windows ターミナル Powerline PowerShell](./../images/powerline-powershell.png)

このチュートリアルでは、次の方法について説明します。

> [!div class="checklist"]
>
> * PowerShell での Powerline の設定
> * Ubuntu または WSL での Powerline の設定
> * 不足している Powerline グリフの追加

## <a name="prerequisites"></a>前提条件

### <a name="install-a-powerline-font"></a>Powerline フォントをインストールする

Powerline では、プロンプトのスタイルを設定するためにグリフを使用します。 お使いのフォントに Powerline グリフが含まれていない場合は、プロンプト全体に Unicode の置換文字 '&#x25AF;' がいくつか表示されることがあります。 [Cascadia Mono](./../cascadia-code.md) には Powerline グリフが含まれていませんが、Powerline のグリフが含まれている Cascadia Code PL または Cascadia Mono PL をインストールできます。 これらのフォントは、[Cascadia Code GitHub リリース ページ](https://github.com/microsoft/cascadia-code/releases)からインストールできます。

## <a name="set-up-powerline-in-powershell"></a>PowerShell での Powerline の設定

### <a name="powershell-prerequisites"></a>PowerShell の前提条件

まだインストールしていない場合は、[Git for Windows をインストール](https://git-scm.com/downloads)します。

PowerShell を使用して、Posh-Git と Oh-My-Posh をインストールします。

```powershell
Install-Module posh-git -Scope CurrentUser
Install-Module oh-my-posh -Scope CurrentUser
```

> [!TIP]
> まだ NuGet をインストールしていない場合は、インストールする必要があります。 この場合、PowerShell コマンド ラインで NuGet をインストールするかどうかが尋ねられます。 [Y] (はい) を選択します。 また、'信頼されていないリポジトリ' [PSGallery](https://docs.microsoft.com/powershell/scripting/gallery/getting-started?view=powershell-7) からモジュールをインストールすることを承認する必要があります。 [Y] (はい) を選択します。

[Posh-Git](https://github.com/dahlbyk/posh-git) は、Git の状態情報をプロンプトに追加すると共に、Git コマンド、パラメーター、リモート、およびブランチ名のタブ補完を追加します。 [Oh-My-Posh](https://github.com/JanDeDobbeleer/oh-my-posh) には、PowerShell プロンプト用のテーマ機能が用意されています。

PowerShell Core を使用している場合は、PSReadline をインストールします。

```powershell
Install-Module -Name PSReadLine -Scope CurrentUser -Force -SkipPublisherCheck
```

[PSReadline](https://docs.microsoft.com/powershell/module/psreadline/?view=powershell-6) を使用すると、PowerShell でコマンド ライン編集環境をカスタマイズできます。

### <a name="customize-your-powershell-prompt"></a>PowerShell プロンプトのカスタマイズ

`notepad $PROFILE` または任意のテキスト エディターを使用して、PowerShell プロファイルを開きます。 これは、Windows ターミナル プロファイルではありません。 PowerShell プロファイルは、PowerShell が起動するたびに実行されるスクリプトです。 [PowerShell プロファイルの詳細](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-7)を参照してください。

PowerShell プロファイルで、ファイルの末尾に次の内容を追加します。

```powershell
Import-Module posh-git
Import-Module oh-my-posh
Set-Theme Paradox
```

これで、Posh-Git と Oh-My-Posh をインポートし、Oh-My-Posh から Paradox のテーマを設定することで、新しい各インスタンスが開始されます。 Oh-My-Posh には[組み込みのテーマ](https://github.com/JanDeDobbeleer/oh-my-posh#themes)がいくつか付属しています。

### <a name="set-cascadia-code-pl-as-fontface-in-settings"></a>設定で Cascadia Code PL を fontFace として設定する

PowerLine で使用するために Cascadia Code PL フォントを (システムでダウンロード、解凍、インストールした後に) 設定するには、Windows ターミナル ドロップダウン メニューから **[設定]** (Ctrl+,) を選択し、settings.json ファイルで[プロファイル設定](../customize-settings/profile-settings.md)を開く必要があります。

settings.json ファイルが開いたら、Windows PowerShell プロファイルを見つけ、`"fontFace": "Cascadia Code PL"` を追加して Cascadia Code PL をフォントとして指定します。 これにより、これらの精錬された Cascadia Code Powerline グリフが使用されます。 エディターで **[保存]** を選択するとすぐに、ターミナルに変更が適用されます。

Windows PowerShell プロファイルの settings.json ファイルは次のようになります。

```json
{
    // Make changes here to the powershell.exe profile.
    "guid": "{61c54bbd-c2c6-5271-96e7-009a87ff44bf}",
    "name": "Windows PowerShell",
    "commandline": "powershell.exe",
    "fontFace": "Cascadia Code PL",
    "hidden": false
},
```

## <a name="set-up-powerline-in-wsl-ubuntu"></a>WSL Ubuntu で Powerline を設定する

### <a name="wsl-ubuntu-prerequisites"></a>WSL Ubuntu の前提条件

Ubuntu には、Powerline からインストールするためのオプションがいくつか用意されています。 このチュートリアルでは、Go と Powerline-Go を使用します。

```bash
sudo apt install golang-go
go get -u github.com/justjanne/powerline-go
```

### <a name="customize-your-ubuntu-prompt"></a>Ubuntu プロンプトをカスタマイズする

`nano ~/.bashrc` または任意のテキスト エディターを使用して、`~/.bashrc` ファイルを開きます。 これは、bash が起動するたびに実行される bash スクリプトです。 次を追加します。ただし、GOPATH は既に存在している可能性があることに注意してください。

```bash
GOPATH=$HOME/go
function _update_ps1() {
    PS1="$($GOPATH/bin/powerline-go -error $?)"
}
if [ "$TERM" != "linux" ] && [ -f "$GOPATH/bin/powerline-go" ]; then
    PROMPT_COMMAND="_update_ps1; $PROMPT_COMMAND"
fi
```

## <a name="additional-resources"></a>その他の資料

* [Scott Hanselman の "How to make a pretty prompt in Windows Terminal"](https://www.hanselman.com/blog/HowToMakeAPrettyPromptInWindowsTerminalWithPowerlineNerdFontsCascadiaCodeWSLAndOhmyposh.aspx) (Windows ターミナルで美しいプロンプトを作成する方法)

* [How to change/set up bash custom prompt (PS1) in Linux](https://www.cyberciti.biz/tips/howto-linux-unix-bash-shell-setup-prompt.html) (Linux で bash カスタム プロンプト (PS1) を変更または設定する方法)
