---
title: Windows ターミナル動的プロファイル
description: Windows ターミナルの動的プロファイルについて説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: concept
ms.service: terminal
ms.openlocfilehash: 9c54dc2182584873d9d0c1358083d5142d07ef48
ms.sourcegitcommit: bb5b7fd7db4b81e0d44e060989dc16b6775c802a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83416127"
---
# <a name="dynamic-profiles-in-windows-terminal"></a><span data-ttu-id="64e5d-103">Windows ターミナルでの動的プロファイル</span><span class="sxs-lookup"><span data-stu-id="64e5d-103">Dynamic profiles in Windows Terminal</span></span>

<span data-ttu-id="64e5d-104">Windows ターミナルでは、Linux 用 Windows サブシステム (WSL) と PowerShell のシェルがコンピューターにインストールされている場合、これらに対するプロファイルが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="64e5d-104">The Windows Terminal will automatically create Windows Subsystem for Linux (WSL) and PowerShell profiles for you if you have these shells installed on your machine.</span></span> <span data-ttu-id="64e5d-105">これにより、実行可能ファイルを探す必要なしに、すべてのシェルをターミナルに簡単に含めることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="64e5d-105">This makes it easier for you to have all of your shells included in the terminal without having to locate their executable files.</span></span> <span data-ttu-id="64e5d-106">これらのプロファイルは、`source` プロパティを使用して生成されます。このプロパティでは、適切な実行可能ファイルを見つける場所がターミナルに通知されます。</span><span class="sxs-lookup"><span data-stu-id="64e5d-106">These profiles are generated with the `source` property, which tells the terminal where to locate the proper executable.</span></span>

<span data-ttu-id="64e5d-107">ターミナルをインストールすると、PowerShell が既定のプロファイルとして設定されます。</span><span class="sxs-lookup"><span data-stu-id="64e5d-107">Upon installing the terminal, it will set PowerShell as your default profile.</span></span> <span data-ttu-id="64e5d-108">既定のプロファイルを変更する方法については、[グローバル設定に関するページ](./customize-settings/global-settings.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64e5d-108">To learn how to change your default profile, visit the [Global settings page](./customize-settings/global-settings.md).</span></span>

<span data-ttu-id="64e5d-109">![Windows ターミナル動的プロファイル](./images/dynamic-profiles.png)
_構成: [ライト テーマ](./custom-terminal-gallery/frosted-glass-theme.md)_</span><span class="sxs-lookup"><span data-stu-id="64e5d-109">![Windows Terminal dynamic profiles](./images/dynamic-profiles.png)
_Configuration: [Light Theme](./custom-terminal-gallery/frosted-glass-theme.md)_</span></span>

## <a name="installing-a-new-shell-after-installing-windows-terminal"></a><span data-ttu-id="64e5d-110">Windows ターミナルをインストールした後で新しいシェルをインストールする</span><span class="sxs-lookup"><span data-stu-id="64e5d-110">Installing a new shell after installing Windows Terminal</span></span>

<span data-ttu-id="64e5d-111">新しいシェルがインストールされるのがターミナルのインストールの前か後かに関係なく、ターミナルでは新しくインストールされたシェルに対する新しいプロファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="64e5d-111">Regardless of whether a new shell is installed before or after your terminal installation, the terminal will create a new profile for the newly installed shell.</span></span>

## <a name="hide-a-profile"></a><span data-ttu-id="64e5d-112">プロファイルを非表示にする</span><span class="sxs-lookup"><span data-stu-id="64e5d-112">Hide a profile</span></span>

<span data-ttu-id="64e5d-113">ターミナルのドロップダウン メニューにプロファイルが表示されないようにするには、settings.json ファイルのプロファイル オブジェクトに `hidden` プロパティを追加して、`true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="64e5d-113">To hide a profile from your terminal dropdown menu, add the `hidden` property to the profile object in your settings.json file and set it to `true`.</span></span>

```json
"hidden": true
```

<span data-ttu-id="64e5d-114">動的に作成されたプロファイルを削除すると、ターミナルによって自動的にプロファイルが再生成され、settings.json ファイルで置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="64e5d-114">If you delete a dynamically-created profile, the terminal will automatically regenerate the profile and replace it in your settings.json file.</span></span>

## <a name="prevent-a-profile-from-being-generated"></a><span data-ttu-id="64e5d-115">プロファイルが生成されないようにする</span><span class="sxs-lookup"><span data-stu-id="64e5d-115">Prevent a profile from being generated</span></span>

<span data-ttu-id="64e5d-116">動的プロファイルが生成されないようにするには、プロファイル ジェネレーターをグローバル設定の `disabledProfileSources` 配列に追加します。</span><span class="sxs-lookup"><span data-stu-id="64e5d-116">To prevent a dynamic profile from being generated, you can add the profile generator to the `disabledProfileSources` array in your global settings.</span></span> <span data-ttu-id="64e5d-117">この設定の詳細については、[グローバル設定に関するページ](./customize-settings/global-settings.md#disable-dynamic-profiles)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64e5d-117">More information on this setting can be found on the [Global settings page](./customize-settings/global-settings.md#disable-dynamic-profiles).</span></span>

```json
"disabledProfileSources": ["Windows.Terminal.Wsl", "Windows.Terminal.Azure", "Windows.Terminal.PowershellCore"]
```
