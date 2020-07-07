---
title: Windows ターミナルの概要
description: Windows ターミナルの概要と、それによってコマンド ライン ワークフローを改善する方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: overview
ms.service: terminal
ms.localizationpriority: high
ms.openlocfilehash: abc0397c3f26da92980377aac2df466fe1bf190e
ms.sourcegitcommit: d8e23557224bc50a82a36dc80ac68b9d11dfdde9
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2020
ms.locfileid: "84720118"
---
# <a name="what-is-windows-terminal"></a><span data-ttu-id="b6b10-103">Windows ターミナルとは</span><span class="sxs-lookup"><span data-stu-id="b6b10-103">What is Windows Terminal?</span></span>

<span data-ttu-id="b6b10-104">Windows ターミナルは、コマンド プロンプト、PowerShell、Linux 用 Windows サブシステム (WSL) などのコマンドライン ツールとシェルのユーザー向けの最新のターミナル アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="b6b10-104">Windows Terminal is a modern terminal application for users of command-line tools and shells like Command Prompt, PowerShell, and Windows Subsystem for Linux (WSL).</span></span> <span data-ttu-id="b6b10-105">主な機能には、複数のタブ、ペイン、Unicode および UTF-8 文字のサポート、GPU で高速化されたテキスト レンダリング エンジン、独自のテーマを作成したり、テキスト、色、背景、およびショートカット キーのバインドをカスタマイズしたりする機能があります。</span><span class="sxs-lookup"><span data-stu-id="b6b10-105">Its main features include multiple tabs, panes, Unicode and UTF-8 character support, a GPU accelerated text rendering engine, and the ability to create your own themes and customize text, colors, backgrounds, and shortcut key bindings.</span></span>

![Windows ターミナルのスクリーンショット](./images/overview.png)

