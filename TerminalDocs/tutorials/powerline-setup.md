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
# <a name="tutorial-set-up-powerline-in-windows-terminal"></a><span data-ttu-id="fa1bb-103">チュートリアル: Windows ターミナルで Powerline をセットアップする</span><span class="sxs-lookup"><span data-stu-id="fa1bb-103">Tutorial: Set up Powerline in Windows Terminal</span></span>

<span data-ttu-id="fa1bb-104">Powerline は、Git 状態の色分けとプロンプトを提供する、カスタマイズされたコマンド プロンプト エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-104">Powerline provides a customized command prompt experience providing Git status color-coding and prompts.</span></span>

![Windows ターミナル Powerline PowerShell](./../images/powerline-powershell.png)

<span data-ttu-id="fa1bb-106">このチュートリアルでは、次の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-106">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="fa1bb-107">PowerShell での Powerline の設定</span><span class="sxs-lookup"><span data-stu-id="fa1bb-107">Set up Powerline in PowerShell</span></span>
> * <span data-ttu-id="fa1bb-108">Ubuntu または WSL での Powerline の設定</span><span class="sxs-lookup"><span data-stu-id="fa1bb-108">Set up Powerline in Ubuntu/WSL</span></span>
> * <span data-ttu-id="fa1bb-109">不足している Powerline グリフの追加</span><span class="sxs-lookup"><span data-stu-id="fa1bb-109">Add missing Powerline glyphs</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fa1bb-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="fa1bb-110">Prerequisites</span></span>

### <a name="install-a-powerline-font"></a><span data-ttu-id="fa1bb-111">Powerline フォントをインストールする</span><span class="sxs-lookup"><span data-stu-id="fa1bb-111">Install a Powerline font</span></span>

