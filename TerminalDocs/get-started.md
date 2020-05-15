---
title: Windows ターミナルのインストール
description: このクイックスタートでは、Windows ターミナルをインストールして実行する方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: quickstart
ms.service: terminal
ms.localizationpriority: high
ms.openlocfilehash: 901e3a0f447cdfe19a69ee43c7f76ed529d87108
ms.sourcegitcommit: bb5b7fd7db4b81e0d44e060989dc16b6775c802a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83415847"
---
# <a name="install-and-set-up-windows-terminal"></a><span data-ttu-id="959f5-103">Windows ターミナルをインストールしてセットアップする</span><span class="sxs-lookup"><span data-stu-id="959f5-103">Install and set up Windows Terminal</span></span>

## <a name="installation"></a><span data-ttu-id="959f5-104">インストール</span><span class="sxs-lookup"><span data-stu-id="959f5-104">Installation</span></span>

<span data-ttu-id="959f5-105">Windows ターミナルは、[Microsoft Store](https://aka.ms/terminal) からインストールできます。</span><span class="sxs-lookup"><span data-stu-id="959f5-105">You can install the Windows Terminal from the [Microsoft Store](https://aka.ms/terminal).</span></span>

<span data-ttu-id="959f5-106">Microsoft Store にアクセスできない場合は、[GitHub のリリース ページ](https://github.com/microsoft/terminal/releases)でビルドが公開されています。</span><span class="sxs-lookup"><span data-stu-id="959f5-106">If you don't have access to the Microsoft Store, the builds are published on the [GitHub releases page](https://github.com/microsoft/terminal/releases).</span></span> <span data-ttu-id="959f5-107">GitHub からインストールしたターミナルの場合、新しいバージョンが公開されても自動的には更新されません。</span><span class="sxs-lookup"><span data-stu-id="959f5-107">If you install from GitHub, the terminal will not automatically update with new versions.</span></span>

## <a name="first-run"></a><span data-ttu-id="959f5-108">最初の実行</span><span class="sxs-lookup"><span data-stu-id="959f5-108">First run</span></span>

<span data-ttu-id="959f5-109">インストール後にターミナルを開くと、開いているタブで PowerShell を既定のプロファイルとして開始されます。</span><span class="sxs-lookup"><span data-stu-id="959f5-109">After installation, when you open the terminal, it will start with PowerShell as the default profile in the open tab.</span></span>

![Windows ターミナルの初回実行](./images/first-run.png)

### <a name="dynamic-profiles"></a><span data-ttu-id="959f5-111">動的プロファイル</span><span class="sxs-lookup"><span data-stu-id="959f5-111">Dynamic profiles</span></span>

<span data-ttu-id="959f5-112">WSL ディストリビューションまたは PowerShell の複数のバージョンがインストールされている場合、ターミナルによって自動的にプロファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="959f5-112">The terminal will automatically create profiles for you if you have WSL distros or multiple versions of PowerShell installed.</span></span> <span data-ttu-id="959f5-113">動的プロファイルの詳細については、[動的プロファイルに関するページ](./dynamic-profiles.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="959f5-113">Learn more about dynamic profiles on the [Dynamic profiles page](./dynamic-profiles.md).</span></span>

## <a name="open-a-new-tab"></a><span data-ttu-id="959f5-114">新しいタブを開く</span><span class="sxs-lookup"><span data-stu-id="959f5-114">Open a new tab</span></span>

<span data-ttu-id="959f5-115"><kbd>Ctrl + Shift + T</kbd> キーを押すか、[+] (プラス) ボタンを選択することで、既定のプロファイルの新しいタブを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="959f5-115">You can open a new tab of the default profile by pressing <kbd>ctrl+shift+t</kbd> or by selecting the + (plus) button.</span></span> <span data-ttu-id="959f5-116">別のプロファイルを開くには、[+] ボタンの横にある [˅] (矢印) を選択して、ドロップダウン メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="959f5-116">To open a different profile, select the ˅ (arrow) next to the + button to open the dropdown menu.</span></span> <span data-ttu-id="959f5-117">そこから、開くプロファイルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="959f5-117">From there, you can select which profile to open.</span></span>

## <a name="open-a-new-pane"></a><span data-ttu-id="959f5-118">新しいペインを開く</span><span class="sxs-lookup"><span data-stu-id="959f5-118">Open a new pane</span></span>

<span data-ttu-id="959f5-119">ペインを使用すると、複数のシェルを並行して実行できます。</span><span class="sxs-lookup"><span data-stu-id="959f5-119">You can run multiple shells side-by-side using panes.</span></span> <span data-ttu-id="959f5-120">ペインを開くには、<kbd>Alt + Shift + D</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="959f5-120">To open a pane, you can use <kbd>alt+shift+d</kbd>.</span></span> <span data-ttu-id="959f5-121">このキー バインドを使用すると、フォーカスが設定されているプロファイルのペインが重複して開かれます。</span><span class="sxs-lookup"><span data-stu-id="959f5-121">This key binding will open a duplicate pane of your focused profile.</span></span> <span data-ttu-id="959f5-122">ペインの詳細については、[ペインに関するページ](./panes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="959f5-122">Learn more about panes on the [Panes page](./panes.md).</span></span>

## <a name="configuration"></a><span data-ttu-id="959f5-123">構成</span><span class="sxs-lookup"><span data-stu-id="959f5-123">Configuration</span></span>

<span data-ttu-id="959f5-124">Windows ターミナルの設定をカスタマイズするには、ドロップダウン メニューの **[設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="959f5-124">To customize the settings of your Windows Terminal, select **Settings** in the dropdown menu.</span></span> <span data-ttu-id="959f5-125">これにより、既定のテキスト エディターで `settings.json` ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="959f5-125">This will open the `settings.json` file in your default text editor.</span></span> <span data-ttu-id="959f5-126">(既定のテキスト エディターは、[Windows 設定](ms-settings:defaultapps)で定義されています)。</span><span class="sxs-lookup"><span data-stu-id="959f5-126">(The default text editor is defined in your [Windows settings](ms-settings:defaultapps).)</span></span>

<span data-ttu-id="959f5-127">ターミナルでは、アプリケーション全体に影響を与える[グローバル プロパティ](./customize-settings/global-settings.md)、各プロファイルの設定に影響する[プロファイル プロパティ](./customize-settings/profile-settings.md)、キーボードを使用してターミナルと対話できるようにする[キー バインド](./customize-settings/key-bindings.md)のカスタマイズがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="959f5-127">The terminal supports customization of [global properties](./customize-settings/global-settings.md) that affect the whole application, [profile properties](./customize-settings/profile-settings.md) that affect the settings of each profile, and [key bindings](./customize-settings/key-bindings.md) that allow you to interact with the terminal using your keyboard.</span></span>

## <a name="command-line-arguments"></a><span data-ttu-id="959f5-128">コマンド ライン引数</span><span class="sxs-lookup"><span data-stu-id="959f5-128">Command line arguments</span></span>

<span data-ttu-id="959f5-129">コマンド ライン引数を使用すると、特定の構成でターミナルを起動できます。</span><span class="sxs-lookup"><span data-stu-id="959f5-129">You can launch the terminal in a specific configuration using command line arguments.</span></span> <span data-ttu-id="959f5-130">これらの引数を使用すると、カスタム プロファイル設定が適用された特定のタブとペインでターミナルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="959f5-130">These arguments let you open the terminal with specific tabs and panes with custom profile settings.</span></span> <span data-ttu-id="959f5-131">コマンド ライン引数の詳細については、[コマンド ライン引数に関するページ](./command-line-arguments.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="959f5-131">Learn more about command line arguments on the [Command line arguments page](./command-line-arguments.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="959f5-132">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="959f5-132">Troubleshooting</span></span>

<span data-ttu-id="959f5-133">ターミナルの使用に関して問題が発生した場合は、[トラブルシューティングのページ](./troubleshooting.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="959f5-133">If you encounter any difficulties using the terminal, reference the [Troubleshooting page](./troubleshooting.md).</span></span> <span data-ttu-id="959f5-134">バグが見つかった場合、または要求したい機能がある場合は、ターミナルの **[バージョン情報]** メニューでフィードバック リンクを選択して [GitHub のページ](https://github.com/microsoft/terminal)に移動し、そこで新しいイシューを報告することができます。</span><span class="sxs-lookup"><span data-stu-id="959f5-134">If you find any bugs or have a feature request, you can select the feedback link in the **About** menu of the terminal to go to the [GitHub page](https://github.com/microsoft/terminal) where you can file a new issue.</span></span>
