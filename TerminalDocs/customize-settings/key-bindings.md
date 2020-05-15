---
title: Windows ターミナルのキー バインド
description: Windows ターミナルのカスタム キー バインドを作成する方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: how-to
ms.service: terminal
ms.localizationpriority: high
ms.openlocfilehash: 76bf91f8d7c2b49c2dc6bcf0c83640b57b2acd01
ms.sourcegitcommit: bb5b7fd7db4b81e0d44e060989dc16b6775c802a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83415967"
---
# <a name="custom-key-bindings-in-windows-terminal"></a><span data-ttu-id="ac6c8-103">Windows ターミナルのカスタム キー バインド</span><span class="sxs-lookup"><span data-stu-id="ac6c8-103">Custom key bindings in Windows Terminal</span></span>

<span data-ttu-id="ac6c8-104">Windows ターミナル内にカスタム キー バインド (キーボード ショートカット) を作成して、キーボードを使用してターミナルとの対話方法を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-104">You can create custom key bindings (keyboard shortcuts) inside the Windows Terminal that give you control of how you interact with the terminal using your keyboard.</span></span>

## <a name="key-binding-formats"></a><span data-ttu-id="ac6c8-105">キー バインドの形式</span><span class="sxs-lookup"><span data-stu-id="ac6c8-105">Key binding formats</span></span>

<span data-ttu-id="ac6c8-106">キー バインドは、次の形式で構成できます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-106">Key bindings can be structured in the following formats:</span></span>

### <a name="commands-without-arguments"></a><span data-ttu-id="ac6c8-107">引数なしのコマンド</span><span class="sxs-lookup"><span data-stu-id="ac6c8-107">Commands without arguments</span></span>

```json
{ "command": "commandName", "keys": "modifiers+key" }
```

<span data-ttu-id="ac6c8-108">たとえば、この既定の設定では、ショートカット キー <kbd>alt+f4</kbd> を使用してターミナル ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-108">For example, this default setting uses the shortcut key <kbd>alt+f4</kbd> to close the terminal window:</span></span>

```json
{ "command": "closeWindow", "keys": "alt+f4" }
```

### <a name="commands-with-arguments"></a><span data-ttu-id="ac6c8-109">引数を指定したコマンド</span><span class="sxs-lookup"><span data-stu-id="ac6c8-109">Commands with arguments</span></span>

```json
{ "command": { "action": "commandName", "argument": "value" }, "keys": "modifiers+key" }
```

<span data-ttu-id="ac6c8-110">たとえば、この既定の設定では、ショートカット キー <kbd>Ctrl + Shift + 1</kbd> を使用すると、ドロップダウン メニューにどのプロファイルが最初に表示されるかに基づいて、ターミナルで新しいタブが開きます (通常は PowerShell プロファイルを開きます)。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-110">For example, this default setting uses the shortcut key <kbd>ctrl+shift+1</kbd> to open a new tab in the terminal based on whichever profile is listed first in your dropdown menu (typically this will open the PowerShell profile):</span></span>

```json
{ "command": { "action": "newTab", "index": 0 }, "keys": "ctrl+shift+1" }
```

<br />

___

## <a name="key-binding-properties"></a><span data-ttu-id="ac6c8-111">キー バインドのプロパティ</span><span class="sxs-lookup"><span data-stu-id="ac6c8-111">Key binding properties</span></span>

<span data-ttu-id="ac6c8-112">キー バインドは、次のプロパティを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-112">Key bindings can be constructed using the following properties.</span></span>

### <a name="command"></a><span data-ttu-id="ac6c8-113">コマンド</span><span class="sxs-lookup"><span data-stu-id="ac6c8-113">Command</span></span>

<span data-ttu-id="ac6c8-114">これは、関連付けられたキーが押されたときに実行されるコマンドです。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-114">This is the command executed when the associated keys are pressed.</span></span>

<span data-ttu-id="ac6c8-115">**プロパティ名:** `command`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-115">**Property name:** `command`</span></span>

<span data-ttu-id="ac6c8-116">**必須かどうか:** 必須</span><span class="sxs-lookup"><span data-stu-id="ac6c8-116">**Necessity:** Required</span></span>

<span data-ttu-id="ac6c8-117">**受け入れ可能:** String</span><span class="sxs-lookup"><span data-stu-id="ac6c8-117">**Accepts:** String</span></span>

### <a name="keys"></a><span data-ttu-id="ac6c8-118">キー</span><span class="sxs-lookup"><span data-stu-id="ac6c8-118">Keys</span></span>

