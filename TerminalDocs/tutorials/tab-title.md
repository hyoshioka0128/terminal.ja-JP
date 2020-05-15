---
title: Windows ターミナルのタブのタイトルの設定
description: このチュートリアルでは、Windows ターミナルでタブのタイトルを設定する方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: tutorial
ms.service: terminal
ms.openlocfilehash: 94c0d9afc8ccd3d95a3f52f5f9f6bdd0cb05bc12
ms.sourcegitcommit: bb5b7fd7db4b81e0d44e060989dc16b6775c802a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83416467"
---
# <a name="tutorial-configure-tab-titles-in-windows-terminal"></a><span data-ttu-id="bb4e2-103">チュートリアル: Windows ターミナルでタブのタイトルを構成する</span><span class="sxs-lookup"><span data-stu-id="bb4e2-103">Tutorial: Configure tab titles in Windows Terminal</span></span>

<span data-ttu-id="bb4e2-104">既定では、タブのタイトルはシェルのタイトルに設定されます。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-104">By default, the tab title is set to the shell's title.</span></span> <span data-ttu-id="bb4e2-105">タブが複数のペインで構成されている場合、タブのタイトルは、現在フォーカスがあるペインのタイトルに設定されます。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-105">If a tab is composed of multiple panes, the tab's title is set to that of the currently focused pane.</span></span> <span data-ttu-id="bb4e2-106">タブのタイトルとして設定する内容をカスタマイズする場合は、このチュートリアルに従ってください。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-106">If you want to customize what is set as the tab title, follow this tutorial.</span></span>

<span data-ttu-id="bb4e2-107">このチュートリアルでは、次の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="bb4e2-108">`tabTitle` 設定を使用する</span><span class="sxs-lookup"><span data-stu-id="bb4e2-108">Use the `tabTitle` setting</span></span>
> * <span data-ttu-id="bb4e2-109">シェルのタイトルを設定する</span><span class="sxs-lookup"><span data-stu-id="bb4e2-109">Set the shell's title</span></span>
> * <span data-ttu-id="bb4e2-110">`suppressApplicationTitle` 設定を使用する</span><span class="sxs-lookup"><span data-stu-id="bb4e2-110">Using the `suppressApplicationTitle` setting</span></span>

## <a name="use-the-tabtitle-setting"></a><span data-ttu-id="bb4e2-111">`tabTitle` 設定を使用する</span><span class="sxs-lookup"><span data-stu-id="bb4e2-111">Use the `tabTitle` setting</span></span>

<span data-ttu-id="bb4e2-112">`tabTitle` 設定では、シェルの新しいインスタンスの開始タイトルを定義できます。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-112">The `tabTitle` setting allows you to define the starting title for a new instance of a shell.</span></span> <span data-ttu-id="bb4e2-113">設定されていない場合は、代わりにプロファイル `name` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-113">If it is not set, the profile `name` is used instead.</span></span> <span data-ttu-id="bb4e2-114">この設定への応答はシェルごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-114">Each shell responds to this setting differently.</span></span>

| <span data-ttu-id="bb4e2-115">Shell</span><span class="sxs-lookup"><span data-stu-id="bb4e2-115">Shell</span></span> | <span data-ttu-id="bb4e2-116">動作</span><span class="sxs-lookup"><span data-stu-id="bb4e2-116">Behavior</span></span> |
| ----- | -------- |
| <span data-ttu-id="bb4e2-117">PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb4e2-117">PowerShell</span></span> | <span data-ttu-id="bb4e2-118">タイトルが設定されます。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-118">The title is set.</span></span> |
| <span data-ttu-id="bb4e2-119">Command Prompt</span><span class="sxs-lookup"><span data-stu-id="bb4e2-119">Command Prompt</span></span> | <span data-ttu-id="bb4e2-120">タイトルが設定されます。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-120">The title is set.</span></span> <span data-ttu-id="bb4e2-121">コマンドが実行されている場合は、一時的にタイトルの末尾にそれが追加されます。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-121">If a command is running, it is temporarily appended to the end of the title.</span></span> |
| <span data-ttu-id="bb4e2-122">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="bb4e2-122">Ubuntu</span></span> | <span data-ttu-id="bb4e2-123">タイトルは無視され、代わりに `user@machine:path` に設定されます</span><span class="sxs-lookup"><span data-stu-id="bb4e2-123">The title is ignored, and instead set to `user@machine:path`</span></span> |
| <span data-ttu-id="bb4e2-124">Debian</span><span class="sxs-lookup"><span data-stu-id="bb4e2-124">Debian</span></span> | <span data-ttu-id="bb4e2-125">タイトルが設定されます。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-125">The title is set.</span></span> |

> [!NOTE]
> <span data-ttu-id="bb4e2-126">Ubuntu と Debian ではどちらも bash が実行されますが、動作は異なります。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-126">Though Ubuntu and Debian both run bash, they have different behaviors.</span></span> <span data-ttu-id="bb4e2-127">これは、ディストリビューションによって動作が異なる場合があることを示しています。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-127">This is to show that different distributions may have different behaviors.</span></span>

