---
title: Windows ターミナルのグローバル設定
description: Windows ターミナル内でグローバル設定をカスタマイズする方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 06/18/2020
ms.topic: how-to
ms.service: terminal
ms.localizationpriority: high
ms.openlocfilehash: ba3197bb8b9466d37c01432b60314a7a00227898
ms.sourcegitcommit: 91a802863cd0730d2e364377ffe44f819a66ff2a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84994295"
---
# <a name="global-settings-in-windows-terminal"></a><span data-ttu-id="0151c-103">Windows ターミナルでのグローバル設定</span><span class="sxs-lookup"><span data-stu-id="0151c-103">Global settings in Windows Terminal</span></span>

<span data-ttu-id="0151c-104">以下に示すプロパティは、プロファイルの設定に関係なく、ターミナル ウィンドウ全体に影響します。</span><span class="sxs-lookup"><span data-stu-id="0151c-104">The properties listed below affect the entire terminal window, regardless of the profile settings.</span></span> <span data-ttu-id="0151c-105">これらは、settings.json ファイルのルートに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0151c-105">These should be placed at the root of your settings.json file.</span></span>

## <a name="default-profile"></a><span data-ttu-id="0151c-106">Default profile</span><span class="sxs-lookup"><span data-stu-id="0151c-106">Default profile</span></span>

<span data-ttu-id="0151c-107"><kbd>Ctrl + Shift + T</kbd> キーを押したとき、`newTab` に割り当てられているキー バインドを押したとき、プロファイルを指定せずに `wt new-tab` を実行したとき、または [+] アイコンをクリックしたときに開かれる、既定のプロファイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="0151c-107">Set the default profile that opens by typing <kbd>ctrl+shift+t</kbd>, typing the key binding assigned to `newTab`, running `wt new-tab` without specifying a profile, or clicking the '+' icon.</span></span>

<span data-ttu-id="0151c-108">**プロパティ名:** `defaultProfile`</span><span class="sxs-lookup"><span data-stu-id="0151c-108">**Property name:** `defaultProfile`</span></span>

<span data-ttu-id="0151c-109">**必須かどうか:** 必須</span><span class="sxs-lookup"><span data-stu-id="0151c-109">**Necessity:** Required</span></span>

<span data-ttu-id="0151c-110">**値:** GUID またはプロファイル名を表す文字列</span><span class="sxs-lookup"><span data-stu-id="0151c-110">**Accepts:** GUID or profile name as a string</span></span>

<span data-ttu-id="0151c-111">**既定値:** PowerShell の GUID</span><span class="sxs-lookup"><span data-stu-id="0151c-111">**Default value:** PowerShell's GUID</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0151c-112">`defaultProfile` のプロファイル名は、[Windows ターミナル プレビュー](https://aka.ms/terminal-preview/)でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0151c-112">Using the profile name for `defaultProfile` is only available in [Windows Terminal Preview](https://aka.ms/terminal-preview/).</span></span>

<br />

___

## <a name="disable-dynamic-profiles"></a><span data-ttu-id="0151c-113">動的プロファイルを無効にする</span><span class="sxs-lookup"><span data-stu-id="0151c-113">Disable dynamic profiles</span></span>