> [!NOTE]
> [<span data-ttu-id="b6b10-107">コンソール、ターミナル、シェルの違いとは</span><span class="sxs-lookup"><span data-stu-id="b6b10-107">What's the difference between a console, a terminal, and a shell?</span></span>](https://www.hanselman.com/blog/WhatsTheDifferenceBetweenAConsoleATerminalAndAShell.aspx) <span data-ttu-id="b6b10-108">Scott Hanselman の説明をお読みください。</span><span class="sxs-lookup"><span data-stu-id="b6b10-108">Read Scott Hanselman's explanation.</span></span>

## <a name="multiple-profiles-supporting-a-variety-of-command-line-applications"></a><span data-ttu-id="b6b10-109">さまざまなコマンドライン アプリケーションをサポートする複数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="b6b10-109">Multiple profiles supporting a variety of command-line applications</span></span>

<span data-ttu-id="b6b10-110">コマンドライン インターフェイスを持つ任意のアプリケーションを Windows ターミナル内で実行できます。</span><span class="sxs-lookup"><span data-stu-id="b6b10-110">Any application that has a command-line interface can be run inside Windows Terminal.</span></span> <span data-ttu-id="b6b10-111">これには、PowerShell およびコマンド プロンプトから Azure Cloud Shell、Ubuntu や Oh-My-Zsh などの任意の WSL ディストリビューションまで、あらゆるものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b6b10-111">This includes everything from PowerShell and Command Prompt to Azure Cloud Shell and any WSL distribution such as Ubuntu or Oh-My-Zsh.</span></span>

## <a name="customized-schemes-and-configurations"></a><span data-ttu-id="b6b10-112">カスタマイズされたスキームと構成</span><span class="sxs-lookup"><span data-stu-id="b6b10-112">Customized schemes and configurations</span></span>

<span data-ttu-id="b6b10-113">Windows ターミナルにさまざまな配色や設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="b6b10-113">You can configure your Windows Terminal to have a variety of color schemes and settings.</span></span> <span data-ttu-id="b6b10-114">独自の配色を作成する方法については、[配色に関するページ](./customize-settings/color-schemes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b10-114">To learn how to make your own color scheme, visit the [Color schemes page](./customize-settings/color-schemes.md).</span></span> <span data-ttu-id="b6b10-115">[カスタム ターミナル ギャラリー](./custom-terminal-gallery/powerline-in-powershell.md)でカスタム ターミナル構成を見つけることもできます。</span><span class="sxs-lookup"><span data-stu-id="b6b10-115">You can also find custom Terminal configurations in the [Custom terminal gallery](./custom-terminal-gallery/powerline-in-powershell.md).</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="b6b10-116">カスタム キー バインド</span><span class="sxs-lookup"><span data-stu-id="b6b10-116">Custom key bindings</span></span>

<span data-ttu-id="b6b10-117">Windows ターミナルでは、より自然に使用できるようにするためにさまざまなカスタム キーの組み合わせが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b6b10-117">There are a variety of custom key combinations you can use in Windows Terminal to have it feel more natural to you.</span></span> <span data-ttu-id="b6b10-118">特定のショートカット キーが気に入らない場合は、お好きなものに変更できます。</span><span class="sxs-lookup"><span data-stu-id="b6b10-118">If you don't like a particular keyboard shortcut, you can change it to whatever you prefer.</span></span>

<span data-ttu-id="b6b10-119">たとえば、コマンド ラインからテキストをコピーするための既定のショートカット キー バインドは、<kbd>ctrl+shift+c</kbd> です。</span><span class="sxs-lookup"><span data-stu-id="b6b10-119">For example, the default shortcut key binding to copy text from the command line is <kbd>ctrl+shift+c</kbd>.</span></span> <span data-ttu-id="b6b10-120">これを、<kbd>ctrl+1</kbd> やお好きなものに変更できます。</span><span class="sxs-lookup"><span data-stu-id="b6b10-120">You can change this to <kbd>ctrl+1</kbd> or whatever you prefer.</span></span> <span data-ttu-id="b6b10-121">新しいタブを開くための既定のショートカットは <kbd>ctrl+shift+t</kbd> ですが、これを <kbd>ctrl+2</kbd> に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="b6b10-121">To open a new tab, the default shortcut is <kbd>ctrl+shift+t</kbd>, but maybe you want to change this to <kbd>ctrl+2</kbd>.</span></span> <span data-ttu-id="b6b10-122">開いているタブの間を切り替える既定のショートカットは <kbd>ctrl+tab</kbd> ですが、これを <kbd>ctrl+-</kbd> に変更し、代わりに新しいタブを作成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6b10-122">The default shortcut to flip between the tabs you have open is <kbd>ctrl+tab</kbd>, this could be changed to <kbd>ctrl+-</kbd> and used to create a new tab instead.</span></span>

<span data-ttu-id="b6b10-123">キー バインドのカスタマイズについては、[キー バインドに関するページ](./customize-settings/key-bindings.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b10-123">You can learn about customizing your key bindings on the [Key bindings page](./customize-settings/key-bindings.md).</span></span>

## <a name="unicode-and-utf-8-character-support"></a><span data-ttu-id="b6b10-124">Unicode および UTF-8 文字のサポート</span><span class="sxs-lookup"><span data-stu-id="b6b10-124">Unicode and UTF-8 character support</span></span>

<span data-ttu-id="b6b10-125">Windows ターミナルでは、絵文字やさまざまな言語の文字などの Unicode および UTF-8 文字を表示できます。</span><span class="sxs-lookup"><span data-stu-id="b6b10-125">Windows Terminal can display Unicode and UTF-8 characters such as emoji and characters from a variety of languages.</span></span>

## <a name="gpu-accelerated-text-rendering"></a><span data-ttu-id="b6b10-126">GPU で高速化されたテキスト レンダリング</span><span class="sxs-lookup"><span data-stu-id="b6b10-126">GPU accelerated text rendering</span></span>

<span data-ttu-id="b6b10-127">Windows ターミナルではテキストのレンダリングに GPU を使用しているため、既定の Windows コマンドライン エクスペリエンスよりもパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="b6b10-127">Windows Terminal uses the GPU to render its text, thus providing improved performance over the default Windows command-line experience.</span></span>

## <a name="background-image-support"></a><span data-ttu-id="b6b10-128">背景画像のサポート</span><span class="sxs-lookup"><span data-stu-id="b6b10-128">Background image support</span></span>

<span data-ttu-id="b6b10-129">Windows ターミナル ウィンドウ内に背景画像と gif を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b6b10-129">You can have background images and gifs inside your Windows Terminal window.</span></span> <span data-ttu-id="b6b10-130">プロファイルに背景画像を追加する方法については、[プロファイル設定に関するページ](./customize-settings/profile-settings.md#background-image-settings)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b10-130">Information on how to add background images to your profile can be found on the [Profile settings page](./customize-settings/profile-settings.md#background-image-settings).</span></span>

## <a name="command-line-arguments"></a><span data-ttu-id="b6b10-131">コマンド ライン引数</span><span class="sxs-lookup"><span data-stu-id="b6b10-131">Command line arguments</span></span>

<span data-ttu-id="b6b10-132">コマンドライン引数を使用して、特定の構成で起動するように Windows ターミナルを設定できます。</span><span class="sxs-lookup"><span data-stu-id="b6b10-132">You can set Windows Terminal to launch in a specific configuration using command-line arguments.</span></span> <span data-ttu-id="b6b10-133">新しいタブで開くプロファイルや選択されるフォルダー ディレクトリを指定したり、分割したウィンドウ ペインでターミナルを開いたり、フォーカスするタブを選択したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="b6b10-133">You can specify which profile to open in a new tab, which folder directory should be selected, open the terminal with split window panes, and choose which tab should be in focus.</span></span>

<span data-ttu-id="b6b10-134">たとえば、左側のペインでコマンド プロンプト プロファイルを実行し、右側のペインを PowerShell と WSL を実行する既定のプロファイルとの間で分割した、3 つのペインがある PowerShell から Windows ターミナルを開くには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b6b10-134">For example, to open Windows Terminal from PowerShell with three panes, with the left pane running a Command Prompt profile and the right pane split between your PowerShell and your default profile running WSL, enter:</span></span>

```bash
wt -p "Command Prompt" `; split-pane -p "Windows PowerShell" `; split-pane -H wsl.exe
```

<span data-ttu-id="b6b10-135">コマンド ライン引数を設定する方法については、[コマンド ライン引数に関するページ](./command-line-arguments.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b10-135">Learn how to set up command-line arguments on the [Command line arguments page](./command-line-arguments.md).</span></span>
