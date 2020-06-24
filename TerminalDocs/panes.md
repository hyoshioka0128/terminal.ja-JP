---
title: Windows ターミナル ペイン
description: Windows ターミナルでペインを分割する方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 06/18/2020
ms.topic: how-to
ms.service: terminal
ms.openlocfilehash: 0e2d7a50e1a3c933f7ab2d98bda5be6b8ee44e7e
ms.sourcegitcommit: 91a802863cd0730d2e364377ffe44f819a66ff2a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84994322"
---
# <a name="panes-in-windows-terminal"></a><span data-ttu-id="c4b02-103">Windows ターミナルのペイン</span><span class="sxs-lookup"><span data-stu-id="c4b02-103">Panes in Windows Terminal</span></span>

<span data-ttu-id="c4b02-104">ペインでは、同じタブ内で複数のコマンドライン アプリケーションを並べて同時に実行することができます。これにより、タブを切り替える必要が最小限に抑えられ、一度に複数のプロンプトを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="c4b02-104">Panes give you the ability to run multiple command-line applications next to each other within the same tab. This minimizes the need to switch between tabs and lets you see multiple prompts at once.</span></span>

## <a name="creating-a-new-pane"></a><span data-ttu-id="c4b02-105">新しいペインを作成する</span><span class="sxs-lookup"><span data-stu-id="c4b02-105">Creating a new pane</span></span>

### <a name="using-the-keyboard"></a><span data-ttu-id="c4b02-106">キーボードを使用する</span><span class="sxs-lookup"><span data-stu-id="c4b02-106">Using the keyboard</span></span>

<span data-ttu-id="c4b02-107">Windows ターミナルで、垂直方向または水平方向の新しいペインを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c4b02-107">You can either create a new vertical or horizontal pane in Windows Terminal.</span></span> <span data-ttu-id="c4b02-108">垂直方向に分割すると、フォーカスがあるペインの右側に新しいペインが開かれ、水平方向に分割すると、フォーカスがあるペインの下に新しいペインが開かれます。</span><span class="sxs-lookup"><span data-stu-id="c4b02-108">Splitting vertically will open a new pane to the right of the focused pane and splitting horizontally will open a new pane below the focused pane.</span></span> <span data-ttu-id="c4b02-109">既定のプロファイルの新しい垂直ペインを作成するには、<kbd>alt+shift+plus</kbd> を入力します。</span><span class="sxs-lookup"><span data-stu-id="c4b02-109">To create a new vertical pane of your default profile, you can type <kbd>alt+shift+plus</kbd>.</span></span> <span data-ttu-id="c4b02-110">既定のプロファイルの水平ペインの場合は、<kbd>alt+shift+-</kbd> と入力します。</span><span class="sxs-lookup"><span data-stu-id="c4b02-110">For a horizontal pane of your default profile, you can type <kbd>alt+shift+-</kbd>.</span></span>

<span data-ttu-id="c4b02-111">![Windows ターミナルのペインの作成](./images/open-panes.gif)
_構成:[Raspberry Ubuntu](./custom-terminal-gallery/raspberry-ubuntu.md)_</span><span class="sxs-lookup"><span data-stu-id="c4b02-111">![Windows Terminal create pane](./images/open-panes.gif)
_Configuration: [Raspberry Ubuntu](./custom-terminal-gallery/raspberry-ubuntu.md)_</span></span>

<span data-ttu-id="c4b02-112">これらのキー バインドを変更する場合は、`splitPane` アクションと、profiles.json ファイルで `split` プロパティの値に `vertical` または `horizontal` を使用することで、新しいキー バインドを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c4b02-112">If you would like to change these key bindings, you can create new ones using the `splitPane` action and `vertical` or `horizontal` values for the `split` property in your profiles.json file.</span></span> <span data-ttu-id="c4b02-113">最大値の領域を持つペインが必要な場合は、`split` を `auto` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="c4b02-113">If you just want a pane with the maximum amount of surface area, you can set `split` to `auto`.</span></span> <span data-ttu-id="c4b02-114">キー バインドの詳細については、[キー バインドに関するページ](./customize-settings/key-bindings.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4b02-114">To learn more about key bindings, visit the [key bindings page](./customize-settings/key-bindings.md).</span></span>

