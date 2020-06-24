---
title: Windows ターミナルのトラブルシューティング
description: Windows ターミナルでの一般的な障害の修正について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: overview
ms.service: terminal
ms.localizationpriority: high
ms.openlocfilehash: ce2fe1e2efb26fe413b23a4e7ab08dcf0e0ed8dc
ms.sourcegitcommit: d8e23557224bc50a82a36dc80ac68b9d11dfdde9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2020
ms.locfileid: "84720078"
---
# <a name="troubleshooting-in-windows-terminal"></a><span data-ttu-id="0e00e-103">Windows ターミナルでのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0e00e-103">Troubleshooting in Windows Terminal</span></span>

<span data-ttu-id="0e00e-104">このガイドでは、Windows ターミナルを使用するときに発生する可能性のある一般的なエラーと障害について説明します。</span><span class="sxs-lookup"><span data-stu-id="0e00e-104">This guide addresses some of the common errors and obstacles you may encounter when using Windows Terminal.</span></span>

## <a name="set-your-wsl-distribution-to-start-in-the-home--directory-when-launched"></a><span data-ttu-id="0e00e-105">起動時にホーム `~` ディレクトリで開始するように WSL ディストリビューションを設定します</span><span class="sxs-lookup"><span data-stu-id="0e00e-105">Set your WSL distribution to start in the home `~` directory when launched</span></span>

<span data-ttu-id="0e00e-106">既定では、プロファイルの `startingDirectory` は `%USERPROFILE%` (`C:\Users\<YourUsername>`) です。</span><span class="sxs-lookup"><span data-stu-id="0e00e-106">By default, the `startingDirectory` of a profile is `%USERPROFILE%` (`C:\Users\<YourUsername>`).</span></span> <span data-ttu-id="0e00e-107">これは Windows パスです。</span><span class="sxs-lookup"><span data-stu-id="0e00e-107">This is a Windows path.</span></span> <span data-ttu-id="0e00e-108">ただし、WSL の場合は、代わりに WSL ホーム パスを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="0e00e-108">For WSL, however, you may want to use the WSL home path instead.</span></span> <span data-ttu-id="0e00e-109">`startingDirectory` は Windows スタイルのパスのみを受け入れます。そのため、WSL ディストリビューション内で開始するように設定するには、プレフィックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="0e00e-109">`startingDirectory` only accepts a Windows-style path, so setting it to start within a WSL distribution requires a prefix.</span></span>