<span data-ttu-id="fa1bb-112">Powerline では、プロンプトのスタイルを設定するためにグリフを使用します。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-112">Powerline uses glyphs in order to style the prompt.</span></span> <span data-ttu-id="fa1bb-113">お使いのフォントに Powerline グリフが含まれていない場合は、プロンプト全体に Unicode の置換文字 '&#x25AF;' がいくつか表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-113">If your font does not include Powerline glyphs, you may see several Unicode replacement characters '&#x25AF;' throughout your prompt.</span></span> <span data-ttu-id="fa1bb-114">[Cascadia Mono](./../cascadia-code.md) には Powerline グリフが含まれていませんが、Powerline のグリフが含まれている Cascadia Code PL または Cascadia Mono PL をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-114">Though [Cascadia Mono](./../cascadia-code.md) does not include Powerline glyphs, you can install Cascadia Code PL or Cascadia Mono PL, which have the Powerline glyphs included.</span></span> <span data-ttu-id="fa1bb-115">これらのフォントは、[Cascadia Code GitHub リリース ページ](https://github.com/microsoft/cascadia-code/releases)からインストールできます。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-115">These fonts can be installed from the [Cascadia Code GitHub releases page](https://github.com/microsoft/cascadia-code/releases).</span></span>

## <a name="set-up-powerline-in-powershell"></a><span data-ttu-id="fa1bb-116">PowerShell での Powerline の設定</span><span class="sxs-lookup"><span data-stu-id="fa1bb-116">Set up Powerline in PowerShell</span></span>

### <a name="powershell-prerequisites"></a><span data-ttu-id="fa1bb-117">PowerShell の前提条件</span><span class="sxs-lookup"><span data-stu-id="fa1bb-117">PowerShell prerequisites</span></span>

<span data-ttu-id="fa1bb-118">まだインストールしていない場合は、[Git for Windows をインストール](https://git-scm.com/downloads)します。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-118">If you don't already have it, [install Git for Windows](https://git-scm.com/downloads).</span></span>

<span data-ttu-id="fa1bb-119">PowerShell を使用して、Posh-Git と Oh-My-Posh をインストールします。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-119">Using PowerShell, install Posh-Git and Oh-My-Posh:</span></span>

```powershell
Install-Module posh-git -Scope CurrentUser
Install-Module oh-my-posh -Scope CurrentUser
```

> [!TIP]
> <span data-ttu-id="fa1bb-120">まだ NuGet をインストールしていない場合は、インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-120">You may need to install NuGet if you don't already have it.</span></span> <span data-ttu-id="fa1bb-121">この場合、PowerShell コマンド ラインで NuGet をインストールするかどうかが尋ねられます。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-121">Your PowerShell command line will ask if you want to install NuGet if this is the case.</span></span> <span data-ttu-id="fa1bb-122">[Y] (はい) を選択します。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-122">Select [Y] Yes.</span></span> <span data-ttu-id="fa1bb-123">また、'信頼されていないリポジトリ' [PSGallery](https://docs.microsoft.com/powershell/scripting/gallery/getting-started?view=powershell-7) からモジュールをインストールすることを承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-123">You may also need to approve that you are installing modules from [PSGallery](https://docs.microsoft.com/powershell/scripting/gallery/getting-started?view=powershell-7), an 'untrusted repository'.</span></span> <span data-ttu-id="fa1bb-124">[Y] (はい) を選択します。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-124">Select [Y] Yes.</span></span>

<span data-ttu-id="fa1bb-125">[Posh-Git](https://github.com/dahlbyk/posh-git) は、Git の状態情報をプロンプトに追加すると共に、Git コマンド、パラメーター、リモート、およびブランチ名のタブ補完を追加します。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-125">[Posh-Git](https://github.com/dahlbyk/posh-git) adds Git status information to your prompt as well as tab-completion for Git commands, parameters, remotes, and branch names.</span></span> <span data-ttu-id="fa1bb-126">[Oh-My-Posh](https://github.com/JanDeDobbeleer/oh-my-posh) には、PowerShell プロンプト用のテーマ機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-126">[Oh-My-Posh](https://github.com/JanDeDobbeleer/oh-my-posh) provides theme capabilities for your PowerShell prompt.</span></span>

<span data-ttu-id="fa1bb-127">PowerShell Core を使用している場合は、PSReadline をインストールします。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-127">If you are using PowerShell Core, install PSReadline:</span></span>

```powershell
Install-Module -Name PSReadLine -Scope CurrentUser -Force -SkipPublisherCheck
```

<span data-ttu-id="fa1bb-128">[PSReadline](https://docs.microsoft.com/powershell/module/psreadline/?view=powershell-6) を使用すると、PowerShell でコマンド ライン編集環境をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-128">[PSReadline](https://docs.microsoft.com/powershell/module/psreadline/?view=powershell-6) lets you customize the command line editing environment in PowerShell.</span></span>

### <a name="customize-your-powershell-prompt"></a><span data-ttu-id="fa1bb-129">PowerShell プロンプトのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="fa1bb-129">Customize your PowerShell prompt</span></span>

<span data-ttu-id="fa1bb-130">`notepad $PROFILE` または任意のテキスト エディターを使用して、PowerShell プロファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-130">Open your PowerShell profile with `notepad $PROFILE` or the text editor of your choice.</span></span> <span data-ttu-id="fa1bb-131">これは、Windows ターミナル プロファイルではありません。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-131">This is not your Windows Terminal profile.</span></span> <span data-ttu-id="fa1bb-132">PowerShell プロファイルは、PowerShell が起動するたびに実行されるスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-132">Your PowerShell profile is a script that runs every time PowerShell starts.</span></span> <span data-ttu-id="fa1bb-133">[PowerShell プロファイルの詳細](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-7)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-133">[Learn more about PowerShell profiles](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-7).</span></span>

<span data-ttu-id="fa1bb-134">PowerShell プロファイルで、ファイルの末尾に次の内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-134">In your PowerShell profile, add the following to the end of the file:</span></span>

```powershell
Import-Module posh-git
Import-Module oh-my-posh
Set-Theme Paradox
```

<span data-ttu-id="fa1bb-135">これで、Posh-Git と Oh-My-Posh をインポートし、Oh-My-Posh から Paradox のテーマを設定することで、新しい各インスタンスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-135">Now, each new instance starts by importing Posh-Git and Oh-My-Posh, then setting the Paradox theme from Oh-My-Posh.</span></span> <span data-ttu-id="fa1bb-136">Oh-My-Posh には[組み込みのテーマ](https://github.com/JanDeDobbeleer/oh-my-posh#themes)がいくつか付属しています。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-136">Oh-My-Posh comes with several [built-in themes](https://github.com/JanDeDobbeleer/oh-my-posh#themes).</span></span>

### <a name="set-cascadia-code-pl-as-fontface-in-settings"></a><span data-ttu-id="fa1bb-137">設定で Cascadia Code PL を fontFace として設定する</span><span class="sxs-lookup"><span data-stu-id="fa1bb-137">Set Cascadia Code PL as fontFace in settings</span></span>

<span data-ttu-id="fa1bb-138">PowerLine で使用するために Cascadia Code PL フォントを (システムでダウンロード、解凍、インストールした後に) 設定するには、Windows ターミナル ドロップダウン メニューから **[設定]** (Ctrl+,) を選択し、settings.json ファイルで[プロファイル設定](../customize-settings/profile-settings.md)を開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-138">To set the Cascadia Code PL font for use with PowerLine (after downloading, unzipping, and installing on your system), you will need to open your [profile settings](../customize-settings/profile-settings.md) in your settings.json file by selecting **Settings** (Ctrl+,) from your Windows Terminal drop-down menu.</span></span>

<span data-ttu-id="fa1bb-139">settings.json ファイルが開いたら、Windows PowerShell プロファイルを見つけ、`"fontFace": "Cascadia Code PL"` を追加して Cascadia Code PL をフォントとして指定します。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-139">Once your settings.json file opens, find the Windows PowerShell profile and add: `"fontFace": "Cascadia Code PL"` to designate Cascadia Code PL as the font.</span></span> <span data-ttu-id="fa1bb-140">これにより、これらの精錬された Cascadia Code Powerline グリフが使用されます。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-140">This will provide those nice Cascadia Code Powerline glyphs.</span></span> <span data-ttu-id="fa1bb-141">エディターで **[保存]** を選択するとすぐに、ターミナルに変更が適用されます。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-141">You should notice the change in your terminal as soon as you select **Save** in your editor.</span></span>

<span data-ttu-id="fa1bb-142">Windows PowerShell プロファイルの settings.json ファイルは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-142">Your Windows PowerShell profile settings.json file should now look like this:</span></span>

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

## <a name="set-up-powerline-in-wsl-ubuntu"></a><span data-ttu-id="fa1bb-143">WSL Ubuntu で Powerline を設定する</span><span class="sxs-lookup"><span data-stu-id="fa1bb-143">Set up Powerline in WSL Ubuntu</span></span>

### <a name="wsl-ubuntu-prerequisites"></a><span data-ttu-id="fa1bb-144">WSL Ubuntu の前提条件</span><span class="sxs-lookup"><span data-stu-id="fa1bb-144">WSL Ubuntu prerequisites</span></span>

<span data-ttu-id="fa1bb-145">Ubuntu には、Powerline からインストールするためのオプションがいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-145">Ubuntu has several Powerline options to install from.</span></span> <span data-ttu-id="fa1bb-146">このチュートリアルでは、Go と Powerline-Go を使用します。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-146">This tutorial will be using Go and Powerline-Go:</span></span>

```bash
sudo apt install golang-go
go get -u github.com/justjanne/powerline-go
```

### <a name="customize-your-ubuntu-prompt"></a><span data-ttu-id="fa1bb-147">Ubuntu プロンプトをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="fa1bb-147">Customize your Ubuntu prompt</span></span>

<span data-ttu-id="fa1bb-148">`nano ~/.bashrc` または任意のテキスト エディターを使用して、`~/.bashrc` ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-148">Open your `~/.bashrc` file with `nano ~/.bashrc` or the text editor of your choice.</span></span> <span data-ttu-id="fa1bb-149">これは、bash が起動するたびに実行される bash スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-149">This is a bash script that runs every time bash starts.</span></span> <span data-ttu-id="fa1bb-150">次を追加します。ただし、GOPATH は既に存在している可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fa1bb-150">Add the following, though beware that GOPATH may already exist:</span></span>

```bash
GOPATH=$HOME/go
function _update_ps1() {
    PS1="$($GOPATH/bin/powerline-go -error $?)"
}
if [ "$TERM" != "linux" ] && [ -f "$GOPATH/bin/powerline-go" ]; then
    PROMPT_COMMAND="_update_ps1; $PROMPT_COMMAND"
fi
```

## <a name="additional-resources"></a><span data-ttu-id="fa1bb-151">その他の資料</span><span class="sxs-lookup"><span data-stu-id="fa1bb-151">Additional resources</span></span>

* <span data-ttu-id="fa1bb-152">[Scott Hanselman の "How to make a pretty prompt in Windows Terminal"](https://www.hanselman.com/blog/HowToMakeAPrettyPromptInWindowsTerminalWithPowerlineNerdFontsCascadiaCodeWSLAndOhmyposh.aspx) (Windows ターミナルで美しいプロンプトを作成する方法)</span><span class="sxs-lookup"><span data-stu-id="fa1bb-152">[Scott Hanselman's "How to make a pretty prompt in Windows Terminal"](https://www.hanselman.com/blog/HowToMakeAPrettyPromptInWindowsTerminalWithPowerlineNerdFontsCascadiaCodeWSLAndOhmyposh.aspx)</span></span>

* <span data-ttu-id="fa1bb-153">[How to change/set up bash custom prompt (PS1) in Linux](https://www.cyberciti.biz/tips/howto-linux-unix-bash-shell-setup-prompt.html) (Linux で bash カスタム プロンプト (PS1) を変更または設定する方法)</span><span class="sxs-lookup"><span data-stu-id="fa1bb-153">[How to change/set up bash custom prompt (PS1) in Linux](https://www.cyberciti.biz/tips/howto-linux-unix-bash-shell-setup-prompt.html)</span></span>