```json
{ "command": { "action": "splitPane", "split": "vertical" }, "keys": "alt+shift+plus" },
{ "command": { "action": "splitPane", "split": "horizontal" }, "keys": "alt+shift+-" },
{ "command": { "action": "splitPane", "split": "auto" }, "keys": "alt+shift+|" }
```

### <a name="using-the-dropdown-menu-preview"></a><span data-ttu-id="c4b02-115">ドロップダウン メニューを使用する ([プレビュー](https://aka.ms/terminal-preview/))</span><span class="sxs-lookup"><span data-stu-id="c4b02-115">Using the dropdown menu ([Preview](https://aka.ms/terminal-preview/))</span></span>

<span data-ttu-id="c4b02-116">ドロップダウン メニューから新しいペインを開く場合、<kbd>Alt</kbd> キーを押しながら、目的のプロファイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4b02-116">If you'd like to open a new pane through the dropdown menu, you can hold <kbd>alt</kbd> and click on your desired profile.</span></span> <span data-ttu-id="c4b02-117">これにより、アクティブなウィンドウまたはペインが、選択したプロファイルの新しいペインに `auto` 分割されます。</span><span class="sxs-lookup"><span data-stu-id="c4b02-117">This will `auto` split the active window or pane into a new pane of the selected profile.</span></span> <span data-ttu-id="c4b02-118">`auto` 分割モードは、ペインを作成するために長辺の方向に分割されます。</span><span class="sxs-lookup"><span data-stu-id="c4b02-118">The `auto` split mode splits in the direction that has the longest edge to create a pane.</span></span>

![Windows ターミナルのドロップダウン ペイン](./images/alt-click-pane.gif)

