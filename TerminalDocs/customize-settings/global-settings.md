---
title: Windows ターミナルのグローバル設定
description: Windows ターミナル内でグローバル設定をカスタマイズする方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: how-to
ms.service: terminal
ms.localizationpriority: high
ms.openlocfilehash: 3cbe4b2b99f8115ff4eeaab5f525de393d7e5eb1
ms.sourcegitcommit: bb5b7fd7db4b81e0d44e060989dc16b6775c802a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83415957"
---
# <a name="global-settings-in-the-windows-terminal"></a><span data-ttu-id="f3784-103">Windows ターミナルでのグローバル設定</span><span class="sxs-lookup"><span data-stu-id="f3784-103">Global settings in the Windows Terminal</span></span>

<span data-ttu-id="f3784-104">以下に示すプロパティは、プロファイルの設定に関係なく、ターミナル ウィンドウ全体に影響します。</span><span class="sxs-lookup"><span data-stu-id="f3784-104">The properties listed below affect the entire terminal window, regardless of the profile settings.</span></span> <span data-ttu-id="f3784-105">これらは、settings.json ファイルのルートに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3784-105">These should be placed at the root of your settings.json file.</span></span>

## <a name="default-profile"></a><span data-ttu-id="f3784-106">Default profile</span><span class="sxs-lookup"><span data-stu-id="f3784-106">Default profile</span></span>

<span data-ttu-id="f3784-107"><kbd>Ctrl + Shift + T</kbd> キーを押したとき、`newTab` に割り当てられているキー バインドを押したとき、プロファイルを指定せずに `wt new-tab` を実行したとき、または [+] アイコンをクリックしたときに開かれる、既定のプロファイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="f3784-107">Set the default profile that opens by typing <kbd>ctrl+shift+t</kbd>, typing the key binding assigned to `newTab`, running `wt new-tab` without specifying a profile, or clicking the '+' icon.</span></span>

<span data-ttu-id="f3784-108">**プロパティ名:** `defaultProfile`</span><span class="sxs-lookup"><span data-stu-id="f3784-108">**Property name:** `defaultProfile`</span></span>

<span data-ttu-id="f3784-109">**必須かどうか:** 必須</span><span class="sxs-lookup"><span data-stu-id="f3784-109">**Necessity:** Required</span></span>

<span data-ttu-id="f3784-110">**値:** 文字列としての GUID</span><span class="sxs-lookup"><span data-stu-id="f3784-110">**Accepts:** GUID as a string</span></span>

<span data-ttu-id="f3784-111">**既定値:** PowerShell の GUID</span><span class="sxs-lookup"><span data-stu-id="f3784-111">**Default value:** PowerShell's GUID</span></span>

<br />

___

## <a name="disable-dynamic-profiles"></a><span data-ttu-id="f3784-112">動的プロファイルを無効にする</span><span class="sxs-lookup"><span data-stu-id="f3784-112">Disable dynamic profiles</span></span>