<span data-ttu-id="0e00e-110">Windows 10 バージョン 1903 以降では、`\\wsl$\` プレフィックスを使用して、WSL ディストリビューションのファイルシステムに対処できます。</span><span class="sxs-lookup"><span data-stu-id="0e00e-110">Beginning in Windows 10 version 1903, the file systems of WSL distributions can be addressed using the `\\wsl$\` prefix.</span></span> <span data-ttu-id="0e00e-111">`DistroName` という名前の WSL ディストリビューションの場合は、そのディストリビューションのファイル システムのルートを指す Windows パスとして `\\wsl$\DistroName` を使用します。</span><span class="sxs-lookup"><span data-stu-id="0e00e-111">For any WSL distribution with the name `DistroName`, use `\\wsl$\DistroName` as a Windows path that points to the root of that distribution's file system.</span></span>

<span data-ttu-id="0e00e-112">たとえば、次の設定では、"Ubuntu-18.04" のディストリビューションがそのホーム ファイル パスで開始されます。</span><span class="sxs-lookup"><span data-stu-id="0e00e-112">For example, the following setting will launch the "Ubuntu-18.04" distribution in its home file path:</span></span>

```json
{
    "name": "Ubuntu-18.04",
    "commandline" : "wsl -d Ubuntu-18.04",
    "startingDirectory" : "//wsl$/Ubuntu-18.04/home/<Your Ubuntu Username>",
}
```

## <a name="setting-the-tab-title"></a><span data-ttu-id="0e00e-113">タブ タイトルを設定する</span><span class="sxs-lookup"><span data-stu-id="0e00e-113">Setting the tab title</span></span>

<span data-ttu-id="0e00e-114">シェルでタブ タイトルを自動的に設定するには、[タブ タイトルの設定のチュートリアル](./tutorials/tab-title.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e00e-114">To have the shell automatically set your tab title, [visit the set the tab title tutorial](./tutorials/tab-title.md).</span></span> <span data-ttu-id="0e00e-115">独自のタブ タイトルを設定する場合は、次の手順に従って、settings.json ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0e00e-115">If you want to set your own tab title, open the settings.json file and follow these steps:</span></span>

1. <span data-ttu-id="0e00e-116">任意のコマンド ラインのプロファイルで、`"suppressApplicationTitle": true` を追加して、シェルから送信されるタイトル変更イベントを抑制します。</span><span class="sxs-lookup"><span data-stu-id="0e00e-116">In the profile for the command line of your choice, add `"suppressApplicationTitle": true` to suppress any title change events that get sent from the shell.</span></span> <span data-ttu-id="0e00e-117">この設定 "*のみ*" をプロファイルに追加すると、タブ タイトルがプロファイルの名前に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0e00e-117">Adding *only* this setting to your profile will set the tab title to the name of your profile.</span></span>

2. <span data-ttu-id="0e00e-118">プロファイルの名前ではないカスタム タブ タイトルが必要な場合は、`"tabTitle": "TITLE"` を追加します。</span><span class="sxs-lookup"><span data-stu-id="0e00e-118">If you want a custom tab title that is not the name of your profile, add `"tabTitle": "TITLE"`.</span></span> <span data-ttu-id="0e00e-119">"TITLE" を任意のタブ タイトルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0e00e-119">Replacing "TITLE" with your preferred tab title.</span></span>

## <a name="command-line-arguments-in-powershell"></a><span data-ttu-id="0e00e-120">PowerShell のコマンド ライン引数</span><span class="sxs-lookup"><span data-stu-id="0e00e-120">Command line arguments in PowerShell</span></span>

<span data-ttu-id="0e00e-121">PowerShell でコマンドライン引数を操作する方法については、[コマンド ライン引数に関するページ](./command-line-arguments.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e00e-121">Visit the [Command line arguments page](./command-line-arguments.md) to learn how command-line arguments operate in PowerShell.</span></span>

## <a name="command-line-arguments-in-wsl"></a><span data-ttu-id="0e00e-122">WSL のコマンド ライン引数</span><span class="sxs-lookup"><span data-stu-id="0e00e-122">Command line arguments in WSL</span></span>

<span data-ttu-id="0e00e-123">WSL でコマンドライン引数を操作する方法については、[コマンド ライン引数に関するページ](./command-line-arguments.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e00e-123">Visit the [Command line arguments page](./command-line-arguments.md) to learn how command-line arguments operate in WSL.</span></span>

## <a name="problem-setting-startingdirectory"></a><span data-ttu-id="0e00e-124">問題の設定 `startingDirectory`</span><span class="sxs-lookup"><span data-stu-id="0e00e-124">Problem setting `startingDirectory`</span></span>

<span data-ttu-id="0e00e-125">プロファイルで `startingDirectory` が無視されている場合は、まず、settings.json の構文が正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0e00e-125">If the `startingDirectory` is being ignored in your profile, first check to make sure your settings.json's syntax is correct.</span></span> <span data-ttu-id="0e00e-126">この構文を確認するために、`"$schema": "https://aka.ms/terminal-profiles-schema"` が自動的に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="0e00e-126">To help you check this syntax, `"$schema": "https://aka.ms/terminal-profiles-schema"` is automatically injected.</span></span> <span data-ttu-id="0e00e-127">[Visual Studio Code](https://code.visualstudio.com/download) などの一部のアプリケーションでは、挿入されたスキーマを使用して、編集を行うときに json ファイルを検証できます。</span><span class="sxs-lookup"><span data-stu-id="0e00e-127">Some applications, like [Visual Studio Code](https://code.visualstudio.com/download), can use that injected schema to validate your json file as you make edits.</span></span>

<span data-ttu-id="0e00e-128">設定が正しい場合は、ターミナルの開始ディレクトリを個別に設定するスタートアップ スクリプトを実行している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0e00e-128">If your settings are correct, you may be running a startup script that sets the starting directory of your terminal separately.</span></span> <span data-ttu-id="0e00e-129">たとえば、PowerShell には独自のプロファイルの概念があります。</span><span class="sxs-lookup"><span data-stu-id="0e00e-129">For example, PowerShell has its own separate concept of profiles.</span></span> <span data-ttu-id="0e00e-130">開始ディレクトリを変更すると、Windows ターミナルで定義されている設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="0e00e-130">If you are changing your starting directory there, it will take precedence over the setting defined in Windows Terminal.</span></span>

<span data-ttu-id="0e00e-131">または、`commandline` プロファイル設定を使用してスクリプトを実行している場合は、そこに場所を設定している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0e00e-131">Alternatively, if you are running a script using the `commandline` profile setting, it may be that you are setting the location there.</span></span> <span data-ttu-id="0e00e-132">PowerShell プロファイルと同様に、そこのコマンドが `startingDirectory` プロファイル設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="0e00e-132">Similar to PowerShell profiles, your commands there take precedence over the `startingDirectory` profile setting.</span></span>

<span data-ttu-id="0e00e-133">`startingDirectory` の目的は、指定されたディレクトリで新しい Windows ターミナル インスタンスを起動することです。</span><span class="sxs-lookup"><span data-stu-id="0e00e-133">The purpose of `startingDirectory` is to launch a new Windows Terminal instance in the given directory.</span></span> <span data-ttu-id="0e00e-134">ターミナルで、そのディレクトリを変更するコードが実行されている場合は、調べてみることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0e00e-134">If the terminal runs any code that changes its directory, that may be a good place to take a look.</span></span>

## <a name="ctrl-does-not-increase-the-font-size"></a><span data-ttu-id="0e00e-135">Ctrl+= でフォント サイズが大きくならない</span><span class="sxs-lookup"><span data-stu-id="0e00e-135">Ctrl+= does not increase the font size</span></span>

<span data-ttu-id="0e00e-136">ドイツ語のキーボード レイアウトを使用している場合は、この問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0e00e-136">If you are using a German keyboard layout, you may run into this problem.</span></span> <span data-ttu-id="0e00e-137">メインのキーボード レイアウトがドイツ語に設定されている場合、<kbd>ctrl+=</kbd> は <kbd>ctrl+shift+0</kbd> として逆シリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="0e00e-137"><kbd>ctrl+=</kbd> gets deserialized as <kbd>ctrl+shift+0</kbd> if your main keyboard layout is set to German.</span></span> <span data-ttu-id="0e00e-138">これは、ドイツ語のキーボードの正しいマッピングです。</span><span class="sxs-lookup"><span data-stu-id="0e00e-138">This is the correct mapping for German keyboards.</span></span>

<span data-ttu-id="0e00e-139">さらに重要なことに、アプリが <kbd>ctrl+shift+0</kbd> キーストロークを受け取ることはありません。</span><span class="sxs-lookup"><span data-stu-id="0e00e-139">More importantly, the app never receives the <kbd>ctrl+shift+0</kbd> keystroke.</span></span> <span data-ttu-id="0e00e-140">これは、複数のキーボード レイアウトをアクティブにしている場合、<kbd>ctrl+shift+0</kbd> は Windows によって予約されるためです。</span><span class="sxs-lookup"><span data-stu-id="0e00e-140">This is because <kbd>ctrl+shift+0</kbd> is reserved by Windows if you have multiple keyboard layouts active.</span></span>

<span data-ttu-id="0e00e-141">`Ctrl+=` を正常に機能させるためにこの機能を無効にする場合は、この[ブログ記事](https://winaero.com/blog/change-hotkeys-switch-keyboard-layout-windows-10/)の「Change Hotkeys to Switch Keyboard Layout in Windows 10」 (Windows 10 でホットキーを変更してキーボード レイアウトを切り替える) の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="0e00e-141">If you would like to disable this feature in order for `Ctrl+=` to work properly, follow the instructions for "Change Hotkeys to Switch Keyboard Layout in Windows 10" in this [blog post](https://winaero.com/blog/change-hotkeys-switch-keyboard-layout-windows-10/).</span></span>

<span data-ttu-id="0e00e-142">[キーボード レイアウトの切り替え] オプションを [割り当てられていません] (または <kbd>ctrl+shift</kbd>) に変更し、 **[OK]** 、 **[適用]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="0e00e-142">Change the 'Switch Keyboard Layout' option to 'Not Assigned' (or off of <kbd>ctrl+shift</kbd>), then select **OK** and then **Apply**.</span></span> <span data-ttu-id="0e00e-143"><kbd>ctrl+shift+0</kbd> はキー バインドとして機能するようになり、ターミナルに渡されます。</span><span class="sxs-lookup"><span data-stu-id="0e00e-143"><kbd>ctrl+shift+0</kbd> should now work as a key binding and is passed through to the terminal.</span></span>

<span data-ttu-id="0e00e-144">一方、複数の入力言語に対してこのホットキー機能を使用する場合は、settings.json ファイルで[独自のカスタム キー バインドを構成](./customize-settings/key-bindings.md)できます。</span><span class="sxs-lookup"><span data-stu-id="0e00e-144">On the other hand, if you do use this hotkey feature for multiple input languages, you can [configure your own custom key binding](./customize-settings/key-bindings.md) in your settings.json file.</span></span>

## <a name="the-text-is-blurry"></a><span data-ttu-id="0e00e-145">テキストがぼやけている</span><span class="sxs-lookup"><span data-stu-id="0e00e-145">The text is blurry</span></span>

<span data-ttu-id="0e00e-146">一部のディスプレイ ドライバーとハードウェアの組み合わせでは、スクロールやダーティ領域の処理で、前のフレームのデータがぼやけてしまいます。</span><span class="sxs-lookup"><span data-stu-id="0e00e-146">Some display drivers and hardware combinations do not handle scroll and/or dirty regions without blurring the data from the previous frame.</span></span> <span data-ttu-id="0e00e-147">この問題を軽減するには、[これらのグローバル レンダリングの設定](./customize-settings/global-settings.md#rendering-settings)の組み合わせを追加して、ターミナル テキスト レンダラーによるハードウェアの負荷を軽減します。</span><span class="sxs-lookup"><span data-stu-id="0e00e-147">To mitigate this problem, you can add a combination of [these global rendering settings](./customize-settings/global-settings.md#rendering-settings) to reduce the strain placed on your hardware caused by the terminal text renderer.</span></span>