> [!IMPORTANT]
> <span data-ttu-id="c4b02-120">この機能は、[Windows ターミナル プレビュー](https://aka.ms/terminal-preview/)でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4b02-120">This feature is only available in [Windows Terminal Preview](https://aka.ms/terminal-preview/).</span></span>

## <a name="switching-between-panes"></a><span data-ttu-id="c4b02-121">ペインを切り替える</span><span class="sxs-lookup"><span data-stu-id="c4b02-121">Switching between panes</span></span>

<span data-ttu-id="c4b02-122">ターミナルでは、キーボードを使用してペイン間を移動できます。</span><span class="sxs-lookup"><span data-stu-id="c4b02-122">The terminal allows you to navigate between panes by using the keyboard.</span></span> <span data-ttu-id="c4b02-123"><kbd>alt</kbd> キーを押したままにすると、方向キーを使用してペイン間でフォーカスを移動できます。</span><span class="sxs-lookup"><span data-stu-id="c4b02-123">If you hold the <kbd>alt</kbd> key, you can use your arrow keys to move your focus between panes.</span></span> <span data-ttu-id="c4b02-124">フォーカスがあるペインは、それを囲むアクセント カラーの境界線で特定できます。</span><span class="sxs-lookup"><span data-stu-id="c4b02-124">You can identify which pane is in focus by the accent color border surrounding it.</span></span> <span data-ttu-id="c4b02-125">このアクセント カラーは、Windows の色の設定で設定されています。</span><span class="sxs-lookup"><span data-stu-id="c4b02-125">Note that this accent color is set in your Windows color settings.</span></span>

![Windows ターミナルのペインの切り替え](./images/navigate-panes.gif)

<span data-ttu-id="c4b02-127">これをカスタマイズするには、`moveFocus` コマンドのキー バインドを追加し、`direction` を `down`、`left`、`right`、`up` のいずれかに設定します。</span><span class="sxs-lookup"><span data-stu-id="c4b02-127">You can customize this by adding key bindings for the `moveFocus` command and setting the `direction` to either `down`, `left`, `right` or `up`.</span></span>

```json
{ "command": { "action": "moveFocus", "direction": "down" }, "keys": "alt+down" },
{ "command": { "action": "moveFocus", "direction": "left" }, "keys": "alt+left" },
{ "command": { "action": "moveFocus", "direction": "right" }, "keys": "alt+right" },
{ "command": { "action": "moveFocus", "direction": "up" }, "keys": "alt+up" }
```

## <a name="resizing-a-pane"></a><span data-ttu-id="c4b02-128">ペインのサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="c4b02-128">Resizing a pane</span></span>

<span data-ttu-id="c4b02-129">ペインのサイズを調整するには、<kbd>alt+shift</kbd> キーを押したまま、方向キーを使用してフォーカスがあるペインのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="c4b02-129">You can adjust the size of your panes by holding <kbd>alt+shift</kbd> and using your arrow keys to resize the focused pane.</span></span>

![Windows ターミナルのペインの作成](./images/resize-panes.gif)

<span data-ttu-id="c4b02-131">このキー バインドをカスタマイズするには、`resizePane` アクションを使用して新しいキー バインドを追加し、`direction` を `down`、`left`、`right`、`up` のいずれかに設定します。</span><span class="sxs-lookup"><span data-stu-id="c4b02-131">To customize this key binding, you can add new ones using the `resizePane` action and setting the `direction` to either `down`, `left`, `right`, or `up`.</span></span>

```json
{ "command": { "action": "resizePane", "direction": "down" }, "keys": "alt+shift+down" },
{ "command": { "action": "resizePane", "direction": "left" }, "keys": "alt+shift+left" },
{ "command": { "action": "resizePane", "direction": "right" }, "keys": "alt+shift+right" },
{ "command": { "action": "resizePane", "direction": "up" }, "keys": "alt+shift+up" }
```

## <a name="closing-a-pane"></a><span data-ttu-id="c4b02-132">ペインを閉じる</span><span class="sxs-lookup"><span data-stu-id="c4b02-132">Closing a pane</span></span>

<span data-ttu-id="c4b02-133"><kbd>ctrl+shift+w</kbd> を入力すると、フォーカスされているペインを閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="c4b02-133">You can close the focused pane by typing <kbd>ctrl+shift+w</kbd>.</span></span> <span data-ttu-id="c4b02-134">ペインが 1 つしかない場合は、<kbd>ctrl+shift+w</kbd> でタブが閉じます。いつものとおり、最後のタブを閉じると、ウィンドウが閉じます。</span><span class="sxs-lookup"><span data-stu-id="c4b02-134">If you only have one pane, <kbd>ctrl+shift+w</kbd> will close the tab. As always, closing the last tab will close the window.</span></span>

![Windows ターミナルのペインを閉じる](./images/close-panes.gif)

<span data-ttu-id="c4b02-136">ペインを閉じるキーを変更するには、`closePane` コマンドを使用するキー バインドを追加します。</span><span class="sxs-lookup"><span data-stu-id="c4b02-136">You can change which keys close the pane by adding a key binding that uses the `closePane` command.</span></span>

```json
{ "command": "closePane", "keys": "ctrl+shift+w" }
```

## <a name="customizing-panes-using-key-bindings"></a><span data-ttu-id="c4b02-137">キー バインドを使用してペインをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="c4b02-137">Customizing panes using key bindings</span></span>

<span data-ttu-id="c4b02-138">カスタム キー バインドに応じて、新しいペイン内に開くものをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="c4b02-138">You can customize what opens inside a new pane depending on your custom key bindings.</span></span>

### <a name="duplicating-a-pane"></a><span data-ttu-id="c4b02-139">ペインを複製する</span><span class="sxs-lookup"><span data-stu-id="c4b02-139">Duplicating a pane</span></span>

<span data-ttu-id="c4b02-140">ターミナルでは、フォーカスがあるペインのプロファイルを別のペインに複製できます。</span><span class="sxs-lookup"><span data-stu-id="c4b02-140">The terminal allows you to duplicate the focused pane's profile into another pane.</span></span>

![Windows ターミナルのペインの複製](./images/duplicate-panes.gif)

<span data-ttu-id="c4b02-142">これを行うには、`splitMode` プロパティと値として `duplicate` を `splitPane` キー バインドに追加します。</span><span class="sxs-lookup"><span data-stu-id="c4b02-142">This can be done by adding the `splitMode` property with `duplicate` as the value to a `splitPane` key binding.</span></span>

```json
{ "command": { "action": "splitPane", "split": "auto", "splitMode": "duplicate" }, "keys": "alt+shift+d" }
```

### <a name="new-terminal-arguments"></a><span data-ttu-id="c4b02-143">新しいターミナル引数</span><span class="sxs-lookup"><span data-stu-id="c4b02-143">New terminal arguments</span></span>

[!INCLUDE [new-terminal-arguments](./new-terminal-arguments.md)]