<span data-ttu-id="f3784-113">無効な動的プロファイル ジェネレーターを設定し、スタートアップ時にそれらのジェネレーターでプロファイルのリストにプロファイルが追加されないようにします。</span><span class="sxs-lookup"><span data-stu-id="f3784-113">This sets which dynamic profile generators are disabled, preventing them from adding their profiles to the list of profiles on startup.</span></span> <span data-ttu-id="f3784-114">動的プロファイルの詳細については、[動的プロファイルに関するページ](./../dynamic-profiles.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3784-114">For information on dynamic profiles, visit the [Dynamic profiles page](./../dynamic-profiles.md).</span></span>

<span data-ttu-id="f3784-115">**プロパティ名:** `disabledProfileSources`</span><span class="sxs-lookup"><span data-stu-id="f3784-115">**Property name:** `disabledProfileSources`</span></span>

<span data-ttu-id="f3784-116">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="f3784-116">**Necessity:** Optional</span></span>

<span data-ttu-id="f3784-117">**値:** `"Windows.Terminal.Wsl"`、`"Windows.Terminal.Azure"`、`"Windows.Terminal.PowershellCore"` (配列内)</span><span class="sxs-lookup"><span data-stu-id="f3784-117">**Accepts:** `"Windows.Terminal.Wsl"`, `"Windows.Terminal.Azure"`, and/or `"Windows.Terminal.PowershellCore"` inside an array</span></span>

<span data-ttu-id="f3784-118">**既定値:** `[]`</span><span class="sxs-lookup"><span data-stu-id="f3784-118">**Default value:** `[]`</span></span>

<br />

___

## <a name="darklight-theme"></a><span data-ttu-id="f3784-119">ダーク/ライト テーマ</span><span class="sxs-lookup"><span data-stu-id="f3784-119">Dark/Light theme</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="f3784-120">アプリケーションのテーマを設定します。</span><span class="sxs-lookup"><span data-stu-id="f3784-120">This sets the theme of the application.</span></span> <span data-ttu-id="f3784-121">`"system"` では、Windows と同じテーマが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f3784-121">`"system"` will use the same theme as Windows.</span></span>

<span data-ttu-id="f3784-122">**プロパティ名:** `theme`</span><span class="sxs-lookup"><span data-stu-id="f3784-122">**Property name:** `theme`</span></span>

<span data-ttu-id="f3784-123">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="f3784-123">**Necessity:** Optional</span></span>

<span data-ttu-id="f3784-124">**値:** `"system"`、`"dark"`、`"light"`</span><span class="sxs-lookup"><span data-stu-id="f3784-124">**Accepts:** `"system"`, `"dark"`, `"light"`</span></span>

<span data-ttu-id="f3784-125">**既定値:** `"system"`</span><span class="sxs-lookup"><span data-stu-id="f3784-125">**Default value:** `"system"`</span></span>

:::column-end:::
:::column span="":::
<span data-ttu-id="f3784-126">![Windows ターミナルのダーク テーマ](./../images/requested-themes.gif)
_構成: [PowerShell での Powerline](./../custom-terminal-gallery/powerline-in-powershell.md)_</span><span class="sxs-lookup"><span data-stu-id="f3784-126">![Windows Terminal dark theme](./../images/requested-themes.gif)
_Configuration: [Powerline in PowerShell](./../custom-terminal-gallery/powerline-in-powershell.md)_</span></span>

:::column-end:::
:::row-end:::

<br />

___

## <a name="tab-settings"></a><span data-ttu-id="f3784-127">タブの設定</span><span class="sxs-lookup"><span data-stu-id="f3784-127">Tab settings</span></span>

### <a name="always-show-tabs"></a><span data-ttu-id="f3784-128">常にタブを表示する</span><span class="sxs-lookup"><span data-stu-id="f3784-128">Always show tabs</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="f3784-129">これが `true` に設定されていると、常にタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3784-129">When this is set to `true`, tabs are always displayed.</span></span> <span data-ttu-id="f3784-130">これが `false` に設定され、`showTabsInTitlebar` が `true` に設定されていると、タブは常にタイトル バーの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3784-130">When it's set to `false` and `showTabsInTitlebar` is set to `true`, tabs are always displayed underneath the title bar.</span></span> <span data-ttu-id="f3784-131">これが `false` に設定され、`showTabsInTitlebar` が `false` に設定されていると、<kbd>Ctrl + Shift + T</kbd> キーを押すか、`newTab` に割り当てられているキー バインドを押すことによって、複数のタブが存在するようになった後でのみ、タブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3784-131">When this is set to `false` and `showTabsInTitlebar` is set to `false`, tabs only appear after more than one tab exists by typing <kbd>ctrl+shift+t</kbd> or by typing the key binding assigned to `newTab`.</span></span> <span data-ttu-id="f3784-132">この設定を変更すると、新しいターミナル インスタンスを開始する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f3784-132">Note that changing this setting will require starting a new terminal instance.</span></span>

<span data-ttu-id="f3784-133">**プロパティ名:** `alwaysShowTabs`</span><span class="sxs-lookup"><span data-stu-id="f3784-133">**Property name:** `alwaysShowTabs`</span></span>

<span data-ttu-id="f3784-134">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="f3784-134">**Necessity:** Optional</span></span>

<span data-ttu-id="f3784-135">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="f3784-135">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="f3784-136">**既定値:** `true`</span><span class="sxs-lookup"><span data-stu-id="f3784-136">**Default value:** `true`</span></span>

:::column-end:::
:::column span="":::
![Windows ターミナルでは常にタブが表示されます](./../images/always-show-tabs.gif)

:::column-end:::
:::row-end:::

### <a name="tab-width-mode"></a><span data-ttu-id="f3784-138">タブ幅モード</span><span class="sxs-lookup"><span data-stu-id="f3784-138">Tab width mode</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="f3784-139">タブの幅を設定します。</span><span class="sxs-lookup"><span data-stu-id="f3784-139">This sets the width of the tabs.</span></span> <span data-ttu-id="f3784-140">`"equal"` を指定すると、各タブの幅が同じになります。</span><span class="sxs-lookup"><span data-stu-id="f3784-140">`"equal"` makes each tab the same width.</span></span> <span data-ttu-id="f3784-141">`"titleLength"` を指定すると、各タブのサイズはタイトルの長さになります。</span><span class="sxs-lookup"><span data-stu-id="f3784-141">`"titleLength"` sizes each tab to the length of its title.</span></span>

<span data-ttu-id="f3784-142">**プロパティ名:** `tabWidthMode`</span><span class="sxs-lookup"><span data-stu-id="f3784-142">**Property name:** `tabWidthMode`</span></span>

<span data-ttu-id="f3784-143">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="f3784-143">**Necessity:** Optional</span></span>

<span data-ttu-id="f3784-144">**値:** `"equal"`、`"titleLength"`</span><span class="sxs-lookup"><span data-stu-id="f3784-144">**Accepts:** `"equal"`, `"titleLength"`</span></span>

<span data-ttu-id="f3784-145">**既定値:** `"equal"`</span><span class="sxs-lookup"><span data-stu-id="f3784-145">**Default value:** `"equal"`</span></span>

:::column-end:::
:::column span="":::
![Windows ターミナルのタブ幅モード](./../images/tab-width-mode.gif)

:::column-end:::
:::row-end:::

### <a name="hide-close-all-tabs-popup"></a><span data-ttu-id="f3784-147">すべてのタブを閉じるポップアップを非表示にする</span><span class="sxs-lookup"><span data-stu-id="f3784-147">Hide close all tabs popup</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="f3784-148">これが `true` に設定されていると、複数のタブが開かれているウィンドウを閉じるときに、確認が "_必要です_"。</span><span class="sxs-lookup"><span data-stu-id="f3784-148">When this is set to `true`, closing a window with multiple tabs open _will_ require confirmation.</span></span> <span data-ttu-id="f3784-149">これが `false` に設定されていると、複数のタブが開かれているウィンドウを閉じるときに、確認は "_必要ありません_"。</span><span class="sxs-lookup"><span data-stu-id="f3784-149">When it's set to `false`, closing a window with multiple tabs open _will not_ require confirmation.</span></span>

<span data-ttu-id="f3784-150">**プロパティ名:** `confirmCloseAllTabs`</span><span class="sxs-lookup"><span data-stu-id="f3784-150">**Property name:** `confirmCloseAllTabs`</span></span>

<span data-ttu-id="f3784-151">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="f3784-151">**Necessity:** Optional</span></span>

<span data-ttu-id="f3784-152">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="f3784-152">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="f3784-153">**既定値:** `true`</span><span class="sxs-lookup"><span data-stu-id="f3784-153">**Default value:** `true`</span></span>

:::column-end:::
:::column span="":::
![Windows ターミナルのすべてのタブを閉じるの確認](./../images/confirm-close-all-tabs.png)

:::column-end:::
:::row-end:::

<br />

___

## <a name="launch-settings"></a><span data-ttu-id="f3784-155">起動の設定</span><span class="sxs-lookup"><span data-stu-id="f3784-155">Launch settings</span></span>

### <a name="launch-maximized"></a><span data-ttu-id="f3784-156">起動時の最大化</span><span class="sxs-lookup"><span data-stu-id="f3784-156">Launch maximized</span></span>

<span data-ttu-id="f3784-157">起動時に、ターミナルを最大化して画面全体に表示するか、またはウィンドウ内に表示するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="f3784-157">This defines whether the terminal will launch as maximized to fill the entire screen or in a window.</span></span>

<span data-ttu-id="f3784-158">**プロパティ名:** `launchMode`</span><span class="sxs-lookup"><span data-stu-id="f3784-158">**Property name:** `launchMode`</span></span>

<span data-ttu-id="f3784-159">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="f3784-159">**Necessity:** Optional</span></span>

<span data-ttu-id="f3784-160">**値:** `"default"`、`"maximized"`</span><span class="sxs-lookup"><span data-stu-id="f3784-160">**Accepts:** `"default"`, `"maximized"`</span></span>

<span data-ttu-id="f3784-161">**既定値:** `"default"`</span><span class="sxs-lookup"><span data-stu-id="f3784-161">**Default value:** `"default"`</span></span>

### <a name="launch-position"></a><span data-ttu-id="f3784-162">起動時の位置</span><span class="sxs-lookup"><span data-stu-id="f3784-162">Launch position</span></span>

<span data-ttu-id="f3784-163">最初に読み込まれたときの、ウィンドウの左上隅のピクセル位置を設定します。</span><span class="sxs-lookup"><span data-stu-id="f3784-163">This sets the pixel position of the top left corner of the window upon first load.</span></span> <span data-ttu-id="f3784-164">複数のディスプレイがあるシステムでは、これらの座標はプライマリ ディスプレイの左上が基準になります。</span><span class="sxs-lookup"><span data-stu-id="f3784-164">On a system with multiple displays, these coordinates are relative to the top left of the primary display.</span></span> <span data-ttu-id="f3784-165">X 座標または Y 座標が指定されていない場合は、その値に対するシステムの既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f3784-165">If an X or Y coordinate is not provided, the terminal will use the system default for that value.</span></span> <span data-ttu-id="f3784-166">`launchMode` が `"maximized"` に設定されている場合、ウィンドウはそれらの座標によって指定されているモニターで最大化されます。</span><span class="sxs-lookup"><span data-stu-id="f3784-166">If `launchMode` is set to `"maximized"`, the window will be maximized on the monitor specified by those coordinates.</span></span>

<span data-ttu-id="f3784-167">**プロパティ名:** `initialPosition`</span><span class="sxs-lookup"><span data-stu-id="f3784-167">**Property name:** `initialPosition`</span></span>

<span data-ttu-id="f3784-168">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="f3784-168">**Necessity:** Optional</span></span>

<span data-ttu-id="f3784-169">**値:** 次の形式の文字列として表された座標: `","`、`"#,#"`、`"#,"`、`",#"`</span><span class="sxs-lookup"><span data-stu-id="f3784-169">**Accepts:** Coordinates as a string in the following formats: `","`, `"#,#"`, `"#,"`, `",#"`</span></span>

<span data-ttu-id="f3784-170">**既定値:** `","`</span><span class="sxs-lookup"><span data-stu-id="f3784-170">**Default value:** `","`</span></span>

### <a name="columns-on-first-launch"></a><span data-ttu-id="f3784-171">最初の起動時の列数</span><span class="sxs-lookup"><span data-stu-id="f3784-171">Columns on first launch</span></span>

<span data-ttu-id="f3784-172">これは、最初の読み込み時にウィンドウに表示される文字の列の数です。</span><span class="sxs-lookup"><span data-stu-id="f3784-172">This is the number of character columns displayed in the window upon first load.</span></span> <span data-ttu-id="f3784-173">`launchMode` が `"maximized"` に設定されていると、このプロパティは無視されます。</span><span class="sxs-lookup"><span data-stu-id="f3784-173">If `launchMode` is set to `"maximized"`, this property is ignored.</span></span>

<span data-ttu-id="f3784-174">**プロパティ名:** `initialCols`</span><span class="sxs-lookup"><span data-stu-id="f3784-174">**Property name:** `initialCols`</span></span>

<span data-ttu-id="f3784-175">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="f3784-175">**Necessity:** Optional</span></span>

<span data-ttu-id="f3784-176">**値:** 整数</span><span class="sxs-lookup"><span data-stu-id="f3784-176">**Accepts:** Integer</span></span>

<span data-ttu-id="f3784-177">**既定値:** `120`</span><span class="sxs-lookup"><span data-stu-id="f3784-177">**Default value:** `120`</span></span>

### <a name="rows-on-first-launch"></a><span data-ttu-id="f3784-178">最初の起動時の行数</span><span class="sxs-lookup"><span data-stu-id="f3784-178">Rows on first launch</span></span>

<span data-ttu-id="f3784-179">これは、最初の読み込み時にウィンドウに表示される行の数です。</span><span class="sxs-lookup"><span data-stu-id="f3784-179">This is the number of rows displayed in the window upon first load.</span></span> <span data-ttu-id="f3784-180">`launchMode` が `"maximized"` に設定されていると、このプロパティは無視されます。</span><span class="sxs-lookup"><span data-stu-id="f3784-180">If `launchMode` is set to `"maximized"`, this property is ignored.</span></span>

<span data-ttu-id="f3784-181">**プロパティ名:** `initialRows`</span><span class="sxs-lookup"><span data-stu-id="f3784-181">**Property name:** `initialRows`</span></span>

<span data-ttu-id="f3784-182">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="f3784-182">**Necessity:** Optional</span></span>

<span data-ttu-id="f3784-183">**値:** 整数</span><span class="sxs-lookup"><span data-stu-id="f3784-183">**Accepts:** Integer</span></span>

<span data-ttu-id="f3784-184">**既定値:** `30`</span><span class="sxs-lookup"><span data-stu-id="f3784-184">**Default value:** `30`</span></span>

<br />

___

## <a name="title-bar-settings"></a><span data-ttu-id="f3784-185">タイトル バーの設定</span><span class="sxs-lookup"><span data-stu-id="f3784-185">Title bar settings</span></span>

### <a name="showhide-the-title-bar"></a><span data-ttu-id="f3784-186">タイトル バーの表示/非表示</span><span class="sxs-lookup"><span data-stu-id="f3784-186">Show/Hide the title bar</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="f3784-187">これを `true` に設定すると、タブはタイトル バー内に移動され、タイトル バーは表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="f3784-187">When this is set to `true`, the tabs are moved into the title bar and the title bar disappears.</span></span> <span data-ttu-id="f3784-188">`false` に設定すると、タイトル バーはタブの上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3784-188">When it's set to `false`, the title bar sits above the tabs.</span></span> <span data-ttu-id="f3784-189">この設定を変更すると、新しいターミナル インスタンスを開始する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f3784-189">Note that changing this setting will require starting a new terminal instance.</span></span>

<span data-ttu-id="f3784-190">**プロパティ名:** `showTabsInTitlebar`</span><span class="sxs-lookup"><span data-stu-id="f3784-190">**Property name:** `showTabsInTitlebar`</span></span>

<span data-ttu-id="f3784-191">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="f3784-191">**Necessity:** Optional</span></span>

<span data-ttu-id="f3784-192">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="f3784-192">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="f3784-193">**既定値:** `true`</span><span class="sxs-lookup"><span data-stu-id="f3784-193">**Default value:** `true`</span></span>

:::column-end:::
:::column span="":::
![Windows ターミナルのタブをタイトル バーに表示する](./../images/show-tabs-in-title-bar.gif)

:::column-end:::
:::row-end:::

### <a name="set-the-text-in-the-title-bar"></a><span data-ttu-id="f3784-195">タイトル バーのテキストを設定する</span><span class="sxs-lookup"><span data-stu-id="f3784-195">Set the text in the title bar</span></span>

<span data-ttu-id="f3784-196">これが `true` に設定されていると、選択されているタブのタイトルがタイトル バーに表示されます。`false` に設定すると、タイトル バーには "Windows ターミナル" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3784-196">When this is set to `true`, the title bar displays the title of the selected tab. When it's set to `false`, title bar displays "Windows Terminal".</span></span> <span data-ttu-id="f3784-197">この設定を変更すると、新しいターミナル インスタンスを開始する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f3784-197">Note that changing this setting will require starting a new terminal instance.</span></span>

<span data-ttu-id="f3784-198">**プロパティ名:** `showTerminalTitleInTitlebar`</span><span class="sxs-lookup"><span data-stu-id="f3784-198">**Property name:** `showTerminalTitleInTitlebar`</span></span>

<span data-ttu-id="f3784-199">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="f3784-199">**Necessity:** Optional</span></span>

<span data-ttu-id="f3784-200">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="f3784-200">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="f3784-201">**既定値:** `true`</span><span class="sxs-lookup"><span data-stu-id="f3784-201">**Default value:** `true`</span></span>

<br />

___

## <a name="selection-settings"></a><span data-ttu-id="f3784-202">選択の設定</span><span class="sxs-lookup"><span data-stu-id="f3784-202">Selection settings</span></span>

### <a name="copy-after-selection-is-made"></a><span data-ttu-id="f3784-203">選択後にコピーする</span><span class="sxs-lookup"><span data-stu-id="f3784-203">Copy after selection is made</span></span>

<span data-ttu-id="f3784-204">これを `true` に設定すると、作成時に選択内容がすぐにクリップボードにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="f3784-204">When this is set to `true`, a selection is immediately copied to your clipboard upon creation.</span></span> <span data-ttu-id="f3784-205">この場合、マウスを右クリックすると常に貼り付けられます。</span><span class="sxs-lookup"><span data-stu-id="f3784-205">The right-click on your mouse will always paste in this case.</span></span> <span data-ttu-id="f3784-206">`false` に設定すると、選択内容が保持され、追加の操作が待機されます。</span><span class="sxs-lookup"><span data-stu-id="f3784-206">When it's set to `false`, the selection persists and awaits further action.</span></span> <span data-ttu-id="f3784-207">マウスを右クリックすると、選択内容がコピーされます。</span><span class="sxs-lookup"><span data-stu-id="f3784-207">Using your mouse to right-click will copy the selection.</span></span>

<span data-ttu-id="f3784-208">**プロパティ名:** `copyOnSelect`</span><span class="sxs-lookup"><span data-stu-id="f3784-208">**Property name:** `copyOnSelect`</span></span>

<span data-ttu-id="f3784-209">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="f3784-209">**Necessity:** Optional</span></span>

<span data-ttu-id="f3784-210">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="f3784-210">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="f3784-211">**既定値:** `false`</span><span class="sxs-lookup"><span data-stu-id="f3784-211">**Default value:** `false`</span></span>

### <a name="copy-formatting"></a><span data-ttu-id="f3784-212">書式指定をコピーする</span><span class="sxs-lookup"><span data-stu-id="f3784-212">Copy formatting</span></span>

<span data-ttu-id="f3784-213">これを `true` に設定すると、選択したテキストの色とフォントの書式もクリップボードにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="f3784-213">When this is set to `true`, the color and font formatting of selected text is also copied to your clipboard.</span></span> <span data-ttu-id="f3784-214">`false` に設定すると、プレーンテキストのみがクリップボードにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="f3784-214">When it's set to `false`, only plain text is copied to your clipboard.</span></span>

<span data-ttu-id="f3784-215">**プロパティ名:** `copyFormatting`</span><span class="sxs-lookup"><span data-stu-id="f3784-215">**Property name:** `copyFormatting`</span></span>

<span data-ttu-id="f3784-216">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="f3784-216">**Necessity:** Optional</span></span>

<span data-ttu-id="f3784-217">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="f3784-217">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="f3784-218">**既定値:** `false`</span><span class="sxs-lookup"><span data-stu-id="f3784-218">**Default value:** `false`</span></span>

### <a name="word-delimiters"></a><span data-ttu-id="f3784-219">単語の区切り記号</span><span class="sxs-lookup"><span data-stu-id="f3784-219">Word delimiters</span></span>

<span data-ttu-id="f3784-220">ダブルクリックの選択で使用される単語の区切り記号を決定します。</span><span class="sxs-lookup"><span data-stu-id="f3784-220">This determines the word delimiters used in a double-click selection.</span></span> <span data-ttu-id="f3784-221">単語の区切り記号は、2 つの単語の間の境界がどこにあるかを指定する文字です。</span><span class="sxs-lookup"><span data-stu-id="f3784-221">Word delimiters are characters that specify where the boundary is between two words.</span></span> <span data-ttu-id="f3784-222">最も一般的な例は、スペース、セミコロン、コンマ、ピリオドなどです。</span><span class="sxs-lookup"><span data-stu-id="f3784-222">The most common examples are spaces, semicolons, commas, and periods.</span></span>

<span data-ttu-id="f3784-223">**プロパティ名:** `wordDelimiters`</span><span class="sxs-lookup"><span data-stu-id="f3784-223">**Property name:** `wordDelimiters`</span></span>

<span data-ttu-id="f3784-224">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="f3784-224">**Necessity:** Optional</span></span>

<span data-ttu-id="f3784-225">**値:** 文字列としての文字</span><span class="sxs-lookup"><span data-stu-id="f3784-225">**Accepts:** Characters as a string</span></span>

<span data-ttu-id="f3784-226">**既定値:** <code>&nbsp;&#x2f;&#x5c;&#x28;&#x29;&#x22;&#x27;&#x2d;&#x3a;&#x2c;&#x2e;&#x3b;&#x3c;&#x3e;&#x7e;&#x21;&#x40;&#x23;&#x24;&#x25;&#x5e;&#x26;&#x2a;&#x7c;&#x2b;&#x3d;&#x5b;&#x5d;&#x7b;&#x7d;&#x7e;&#x3f;│</code></span><span class="sxs-lookup"><span data-stu-id="f3784-226">**Default value:** <code>&nbsp;&#x2f;&#x5c;&#x28;&#x29;&#x22;&#x27;&#x2d;&#x3a;&#x2c;&#x2e;&#x3b;&#x3c;&#x3e;&#x7e;&#x21;&#x40;&#x23;&#x24;&#x25;&#x5e;&#x26;&#x2a;&#x7c;&#x2b;&#x3d;&#x5b;&#x5d;&#x7b;&#x7d;&#x7e;&#x3f;│</code></span></span><br><span data-ttu-id="f3784-227">_(`│` は `U+2502 BOX DRAWINGS LIGHT VERTICAL` です)_</span><span class="sxs-lookup"><span data-stu-id="f3784-227">_(`│` is `U+2502 BOX DRAWINGS LIGHT VERTICAL`)_</span></span>

<br />

___

## <a name="scroll-speed"></a><span data-ttu-id="f3784-228">スクロール速度</span><span class="sxs-lookup"><span data-stu-id="f3784-228">Scroll speed</span></span>

<span data-ttu-id="f3784-229">これは、マウス ホイールで一度にスクロールする行の数です。</span><span class="sxs-lookup"><span data-stu-id="f3784-229">This is the number of rows to scroll at a time with the mouse wheel.</span></span> <span data-ttu-id="f3784-230">値がゼロまたは `"system"` でない場合は、システム設定がオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="f3784-230">This will override the system setting if the value is not zero or `"system"`.</span></span>

<span data-ttu-id="f3784-231">**プロパティ名:** `rowsToScroll`</span><span class="sxs-lookup"><span data-stu-id="f3784-231">**Property name:** `rowsToScroll`</span></span>

<span data-ttu-id="f3784-232">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="f3784-232">**Necessity:** Optional</span></span>

<span data-ttu-id="f3784-233">**値:** 整数</span><span class="sxs-lookup"><span data-stu-id="f3784-233">**Accepts:** Integer</span></span>

<span data-ttu-id="f3784-234">**既定値:** `"system"`</span><span class="sxs-lookup"><span data-stu-id="f3784-234">**Default value:** `"system"`</span></span>

<br />

___

## <a name="window-resize-behavior"></a><span data-ttu-id="f3784-235">ウィンドウ サイズ変更の動作</span><span class="sxs-lookup"><span data-stu-id="f3784-235">Window resize behavior</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="f3784-236">これを `true` に設定すると、サイズ変更時にウィンドウは最も近い文字境界にスナップされます。</span><span class="sxs-lookup"><span data-stu-id="f3784-236">When this is set to `true`, the window will snap to the nearest character boundary on resize.</span></span> <span data-ttu-id="f3784-237">`false` に設定すると、ウィンドウのサイズは "スムーズ" に変更されます。</span><span class="sxs-lookup"><span data-stu-id="f3784-237">When it's set to `false`, the window will resize "smoothly".</span></span>

<span data-ttu-id="f3784-238">**プロパティ名:** `snapToGridOnResize`</span><span class="sxs-lookup"><span data-stu-id="f3784-238">**Property name:** `snapToGridOnResize`</span></span>

<span data-ttu-id="f3784-239">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="f3784-239">**Necessity:** Optional</span></span>

<span data-ttu-id="f3784-240">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="f3784-240">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="f3784-241">**既定値:** `true`</span><span class="sxs-lookup"><span data-stu-id="f3784-241">**Default value:** `true`</span></span>

:::column-end:::
:::column span="":::
![サイズ変更時に Windows ターミナルはグリッドにスナップする](./../images/snap-to-grid-on-resize.gif)

:::column-end:::
:::row-end:::
