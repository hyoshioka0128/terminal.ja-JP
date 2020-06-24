---
title: Windows ターミナルのキー バインド
description: Windows ターミナルのカスタム キー バインドを作成する方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 06/18/2020
ms.topic: how-to
ms.service: terminal
ms.localizationpriority: high
ms.openlocfilehash: 2716e3bfbbc290eb3f2bdce58d0de5c12ee3225d
ms.sourcegitcommit: 91a802863cd0730d2e364377ffe44f819a66ff2a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84994291"
---
# <a name="custom-key-bindings-in-windows-terminal"></a><span data-ttu-id="7800c-103">Windows ターミナルのカスタム キー バインド</span><span class="sxs-lookup"><span data-stu-id="7800c-103">Custom key bindings in Windows Terminal</span></span>

<span data-ttu-id="7800c-104">Windows ターミナル内にカスタム キー バインド (キーボード ショートカット) を作成し、キーボードを使用してターミナルとの対話方法を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="7800c-104">You can create custom key bindings (keyboard shortcuts) inside Windows Terminal that give you control of how you interact with the terminal using your keyboard.</span></span>

## <a name="key-binding-formats"></a><span data-ttu-id="7800c-105">キー バインドの形式</span><span class="sxs-lookup"><span data-stu-id="7800c-105">Key binding formats</span></span>

<span data-ttu-id="7800c-106">キー バインドは、次の形式で構成できます。</span><span class="sxs-lookup"><span data-stu-id="7800c-106">Key bindings can be structured in the following formats:</span></span>

### <a name="commands-without-arguments"></a><span data-ttu-id="7800c-107">引数なしのコマンド</span><span class="sxs-lookup"><span data-stu-id="7800c-107">Commands without arguments</span></span>

```json
{ "command": "commandName", "keys": "modifiers+key" }
```

<span data-ttu-id="7800c-108">たとえば、この既定の設定では、ショートカット キー <kbd>alt+f4</kbd> を使用してターミナル ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7800c-108">For example, this default setting uses the shortcut key <kbd>alt+f4</kbd> to close the terminal window:</span></span>

```json
{ "command": "closeWindow", "keys": "alt+f4" }
```

### <a name="commands-with-arguments"></a><span data-ttu-id="7800c-109">引数を指定したコマンド</span><span class="sxs-lookup"><span data-stu-id="7800c-109">Commands with arguments</span></span>

```json
{ "command": { "action": "commandName", "argument": "value" }, "keys": "modifiers+key" }
```

<span data-ttu-id="7800c-110">たとえば、この既定の設定では、ショートカット キー <kbd>Ctrl + Shift + 1</kbd> を使用すると、ドロップダウン メニューにどのプロファイルが最初に表示されるかに基づいて、ターミナルで新しいタブが開きます (通常は PowerShell プロファイルを開きます)。</span><span class="sxs-lookup"><span data-stu-id="7800c-110">For example, this default setting uses the shortcut key <kbd>ctrl+shift+1</kbd> to open a new tab in the terminal based on whichever profile is listed first in your dropdown menu (typically this will open the PowerShell profile):</span></span>

```json
{ "command": { "action": "newTab", "index": 0 }, "keys": "ctrl+shift+1" }
```

<br />

___

## <a name="key-binding-properties"></a><span data-ttu-id="7800c-111">キー バインドのプロパティ</span><span class="sxs-lookup"><span data-stu-id="7800c-111">Key binding properties</span></span>

<span data-ttu-id="7800c-112">キー バインドは、次のプロパティを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="7800c-112">Key bindings can be constructed using the following properties.</span></span>

### <a name="command"></a><span data-ttu-id="7800c-113">コマンド</span><span class="sxs-lookup"><span data-stu-id="7800c-113">Command</span></span>

<span data-ttu-id="7800c-114">これは、関連付けられたキーが押されたときに実行されるコマンドです。</span><span class="sxs-lookup"><span data-stu-id="7800c-114">This is the command executed when the associated keys are pressed.</span></span>

<span data-ttu-id="7800c-115">**プロパティ名:** `command`</span><span class="sxs-lookup"><span data-stu-id="7800c-115">**Property name:** `command`</span></span>

<span data-ttu-id="7800c-116">**必須かどうか:** 必須</span><span class="sxs-lookup"><span data-stu-id="7800c-116">**Necessity:** Required</span></span>

<span data-ttu-id="7800c-117">**受け入れ可能:** String</span><span class="sxs-lookup"><span data-stu-id="7800c-117">**Accepts:** String</span></span>

### <a name="keys"></a><span data-ttu-id="7800c-118">キー</span><span class="sxs-lookup"><span data-stu-id="7800c-118">Keys</span></span>