## <a name="set-the-shells-title"></a><span data-ttu-id="bb4e2-128">シェルのタイトルを設定する</span><span class="sxs-lookup"><span data-stu-id="bb4e2-128">Set the shell's title</span></span>

<span data-ttu-id="bb4e2-129">シェルは、自身のタイトルを完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-129">A shell has full control over its own title.</span></span> <span data-ttu-id="bb4e2-130">ただし、各シェルのタイトルの設定方法は異なります。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-130">However, each shell sets its title differently.</span></span>

| <span data-ttu-id="bb4e2-131">Shell</span><span class="sxs-lookup"><span data-stu-id="bb4e2-131">Shell</span></span> | <span data-ttu-id="bb4e2-132">コマンド</span><span class="sxs-lookup"><span data-stu-id="bb4e2-132">Command</span></span> |
| ----- | ------- |
| <span data-ttu-id="bb4e2-133">PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb4e2-133">PowerShell</span></span> | `$Host.UI.RawUI.WindowTitle = "New Title"` |
| <span data-ttu-id="bb4e2-134">Command Prompt</span><span class="sxs-lookup"><span data-stu-id="bb4e2-134">Command Prompt</span></span> | `TITLE "New Title"` |
| <span data-ttu-id="bb4e2-135">bash\*</span><span class="sxs-lookup"><span data-stu-id="bb4e2-135">bash\*</span></span> | `echo -ne "\033]0;New Title\a"` |

<span data-ttu-id="bb4e2-136">一部の Linux ディストリビューション (Ubuntu) では、シェルと対話するときにタイトルが自動的に設定されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-136">Note that some Linux distributions (i.e. Ubuntu) set their title automatically as you interact with the shell.</span></span> <span data-ttu-id="bb4e2-137">上記のコマンドが動作しない場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-137">If the above command doesn't work, run the following command:</span></span>

```bash
PS1=$
PROMPT_COMMAND=
echo -ne "\033]0;New Title\a"
```

<span data-ttu-id="bb4e2-138">これにより、タイトルが "New Title" に変更され、プロンプトが "$" に設定されます。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-138">This will change the title to 'New Title', and also set the prompt to '$'.</span></span>

## <a name="use-the-suppressapplicationtitle-setting"></a><span data-ttu-id="bb4e2-139">`suppressApplicationTitle` 設定を使用する</span><span class="sxs-lookup"><span data-stu-id="bb4e2-139">Use the `suppressApplicationTitle` setting</span></span>

<span data-ttu-id="bb4e2-140">シェルは自身のタイトルを制御しているため、いつでもタブタイトルを上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-140">Since a shell has control over its title, it may choose to overwrite the tab title at any time.</span></span> <span data-ttu-id="bb4e2-141">たとえば、PowerShell の `posh-git` モジュールでは、Git リポジトリに関する情報がタイトルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-141">For example, the `posh-git` module for PowerShell adds information about your Git repository to the title.</span></span>

<span data-ttu-id="bb4e2-142">Windows ターミナルでは、プロファイルの `suppressApplicationTitle` を `true` に設定することによって、タイトルの変更を抑制できます。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-142">Windows Terminal allows you to suppress changes to the title by setting `suppressApplicationTitle` to `true` in your profile.</span></span> <span data-ttu-id="bb4e2-143">これにより、プロファイルの新しいインスタンスによって、表示されるタイトルが `tabTitle` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-143">This makes new instances of the profile set your visible title to `tabTitle`.</span></span> <span data-ttu-id="bb4e2-144">`tabTitle` が設定されていない場合、表示されるタイトルはプロファイルの `name` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-144">If `tabTitle` is not set, the visible title is set to the profile's `name`.</span></span>

<span data-ttu-id="bb4e2-145">これにより、タブに表示されている表示タイトルからシェルのタイトルが分離されることに注意してください。タイトルが設定されているシェルの変数を読み取ると、タブのタイトルと異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bb4e2-145">Note that this decouples the shell's title from the visible title presented on the tab. If you read the shell's variable where the title is set, it may differ from the tab's title.</span></span>

## <a name="resources"></a><span data-ttu-id="bb4e2-146">参照情報</span><span class="sxs-lookup"><span data-stu-id="bb4e2-146">Resources</span></span>

* [<span data-ttu-id="bb4e2-147">コンソールのタイトルが現在の作業ディレクトリになるように設定する</span><span class="sxs-lookup"><span data-stu-id="bb4e2-147">Setting the console title to be your current working directory</span></span>](https://devblogs.microsoft.com/powershell/setting-the-console-title-to-be-your-current-working-directory/)
* [<span data-ttu-id="bb4e2-148">Ubuntu 16.04 でターミナルのタイトルを変更する</span><span class="sxs-lookup"><span data-stu-id="bb4e2-148">Change the title of a terminal on Ubuntu 16.04</span></span>](https://www.zachpfeffer.com/single-post/Change-the-title-of-a-terminal-on-Ubuntu-1604)