<span data-ttu-id="ac6c8-119">コマンドを呼び出すために使用するキーの組み合わせを定義します。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-119">This defines the key combinations used to call the command.</span></span> <span data-ttu-id="ac6c8-120">1 つのキーで任意の数の修飾子を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-120">Keys can have any number of modifiers with one key.</span></span> <span data-ttu-id="ac6c8-121">受け入れられる修飾子とキーを[以下](#accepted-modifiers-and-keys)に一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-121">Accepted modifiers and keys are listed [below](#accepted-modifiers-and-keys).</span></span>

<span data-ttu-id="ac6c8-122">**プロパティ名:** `keys`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-122">**Property name:** `keys`</span></span>

<span data-ttu-id="ac6c8-123">**必須かどうか:** 必須</span><span class="sxs-lookup"><span data-stu-id="ac6c8-123">**Necessity:** Required</span></span>

<span data-ttu-id="ac6c8-124">**受け入れ可能:** String または array[string]</span><span class="sxs-lookup"><span data-stu-id="ac6c8-124">**Accepts:** String or array[string]</span></span>

### <a name="action"></a><span data-ttu-id="ac6c8-125">操作</span><span class="sxs-lookup"><span data-stu-id="ac6c8-125">Action</span></span>

<span data-ttu-id="ac6c8-126">これにより、特定のコマンドに機能が追加されます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-126">This adds additional functionality to certain commands.</span></span>

<span data-ttu-id="ac6c8-127">**プロパティ名:** `action`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-127">**Property name:** `action`</span></span>

<span data-ttu-id="ac6c8-128">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="ac6c8-128">**Necessity:** Optional</span></span>

<span data-ttu-id="ac6c8-129">**受け入れ可能:** String</span><span class="sxs-lookup"><span data-stu-id="ac6c8-129">**Accepts:** String</span></span>

<br />

___

## <a name="accepted-modifiers-and-keys"></a><span data-ttu-id="ac6c8-130">受け入れられる修飾子とキー</span><span class="sxs-lookup"><span data-stu-id="ac6c8-130">Accepted modifiers and keys</span></span>

### <a name="modifiers"></a><span data-ttu-id="ac6c8-131">修飾子</span><span class="sxs-lookup"><span data-stu-id="ac6c8-131">Modifiers</span></span>

<span data-ttu-id="ac6c8-132">`ctrl+`、`shift+`、`alt+`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-132">`ctrl+`, `shift+`, `alt+`</span></span>

### <a name="modifier-keys"></a><span data-ttu-id="ac6c8-133">修飾キー</span><span class="sxs-lookup"><span data-stu-id="ac6c8-133">Modifier keys</span></span>

| <span data-ttu-id="ac6c8-134">種類</span><span class="sxs-lookup"><span data-stu-id="ac6c8-134">Type</span></span> | <span data-ttu-id="ac6c8-135">キー</span><span class="sxs-lookup"><span data-stu-id="ac6c8-135">Keys</span></span> |
| ---- | ---- |
| <span data-ttu-id="ac6c8-136">関数と英数字キー</span><span class="sxs-lookup"><span data-stu-id="ac6c8-136">Function and alphanumeric keys</span></span> | <span data-ttu-id="ac6c8-137">`f1-f24`、`a-z`、`0-9`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-137">`f1-f24`, `a-z`, `0-9`</span></span> |
| <span data-ttu-id="ac6c8-138">記号</span><span class="sxs-lookup"><span data-stu-id="ac6c8-138">Symbols</span></span> | <span data-ttu-id="ac6c8-139">``` ` ```、`-`、`=`、`[`、`]`、`\`、`;`、`'`、`,`、`.`、`/`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-139">``` ` ```, `-`, `=`, `[`, `]`, `\`, `;`, `'`, `,`, `.`, `/`</span></span> |
| <span data-ttu-id="ac6c8-140">方向キー</span><span class="sxs-lookup"><span data-stu-id="ac6c8-140">Arrow keys</span></span> | <span data-ttu-id="ac6c8-141">`down`、`left`、`right`、`up`、`pagedown`、`pageup`、`pgdn`、`pgup`、`end`、`home`、`plus`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-141">`down`, `left`, `right`, `up`, `pagedown`, `pageup`, `pgdn`, `pgup`, `end`, `home`, `plus`</span></span> |
| <span data-ttu-id="ac6c8-142">アクション キー</span><span class="sxs-lookup"><span data-stu-id="ac6c8-142">Action keys</span></span> | <span data-ttu-id="ac6c8-143">`tab`、`enter`、`esc`、`escape`、`space`、`backspace`、`delete`、`insert`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-143">`tab`, `enter`, `esc`, `escape`, `space`, `backspace`, `delete`, `insert`</span></span> |
| <span data-ttu-id="ac6c8-144">テンキーのキー</span><span class="sxs-lookup"><span data-stu-id="ac6c8-144">Numpad keys</span></span> | <span data-ttu-id="ac6c8-145">`numpad_0-numpad_9`、`numpad0-numpad9`、`numpad_add`、`numpad_plus`、`numpad_decimal`、`numpad_period`、`numpad_divide`、`numpad_minus`、`numpad_subtract`、`numpad_multiply`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-145">`numpad_0-numpad_9`, `numpad0-numpad9`, `numpad_add`, `numpad_plus`, `numpad_decimal`, `numpad_period`, `numpad_divide`, `numpad_minus`, `numpad_subtract`, `numpad_multiply`</span></span> |

<br />

___

## <a name="application-level-commands"></a><span data-ttu-id="ac6c8-146">アプリケーションレベルのコマンド</span><span class="sxs-lookup"><span data-stu-id="ac6c8-146">Application-level commands</span></span>

### <a name="close-window"></a><span data-ttu-id="ac6c8-147">ウィンドウを閉じる</span><span class="sxs-lookup"><span data-stu-id="ac6c8-147">Close window</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="ac6c8-148">現在のウィンドウとその中のすべてのタブが閉じられます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-148">This closes the current window and all tabs within it.</span></span> <span data-ttu-id="ac6c8-149">`confirmCloseAllTabs` が `true` に設定されている場合は、すべてのタブを閉じることを確認する確認ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-149">If `confirmCloseAllTabs` is set to `true`, a confirmation dialog will appear to ensure you'd like to close all your tabs.</span></span> <span data-ttu-id="ac6c8-150">この設定の詳細については、[グローバル設定に関するページ](./global-settings.md#hide-close-all-tabs-popup)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-150">More information on this setting can be found on the [Global settings page](./global-settings.md#hide-close-all-tabs-popup).</span></span>

<span data-ttu-id="ac6c8-151">**コマンド名:** `closeWindow`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-151">**Command name:** `closeWindow`</span></span>

<span data-ttu-id="ac6c8-152">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="ac6c8-152">**Default binding:**</span></span>

```json
{ "command": "closeWindow", "keys": "alt+f4" }
```

:::column-end:::
:::column span="":::
![Windows ターミナルのすべてのタブを閉じるの確認](./../images/confirm-close-all-tabs.png)

:::column-end:::
:::row-end:::

### <a name="find"></a><span data-ttu-id="ac6c8-154">［検索］</span><span class="sxs-lookup"><span data-stu-id="ac6c8-154">Find</span></span>

<span data-ttu-id="ac6c8-155">[検索] ダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-155">This opens the search dialog box.</span></span> <span data-ttu-id="ac6c8-156">検索の詳細については、[検索に関するページ](./../search.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-156">More information on search can be found on the [Search page](./../search.md).</span></span>

<span data-ttu-id="ac6c8-157">**コマンド名:** `find`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-157">**Command name:** `find`</span></span>

<span data-ttu-id="ac6c8-158">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="ac6c8-158">**Default binding:**</span></span>

```json
{ "command": "find", "keys": "ctrl+shift+f" }
```

### <a name="open-the-dropdown"></a><span data-ttu-id="ac6c8-159">ドロップダウンを開く</span><span class="sxs-lookup"><span data-stu-id="ac6c8-159">Open the dropdown</span></span>

<span data-ttu-id="ac6c8-160">ドロップダウン メニューが開きます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-160">This opens the dropdown menu.</span></span>

<span data-ttu-id="ac6c8-161">**コマンド名:** `openNewTabDropdown`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-161">**Command name:** `openNewTabDropdown`</span></span>

<span data-ttu-id="ac6c8-162">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="ac6c8-162">**Default binding:**</span></span>

```json
{ "command": "openNewTabDropdown", "keys": "ctrl+shift+space" }
```

### <a name="open-settings-file"></a><span data-ttu-id="ac6c8-163">設定ファイルを開く</span><span class="sxs-lookup"><span data-stu-id="ac6c8-163">Open settings file</span></span>

<span data-ttu-id="ac6c8-164">設定ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-164">This opens the settings file.</span></span>

<span data-ttu-id="ac6c8-165">**コマンド名:** `openSettings`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-165">**Command name:** `openSettings`</span></span>

<span data-ttu-id="ac6c8-166">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="ac6c8-166">**Default binding:**</span></span>

```json
{ "command": "openSettings", "keys": "ctrl+," }
```

### <a name="toggle-full-screen"></a><span data-ttu-id="ac6c8-167">全画面表示の切り替え</span><span class="sxs-lookup"><span data-stu-id="ac6c8-167">Toggle full screen</span></span>

<span data-ttu-id="ac6c8-168">全画面表示と既定のウィンドウ サイズを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-168">This allows you to switch between full screen and default window sizes.</span></span>

<span data-ttu-id="ac6c8-169">**コマンド名:** `toggleFullscreen`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-169">**Command name:** `toggleFullscreen`</span></span>

<span data-ttu-id="ac6c8-170">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="ac6c8-170">**Default bindings:**</span></span>

```json
{ "command": "toggleFullscreen", "keys": "alt+enter" },
{ "command": "toggleFullscreen", "keys": "f11" }
```

<br />

___

## <a name="tab-management-commands"></a><span data-ttu-id="ac6c8-171">タブ管理コマンド</span><span class="sxs-lookup"><span data-stu-id="ac6c8-171">Tab management commands</span></span>

### <a name="close-tab"></a><span data-ttu-id="ac6c8-172">タブを閉じる</span><span class="sxs-lookup"><span data-stu-id="ac6c8-172">Close tab</span></span>

<span data-ttu-id="ac6c8-173">現在のタブが閉じます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-173">This closes the current tab.</span></span>

<span data-ttu-id="ac6c8-174">**コマンド名:** `closeTab`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-174">**Command name:** `closeTab`</span></span>

### <a name="duplicate-tab"></a><span data-ttu-id="ac6c8-175">タブを複製</span><span class="sxs-lookup"><span data-stu-id="ac6c8-175">Duplicate tab</span></span>

<span data-ttu-id="ac6c8-176">現在のタブのコピーが作成されて開きます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-176">This makes a copy of the current tab and opens it.</span></span>

<span data-ttu-id="ac6c8-177">**コマンド名:** `duplicateTab`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-177">**Command name:** `duplicateTab`</span></span>

<span data-ttu-id="ac6c8-178">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="ac6c8-178">**Default binding:**</span></span>

```json
{ "command": "duplicateTab", "keys": "ctrl+shift+d" }
```

### <a name="new-tab"></a><span data-ttu-id="ac6c8-179">新しいタブ</span><span class="sxs-lookup"><span data-stu-id="ac6c8-179">New tab</span></span>

<span data-ttu-id="ac6c8-180">新しいタブが作成されます。引数を指定しないと、既定のプロファイルが新しいタブで開きます。アクションが指定されていない場合は、既定のプロファイルの同等の設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-180">This creates a new tab. Without any arguments, this will open the default profile in a new tab. If an action is not specified, the default profile's equivalent setting will be used.</span></span>

<span data-ttu-id="ac6c8-181">**コマンド名:** `newTab`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-181">**Command name:** `newTab`</span></span>

<span data-ttu-id="ac6c8-182">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="ac6c8-182">**Default bindings:**</span></span>

```json
{ "command": "newTab", "keys": "ctrl+shift+t" },
{ "command": { "action": "newTab", "index": 0 }, "keys": "ctrl+shift+1" },
{ "command": { "action": "newTab", "index": 1 }, "keys": "ctrl+shift+2" },
{ "command": { "action": "newTab", "index": 2 }, "keys": "ctrl+shift+3" },
{ "command": { "action": "newTab", "index": 3 }, "keys": "ctrl+shift+4" },
{ "command": { "action": "newTab", "index": 4 }, "keys": "ctrl+shift+5" },
{ "command": { "action": "newTab", "index": 5 }, "keys": "ctrl+shift+6" },
{ "command": { "action": "newTab", "index": 6 }, "keys": "ctrl+shift+7" },
{ "command": { "action": "newTab", "index": 7 }, "keys": "ctrl+shift+8" },
{ "command": { "action": "newTab", "index": 8 }, "keys": "ctrl+shift+9" }
```

#### <a name="actions"></a><span data-ttu-id="ac6c8-183">操作</span><span class="sxs-lookup"><span data-stu-id="ac6c8-183">Actions</span></span>

| <span data-ttu-id="ac6c8-184">名前</span><span class="sxs-lookup"><span data-stu-id="ac6c8-184">Name</span></span> | <span data-ttu-id="ac6c8-185">必要</span><span class="sxs-lookup"><span data-stu-id="ac6c8-185">Necessity</span></span> | <span data-ttu-id="ac6c8-186">受け入れられる型</span><span class="sxs-lookup"><span data-stu-id="ac6c8-186">Accepts</span></span> | <span data-ttu-id="ac6c8-187">説明</span><span class="sxs-lookup"><span data-stu-id="ac6c8-187">Description</span></span> |
| ---- | --------- | ------- | ----------- |
| `commandLine` | <span data-ttu-id="ac6c8-188">オプション</span><span class="sxs-lookup"><span data-stu-id="ac6c8-188">Optional</span></span> | <span data-ttu-id="ac6c8-189">実行可能ファイル名を表す文字列</span><span class="sxs-lookup"><span data-stu-id="ac6c8-189">Executable file name as a string</span></span> | <span data-ttu-id="ac6c8-190">実行可能ファイルがタブ内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-190">Executable run within the tab.</span></span> |
| `startingDirectory` | <span data-ttu-id="ac6c8-191">オプション</span><span class="sxs-lookup"><span data-stu-id="ac6c8-191">Optional</span></span> | <span data-ttu-id="ac6c8-192">フォルダーの場所を表す文字列</span><span class="sxs-lookup"><span data-stu-id="ac6c8-192">Folder location as a string</span></span> | <span data-ttu-id="ac6c8-193">タブが開かれるディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-193">Directory in which the tab will open.</span></span> |
| `tabTitle` | <span data-ttu-id="ac6c8-194">オプション</span><span class="sxs-lookup"><span data-stu-id="ac6c8-194">Optional</span></span> | <span data-ttu-id="ac6c8-195">String</span><span class="sxs-lookup"><span data-stu-id="ac6c8-195">String</span></span> | <span data-ttu-id="ac6c8-196">新しいタブのタイトル。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-196">Title of the new tab.</span></span> |
| `index` | <span data-ttu-id="ac6c8-197">オプション</span><span class="sxs-lookup"><span data-stu-id="ac6c8-197">Optional</span></span> | <span data-ttu-id="ac6c8-198">整数</span><span class="sxs-lookup"><span data-stu-id="ac6c8-198">Integer</span></span> | <span data-ttu-id="ac6c8-199">ドロップダウンでの位置 (0 から開始) に基づいて開かれるプロファイル。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-199">Profile that will open based on its position in the dropdown (starting at 0).</span></span> |
| `profile` | <span data-ttu-id="ac6c8-200">オプション</span><span class="sxs-lookup"><span data-stu-id="ac6c8-200">Optional</span></span> | <span data-ttu-id="ac6c8-201">プロファイルの名前または GUID を表す文字列</span><span class="sxs-lookup"><span data-stu-id="ac6c8-201">Profile's name or GUID as a string</span></span> | <span data-ttu-id="ac6c8-202">GUID または名前に基づいて開かれるプロファイル。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-202">Profile that will open based on its GUID or name.</span></span> |

### <a name="open-next-tab"></a><span data-ttu-id="ac6c8-203">次のタブを開く</span><span class="sxs-lookup"><span data-stu-id="ac6c8-203">Open next tab</span></span>

<span data-ttu-id="ac6c8-204">現在のタブの右側にタブが開きます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-204">This opens the tab to the right of the current one.</span></span>

<span data-ttu-id="ac6c8-205">**コマンド名:** `nextTab`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-205">**Command name:** `nextTab`</span></span>

<span data-ttu-id="ac6c8-206">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="ac6c8-206">**Default binding:**</span></span>

```json
{ "command": "nextTab", "keys": "ctrl+tab" }
```

### <a name="open-previous-tab"></a><span data-ttu-id="ac6c8-207">前のタブを開く</span><span class="sxs-lookup"><span data-stu-id="ac6c8-207">Open previous tab</span></span>

<span data-ttu-id="ac6c8-208">現在のタブの左側にタブが開きます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-208">This opens the tab to the left of the current one.</span></span>

<span data-ttu-id="ac6c8-209">**コマンド名:** `prevTab`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-209">**Command name:** `prevTab`</span></span>

<span data-ttu-id="ac6c8-210">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="ac6c8-210">**Default binding:**</span></span>

```json
{ "command": "prevTab", "keys": "ctrl+shift+tab" }
```

### <a name="open-a-specific-tab"></a><span data-ttu-id="ac6c8-211">特定のタブを開く</span><span class="sxs-lookup"><span data-stu-id="ac6c8-211">Open a specific tab</span></span>

<span data-ttu-id="ac6c8-212">インデックスに応じて特定のタブが開きます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-212">This opens a specific tab depending on the index.</span></span>

<span data-ttu-id="ac6c8-213">**コマンド名:** `switchToTab`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-213">**Command name:** `switchToTab`</span></span>

<span data-ttu-id="ac6c8-214">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="ac6c8-214">**Default bindings:**</span></span>

```json
{ "command": { "action": "switchToTab", "index": 0 }, "keys": "ctrl+alt+1" },
{ "command": { "action": "switchToTab", "index": 1 }, "keys": "ctrl+alt+2" },
{ "command": { "action": "switchToTab", "index": 2 }, "keys": "ctrl+alt+3" },
{ "command": { "action": "switchToTab", "index": 3 }, "keys": "ctrl+alt+4" },
{ "command": { "action": "switchToTab", "index": 4 }, "keys": "ctrl+alt+5" },
{ "command": { "action": "switchToTab", "index": 5 }, "keys": "ctrl+alt+6" },
{ "command": { "action": "switchToTab", "index": 6 }, "keys": "ctrl+alt+7" },
{ "command": { "action": "switchToTab", "index": 7 }, "keys": "ctrl+alt+8" },
{ "command": { "action": "switchToTab", "index": 8 }, "keys": "ctrl+alt+9" }
```

#### <a name="actions"></a><span data-ttu-id="ac6c8-215">操作</span><span class="sxs-lookup"><span data-stu-id="ac6c8-215">Actions</span></span>

| <span data-ttu-id="ac6c8-216">名前</span><span class="sxs-lookup"><span data-stu-id="ac6c8-216">Name</span></span> | <span data-ttu-id="ac6c8-217">必要</span><span class="sxs-lookup"><span data-stu-id="ac6c8-217">Necessity</span></span> | <span data-ttu-id="ac6c8-218">受け入れられる型</span><span class="sxs-lookup"><span data-stu-id="ac6c8-218">Accepts</span></span> | <span data-ttu-id="ac6c8-219">説明</span><span class="sxs-lookup"><span data-stu-id="ac6c8-219">Description</span></span> |
| ---- | --------- | ------- | ----------- |
| `index` | <span data-ttu-id="ac6c8-220">必須</span><span class="sxs-lookup"><span data-stu-id="ac6c8-220">Required</span></span> | <span data-ttu-id="ac6c8-221">整数</span><span class="sxs-lookup"><span data-stu-id="ac6c8-221">Integer</span></span> | <span data-ttu-id="ac6c8-222">タブ バー内の位置 (0 から開始) に基づいて開かれるタブ。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-222">Tab that will open based on its position in the tab bar (starting at 0).</span></span> |

<br />

___

## <a name="pane-management-commands"></a><span data-ttu-id="ac6c8-223">ペイン管理コマンド</span><span class="sxs-lookup"><span data-stu-id="ac6c8-223">Pane management commands</span></span>

### <a name="close-pane"></a><span data-ttu-id="ac6c8-224">ペインを閉じる</span><span class="sxs-lookup"><span data-stu-id="ac6c8-224">Close pane</span></span>

<span data-ttu-id="ac6c8-225">アクティブなペインを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-225">This closes the active pane.</span></span> <span data-ttu-id="ac6c8-226">分割ペインがない場合は、現在のタブが閉じられます。開いているタブが 1 つだけの場合は、ウィンドウが閉じられます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-226">If there aren't any split panes, this will close the current tab. If there is only one tab open, this will close the window.</span></span>

<span data-ttu-id="ac6c8-227">**コマンド名:** `closePane`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-227">**Command name:** `closePane`</span></span>

<span data-ttu-id="ac6c8-228">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="ac6c8-228">**Default binding:**</span></span>

```json
{ "command": "closePane", "keys": "ctrl+shift+w" }
```

### <a name="move-pane-focus"></a><span data-ttu-id="ac6c8-229">ペイン フォーカスの移動</span><span class="sxs-lookup"><span data-stu-id="ac6c8-229">Move pane focus</span></span>

<span data-ttu-id="ac6c8-230">方向に応じて、別のペインにフォーカスが移動します。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-230">This changes focus to a different pane depending on the direction.</span></span>

<span data-ttu-id="ac6c8-231">**コマンド名:** `moveFocus`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-231">**Command name:** `moveFocus`</span></span>

<span data-ttu-id="ac6c8-232">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="ac6c8-232">**Default bindings:**</span></span>

```json
{ "command": { "action": "moveFocus", "direction": "down" }, "keys": "alt+down" },
{ "command": { "action": "moveFocus", "direction": "left" }, "keys": "alt+left" },
{ "command": { "action": "moveFocus", "direction": "right" }, "keys": "alt+right" },
{ "command": { "action": "moveFocus", "direction": "up" }, "keys": "alt+up" }
```

#### <a name="actions"></a><span data-ttu-id="ac6c8-233">操作</span><span class="sxs-lookup"><span data-stu-id="ac6c8-233">Actions</span></span>

| <span data-ttu-id="ac6c8-234">名前</span><span class="sxs-lookup"><span data-stu-id="ac6c8-234">Name</span></span> | <span data-ttu-id="ac6c8-235">必要</span><span class="sxs-lookup"><span data-stu-id="ac6c8-235">Necessity</span></span> | <span data-ttu-id="ac6c8-236">受け入れられる型</span><span class="sxs-lookup"><span data-stu-id="ac6c8-236">Accepts</span></span> | <span data-ttu-id="ac6c8-237">説明</span><span class="sxs-lookup"><span data-stu-id="ac6c8-237">Description</span></span> |
| ---- | --------- | ------- | ----------- |
| `direction` | <span data-ttu-id="ac6c8-238">必須</span><span class="sxs-lookup"><span data-stu-id="ac6c8-238">Required</span></span> | <span data-ttu-id="ac6c8-239">`"left"`、`"right"`、`"up"`、`"down"`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-239">`"left"`, `"right"`, `"up"`, `"down"`</span></span> | <span data-ttu-id="ac6c8-240">フォーカスを移動する方向。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-240">Direction in which the focus will move.</span></span> |

### <a name="resize-a-pane"></a><span data-ttu-id="ac6c8-241">ペインのサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="ac6c8-241">Resize a pane</span></span>

<span data-ttu-id="ac6c8-242">アクティブなペインのサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-242">This changes the size of the active pane.</span></span>

<span data-ttu-id="ac6c8-243">**コマンド名:** `resizePane`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-243">**Command name:** `resizePane`</span></span>

<span data-ttu-id="ac6c8-244">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="ac6c8-244">**Default bindings:**</span></span>

```json
{ "command": { "action": "resizePane", "direction": "down" }, "keys": "alt+shift+down" },
{ "command": { "action": "resizePane", "direction": "left" }, "keys": "alt+shift+left" },
{ "command": { "action": "resizePane", "direction": "right" }, "keys": "alt+shift+right" },
{ "command": { "action": "resizePane", "direction": "up" }, "keys": "alt+shift+up" }
```

#### <a name="actions"></a><span data-ttu-id="ac6c8-245">操作</span><span class="sxs-lookup"><span data-stu-id="ac6c8-245">Actions</span></span>

| <span data-ttu-id="ac6c8-246">名前</span><span class="sxs-lookup"><span data-stu-id="ac6c8-246">Name</span></span> | <span data-ttu-id="ac6c8-247">必要</span><span class="sxs-lookup"><span data-stu-id="ac6c8-247">Necessity</span></span> | <span data-ttu-id="ac6c8-248">受け入れられる型</span><span class="sxs-lookup"><span data-stu-id="ac6c8-248">Accepts</span></span> | <span data-ttu-id="ac6c8-249">説明</span><span class="sxs-lookup"><span data-stu-id="ac6c8-249">Description</span></span> |
| ---- | --------- | ------- | ----------- |
| `direction` | <span data-ttu-id="ac6c8-250">必須</span><span class="sxs-lookup"><span data-stu-id="ac6c8-250">Required</span></span> | <span data-ttu-id="ac6c8-251">`"left"`、`"right"`、`"up"`、`"down"`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-251">`"left"`, `"right"`, `"up"`, `"down"`</span></span> | <span data-ttu-id="ac6c8-252">ペインのサイズを変更する方向。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-252">Direction in which the pane will be resized.</span></span> |

### <a name="split-a-pane"></a><span data-ttu-id="ac6c8-253">ペインの分割</span><span class="sxs-lookup"><span data-stu-id="ac6c8-253">Split a pane</span></span>

<span data-ttu-id="ac6c8-254">アクティブなペインのサイズが半分になり、別のペインが開きます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-254">This halves the size of the active pane and opens another.</span></span> <span data-ttu-id="ac6c8-255">引数を指定しないと、既定のプロファイルが新しいペインで開かれます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-255">Without any arguments, this will open the default profile in the new pane.</span></span> <span data-ttu-id="ac6c8-256">アクションが指定されていない場合は、既定のプロファイルの同等の設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-256">If an action is not specified, the default profile's equivalent setting will be used.</span></span>

<span data-ttu-id="ac6c8-257">**コマンド名:** `splitPane`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-257">**Command name:** `splitPane`</span></span>

<span data-ttu-id="ac6c8-258">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="ac6c8-258">**Default bindings:**</span></span>

```json
// In settings.json
{ "command": { "action": "splitPane", "split": "auto", "splitMode": "duplicate" }, "keys": "alt+shift+d" },

// In defaults.json
{ "command": { "action": "splitPane", "split": "horizontal"}, "keys": "alt+shift+-" },
{ "command": { "action": "splitPane", "split": "vertical"}, "keys": "alt+shift+plus" }
```

#### <a name="actions"></a><span data-ttu-id="ac6c8-259">操作</span><span class="sxs-lookup"><span data-stu-id="ac6c8-259">Actions</span></span>

| <span data-ttu-id="ac6c8-260">名前</span><span class="sxs-lookup"><span data-stu-id="ac6c8-260">Name</span></span> | <span data-ttu-id="ac6c8-261">必要</span><span class="sxs-lookup"><span data-stu-id="ac6c8-261">Necessity</span></span> | <span data-ttu-id="ac6c8-262">受け入れられる型</span><span class="sxs-lookup"><span data-stu-id="ac6c8-262">Accepts</span></span> | <span data-ttu-id="ac6c8-263">説明</span><span class="sxs-lookup"><span data-stu-id="ac6c8-263">Description</span></span> |
| ---- | --------- | ------- | ----------- |
| `split` | <span data-ttu-id="ac6c8-264">必須</span><span class="sxs-lookup"><span data-stu-id="ac6c8-264">Required</span></span> | <span data-ttu-id="ac6c8-265">`"vertical"`、`"horizontal"`、`"auto"`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-265">`"vertical"`, `"horizontal"`, `"auto"`</span></span> | <span data-ttu-id="ac6c8-266">ペインの分割方法。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-266">How the pane will split.</span></span> <span data-ttu-id="ac6c8-267">`"auto"` は、最も多くの領域を提供する方向に分割します。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-267">`"auto"` will split in the direction that provides the most surface area.</span></span> |
| `commandLine` | <span data-ttu-id="ac6c8-268">オプション</span><span class="sxs-lookup"><span data-stu-id="ac6c8-268">Optional</span></span> | <span data-ttu-id="ac6c8-269">実行可能ファイル名を表す文字列</span><span class="sxs-lookup"><span data-stu-id="ac6c8-269">Executable file name as a string</span></span> | <span data-ttu-id="ac6c8-270">実行可能ファイルがペイン内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-270">Executable run within the pane.</span></span> |
| `startingDirectory` | <span data-ttu-id="ac6c8-271">オプション</span><span class="sxs-lookup"><span data-stu-id="ac6c8-271">Optional</span></span> | <span data-ttu-id="ac6c8-272">フォルダーの場所を表す文字列</span><span class="sxs-lookup"><span data-stu-id="ac6c8-272">Folder location as a string</span></span> | <span data-ttu-id="ac6c8-273">ペインが開かれるディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-273">Directory in which the pane will open.</span></span> |
| `tabTitle` | <span data-ttu-id="ac6c8-274">オプション</span><span class="sxs-lookup"><span data-stu-id="ac6c8-274">Optional</span></span> | <span data-ttu-id="ac6c8-275">String</span><span class="sxs-lookup"><span data-stu-id="ac6c8-275">String</span></span> | <span data-ttu-id="ac6c8-276">新しいペインにフォーカスがあるときのタブのタイトル。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-276">Title of the tab when the new pane is focused.</span></span> |
| `index` | <span data-ttu-id="ac6c8-277">オプション</span><span class="sxs-lookup"><span data-stu-id="ac6c8-277">Optional</span></span> | <span data-ttu-id="ac6c8-278">整数</span><span class="sxs-lookup"><span data-stu-id="ac6c8-278">Integer</span></span> | <span data-ttu-id="ac6c8-279">ドロップダウンでの位置 (0 から開始) に基づいて開かれるプロファイル。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-279">Profile that will open based on its position in the dropdown (starting at 0).</span></span> |
| `profile` | <span data-ttu-id="ac6c8-280">オプション</span><span class="sxs-lookup"><span data-stu-id="ac6c8-280">Optional</span></span> | <span data-ttu-id="ac6c8-281">プロファイルの名前または GUID を表す文字列</span><span class="sxs-lookup"><span data-stu-id="ac6c8-281">Profile's name or GUID as a string</span></span> | <span data-ttu-id="ac6c8-282">GUID または名前に基づいて開かれるプロファイル。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-282">Profile that will open based on its GUID or name.</span></span> |
| `splitMode` | <span data-ttu-id="ac6c8-283">オプション</span><span class="sxs-lookup"><span data-stu-id="ac6c8-283">Optional</span></span> | `"duplicate"` | <span data-ttu-id="ac6c8-284">ペインの分割方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-284">Controls how the pane splits.</span></span> <span data-ttu-id="ac6c8-285">フォーカスがあるペインのプロファイルを新しいペインに複製する、`"duplicate"` のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-285">Only accepts `"duplicate"`, which will duplicate the focused pane's profile into a new pane.</span></span> |

<br />

___

## <a name="clipboard-integration-commands"></a><span data-ttu-id="ac6c8-286">クリップボードの統合コマンド</span><span class="sxs-lookup"><span data-stu-id="ac6c8-286">Clipboard integration commands</span></span>

### <a name="copy"></a><span data-ttu-id="ac6c8-287">コピー</span><span class="sxs-lookup"><span data-stu-id="ac6c8-287">Copy</span></span>

<span data-ttu-id="ac6c8-288">選択したターミナル コンテンツがクリップボードにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-288">This copies the selected terminal content to your clipboard.</span></span>

<span data-ttu-id="ac6c8-289">**コマンド名:** `copy`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-289">**Command name:** `copy`</span></span>

<span data-ttu-id="ac6c8-290">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="ac6c8-290">**Default bindings:**</span></span>

```json
// In settings.json
{ "command": { "action": "copy", "singleLine": false }, "keys": "ctrl+c" },

// In defaults.json
{ "command": { "action": "copy", "singleLine": false }, "keys": "ctrl+shift+c" },
{ "command": { "action": "copy", "singleLine": false }, "keys": "ctrl+insert" }
```

#### <a name="clipboard-actions"></a><span data-ttu-id="ac6c8-291">クリップボードのアクセス</span><span class="sxs-lookup"><span data-stu-id="ac6c8-291">Clipboard Actions</span></span>

| <span data-ttu-id="ac6c8-292">名前</span><span class="sxs-lookup"><span data-stu-id="ac6c8-292">Name</span></span> | <span data-ttu-id="ac6c8-293">必要</span><span class="sxs-lookup"><span data-stu-id="ac6c8-293">Necessity</span></span> | <span data-ttu-id="ac6c8-294">受け入れられる型</span><span class="sxs-lookup"><span data-stu-id="ac6c8-294">Accepts</span></span> | <span data-ttu-id="ac6c8-295">説明</span><span class="sxs-lookup"><span data-stu-id="ac6c8-295">Description</span></span> |
| ---- | --------- | ------- | ----------- |
| `singleLine` | <span data-ttu-id="ac6c8-296">オプション</span><span class="sxs-lookup"><span data-stu-id="ac6c8-296">Optional</span></span> | <span data-ttu-id="ac6c8-297">`true`、`false`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-297">`true`, `false`</span></span> | <span data-ttu-id="ac6c8-298">`true` の場合、コピーされたコンテンツは単一行としてコピーされます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-298">When `true`, the copied content will be copied as a single line.</span></span> <span data-ttu-id="ac6c8-299">`false` の場合、選択したテキストから改行が保持されます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-299">When `false`, newlines persist from the selected text.</span></span> |

### <a name="paste"></a><span data-ttu-id="ac6c8-300">貼り付け</span><span class="sxs-lookup"><span data-stu-id="ac6c8-300">Paste</span></span>

<span data-ttu-id="ac6c8-301">クリップボードにコピーされたコンテンツが挿入されます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-301">This inserts the content that was copied onto the clipboard.</span></span>

<span data-ttu-id="ac6c8-302">**コマンド名:** `paste`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-302">**Command name:** `paste`</span></span>

<span data-ttu-id="ac6c8-303">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="ac6c8-303">**Default bindings:**</span></span>

```json
// In settings.json
{ "command": "paste", "keys": "ctrl+v" },

// In defaults.json
{ "command": "paste", "keys": "ctrl+shift+v" },
{ "command": "paste", "keys": "shift+insert" }
```

<br />

___

## <a name="scrollback-commands"></a><span data-ttu-id="ac6c8-304">Scrollback コマンド</span><span class="sxs-lookup"><span data-stu-id="ac6c8-304">Scrollback commands</span></span>

### <a name="scroll-up"></a><span data-ttu-id="ac6c8-305">上にスクロール</span><span class="sxs-lookup"><span data-stu-id="ac6c8-305">Scroll up</span></span>

<span data-ttu-id="ac6c8-306">画面を上にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-306">This scrolls the screen up.</span></span>

<span data-ttu-id="ac6c8-307">**コマンド名:** `scrollUp`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-307">**Command name:** `scrollUp`</span></span>

<span data-ttu-id="ac6c8-308">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="ac6c8-308">**Default binding:**</span></span>

```json
{ "command": "scrollUp", "keys": "ctrl+shift+up" }
```

### <a name="scroll-down"></a><span data-ttu-id="ac6c8-309">下にスクロール</span><span class="sxs-lookup"><span data-stu-id="ac6c8-309">Scroll down</span></span>

<span data-ttu-id="ac6c8-310">画面を下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-310">This scrolls the screen down.</span></span>

<span data-ttu-id="ac6c8-311">**コマンド名:** `scrollDown`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-311">**Command name:** `scrollDown`</span></span>

<span data-ttu-id="ac6c8-312">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="ac6c8-312">**Default binding:**</span></span>

```json
{ "command": "scrollDown", "keys": "ctrl+shift+down" }
```

### <a name="scroll-up-a-whole-page"></a><span data-ttu-id="ac6c8-313">ページ全体を上にスクロール</span><span class="sxs-lookup"><span data-stu-id="ac6c8-313">Scroll up a whole page</span></span>

<span data-ttu-id="ac6c8-314">ページ全体 (ウィンドウの高さ) で画面を上にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-314">This scrolls the screen up by a whole page, which is the height of the window.</span></span>

<span data-ttu-id="ac6c8-315">**コマンド名:** `scrollUpPage`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-315">**Command name:** `scrollUpPage`</span></span>

<span data-ttu-id="ac6c8-316">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="ac6c8-316">**Default binding:**</span></span>

```json
{ "command": "scrollUpPage", "keys": "ctrl+shift+pgup" }
```

### <a name="scroll-down-a-whole-page"></a><span data-ttu-id="ac6c8-317">ページ全体を下にスクロール</span><span class="sxs-lookup"><span data-stu-id="ac6c8-317">Scroll down a whole page</span></span>

<span data-ttu-id="ac6c8-318">ページ全体 (ウィンドウの高さ) で画面を下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-318">This scrolls the screen down by a whole page, which is the height of the window.</span></span>

<span data-ttu-id="ac6c8-319">**コマンド名:** `scrollDownPage`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-319">**Command name:** `scrollDownPage`</span></span>

<span data-ttu-id="ac6c8-320">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="ac6c8-320">**Default binding:**</span></span>

```json
{ "command": "scrollDownPage", "keys": "ctrl+shift+pgdn" }
```

<br />

___

## <a name="visual-adjustment-commands"></a><span data-ttu-id="ac6c8-321">ビジュアル調整コマンド</span><span class="sxs-lookup"><span data-stu-id="ac6c8-321">Visual adjustment commands</span></span>

### <a name="adjust-font-size"></a><span data-ttu-id="ac6c8-322">フォント サイズの調整</span><span class="sxs-lookup"><span data-stu-id="ac6c8-322">Adjust font size</span></span>

<span data-ttu-id="ac6c8-323">指定したポイントの大きさによってテキストのサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-323">This changes the text size by a specified point amount.</span></span>

<span data-ttu-id="ac6c8-324">**コマンド名:** `adjustFontSize`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-324">**Command name:** `adjustFontSize`</span></span>

<span data-ttu-id="ac6c8-325">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="ac6c8-325">**Default bindings:**</span></span>

```json
{ "command": { "action": "adjustFontSize", "delta": 1 }, "keys": "ctrl+=" },
{ "command": { "action": "adjustFontSize", "delta": -1 }, "keys": "ctrl+-" }
```

#### <a name="actions"></a><span data-ttu-id="ac6c8-326">操作</span><span class="sxs-lookup"><span data-stu-id="ac6c8-326">Actions</span></span>

| <span data-ttu-id="ac6c8-327">名前</span><span class="sxs-lookup"><span data-stu-id="ac6c8-327">Name</span></span> | <span data-ttu-id="ac6c8-328">必要</span><span class="sxs-lookup"><span data-stu-id="ac6c8-328">Necessity</span></span> | <span data-ttu-id="ac6c8-329">受け入れられる型</span><span class="sxs-lookup"><span data-stu-id="ac6c8-329">Accepts</span></span> | <span data-ttu-id="ac6c8-330">説明</span><span class="sxs-lookup"><span data-stu-id="ac6c8-330">Description</span></span> |
| ---- | --------- | ------- | ----------- |
| `delta` | <span data-ttu-id="ac6c8-331">必須</span><span class="sxs-lookup"><span data-stu-id="ac6c8-331">Required</span></span> | <span data-ttu-id="ac6c8-332">整数</span><span class="sxs-lookup"><span data-stu-id="ac6c8-332">Integer</span></span> | <span data-ttu-id="ac6c8-333">コマンド呼び出しごとのサイズ変更の量。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-333">Amount of size change per command invocation.</span></span> |

### <a name="reset-font-size"></a><span data-ttu-id="ac6c8-334">フォント サイズのリセット</span><span class="sxs-lookup"><span data-stu-id="ac6c8-334">Reset font size</span></span>

<span data-ttu-id="ac6c8-335">テキスト サイズが既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-335">This resets the text size to the default value.</span></span>

<span data-ttu-id="ac6c8-336">**コマンド名:** `resetFontSize`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-336">**Command name:** `resetFontSize`</span></span>

<span data-ttu-id="ac6c8-337">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="ac6c8-337">**Default binding:**</span></span>

```json
{ "command": "resetFontSize", "keys": "ctrl+0" }
```

<br />

___

## <a name="unbind-keys"></a><span data-ttu-id="ac6c8-338">キーのバインド解除</span><span class="sxs-lookup"><span data-stu-id="ac6c8-338">Unbind keys</span></span>

<span data-ttu-id="ac6c8-339">関連付けられたキーが任意のコマンドからバインド解除されます。</span><span class="sxs-lookup"><span data-stu-id="ac6c8-339">This unbinds the associated keys from any command.</span></span>

<span data-ttu-id="ac6c8-340">**コマンド名:** `unbound`</span><span class="sxs-lookup"><span data-stu-id="ac6c8-340">**Command name:** `unbound`</span></span>