<span data-ttu-id="0151c-114">無効な動的プロファイル ジェネレーターを設定し、スタートアップ時にそれらのジェネレーターでプロファイルのリストにプロファイルが追加されないようにします。</span><span class="sxs-lookup"><span data-stu-id="0151c-114">This sets which dynamic profile generators are disabled, preventing them from adding their profiles to the list of profiles on startup.</span></span> <span data-ttu-id="0151c-115">動的プロファイルの詳細については、[動的プロファイルに関するページ](./../dynamic-profiles.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0151c-115">For information on dynamic profiles, visit the [Dynamic profiles page](./../dynamic-profiles.md).</span></span>

<span data-ttu-id="0151c-116">**プロパティ名:** `disabledProfileSources`</span><span class="sxs-lookup"><span data-stu-id="0151c-116">**Property name:** `disabledProfileSources`</span></span>

<span data-ttu-id="0151c-117">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="0151c-117">**Necessity:** Optional</span></span>

<span data-ttu-id="0151c-118">**値:** `"Windows.Terminal.Wsl"`、`"Windows.Terminal.Azure"`、`"Windows.Terminal.PowershellCore"` (配列内)</span><span class="sxs-lookup"><span data-stu-id="0151c-118">**Accepts:** `"Windows.Terminal.Wsl"`, `"Windows.Terminal.Azure"`, and/or `"Windows.Terminal.PowershellCore"` inside an array</span></span>

<span data-ttu-id="0151c-119">**既定値:** `[]`</span><span class="sxs-lookup"><span data-stu-id="0151c-119">**Default value:** `[]`</span></span>

<br />

___

## <a name="darklight-theme"></a><span data-ttu-id="0151c-120">ダーク/ライト テーマ</span><span class="sxs-lookup"><span data-stu-id="0151c-120">Dark/Light theme</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="0151c-121">アプリケーションのテーマを設定します。</span><span class="sxs-lookup"><span data-stu-id="0151c-121">This sets the theme of the application.</span></span> <span data-ttu-id="0151c-122">`"system"` では、Windows と同じテーマが使用されます。</span><span class="sxs-lookup"><span data-stu-id="0151c-122">`"system"` will use the same theme as Windows.</span></span>

<span data-ttu-id="0151c-123">**プロパティ名:** `theme`</span><span class="sxs-lookup"><span data-stu-id="0151c-123">**Property name:** `theme`</span></span>

<span data-ttu-id="0151c-124">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="0151c-124">**Necessity:** Optional</span></span>

<span data-ttu-id="0151c-125">**値:** `"system"`、`"dark"`、`"light"`</span><span class="sxs-lookup"><span data-stu-id="0151c-125">**Accepts:** `"system"`, `"dark"`, `"light"`</span></span>

<span data-ttu-id="0151c-126">**既定値:** `"system"`</span><span class="sxs-lookup"><span data-stu-id="0151c-126">**Default value:** `"system"`</span></span>

:::column-end:::
:::column span="":::
<span data-ttu-id="0151c-127">![Windows ターミナルのダーク テーマ](./../images/requested-themes.gif)
_構成: [PowerShell での Powerline](./../custom-terminal-gallery/powerline-in-powershell.md)_</span><span class="sxs-lookup"><span data-stu-id="0151c-127">![Windows Terminal dark theme](./../images/requested-themes.gif)
_Configuration: [Powerline in PowerShell](./../custom-terminal-gallery/powerline-in-powershell.md)_</span></span>

:::column-end:::
:::row-end:::

<br />

___

## <a name="tab-settings"></a><span data-ttu-id="0151c-128">タブの設定</span><span class="sxs-lookup"><span data-stu-id="0151c-128">Tab settings</span></span>

### <a name="always-show-tabs"></a><span data-ttu-id="0151c-129">常にタブを表示する</span><span class="sxs-lookup"><span data-stu-id="0151c-129">Always show tabs</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="0151c-130">これが `true` に設定されていると、常にタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0151c-130">When this is set to `true`, tabs are always displayed.</span></span> <span data-ttu-id="0151c-131">これが `false` に設定され、`showTabsInTitlebar` が `true` に設定されていると、タブは常にタイトル バーの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0151c-131">When it's set to `false` and `showTabsInTitlebar` is set to `true`, tabs are always displayed underneath the title bar.</span></span> <span data-ttu-id="0151c-132">これが `false` に設定され、`showTabsInTitlebar` が `false` に設定されていると、<kbd>Ctrl + Shift + T</kbd> キーを押すか、`newTab` に割り当てられているキー バインドを押すことによって、複数のタブが存在するようになった後でのみ、タブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0151c-132">When this is set to `false` and `showTabsInTitlebar` is set to `false`, tabs only appear after more than one tab exists by typing <kbd>ctrl+shift+t</kbd> or by typing the key binding assigned to `newTab`.</span></span> <span data-ttu-id="0151c-133">この設定を変更すると、新しいターミナル インスタンスを開始する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0151c-133">Note that changing this setting will require starting a new terminal instance.</span></span>

<span data-ttu-id="0151c-134">**プロパティ名:** `alwaysShowTabs`</span><span class="sxs-lookup"><span data-stu-id="0151c-134">**Property name:** `alwaysShowTabs`</span></span>

<span data-ttu-id="0151c-135">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="0151c-135">**Necessity:** Optional</span></span>

<span data-ttu-id="0151c-136">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="0151c-136">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="0151c-137">**既定値:** `true`</span><span class="sxs-lookup"><span data-stu-id="0151c-137">**Default value:** `true`</span></span>

:::column-end:::
:::column span="":::
![Windows ターミナルでは常にタブが表示されます](./../images/always-show-tabs.gif)

:::column-end:::
:::row-end:::

### <a name="tab-width-mode"></a><span data-ttu-id="0151c-139">タブ幅モード</span><span class="sxs-lookup"><span data-stu-id="0151c-139">Tab width mode</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="0151c-140">タブの幅を設定します。</span><span class="sxs-lookup"><span data-stu-id="0151c-140">This sets the width of the tabs.</span></span> <span data-ttu-id="0151c-141">`"equal"` を指定すると、各タブの幅が同じになります。</span><span class="sxs-lookup"><span data-stu-id="0151c-141">`"equal"` makes each tab the same width.</span></span> <span data-ttu-id="0151c-142">`"titleLength"` を指定すると、各タブのサイズはタイトルの長さになります。</span><span class="sxs-lookup"><span data-stu-id="0151c-142">`"titleLength"` sizes each tab to the length of its title.</span></span> <span data-ttu-id="0151c-143">`"compact"` は、すべての非アクティブなタブをアイコンの幅に縮小し、アクティブなタブのフル タイトルを表示するための領域を増やします。</span><span class="sxs-lookup"><span data-stu-id="0151c-143">`"compact"` will shrink every inactive tab to the width of the icon, leaving the active tab more space to display its full title.</span></span>

<span data-ttu-id="0151c-144">**プロパティ名:** `tabWidthMode`</span><span class="sxs-lookup"><span data-stu-id="0151c-144">**Property name:** `tabWidthMode`</span></span>

<span data-ttu-id="0151c-145">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="0151c-145">**Necessity:** Optional</span></span>

<span data-ttu-id="0151c-146">**値:** `"equal"`、`"titleLength"`、`"compact"`</span><span class="sxs-lookup"><span data-stu-id="0151c-146">**Accepts:** `"equal"`, `"titleLength"`, `"compact"`</span></span>

<span data-ttu-id="0151c-147">**既定値:** `"equal"`</span><span class="sxs-lookup"><span data-stu-id="0151c-147">**Default value:** `"equal"`</span></span>

:::column-end:::
:::column span="":::
![Windows ターミナルのタブ幅モード](./../images/tab-width-mode.gif)

:::column-end:::
:::row-end:::

> [!IMPORTANT]
> <span data-ttu-id="0151c-149">`"compact"` の設定は、[Windows ターミナル プレビュー](https://aka.ms/terminal-preview/)でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0151c-149">The `"compact"` setting is only available in [Windows Terminal Preview](https://aka.ms/terminal-preview/).</span></span>

### <a name="hide-close-all-tabs-popup"></a><span data-ttu-id="0151c-150">すべてのタブを閉じるポップアップを非表示にする</span><span class="sxs-lookup"><span data-stu-id="0151c-150">Hide close all tabs popup</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="0151c-151">これが `true` に設定されていると、複数のタブが開かれているウィンドウを閉じるときに、確認が "_必要です_"。</span><span class="sxs-lookup"><span data-stu-id="0151c-151">When this is set to `true`, closing a window with multiple tabs open _will_ require confirmation.</span></span> <span data-ttu-id="0151c-152">これが `false` に設定されていると、複数のタブが開かれているウィンドウを閉じるときに、確認は "_必要ありません_"。</span><span class="sxs-lookup"><span data-stu-id="0151c-152">When it's set to `false`, closing a window with multiple tabs open _will not_ require confirmation.</span></span>

<span data-ttu-id="0151c-153">**プロパティ名:** `confirmCloseAllTabs`</span><span class="sxs-lookup"><span data-stu-id="0151c-153">**Property name:** `confirmCloseAllTabs`</span></span>

<span data-ttu-id="0151c-154">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="0151c-154">**Necessity:** Optional</span></span>

<span data-ttu-id="0151c-155">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="0151c-155">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="0151c-156">**既定値:** `true`</span><span class="sxs-lookup"><span data-stu-id="0151c-156">**Default value:** `true`</span></span>

:::column-end:::
:::column span="":::
![Windows ターミナルのすべてのタブを閉じるの確認](./../images/confirm-close-all-tabs.png)

:::column-end:::
:::row-end:::

<br />

___

## <a name="launch-settings"></a><span data-ttu-id="0151c-158">起動の設定</span><span class="sxs-lookup"><span data-stu-id="0151c-158">Launch settings</span></span>

### <a name="launch-on-startup-preview"></a><span data-ttu-id="0151c-159">スタートアップ時に起動 ([プレビュー](https://aka.ms/terminal-preview/))</span><span class="sxs-lookup"><span data-stu-id="0151c-159">Launch on startup ([Preview](https://aka.ms/terminal-preview/))</span></span>

<span data-ttu-id="0151c-160">`true` に設定すると、スタートアップ時に Windows ターミナルを起動できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0151c-160">When set to `true`, this enables the launch of Windows Terminal at startup.</span></span> <span data-ttu-id="0151c-161">これを `false` に設定すると、スタートアップ タスクのエントリが無効になります。</span><span class="sxs-lookup"><span data-stu-id="0151c-161">Setting this to `false` will disable the startup task entry.</span></span> <span data-ttu-id="0151c-162">注: Windows ターミナル スタートアップ タスクのエントリが組織のポリシーまたはユーザーの操作によって無効にされている場合、この設定は効果がありません。</span><span class="sxs-lookup"><span data-stu-id="0151c-162">Note: if the Windows Terminal startup task entry is disabled either by org policy or by user action this setting will have no effect.</span></span>

<span data-ttu-id="0151c-163">**プロパティ名:** `startOnUserLogin`</span><span class="sxs-lookup"><span data-stu-id="0151c-163">**Property name:** `startOnUserLogin`</span></span>

<span data-ttu-id="0151c-164">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="0151c-164">**Necessity:** Optional</span></span>

<span data-ttu-id="0151c-165">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="0151c-165">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="0151c-166">**既定値:** `false`</span><span class="sxs-lookup"><span data-stu-id="0151c-166">**Default value:** `false`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0151c-167">この機能は、[Windows ターミナル プレビュー](https://aka.ms/terminal-preview/)でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0151c-167">This feature is only available in [Windows Terminal Preview](https://aka.ms/terminal-preview/).</span></span>

### <a name="launch-size"></a><span data-ttu-id="0151c-168">起動サイズ</span><span class="sxs-lookup"><span data-stu-id="0151c-168">Launch size</span></span>

<span data-ttu-id="0151c-169">起動時に、ターミナルを最大化して全画面で表示するか、ウィンドウ内に表示するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="0151c-169">This defines whether the terminal will launch as maximized, fullscreen, or in a window.</span></span>

<span data-ttu-id="0151c-170">**プロパティ名:** `launchMode`</span><span class="sxs-lookup"><span data-stu-id="0151c-170">**Property name:** `launchMode`</span></span>

<span data-ttu-id="0151c-171">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="0151c-171">**Necessity:** Optional</span></span>

<span data-ttu-id="0151c-172">**値:** `"default"`、`"maximized"`、`"fullscreen"`</span><span class="sxs-lookup"><span data-stu-id="0151c-172">**Accepts:** `"default"`, `"maximized"`, `"fullscreen"`</span></span>

<span data-ttu-id="0151c-173">**既定値:** `"default"`</span><span class="sxs-lookup"><span data-stu-id="0151c-173">**Default value:** `"default"`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0151c-174">`"fullscreen"` の設定は、[Windows ターミナル プレビュー](https://aka.ms/terminal-preview/)でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0151c-174">The `"fullscreen"` setting is only available in [Windows Terminal Preview](https://aka.ms/terminal-preview/).</span></span>

### <a name="launch-position"></a><span data-ttu-id="0151c-175">起動時の位置</span><span class="sxs-lookup"><span data-stu-id="0151c-175">Launch position</span></span>

<span data-ttu-id="0151c-176">最初に読み込まれたときの、ウィンドウの左上隅のピクセル位置を設定します。</span><span class="sxs-lookup"><span data-stu-id="0151c-176">This sets the pixel position of the top left corner of the window upon first load.</span></span> <span data-ttu-id="0151c-177">複数のディスプレイがあるシステムでは、これらの座標はプライマリ ディスプレイの左上が基準になります。</span><span class="sxs-lookup"><span data-stu-id="0151c-177">On a system with multiple displays, these coordinates are relative to the top left of the primary display.</span></span> <span data-ttu-id="0151c-178">X 座標または Y 座標が指定されていない場合は、その値に対するシステムの既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0151c-178">If an X or Y coordinate is not provided, the terminal will use the system default for that value.</span></span> <span data-ttu-id="0151c-179">`launchMode` が `"maximized"` に設定されている場合、ウィンドウはそれらの座標によって指定されているモニターで最大化されます。</span><span class="sxs-lookup"><span data-stu-id="0151c-179">If `launchMode` is set to `"maximized"`, the window will be maximized on the monitor specified by those coordinates.</span></span>

<span data-ttu-id="0151c-180">**プロパティ名:** `initialPosition`</span><span class="sxs-lookup"><span data-stu-id="0151c-180">**Property name:** `initialPosition`</span></span>

<span data-ttu-id="0151c-181">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="0151c-181">**Necessity:** Optional</span></span>

<span data-ttu-id="0151c-182">**値:** 次の形式の文字列として表された座標: `","`、`"#,#"`、`"#,"`、`",#"`</span><span class="sxs-lookup"><span data-stu-id="0151c-182">**Accepts:** Coordinates as a string in the following formats: `","`, `"#,#"`, `"#,"`, `",#"`</span></span>

<span data-ttu-id="0151c-183">**既定値:** `","`</span><span class="sxs-lookup"><span data-stu-id="0151c-183">**Default value:** `","`</span></span>

### <a name="columns-on-first-launch"></a><span data-ttu-id="0151c-184">最初の起動時の列数</span><span class="sxs-lookup"><span data-stu-id="0151c-184">Columns on first launch</span></span>

<span data-ttu-id="0151c-185">これは、最初の読み込み時にウィンドウに表示される文字の列の数です。</span><span class="sxs-lookup"><span data-stu-id="0151c-185">This is the number of character columns displayed in the window upon first load.</span></span> <span data-ttu-id="0151c-186">`launchMode` が `"maximized"` に設定されていると、このプロパティは無視されます。</span><span class="sxs-lookup"><span data-stu-id="0151c-186">If `launchMode` is set to `"maximized"`, this property is ignored.</span></span>

<span data-ttu-id="0151c-187">**プロパティ名:** `initialCols`</span><span class="sxs-lookup"><span data-stu-id="0151c-187">**Property name:** `initialCols`</span></span>

<span data-ttu-id="0151c-188">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="0151c-188">**Necessity:** Optional</span></span>

<span data-ttu-id="0151c-189">**値:** 整数</span><span class="sxs-lookup"><span data-stu-id="0151c-189">**Accepts:** Integer</span></span>

<span data-ttu-id="0151c-190">**既定値:** `120`</span><span class="sxs-lookup"><span data-stu-id="0151c-190">**Default value:** `120`</span></span>

### <a name="rows-on-first-launch"></a><span data-ttu-id="0151c-191">最初の起動時の行数</span><span class="sxs-lookup"><span data-stu-id="0151c-191">Rows on first launch</span></span>

<span data-ttu-id="0151c-192">これは、最初の読み込み時にウィンドウに表示される行の数です。</span><span class="sxs-lookup"><span data-stu-id="0151c-192">This is the number of rows displayed in the window upon first load.</span></span> <span data-ttu-id="0151c-193">`launchMode` が `"maximized"` に設定されていると、このプロパティは無視されます。</span><span class="sxs-lookup"><span data-stu-id="0151c-193">If `launchMode` is set to `"maximized"`, this property is ignored.</span></span>

<span data-ttu-id="0151c-194">**プロパティ名:** `initialRows`</span><span class="sxs-lookup"><span data-stu-id="0151c-194">**Property name:** `initialRows`</span></span>

<span data-ttu-id="0151c-195">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="0151c-195">**Necessity:** Optional</span></span>

<span data-ttu-id="0151c-196">**値:** 整数</span><span class="sxs-lookup"><span data-stu-id="0151c-196">**Accepts:** Integer</span></span>

<span data-ttu-id="0151c-197">**既定値:** `30`</span><span class="sxs-lookup"><span data-stu-id="0151c-197">**Default value:** `30`</span></span>

<br />

___

## <a name="title-bar-settings"></a><span data-ttu-id="0151c-198">タイトル バーの設定</span><span class="sxs-lookup"><span data-stu-id="0151c-198">Title bar settings</span></span>

### <a name="showhide-the-title-bar"></a><span data-ttu-id="0151c-199">タイトル バーの表示/非表示</span><span class="sxs-lookup"><span data-stu-id="0151c-199">Show/Hide the title bar</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="0151c-200">これを `true` に設定すると、タブはタイトル バー内に移動され、タイトル バーは表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="0151c-200">When this is set to `true`, the tabs are moved into the title bar and the title bar disappears.</span></span> <span data-ttu-id="0151c-201">`false` に設定すると、タイトル バーはタブの上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0151c-201">When it's set to `false`, the title bar sits above the tabs.</span></span> <span data-ttu-id="0151c-202">この設定を変更すると、新しいターミナル インスタンスを開始する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0151c-202">Note that changing this setting will require starting a new terminal instance.</span></span>

<span data-ttu-id="0151c-203">**プロパティ名:** `showTabsInTitlebar`</span><span class="sxs-lookup"><span data-stu-id="0151c-203">**Property name:** `showTabsInTitlebar`</span></span>

<span data-ttu-id="0151c-204">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="0151c-204">**Necessity:** Optional</span></span>

<span data-ttu-id="0151c-205">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="0151c-205">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="0151c-206">**既定値:** `true`</span><span class="sxs-lookup"><span data-stu-id="0151c-206">**Default value:** `true`</span></span>

:::column-end:::
:::column span="":::
![Windows ターミナルのタブをタイトル バーに表示する](./../images/show-tabs-in-title-bar.gif)

:::column-end:::
:::row-end:::

### <a name="set-the-text-in-the-title-bar"></a><span data-ttu-id="0151c-208">タイトル バーのテキストを設定する</span><span class="sxs-lookup"><span data-stu-id="0151c-208">Set the text in the title bar</span></span>

<span data-ttu-id="0151c-209">これが `true` に設定されていると、選択されているタブのタイトルがタイトル バーに表示されます。`false` に設定すると、タイトル バーには "Windows ターミナル" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="0151c-209">When this is set to `true`, the title bar displays the title of the selected tab. When it's set to `false`, title bar displays "Windows Terminal".</span></span> <span data-ttu-id="0151c-210">この設定を変更すると、新しいターミナル インスタンスを開始する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0151c-210">Note that changing this setting will require starting a new terminal instance.</span></span>

<span data-ttu-id="0151c-211">**プロパティ名:** `showTerminalTitleInTitlebar`</span><span class="sxs-lookup"><span data-stu-id="0151c-211">**Property name:** `showTerminalTitleInTitlebar`</span></span>

<span data-ttu-id="0151c-212">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="0151c-212">**Necessity:** Optional</span></span>

<span data-ttu-id="0151c-213">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="0151c-213">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="0151c-214">**既定値:** `true`</span><span class="sxs-lookup"><span data-stu-id="0151c-214">**Default value:** `true`</span></span>

<br />

___

## <a name="selection-settings"></a><span data-ttu-id="0151c-215">選択の設定</span><span class="sxs-lookup"><span data-stu-id="0151c-215">Selection settings</span></span>

### <a name="copy-after-selection-is-made"></a><span data-ttu-id="0151c-216">選択後にコピーする</span><span class="sxs-lookup"><span data-stu-id="0151c-216">Copy after selection is made</span></span>

<span data-ttu-id="0151c-217">これを `true` に設定すると、作成時に選択内容がすぐにクリップボードにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="0151c-217">When this is set to `true`, a selection is immediately copied to your clipboard upon creation.</span></span> <span data-ttu-id="0151c-218">この場合、マウスを右クリックすると常に貼り付けられます。</span><span class="sxs-lookup"><span data-stu-id="0151c-218">The right-click on your mouse will always paste in this case.</span></span> <span data-ttu-id="0151c-219">`false` に設定すると、選択内容が保持され、追加の操作が待機されます。</span><span class="sxs-lookup"><span data-stu-id="0151c-219">When it's set to `false`, the selection persists and awaits further action.</span></span> <span data-ttu-id="0151c-220">マウスを右クリックすると、選択内容がコピーされます。</span><span class="sxs-lookup"><span data-stu-id="0151c-220">Using your mouse to right-click will copy the selection.</span></span>

<span data-ttu-id="0151c-221">**プロパティ名:** `copyOnSelect`</span><span class="sxs-lookup"><span data-stu-id="0151c-221">**Property name:** `copyOnSelect`</span></span>

<span data-ttu-id="0151c-222">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="0151c-222">**Necessity:** Optional</span></span>

<span data-ttu-id="0151c-223">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="0151c-223">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="0151c-224">**既定値:** `false`</span><span class="sxs-lookup"><span data-stu-id="0151c-224">**Default value:** `false`</span></span>

### <a name="copy-formatting"></a><span data-ttu-id="0151c-225">書式指定をコピーする</span><span class="sxs-lookup"><span data-stu-id="0151c-225">Copy formatting</span></span>

<span data-ttu-id="0151c-226">これを `true` に設定すると、選択したテキストの色とフォントの書式もクリップボードにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="0151c-226">When this is set to `true`, the color and font formatting of selected text is also copied to your clipboard.</span></span> <span data-ttu-id="0151c-227">`false` に設定すると、プレーンテキストのみがクリップボードにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="0151c-227">When it's set to `false`, only plain text is copied to your clipboard.</span></span>

<span data-ttu-id="0151c-228">**プロパティ名:** `copyFormatting`</span><span class="sxs-lookup"><span data-stu-id="0151c-228">**Property name:** `copyFormatting`</span></span>

<span data-ttu-id="0151c-229">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="0151c-229">**Necessity:** Optional</span></span>

<span data-ttu-id="0151c-230">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="0151c-230">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="0151c-231">**既定値:** `false`</span><span class="sxs-lookup"><span data-stu-id="0151c-231">**Default value:** `false`</span></span>

### <a name="word-delimiters"></a><span data-ttu-id="0151c-232">単語の区切り記号</span><span class="sxs-lookup"><span data-stu-id="0151c-232">Word delimiters</span></span>

<span data-ttu-id="0151c-233">ダブルクリックの選択で使用される単語の区切り記号を決定します。</span><span class="sxs-lookup"><span data-stu-id="0151c-233">This determines the word delimiters used in a double-click selection.</span></span> <span data-ttu-id="0151c-234">単語の区切り記号は、2 つの単語の間の境界がどこにあるかを指定する文字です。</span><span class="sxs-lookup"><span data-stu-id="0151c-234">Word delimiters are characters that specify where the boundary is between two words.</span></span> <span data-ttu-id="0151c-235">最も一般的な例は、スペース、セミコロン、コンマ、ピリオドなどです。</span><span class="sxs-lookup"><span data-stu-id="0151c-235">The most common examples are spaces, semicolons, commas, and periods.</span></span>

<span data-ttu-id="0151c-236">**プロパティ名:** `wordDelimiters`</span><span class="sxs-lookup"><span data-stu-id="0151c-236">**Property name:** `wordDelimiters`</span></span>

<span data-ttu-id="0151c-237">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="0151c-237">**Necessity:** Optional</span></span>

<span data-ttu-id="0151c-238">**値:** 文字列としての文字</span><span class="sxs-lookup"><span data-stu-id="0151c-238">**Accepts:** Characters as a string</span></span>

<span data-ttu-id="0151c-239">**既定値:** <code>&nbsp;&#x2f;&#x5c;&#x28;&#x29;&#x22;&#x27;&#x2d;&#x3a;&#x2c;&#x2e;&#x3b;&#x3c;&#x3e;&#x7e;&#x21;&#x40;&#x23;&#x24;&#x25;&#x5e;&#x26;&#x2a;&#x7c;&#x2b;&#x3d;&#x5b;&#x5d;&#x7b;&#x7d;&#x7e;&#x3f;│</code></span><span class="sxs-lookup"><span data-stu-id="0151c-239">**Default value:** <code>&nbsp;&#x2f;&#x5c;&#x28;&#x29;&#x22;&#x27;&#x2d;&#x3a;&#x2c;&#x2e;&#x3b;&#x3c;&#x3e;&#x7e;&#x21;&#x40;&#x23;&#x24;&#x25;&#x5e;&#x26;&#x2a;&#x7c;&#x2b;&#x3d;&#x5b;&#x5d;&#x7b;&#x7d;&#x7e;&#x3f;│</code></span></span><br><span data-ttu-id="0151c-240">_(`│` は `U+2502 BOX DRAWINGS LIGHT VERTICAL` です)_</span><span class="sxs-lookup"><span data-stu-id="0151c-240">_(`│` is `U+2502 BOX DRAWINGS LIGHT VERTICAL`)_</span></span>

<br />

___

## <a name="scroll-speed"></a><span data-ttu-id="0151c-241">スクロール速度</span><span class="sxs-lookup"><span data-stu-id="0151c-241">Scroll speed</span></span>

<span data-ttu-id="0151c-242">これは、マウス ホイールで一度にスクロールする行の数です。</span><span class="sxs-lookup"><span data-stu-id="0151c-242">This is the number of rows to scroll at a time with the mouse wheel.</span></span> <span data-ttu-id="0151c-243">値がゼロまたは `"system"` でない場合は、システム設定がオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="0151c-243">This will override the system setting if the value is not zero or `"system"`.</span></span>

<span data-ttu-id="0151c-244">**プロパティ名:** `rowsToScroll`</span><span class="sxs-lookup"><span data-stu-id="0151c-244">**Property name:** `rowsToScroll`</span></span>

<span data-ttu-id="0151c-245">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="0151c-245">**Necessity:** Optional</span></span>

<span data-ttu-id="0151c-246">**値:** 整数</span><span class="sxs-lookup"><span data-stu-id="0151c-246">**Accepts:** Integer</span></span>

<span data-ttu-id="0151c-247">**既定値:** `"system"`</span><span class="sxs-lookup"><span data-stu-id="0151c-247">**Default value:** `"system"`</span></span>

<br />

___

## <a name="window-resize-behavior"></a><span data-ttu-id="0151c-248">ウィンドウ サイズ変更の動作</span><span class="sxs-lookup"><span data-stu-id="0151c-248">Window resize behavior</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="0151c-249">これを `true` に設定すると、サイズ変更時にウィンドウは最も近い文字境界にスナップされます。</span><span class="sxs-lookup"><span data-stu-id="0151c-249">When this is set to `true`, the window will snap to the nearest character boundary on resize.</span></span> <span data-ttu-id="0151c-250">`false` に設定すると、ウィンドウのサイズは "スムーズ" に変更されます。</span><span class="sxs-lookup"><span data-stu-id="0151c-250">When it's set to `false`, the window will resize "smoothly".</span></span>

<span data-ttu-id="0151c-251">**プロパティ名:** `snapToGridOnResize`</span><span class="sxs-lookup"><span data-stu-id="0151c-251">**Property name:** `snapToGridOnResize`</span></span>

<span data-ttu-id="0151c-252">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="0151c-252">**Necessity:** Optional</span></span>

<span data-ttu-id="0151c-253">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="0151c-253">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="0151c-254">**既定値:** `true`</span><span class="sxs-lookup"><span data-stu-id="0151c-254">**Default value:** `true`</span></span>

:::column-end:::
:::column span="":::
![サイズ変更時に Windows ターミナルはグリッドにスナップする](./../images/snap-to-grid-on-resize.gif)

:::column-end:::
:::row-end:::

<br />

___

## <a name="rendering-settings"></a><span data-ttu-id="0151c-256">レンダリング設定</span><span class="sxs-lookup"><span data-stu-id="0151c-256">Rendering settings</span></span>

<span data-ttu-id="0151c-257">レンダリング設定の変更を検討している場合、[トラブルシューティング ページ](./../troubleshooting.md#the-text-is-blurry)にある追加情報を参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="0151c-257">If you are thinking about changing the rendering settings, additional information is provided on the [Troubleshooting page](./../troubleshooting.md#the-text-is-blurry) to help guide you.</span></span>

### <a name="screen-redrawing"></a><span data-ttu-id="0151c-258">画面の再描画</span><span class="sxs-lookup"><span data-stu-id="0151c-258">Screen redrawing</span></span>

<span data-ttu-id="0151c-259">`true` に設定されている場合、ターミナルでは各フレームの画面全体を再描画します。</span><span class="sxs-lookup"><span data-stu-id="0151c-259">When this set to `true`, the terminal will redraw the entire screen each frame.</span></span> <span data-ttu-id="0151c-260">`false` に設定されている場合、フレーム間の画面の更新のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0151c-260">When set to `false`, it will render only the updates to the screen between frames.</span></span>

<span data-ttu-id="0151c-261">**プロパティ名:** `experimental.rendering.forceFullRepaint`</span><span class="sxs-lookup"><span data-stu-id="0151c-261">**Property name:** `experimental.rendering.forceFullRepaint`</span></span>

<span data-ttu-id="0151c-262">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="0151c-262">**Necessity:** Optional</span></span>

<span data-ttu-id="0151c-263">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="0151c-263">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="0151c-264">**既定値:** `false`</span><span class="sxs-lookup"><span data-stu-id="0151c-264">**Default value:** `false`</span></span>

### <a name="software-rendering"></a><span data-ttu-id="0151c-265">ソフトウェア レンダリング</span><span class="sxs-lookup"><span data-stu-id="0151c-265">Software rendering</span></span>

<span data-ttu-id="0151c-266">`true` に設定されている場合、ターミナルでは、ハードウェア レンダラーの代わりに</span><span class="sxs-lookup"><span data-stu-id="0151c-266">When this is set to `true`, the terminal will use the software renderer (a.k.a.</span></span> <span data-ttu-id="0151c-267">ソフトウェア レンダラー (WARP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="0151c-267">WARP) instead of the hardware one.</span></span>

<span data-ttu-id="0151c-268">**プロパティ名:** `experimental.rendering.software`</span><span class="sxs-lookup"><span data-stu-id="0151c-268">**Property name:** `experimental.rendering.software`</span></span>

<span data-ttu-id="0151c-269">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="0151c-269">**Necessity:** Optional</span></span>

<span data-ttu-id="0151c-270">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="0151c-270">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="0151c-271">**既定値:** `false`</span><span class="sxs-lookup"><span data-stu-id="0151c-271">**Default value:** `false`</span></span>