<span data-ttu-id="7800c-119">コマンドを呼び出すために使用するキーの組み合わせを定義します。</span><span class="sxs-lookup"><span data-stu-id="7800c-119">This defines the key combinations used to call the command.</span></span> <span data-ttu-id="7800c-120">1 つのキーで任意の数の修飾子を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="7800c-120">Keys can have any number of modifiers with one key.</span></span> <span data-ttu-id="7800c-121">受け入れられる修飾子とキーを[以下](#accepted-modifiers-and-keys)に一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7800c-121">Accepted modifiers and keys are listed [below](#accepted-modifiers-and-keys).</span></span>

<span data-ttu-id="7800c-122">**プロパティ名:** `keys`</span><span class="sxs-lookup"><span data-stu-id="7800c-122">**Property name:** `keys`</span></span>

<span data-ttu-id="7800c-123">**必須かどうか:** 必須</span><span class="sxs-lookup"><span data-stu-id="7800c-123">**Necessity:** Required</span></span>

<span data-ttu-id="7800c-124">**受け入れ可能:** String または array[string]</span><span class="sxs-lookup"><span data-stu-id="7800c-124">**Accepts:** String or array[string]</span></span>

### <a name="action"></a><span data-ttu-id="7800c-125">操作</span><span class="sxs-lookup"><span data-stu-id="7800c-125">Action</span></span>

<span data-ttu-id="7800c-126">これにより、特定のコマンドに機能が追加されます。</span><span class="sxs-lookup"><span data-stu-id="7800c-126">This adds additional functionality to certain commands.</span></span>

<span data-ttu-id="7800c-127">**プロパティ名:** `action`</span><span class="sxs-lookup"><span data-stu-id="7800c-127">**Property name:** `action`</span></span>

<span data-ttu-id="7800c-128">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="7800c-128">**Necessity:** Optional</span></span>

<span data-ttu-id="7800c-129">**受け入れ可能:** String</span><span class="sxs-lookup"><span data-stu-id="7800c-129">**Accepts:** String</span></span>

<br />

___

## <a name="accepted-modifiers-and-keys"></a><span data-ttu-id="7800c-130">受け入れられる修飾子とキー</span><span class="sxs-lookup"><span data-stu-id="7800c-130">Accepted modifiers and keys</span></span>

### <a name="modifiers"></a><span data-ttu-id="7800c-131">修飾子</span><span class="sxs-lookup"><span data-stu-id="7800c-131">Modifiers</span></span>

<span data-ttu-id="7800c-132">`ctrl+`、`shift+`、`alt+`</span><span class="sxs-lookup"><span data-stu-id="7800c-132">`ctrl+`, `shift+`, `alt+`</span></span>

### <a name="modifier-keys"></a><span data-ttu-id="7800c-133">修飾キー</span><span class="sxs-lookup"><span data-stu-id="7800c-133">Modifier keys</span></span>

| <span data-ttu-id="7800c-134">種類</span><span class="sxs-lookup"><span data-stu-id="7800c-134">Type</span></span> | <span data-ttu-id="7800c-135">キー</span><span class="sxs-lookup"><span data-stu-id="7800c-135">Keys</span></span> |
| ---- | ---- |
| <span data-ttu-id="7800c-136">関数と英数字キー</span><span class="sxs-lookup"><span data-stu-id="7800c-136">Function and alphanumeric keys</span></span> | <span data-ttu-id="7800c-137">`f1-f24`、`a-z`、`0-9`</span><span class="sxs-lookup"><span data-stu-id="7800c-137">`f1-f24`, `a-z`, `0-9`</span></span> |
| <span data-ttu-id="7800c-138">記号</span><span class="sxs-lookup"><span data-stu-id="7800c-138">Symbols</span></span> | <span data-ttu-id="7800c-139">``` ` ```、`-`、`=`、`[`、`]`、`\`、`;`、`'`、`,`、`.`、`/`</span><span class="sxs-lookup"><span data-stu-id="7800c-139">``` ` ```, `-`, `=`, `[`, `]`, `\`, `;`, `'`, `,`, `.`, `/`</span></span> |
| <span data-ttu-id="7800c-140">方向キー</span><span class="sxs-lookup"><span data-stu-id="7800c-140">Arrow keys</span></span> | <span data-ttu-id="7800c-141">`down`、`left`、`right`、`up`、`pagedown`、`pageup`、`pgdn`、`pgup`、`end`、`home`、`plus`</span><span class="sxs-lookup"><span data-stu-id="7800c-141">`down`, `left`, `right`, `up`, `pagedown`, `pageup`, `pgdn`, `pgup`, `end`, `home`, `plus`</span></span> |
| <span data-ttu-id="7800c-142">アクション キー</span><span class="sxs-lookup"><span data-stu-id="7800c-142">Action keys</span></span> | <span data-ttu-id="7800c-143">`tab`、`enter`、`esc`、`escape`、`space`、`backspace`、`delete`、`insert`</span><span class="sxs-lookup"><span data-stu-id="7800c-143">`tab`, `enter`, `esc`, `escape`, `space`, `backspace`, `delete`, `insert`</span></span> |
| <span data-ttu-id="7800c-144">テンキーのキー</span><span class="sxs-lookup"><span data-stu-id="7800c-144">Numpad keys</span></span> | <span data-ttu-id="7800c-145">`numpad_0-numpad_9`、`numpad0-numpad9`、`numpad_add`、`numpad_plus`、`numpad_decimal`、`numpad_period`、`numpad_divide`、`numpad_minus`、`numpad_subtract`、`numpad_multiply`</span><span class="sxs-lookup"><span data-stu-id="7800c-145">`numpad_0-numpad_9`, `numpad0-numpad9`, `numpad_add`, `numpad_plus`, `numpad_decimal`, `numpad_period`, `numpad_divide`, `numpad_minus`, `numpad_subtract`, `numpad_multiply`</span></span> |

<br />

___

## <a name="application-level-commands"></a><span data-ttu-id="7800c-146">アプリケーションレベルのコマンド</span><span class="sxs-lookup"><span data-stu-id="7800c-146">Application-level commands</span></span>

### <a name="close-window"></a><span data-ttu-id="7800c-147">ウィンドウを閉じる</span><span class="sxs-lookup"><span data-stu-id="7800c-147">Close window</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="7800c-148">現在のウィンドウとその中のすべてのタブが閉じられます。</span><span class="sxs-lookup"><span data-stu-id="7800c-148">This closes the current window and all tabs within it.</span></span> <span data-ttu-id="7800c-149">`confirmCloseAllTabs` が `true` に設定されている場合は、すべてのタブを閉じることを確認する確認ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7800c-149">If `confirmCloseAllTabs` is set to `true`, a confirmation dialog will appear to ensure you'd like to close all your tabs.</span></span> <span data-ttu-id="7800c-150">この設定の詳細については、[グローバル設定に関するページ](./global-settings.md#hide-close-all-tabs-popup)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7800c-150">More information on this setting can be found on the [Global settings page](./global-settings.md#hide-close-all-tabs-popup).</span></span>

<span data-ttu-id="7800c-151">**コマンド名:** `closeWindow`</span><span class="sxs-lookup"><span data-stu-id="7800c-151">**Command name:** `closeWindow`</span></span>

<span data-ttu-id="7800c-152">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="7800c-152">**Default binding:**</span></span>

```json
{ "command": "closeWindow", "keys": "alt+f4" }
```

:::column-end:::
:::column span="":::
![Windows ターミナルのすべてのタブを閉じるの確認](./../images/confirm-close-all-tabs.png)

:::column-end:::
:::row-end:::

### <a name="find"></a><span data-ttu-id="7800c-154">［検索］</span><span class="sxs-lookup"><span data-stu-id="7800c-154">Find</span></span>

<span data-ttu-id="7800c-155">[検索] ダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="7800c-155">This opens the search dialog box.</span></span> <span data-ttu-id="7800c-156">検索の詳細については、[検索に関するページ](./../search.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7800c-156">More information on search can be found on the [Search page](./../search.md).</span></span>

<span data-ttu-id="7800c-157">**コマンド名:** `find`</span><span class="sxs-lookup"><span data-stu-id="7800c-157">**Command name:** `find`</span></span>

<span data-ttu-id="7800c-158">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="7800c-158">**Default binding:**</span></span>

```json
{ "command": "find", "keys": "ctrl+shift+f" }
```

### <a name="open-the-dropdown"></a><span data-ttu-id="7800c-159">ドロップダウンを開く</span><span class="sxs-lookup"><span data-stu-id="7800c-159">Open the dropdown</span></span>

<span data-ttu-id="7800c-160">ドロップダウン メニューが開きます。</span><span class="sxs-lookup"><span data-stu-id="7800c-160">This opens the dropdown menu.</span></span>

<span data-ttu-id="7800c-161">**コマンド名:** `openNewTabDropdown`</span><span class="sxs-lookup"><span data-stu-id="7800c-161">**Command name:** `openNewTabDropdown`</span></span>

<span data-ttu-id="7800c-162">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="7800c-162">**Default binding:**</span></span>

```json
{ "command": "openNewTabDropdown", "keys": "ctrl+shift+space" }
```

### <a name="open-settings-files"></a><span data-ttu-id="7800c-163">設定ファイルを開く</span><span class="sxs-lookup"><span data-stu-id="7800c-163">Open settings files</span></span>

<span data-ttu-id="7800c-164">これにより、既定の設定ファイルまたはカスタム設定ファイルのいずれかが開きます。</span><span class="sxs-lookup"><span data-stu-id="7800c-164">This opens either the default or custom settings files.</span></span> <span data-ttu-id="7800c-165">`target` フィールドがない場合は、settings.json ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="7800c-165">Without the `target` field, this will open the settings.json file.</span></span>

<span data-ttu-id="7800c-166">**コマンド名:** `openSettings`</span><span class="sxs-lookup"><span data-stu-id="7800c-166">**Command name:** `openSettings`</span></span>

<span data-ttu-id="7800c-167">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="7800c-167">**Default binding:**</span></span>

```json
{ "command": "openSettings", "keys": "ctrl+," },
{ "command": { "action": "openSettings", "target": "defaultsFile" }, "keys": "ctrl+alt+," },
```

#### <a name="actions"></a><span data-ttu-id="7800c-168">操作</span><span class="sxs-lookup"><span data-stu-id="7800c-168">Actions</span></span>

| <span data-ttu-id="7800c-169">名前</span><span class="sxs-lookup"><span data-stu-id="7800c-169">Name</span></span> | <span data-ttu-id="7800c-170">必要</span><span class="sxs-lookup"><span data-stu-id="7800c-170">Necessity</span></span> | <span data-ttu-id="7800c-171">受け入れられる型</span><span class="sxs-lookup"><span data-stu-id="7800c-171">Accepts</span></span> | <span data-ttu-id="7800c-172">説明</span><span class="sxs-lookup"><span data-stu-id="7800c-172">Description</span></span> |
| ---- | --------- | ------- | ----------- |
| `target` | <span data-ttu-id="7800c-173">オプション</span><span class="sxs-lookup"><span data-stu-id="7800c-173">Optional</span></span> | <span data-ttu-id="7800c-174">`"settingsFile"`、`"defaultsFile"`、`"allFiles"`</span><span class="sxs-lookup"><span data-stu-id="7800c-174">`"settingsFile"`, `"defaultsFile"`, `"allFiles"`</span></span> | <span data-ttu-id="7800c-175">開く設定ファイルです。</span><span class="sxs-lookup"><span data-stu-id="7800c-175">The settings file to open.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="7800c-176">`target` フィールドは、[Windows ターミナル プレビュー](https://aka.ms/terminal-preview/)でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="7800c-176">The `target` field is only available in [Windows Terminal Preview](https://aka.ms/terminal-preview/).</span></span>

### <a name="toggle-full-screen"></a><span data-ttu-id="7800c-177">全画面表示の切り替え</span><span class="sxs-lookup"><span data-stu-id="7800c-177">Toggle full screen</span></span>

<span data-ttu-id="7800c-178">全画面表示と既定のウィンドウ サイズを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="7800c-178">This allows you to switch between full screen and default window sizes.</span></span>

<span data-ttu-id="7800c-179">**コマンド名:** `toggleFullscreen`</span><span class="sxs-lookup"><span data-stu-id="7800c-179">**Command name:** `toggleFullscreen`</span></span>

<span data-ttu-id="7800c-180">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="7800c-180">**Default bindings:**</span></span>

```json
{ "command": "toggleFullscreen", "keys": "alt+enter" },
{ "command": "toggleFullscreen", "keys": "f11" }
```

<br />

___

## <a name="tab-management-commands"></a><span data-ttu-id="7800c-181">タブ管理コマンド</span><span class="sxs-lookup"><span data-stu-id="7800c-181">Tab management commands</span></span>

### <a name="close-tab"></a><span data-ttu-id="7800c-182">タブを閉じる</span><span class="sxs-lookup"><span data-stu-id="7800c-182">Close tab</span></span>

<span data-ttu-id="7800c-183">現在のタブが閉じます。</span><span class="sxs-lookup"><span data-stu-id="7800c-183">This closes the current tab.</span></span>

<span data-ttu-id="7800c-184">**コマンド名:** `closeTab`</span><span class="sxs-lookup"><span data-stu-id="7800c-184">**Command name:** `closeTab`</span></span>

### <a name="duplicate-tab"></a><span data-ttu-id="7800c-185">タブを複製</span><span class="sxs-lookup"><span data-stu-id="7800c-185">Duplicate tab</span></span>

<span data-ttu-id="7800c-186">現在のタブのコピーが作成されて開きます。</span><span class="sxs-lookup"><span data-stu-id="7800c-186">This makes a copy of the current tab and opens it.</span></span>

<span data-ttu-id="7800c-187">**コマンド名:** `duplicateTab`</span><span class="sxs-lookup"><span data-stu-id="7800c-187">**Command name:** `duplicateTab`</span></span>

<span data-ttu-id="7800c-188">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="7800c-188">**Default binding:**</span></span>

```json
{ "command": "duplicateTab", "keys": "ctrl+shift+d" }
```

### <a name="new-tab"></a><span data-ttu-id="7800c-189">新しいタブ</span><span class="sxs-lookup"><span data-stu-id="7800c-189">New tab</span></span>

<span data-ttu-id="7800c-190">新しいタブが作成されます。引数を指定しないと、既定のプロファイルが新しいタブで開きます。アクションが指定されていない場合は、既定のプロファイルの同等の設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7800c-190">This creates a new tab. Without any arguments, this will open the default profile in a new tab. If an action is not specified, the default profile's equivalent setting will be used.</span></span>

<span data-ttu-id="7800c-191">**コマンド名:** `newTab`</span><span class="sxs-lookup"><span data-stu-id="7800c-191">**Command name:** `newTab`</span></span>

<span data-ttu-id="7800c-192">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="7800c-192">**Default bindings:**</span></span>

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

#### <a name="actions"></a><span data-ttu-id="7800c-193">操作</span><span class="sxs-lookup"><span data-stu-id="7800c-193">Actions</span></span>

| <span data-ttu-id="7800c-194">名前</span><span class="sxs-lookup"><span data-stu-id="7800c-194">Name</span></span> | <span data-ttu-id="7800c-195">必要</span><span class="sxs-lookup"><span data-stu-id="7800c-195">Necessity</span></span> | <span data-ttu-id="7800c-196">受け入れられる型</span><span class="sxs-lookup"><span data-stu-id="7800c-196">Accepts</span></span> | <span data-ttu-id="7800c-197">説明</span><span class="sxs-lookup"><span data-stu-id="7800c-197">Description</span></span> |
| ---- | --------- | ------- | ----------- |
| `commandLine` | <span data-ttu-id="7800c-198">オプション</span><span class="sxs-lookup"><span data-stu-id="7800c-198">Optional</span></span> | <span data-ttu-id="7800c-199">実行可能ファイル名を表す文字列</span><span class="sxs-lookup"><span data-stu-id="7800c-199">Executable file name as a string</span></span> | <span data-ttu-id="7800c-200">実行可能ファイルがタブ内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="7800c-200">Executable run within the tab.</span></span> |
| `startingDirectory` | <span data-ttu-id="7800c-201">オプション</span><span class="sxs-lookup"><span data-stu-id="7800c-201">Optional</span></span> | <span data-ttu-id="7800c-202">フォルダーの場所を表す文字列</span><span class="sxs-lookup"><span data-stu-id="7800c-202">Folder location as a string</span></span> | <span data-ttu-id="7800c-203">タブが開かれるディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="7800c-203">Directory in which the tab will open.</span></span> |
| `tabTitle` | <span data-ttu-id="7800c-204">オプション</span><span class="sxs-lookup"><span data-stu-id="7800c-204">Optional</span></span> | <span data-ttu-id="7800c-205">String</span><span class="sxs-lookup"><span data-stu-id="7800c-205">String</span></span> | <span data-ttu-id="7800c-206">新しいタブのタイトル。</span><span class="sxs-lookup"><span data-stu-id="7800c-206">Title of the new tab.</span></span> |
| `index` | <span data-ttu-id="7800c-207">オプション</span><span class="sxs-lookup"><span data-stu-id="7800c-207">Optional</span></span> | <span data-ttu-id="7800c-208">整数</span><span class="sxs-lookup"><span data-stu-id="7800c-208">Integer</span></span> | <span data-ttu-id="7800c-209">ドロップダウンでの位置 (0 から開始) に基づいて開かれるプロファイル。</span><span class="sxs-lookup"><span data-stu-id="7800c-209">Profile that will open based on its position in the dropdown (starting at 0).</span></span> |
| `profile` | <span data-ttu-id="7800c-210">オプション</span><span class="sxs-lookup"><span data-stu-id="7800c-210">Optional</span></span> | <span data-ttu-id="7800c-211">プロファイルの名前または GUID を表す文字列</span><span class="sxs-lookup"><span data-stu-id="7800c-211">Profile's name or GUID as a string</span></span> | <span data-ttu-id="7800c-212">GUID または名前に基づいて開かれるプロファイル。</span><span class="sxs-lookup"><span data-stu-id="7800c-212">Profile that will open based on its GUID or name.</span></span> |

### <a name="open-next-tab"></a><span data-ttu-id="7800c-213">次のタブを開く</span><span class="sxs-lookup"><span data-stu-id="7800c-213">Open next tab</span></span>

<span data-ttu-id="7800c-214">現在のタブの右側にタブが開きます。</span><span class="sxs-lookup"><span data-stu-id="7800c-214">This opens the tab to the right of the current one.</span></span>

<span data-ttu-id="7800c-215">**コマンド名:** `nextTab`</span><span class="sxs-lookup"><span data-stu-id="7800c-215">**Command name:** `nextTab`</span></span>

<span data-ttu-id="7800c-216">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="7800c-216">**Default binding:**</span></span>

```json
{ "command": "nextTab", "keys": "ctrl+tab" }
```

### <a name="open-previous-tab"></a><span data-ttu-id="7800c-217">前のタブを開く</span><span class="sxs-lookup"><span data-stu-id="7800c-217">Open previous tab</span></span>

<span data-ttu-id="7800c-218">現在のタブの左側にタブが開きます。</span><span class="sxs-lookup"><span data-stu-id="7800c-218">This opens the tab to the left of the current one.</span></span>

<span data-ttu-id="7800c-219">**コマンド名:** `prevTab`</span><span class="sxs-lookup"><span data-stu-id="7800c-219">**Command name:** `prevTab`</span></span>

<span data-ttu-id="7800c-220">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="7800c-220">**Default binding:**</span></span>

```json
{ "command": "prevTab", "keys": "ctrl+shift+tab" }
```

### <a name="open-a-specific-tab"></a><span data-ttu-id="7800c-221">特定のタブを開く</span><span class="sxs-lookup"><span data-stu-id="7800c-221">Open a specific tab</span></span>

<span data-ttu-id="7800c-222">インデックスに応じて特定のタブが開きます。</span><span class="sxs-lookup"><span data-stu-id="7800c-222">This opens a specific tab depending on the index.</span></span>

<span data-ttu-id="7800c-223">**コマンド名:** `switchToTab`</span><span class="sxs-lookup"><span data-stu-id="7800c-223">**Command name:** `switchToTab`</span></span>

<span data-ttu-id="7800c-224">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="7800c-224">**Default bindings:**</span></span>

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

#### <a name="actions"></a><span data-ttu-id="7800c-225">操作</span><span class="sxs-lookup"><span data-stu-id="7800c-225">Actions</span></span>

| <span data-ttu-id="7800c-226">名前</span><span class="sxs-lookup"><span data-stu-id="7800c-226">Name</span></span> | <span data-ttu-id="7800c-227">必要</span><span class="sxs-lookup"><span data-stu-id="7800c-227">Necessity</span></span> | <span data-ttu-id="7800c-228">受け入れられる型</span><span class="sxs-lookup"><span data-stu-id="7800c-228">Accepts</span></span> | <span data-ttu-id="7800c-229">説明</span><span class="sxs-lookup"><span data-stu-id="7800c-229">Description</span></span> |
| ---- | --------- | ------- | ----------- |
| `index` | <span data-ttu-id="7800c-230">必須</span><span class="sxs-lookup"><span data-stu-id="7800c-230">Required</span></span> | <span data-ttu-id="7800c-231">整数</span><span class="sxs-lookup"><span data-stu-id="7800c-231">Integer</span></span> | <span data-ttu-id="7800c-232">タブ バー内の位置 (0 から開始) に基づいて開かれるタブ。</span><span class="sxs-lookup"><span data-stu-id="7800c-232">Tab that will open based on its position in the tab bar (starting at 0).</span></span> |

<br />

___

## <a name="pane-management-commands"></a><span data-ttu-id="7800c-233">ペイン管理コマンド</span><span class="sxs-lookup"><span data-stu-id="7800c-233">Pane management commands</span></span>

### <a name="close-pane"></a><span data-ttu-id="7800c-234">ペインを閉じる</span><span class="sxs-lookup"><span data-stu-id="7800c-234">Close pane</span></span>

<span data-ttu-id="7800c-235">アクティブなペインを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7800c-235">This closes the active pane.</span></span> <span data-ttu-id="7800c-236">分割ペインがない場合は、現在のタブが閉じられます。開いているタブが 1 つだけの場合は、ウィンドウが閉じられます。</span><span class="sxs-lookup"><span data-stu-id="7800c-236">If there aren't any split panes, this will close the current tab. If there is only one tab open, this will close the window.</span></span>

<span data-ttu-id="7800c-237">**コマンド名:** `closePane`</span><span class="sxs-lookup"><span data-stu-id="7800c-237">**Command name:** `closePane`</span></span>

<span data-ttu-id="7800c-238">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="7800c-238">**Default binding:**</span></span>

```json
{ "command": "closePane", "keys": "ctrl+shift+w" }
```

### <a name="move-pane-focus"></a><span data-ttu-id="7800c-239">ペイン フォーカスの移動</span><span class="sxs-lookup"><span data-stu-id="7800c-239">Move pane focus</span></span>

<span data-ttu-id="7800c-240">方向に応じて、別のペインにフォーカスが移動します。</span><span class="sxs-lookup"><span data-stu-id="7800c-240">This changes focus to a different pane depending on the direction.</span></span>

<span data-ttu-id="7800c-241">**コマンド名:** `moveFocus`</span><span class="sxs-lookup"><span data-stu-id="7800c-241">**Command name:** `moveFocus`</span></span>

<span data-ttu-id="7800c-242">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="7800c-242">**Default bindings:**</span></span>

```json
{ "command": { "action": "moveFocus", "direction": "down" }, "keys": "alt+down" },
{ "command": { "action": "moveFocus", "direction": "left" }, "keys": "alt+left" },
{ "command": { "action": "moveFocus", "direction": "right" }, "keys": "alt+right" },
{ "command": { "action": "moveFocus", "direction": "up" }, "keys": "alt+up" }
```

#### <a name="actions"></a><span data-ttu-id="7800c-243">操作</span><span class="sxs-lookup"><span data-stu-id="7800c-243">Actions</span></span>

| <span data-ttu-id="7800c-244">名前</span><span class="sxs-lookup"><span data-stu-id="7800c-244">Name</span></span> | <span data-ttu-id="7800c-245">必要</span><span class="sxs-lookup"><span data-stu-id="7800c-245">Necessity</span></span> | <span data-ttu-id="7800c-246">受け入れられる型</span><span class="sxs-lookup"><span data-stu-id="7800c-246">Accepts</span></span> | <span data-ttu-id="7800c-247">説明</span><span class="sxs-lookup"><span data-stu-id="7800c-247">Description</span></span> |
| ---- | --------- | ------- | ----------- |
| `direction` | <span data-ttu-id="7800c-248">必須</span><span class="sxs-lookup"><span data-stu-id="7800c-248">Required</span></span> | <span data-ttu-id="7800c-249">`"left"`、`"right"`、`"up"`、`"down"`</span><span class="sxs-lookup"><span data-stu-id="7800c-249">`"left"`, `"right"`, `"up"`, `"down"`</span></span> | <span data-ttu-id="7800c-250">フォーカスを移動する方向。</span><span class="sxs-lookup"><span data-stu-id="7800c-250">Direction in which the focus will move.</span></span> |

### <a name="resize-a-pane"></a><span data-ttu-id="7800c-251">ペインのサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="7800c-251">Resize a pane</span></span>

<span data-ttu-id="7800c-252">アクティブなペインのサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="7800c-252">This changes the size of the active pane.</span></span>

<span data-ttu-id="7800c-253">**コマンド名:** `resizePane`</span><span class="sxs-lookup"><span data-stu-id="7800c-253">**Command name:** `resizePane`</span></span>

<span data-ttu-id="7800c-254">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="7800c-254">**Default bindings:**</span></span>

```json
{ "command": { "action": "resizePane", "direction": "down" }, "keys": "alt+shift+down" },
{ "command": { "action": "resizePane", "direction": "left" }, "keys": "alt+shift+left" },
{ "command": { "action": "resizePane", "direction": "right" }, "keys": "alt+shift+right" },
{ "command": { "action": "resizePane", "direction": "up" }, "keys": "alt+shift+up" }
```

#### <a name="actions"></a><span data-ttu-id="7800c-255">操作</span><span class="sxs-lookup"><span data-stu-id="7800c-255">Actions</span></span>

| <span data-ttu-id="7800c-256">名前</span><span class="sxs-lookup"><span data-stu-id="7800c-256">Name</span></span> | <span data-ttu-id="7800c-257">必要</span><span class="sxs-lookup"><span data-stu-id="7800c-257">Necessity</span></span> | <span data-ttu-id="7800c-258">受け入れられる型</span><span class="sxs-lookup"><span data-stu-id="7800c-258">Accepts</span></span> | <span data-ttu-id="7800c-259">説明</span><span class="sxs-lookup"><span data-stu-id="7800c-259">Description</span></span> |
| ---- | --------- | ------- | ----------- |
| `direction` | <span data-ttu-id="7800c-260">必須</span><span class="sxs-lookup"><span data-stu-id="7800c-260">Required</span></span> | <span data-ttu-id="7800c-261">`"left"`、`"right"`、`"up"`、`"down"`</span><span class="sxs-lookup"><span data-stu-id="7800c-261">`"left"`, `"right"`, `"up"`, `"down"`</span></span> | <span data-ttu-id="7800c-262">ペインのサイズを変更する方向。</span><span class="sxs-lookup"><span data-stu-id="7800c-262">Direction in which the pane will be resized.</span></span> |

### <a name="split-a-pane"></a><span data-ttu-id="7800c-263">ペインの分割</span><span class="sxs-lookup"><span data-stu-id="7800c-263">Split a pane</span></span>

<span data-ttu-id="7800c-264">アクティブなペインのサイズが半分になり、別のペインが開きます。</span><span class="sxs-lookup"><span data-stu-id="7800c-264">This halves the size of the active pane and opens another.</span></span> <span data-ttu-id="7800c-265">引数を指定しないと、既定のプロファイルが新しいペインで開かれます。</span><span class="sxs-lookup"><span data-stu-id="7800c-265">Without any arguments, this will open the default profile in the new pane.</span></span> <span data-ttu-id="7800c-266">アクションが指定されていない場合は、既定のプロファイルの同等の設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7800c-266">If an action is not specified, the default profile's equivalent setting will be used.</span></span>

<span data-ttu-id="7800c-267">**コマンド名:** `splitPane`</span><span class="sxs-lookup"><span data-stu-id="7800c-267">**Command name:** `splitPane`</span></span>

<span data-ttu-id="7800c-268">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="7800c-268">**Default bindings:**</span></span>

```json
// In settings.json
{ "command": { "action": "splitPane", "split": "auto", "splitMode": "duplicate" }, "keys": "alt+shift+d" },

// In defaults.json
{ "command": { "action": "splitPane", "split": "horizontal"}, "keys": "alt+shift+-" },
{ "command": { "action": "splitPane", "split": "vertical"}, "keys": "alt+shift+plus" }
```

#### <a name="actions"></a><span data-ttu-id="7800c-269">操作</span><span class="sxs-lookup"><span data-stu-id="7800c-269">Actions</span></span>

| <span data-ttu-id="7800c-270">名前</span><span class="sxs-lookup"><span data-stu-id="7800c-270">Name</span></span> | <span data-ttu-id="7800c-271">必要</span><span class="sxs-lookup"><span data-stu-id="7800c-271">Necessity</span></span> | <span data-ttu-id="7800c-272">受け入れられる型</span><span class="sxs-lookup"><span data-stu-id="7800c-272">Accepts</span></span> | <span data-ttu-id="7800c-273">説明</span><span class="sxs-lookup"><span data-stu-id="7800c-273">Description</span></span> |
| ---- | --------- | ------- | ----------- |
| `split` | <span data-ttu-id="7800c-274">必須</span><span class="sxs-lookup"><span data-stu-id="7800c-274">Required</span></span> | <span data-ttu-id="7800c-275">`"vertical"`、`"horizontal"`、`"auto"`</span><span class="sxs-lookup"><span data-stu-id="7800c-275">`"vertical"`, `"horizontal"`, `"auto"`</span></span> | <span data-ttu-id="7800c-276">ペインの分割方法。</span><span class="sxs-lookup"><span data-stu-id="7800c-276">How the pane will split.</span></span> <span data-ttu-id="7800c-277">`"auto"` は、最も多くの領域を提供する方向に分割します。</span><span class="sxs-lookup"><span data-stu-id="7800c-277">`"auto"` will split in the direction that provides the most surface area.</span></span> |
| `commandLine` | <span data-ttu-id="7800c-278">オプション</span><span class="sxs-lookup"><span data-stu-id="7800c-278">Optional</span></span> | <span data-ttu-id="7800c-279">実行可能ファイル名を表す文字列</span><span class="sxs-lookup"><span data-stu-id="7800c-279">Executable file name as a string</span></span> | <span data-ttu-id="7800c-280">実行可能ファイルがペイン内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="7800c-280">Executable run within the pane.</span></span> |
| `startingDirectory` | <span data-ttu-id="7800c-281">オプション</span><span class="sxs-lookup"><span data-stu-id="7800c-281">Optional</span></span> | <span data-ttu-id="7800c-282">フォルダーの場所を表す文字列</span><span class="sxs-lookup"><span data-stu-id="7800c-282">Folder location as a string</span></span> | <span data-ttu-id="7800c-283">ペインが開かれるディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="7800c-283">Directory in which the pane will open.</span></span> |
| `tabTitle` | <span data-ttu-id="7800c-284">オプション</span><span class="sxs-lookup"><span data-stu-id="7800c-284">Optional</span></span> | <span data-ttu-id="7800c-285">String</span><span class="sxs-lookup"><span data-stu-id="7800c-285">String</span></span> | <span data-ttu-id="7800c-286">新しいペインにフォーカスがあるときのタブのタイトル。</span><span class="sxs-lookup"><span data-stu-id="7800c-286">Title of the tab when the new pane is focused.</span></span> |
| `index` | <span data-ttu-id="7800c-287">オプション</span><span class="sxs-lookup"><span data-stu-id="7800c-287">Optional</span></span> | <span data-ttu-id="7800c-288">整数</span><span class="sxs-lookup"><span data-stu-id="7800c-288">Integer</span></span> | <span data-ttu-id="7800c-289">ドロップダウンでの位置 (0 から開始) に基づいて開かれるプロファイル。</span><span class="sxs-lookup"><span data-stu-id="7800c-289">Profile that will open based on its position in the dropdown (starting at 0).</span></span> |
| `profile` | <span data-ttu-id="7800c-290">オプション</span><span class="sxs-lookup"><span data-stu-id="7800c-290">Optional</span></span> | <span data-ttu-id="7800c-291">プロファイルの名前または GUID を表す文字列</span><span class="sxs-lookup"><span data-stu-id="7800c-291">Profile's name or GUID as a string</span></span> | <span data-ttu-id="7800c-292">GUID または名前に基づいて開かれるプロファイル。</span><span class="sxs-lookup"><span data-stu-id="7800c-292">Profile that will open based on its GUID or name.</span></span> |
| `splitMode` | <span data-ttu-id="7800c-293">オプション</span><span class="sxs-lookup"><span data-stu-id="7800c-293">Optional</span></span> | `"duplicate"` | <span data-ttu-id="7800c-294">ペインの分割方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="7800c-294">Controls how the pane splits.</span></span> <span data-ttu-id="7800c-295">フォーカスがあるペインのプロファイルを新しいペインに複製する、`"duplicate"` のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="7800c-295">Only accepts `"duplicate"`, which will duplicate the focused pane's profile into a new pane.</span></span> |

<br />

___

## <a name="clipboard-integration-commands"></a><span data-ttu-id="7800c-296">クリップボードの統合コマンド</span><span class="sxs-lookup"><span data-stu-id="7800c-296">Clipboard integration commands</span></span>

### <a name="copy"></a><span data-ttu-id="7800c-297">コピー</span><span class="sxs-lookup"><span data-stu-id="7800c-297">Copy</span></span>

<span data-ttu-id="7800c-298">選択したターミナル コンテンツがクリップボードにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="7800c-298">This copies the selected terminal content to your clipboard.</span></span>

<span data-ttu-id="7800c-299">**コマンド名:** `copy`</span><span class="sxs-lookup"><span data-stu-id="7800c-299">**Command name:** `copy`</span></span>

<span data-ttu-id="7800c-300">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="7800c-300">**Default bindings:**</span></span>

```json
// In settings.json
{ "command": { "action": "copy", "singleLine": false }, "keys": "ctrl+c" },

// In defaults.json
{ "command": { "action": "copy", "singleLine": false }, "keys": "ctrl+shift+c" },
{ "command": { "action": "copy", "singleLine": false }, "keys": "ctrl+insert" }
```

#### <a name="clipboard-actions"></a><span data-ttu-id="7800c-301">クリップボードのアクセス</span><span class="sxs-lookup"><span data-stu-id="7800c-301">Clipboard Actions</span></span>

| <span data-ttu-id="7800c-302">名前</span><span class="sxs-lookup"><span data-stu-id="7800c-302">Name</span></span> | <span data-ttu-id="7800c-303">必要</span><span class="sxs-lookup"><span data-stu-id="7800c-303">Necessity</span></span> | <span data-ttu-id="7800c-304">受け入れられる型</span><span class="sxs-lookup"><span data-stu-id="7800c-304">Accepts</span></span> | <span data-ttu-id="7800c-305">説明</span><span class="sxs-lookup"><span data-stu-id="7800c-305">Description</span></span> |
| ---- | --------- | ------- | ----------- |
| `singleLine` | <span data-ttu-id="7800c-306">オプション</span><span class="sxs-lookup"><span data-stu-id="7800c-306">Optional</span></span> | <span data-ttu-id="7800c-307">`true`、`false`</span><span class="sxs-lookup"><span data-stu-id="7800c-307">`true`, `false`</span></span> | <span data-ttu-id="7800c-308">`true` の場合、コピーされたコンテンツは単一行としてコピーされます。</span><span class="sxs-lookup"><span data-stu-id="7800c-308">When `true`, the copied content will be copied as a single line.</span></span> <span data-ttu-id="7800c-309">`false` の場合、選択したテキストから改行が保持されます。</span><span class="sxs-lookup"><span data-stu-id="7800c-309">When `false`, newlines persist from the selected text.</span></span> |

### <a name="paste"></a><span data-ttu-id="7800c-310">貼り付け</span><span class="sxs-lookup"><span data-stu-id="7800c-310">Paste</span></span>

<span data-ttu-id="7800c-311">クリップボードにコピーされたコンテンツが挿入されます。</span><span class="sxs-lookup"><span data-stu-id="7800c-311">This inserts the content that was copied onto the clipboard.</span></span>

<span data-ttu-id="7800c-312">**コマンド名:** `paste`</span><span class="sxs-lookup"><span data-stu-id="7800c-312">**Command name:** `paste`</span></span>

<span data-ttu-id="7800c-313">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="7800c-313">**Default bindings:**</span></span>

```json
// In settings.json
{ "command": "paste", "keys": "ctrl+v" },

// In defaults.json
{ "command": "paste", "keys": "ctrl+shift+v" },
{ "command": "paste", "keys": "shift+insert" }
```

<br />

___

## <a name="scrollback-commands"></a><span data-ttu-id="7800c-314">Scrollback コマンド</span><span class="sxs-lookup"><span data-stu-id="7800c-314">Scrollback commands</span></span>

### <a name="scroll-up"></a><span data-ttu-id="7800c-315">上にスクロール</span><span class="sxs-lookup"><span data-stu-id="7800c-315">Scroll up</span></span>

<span data-ttu-id="7800c-316">画面を上にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="7800c-316">This scrolls the screen up.</span></span>

<span data-ttu-id="7800c-317">**コマンド名:** `scrollUp`</span><span class="sxs-lookup"><span data-stu-id="7800c-317">**Command name:** `scrollUp`</span></span>

<span data-ttu-id="7800c-318">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="7800c-318">**Default binding:**</span></span>

```json
{ "command": "scrollUp", "keys": "ctrl+shift+up" }
```

### <a name="scroll-down"></a><span data-ttu-id="7800c-319">下にスクロール</span><span class="sxs-lookup"><span data-stu-id="7800c-319">Scroll down</span></span>

<span data-ttu-id="7800c-320">画面を下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="7800c-320">This scrolls the screen down.</span></span>

<span data-ttu-id="7800c-321">**コマンド名:** `scrollDown`</span><span class="sxs-lookup"><span data-stu-id="7800c-321">**Command name:** `scrollDown`</span></span>

<span data-ttu-id="7800c-322">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="7800c-322">**Default binding:**</span></span>

```json
{ "command": "scrollDown", "keys": "ctrl+shift+down" }
```

### <a name="scroll-up-a-whole-page"></a><span data-ttu-id="7800c-323">ページ全体を上にスクロール</span><span class="sxs-lookup"><span data-stu-id="7800c-323">Scroll up a whole page</span></span>

<span data-ttu-id="7800c-324">ページ全体 (ウィンドウの高さ) で画面を上にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="7800c-324">This scrolls the screen up by a whole page, which is the height of the window.</span></span>

<span data-ttu-id="7800c-325">**コマンド名:** `scrollUpPage`</span><span class="sxs-lookup"><span data-stu-id="7800c-325">**Command name:** `scrollUpPage`</span></span>

<span data-ttu-id="7800c-326">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="7800c-326">**Default binding:**</span></span>

```json
{ "command": "scrollUpPage", "keys": "ctrl+shift+pgup" }
```

### <a name="scroll-down-a-whole-page"></a><span data-ttu-id="7800c-327">ページ全体を下にスクロール</span><span class="sxs-lookup"><span data-stu-id="7800c-327">Scroll down a whole page</span></span>

<span data-ttu-id="7800c-328">ページ全体 (ウィンドウの高さ) で画面を下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="7800c-328">This scrolls the screen down by a whole page, which is the height of the window.</span></span>

<span data-ttu-id="7800c-329">**コマンド名:** `scrollDownPage`</span><span class="sxs-lookup"><span data-stu-id="7800c-329">**Command name:** `scrollDownPage`</span></span>

<span data-ttu-id="7800c-330">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="7800c-330">**Default binding:**</span></span>

```json
{ "command": "scrollDownPage", "keys": "ctrl+shift+pgdn" }
```

<br />

___

## <a name="visual-adjustment-commands"></a><span data-ttu-id="7800c-331">ビジュアル調整コマンド</span><span class="sxs-lookup"><span data-stu-id="7800c-331">Visual adjustment commands</span></span>

### <a name="adjust-font-size"></a><span data-ttu-id="7800c-332">フォント サイズの調整</span><span class="sxs-lookup"><span data-stu-id="7800c-332">Adjust font size</span></span>

<span data-ttu-id="7800c-333">指定したポイントの大きさによってテキストのサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="7800c-333">This changes the text size by a specified point amount.</span></span>

<span data-ttu-id="7800c-334">**コマンド名:** `adjustFontSize`</span><span class="sxs-lookup"><span data-stu-id="7800c-334">**Command name:** `adjustFontSize`</span></span>

<span data-ttu-id="7800c-335">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="7800c-335">**Default bindings:**</span></span>

```json
{ "command": { "action": "adjustFontSize", "delta": 1 }, "keys": "ctrl+=" },
{ "command": { "action": "adjustFontSize", "delta": -1 }, "keys": "ctrl+-" }
```

#### <a name="actions"></a><span data-ttu-id="7800c-336">操作</span><span class="sxs-lookup"><span data-stu-id="7800c-336">Actions</span></span>

| <span data-ttu-id="7800c-337">名前</span><span class="sxs-lookup"><span data-stu-id="7800c-337">Name</span></span> | <span data-ttu-id="7800c-338">必要</span><span class="sxs-lookup"><span data-stu-id="7800c-338">Necessity</span></span> | <span data-ttu-id="7800c-339">受け入れられる型</span><span class="sxs-lookup"><span data-stu-id="7800c-339">Accepts</span></span> | <span data-ttu-id="7800c-340">説明</span><span class="sxs-lookup"><span data-stu-id="7800c-340">Description</span></span> |
| ---- | --------- | ------- | ----------- |
| `delta` | <span data-ttu-id="7800c-341">必須</span><span class="sxs-lookup"><span data-stu-id="7800c-341">Required</span></span> | <span data-ttu-id="7800c-342">整数</span><span class="sxs-lookup"><span data-stu-id="7800c-342">Integer</span></span> | <span data-ttu-id="7800c-343">コマンド呼び出しごとのサイズ変更の量。</span><span class="sxs-lookup"><span data-stu-id="7800c-343">Amount of size change per command invocation.</span></span> |

### <a name="reset-font-size"></a><span data-ttu-id="7800c-344">フォント サイズのリセット</span><span class="sxs-lookup"><span data-stu-id="7800c-344">Reset font size</span></span>

<span data-ttu-id="7800c-345">テキスト サイズが既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="7800c-345">This resets the text size to the default value.</span></span>

<span data-ttu-id="7800c-346">**コマンド名:** `resetFontSize`</span><span class="sxs-lookup"><span data-stu-id="7800c-346">**Command name:** `resetFontSize`</span></span>

<span data-ttu-id="7800c-347">**既定のバインド:**</span><span class="sxs-lookup"><span data-stu-id="7800c-347">**Default binding:**</span></span>

```json
{ "command": "resetFontSize", "keys": "ctrl+0" }
```

<br />

___

## <a name="unbind-keys"></a><span data-ttu-id="7800c-348">キーのバインド解除</span><span class="sxs-lookup"><span data-stu-id="7800c-348">Unbind keys</span></span>

<span data-ttu-id="7800c-349">関連付けられたキーが任意のコマンドからバインド解除されます。</span><span class="sxs-lookup"><span data-stu-id="7800c-349">This unbinds the associated keys from any command.</span></span>

<span data-ttu-id="7800c-350">**コマンド名:** `unbound`</span><span class="sxs-lookup"><span data-stu-id="7800c-350">**Command name:** `unbound`</span></span>
