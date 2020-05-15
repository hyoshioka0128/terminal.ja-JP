---
title: Windows ターミナル プロファイルの設定
description: Windows ターミナル内の個々のプロファイルをカスタマイズする方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: how-to
ms.service: terminal
ms.localizationpriority: high
ms.openlocfilehash: 309fb40736718df7d1670a7376806b70ef0e35fe
ms.sourcegitcommit: bb5b7fd7db4b81e0d44e060989dc16b6775c802a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83416087"
---
# <a name="profile-settings-in-the-windows-terminal"></a><span data-ttu-id="052e7-103">Windows ターミナルでのプロファイル設定</span><span class="sxs-lookup"><span data-stu-id="052e7-103">Profile settings in the Windows Terminal</span></span>

<span data-ttu-id="052e7-104">以下に示す設定は、それぞれ一意のプロファイルに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="052e7-104">The settings listed below are specific to each unique profile.</span></span> <span data-ttu-id="052e7-105">設定を自分のすべてのプロファイルに適用する場合は、ご自分の settings.json ファイル内のプロファイルの一覧の上にある `defaults` セクションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="052e7-105">If you'd like a setting to apply to all of your profiles, you can add it to the `defaults` section above the list of profiles in your settings.json file.</span></span>

```json
"defaults":
{
    // SETTINGS TO APPLY TO ALL PROFILES
},
"list":
[
    // PROFILE OBJECTS
]
```

## <a name="unique-identifier"></a><span data-ttu-id="052e7-106">一意識別子</span><span class="sxs-lookup"><span data-stu-id="052e7-106">Unique identifier</span></span>

<span data-ttu-id="052e7-107">プロファイルでは、GUID を一意の識別子として使用できます。</span><span class="sxs-lookup"><span data-stu-id="052e7-107">Profiles can use a GUID as a unique identifier.</span></span> <span data-ttu-id="052e7-108">プロファイルを既定のプロファイルにするには、`defaultProfile` グローバル設定の GUID が必要です。</span><span class="sxs-lookup"><span data-stu-id="052e7-108">To make a profile your default profile, it needs a GUID for the `defaultProfile` global setting.</span></span>

<span data-ttu-id="052e7-109">**プロパティ名:** `guid`</span><span class="sxs-lookup"><span data-stu-id="052e7-109">**Property name:** `guid`</span></span>

<span data-ttu-id="052e7-110">**必須かどうか:** 必須</span><span class="sxs-lookup"><span data-stu-id="052e7-110">**Necessity:** Required</span></span>

<span data-ttu-id="052e7-111">**受け入れ可能:** レジストリ形式の GUID を表す文字列: `"{00000000-0000-0000-0000-000000000000}"`</span><span class="sxs-lookup"><span data-stu-id="052e7-111">**Accepts:** GUID as a string in registry format: `"{00000000-0000-0000-0000-000000000000}"`</span></span>

<br />

___

## <a name="executable-settings"></a><span data-ttu-id="052e7-112">実行可能ファイルの設定</span><span class="sxs-lookup"><span data-stu-id="052e7-112">Executable settings</span></span>

### <a name="command-line"></a><span data-ttu-id="052e7-113">コマンド ライン</span><span class="sxs-lookup"><span data-stu-id="052e7-113">Command line</span></span>

<span data-ttu-id="052e7-114">これは、プロファイルで使用される実行可能ファイルです。</span><span class="sxs-lookup"><span data-stu-id="052e7-114">This is the executable used in the profile.</span></span>

<span data-ttu-id="052e7-115">**プロパティ名:** `commandline`</span><span class="sxs-lookup"><span data-stu-id="052e7-115">**Property name:** `commandline`</span></span>

<span data-ttu-id="052e7-116">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-116">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-117">**受け入れ可能:** 実行可能ファイル名を表す文字列</span><span class="sxs-lookup"><span data-stu-id="052e7-117">**Accepts:** Executable file name as a string</span></span>

<span data-ttu-id="052e7-118">**既定値:** `"cmd.exe"`</span><span class="sxs-lookup"><span data-stu-id="052e7-118">**Default value:** `"cmd.exe"`</span></span>

### <a name="source"></a><span data-ttu-id="052e7-119">ソース</span><span class="sxs-lookup"><span data-stu-id="052e7-119">Source</span></span>

<span data-ttu-id="052e7-120">これには、プロファイルを生成したプロファイル ジェネレーターの名前が格納されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-120">This stores the name of the profile generator that originated the profile.</span></span> <span data-ttu-id="052e7-121">_このフィールドには検出可能な値がありません。_</span><span class="sxs-lookup"><span data-stu-id="052e7-121">_There are no discoverable values for this field._</span></span> <span data-ttu-id="052e7-122">動的プロファイルの詳細については、[動的プロファイルに関するページ](./../dynamic-profiles.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="052e7-122">For additional information on dynamic profiles, visit the [Dynamic profiles page](./../dynamic-profiles.md).</span></span>

<span data-ttu-id="052e7-123">**プロパティ名:** `source`</span><span class="sxs-lookup"><span data-stu-id="052e7-123">**Property name:** `source`</span></span>

<span data-ttu-id="052e7-124">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-124">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-125">**受け入れ可能:** String</span><span class="sxs-lookup"><span data-stu-id="052e7-125">**Accepts:** String</span></span>

### <a name="starting-directory"></a><span data-ttu-id="052e7-126">開始ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="052e7-126">Starting directory</span></span>

<span data-ttu-id="052e7-127">これは、シェルが読み込まれるときに開始されるディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="052e7-127">This is the directory the shell starts in when it is loaded.</span></span>

<span data-ttu-id="052e7-128">**プロパティ名:** `startingDirectory`</span><span class="sxs-lookup"><span data-stu-id="052e7-128">**Property name:** `startingDirectory`</span></span>

<span data-ttu-id="052e7-129">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-129">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-130">**受け入れ可能:** フォルダーの場所を表す文字列</span><span class="sxs-lookup"><span data-stu-id="052e7-130">**Accepts:** Folder location as a string</span></span>

<span data-ttu-id="052e7-131">**既定値:** `"%USERPROFILE%"`</span><span class="sxs-lookup"><span data-stu-id="052e7-131">**Default value:** `"%USERPROFILE%"`</span></span>

<br />

___

## <a name="dropdown-settings"></a><span data-ttu-id="052e7-132">ドロップダウンの設定</span><span class="sxs-lookup"><span data-stu-id="052e7-132">Dropdown settings</span></span>

<span data-ttu-id="052e7-133">![Windows ターミナルのドロップダウン](./../images/dropdown.png)
_構成:[Raspberry Ubuntu](./../custom-terminal-gallery/raspberry-ubuntu.md)_</span><span class="sxs-lookup"><span data-stu-id="052e7-133">![Windows Terminal dropdown](./../images/dropdown.png)
_Configuration: [Raspberry Ubuntu](./../custom-terminal-gallery/raspberry-ubuntu.md)_</span></span>

### <a name="name"></a><span data-ttu-id="052e7-134">名前</span><span class="sxs-lookup"><span data-stu-id="052e7-134">Name</span></span>

<span data-ttu-id="052e7-135">これは、ドロップダウン メニューに表示されるプロファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="052e7-135">This is the name of the profile that will be displayed in the dropdown menu.</span></span> <span data-ttu-id="052e7-136">この値は、起動時にシェルに渡す "タイトル" としても使用されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-136">This value is also used as the "title" to pass to the shell on startup.</span></span> <span data-ttu-id="052e7-137">一部のシェル (`bash` など) では、この初期値を無視することができますが、他のシェル (`Command Prompt`、`PowerShell`) では、アプリケーションの有効期間中、この値を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="052e7-137">Some shells (like `bash`) may choose to ignore this initial value, while others (`Command Prompt`, `PowerShell`) may use this value over the lifetime of the application.</span></span> <span data-ttu-id="052e7-138">この "タイトル" の動作は、`tabTitle` を使用してオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="052e7-138">This "title" behavior can be overridden by using `tabTitle`.</span></span>

<span data-ttu-id="052e7-139">**プロパティ名:** `name`</span><span class="sxs-lookup"><span data-stu-id="052e7-139">**Property name:** `name`</span></span>

<span data-ttu-id="052e7-140">**必須かどうか:** 必須</span><span class="sxs-lookup"><span data-stu-id="052e7-140">**Necessity:** Required</span></span>

<span data-ttu-id="052e7-141">**受け入れ可能:** String</span><span class="sxs-lookup"><span data-stu-id="052e7-141">**Accepts:** String</span></span>

### <a name="icon"></a><span data-ttu-id="052e7-142">［アイコン］</span><span class="sxs-lookup"><span data-stu-id="052e7-142">Icon</span></span>

<span data-ttu-id="052e7-143">これにより、タブとドロップダウン メニュー内に表示されるアイコンが設定されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-143">This sets the icon that displays within the tab and the dropdown menu.</span></span>

<span data-ttu-id="052e7-144">**プロパティ名:** `icon`</span><span class="sxs-lookup"><span data-stu-id="052e7-144">**Property name:** `icon`</span></span>

<span data-ttu-id="052e7-145">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-145">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-146">**受け入れ可能:** ファイルの場所を表す文字列</span><span class="sxs-lookup"><span data-stu-id="052e7-146">**Accepts:** File location as a string</span></span>

### <a name="hide-a-profile-from-the-dropdown"></a><span data-ttu-id="052e7-147">ドロップダウンからプロファイルを非表示にする</span><span class="sxs-lookup"><span data-stu-id="052e7-147">Hide a profile from the dropdown</span></span>

<span data-ttu-id="052e7-148">`hidden` が `true` に設定されている場合、そのプロファイルはプロファイルの一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="052e7-148">If `hidden` is set to `true`, the profile will not appear in the list of profiles.</span></span> <span data-ttu-id="052e7-149">これを使用すると、既定のプロファイルと動的に生成されたプロファイルを設定ファイルに残したまま、非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="052e7-149">This can be used to hide default profiles and dynamically generated profiles, while leaving them in your settings file.</span></span> <span data-ttu-id="052e7-150">動的プロファイルの詳細については、[動的プロファイルに関するページ](./../dynamic-profiles.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="052e7-150">To learn more about dynamic profiles, visit the [Dynamic profiles page](./../dynamic-profiles.md).</span></span>

<span data-ttu-id="052e7-151">**プロパティ名:** `hidden`</span><span class="sxs-lookup"><span data-stu-id="052e7-151">**Property name:** `hidden`</span></span>

<span data-ttu-id="052e7-152">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-152">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-153">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="052e7-153">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="052e7-154">**既定値:** `false`</span><span class="sxs-lookup"><span data-stu-id="052e7-154">**Default value:** `false`</span></span>

<br />

___

## <a name="tab-title-settings"></a><span data-ttu-id="052e7-155">タブ タイトルの設定</span><span class="sxs-lookup"><span data-stu-id="052e7-155">Tab title settings</span></span>

### <a name="custom-tab-title"></a><span data-ttu-id="052e7-156">カスタム タブのタイトル</span><span class="sxs-lookup"><span data-stu-id="052e7-156">Custom tab title</span></span>

<span data-ttu-id="052e7-157">設定すると、起動時にシェルに渡すタイトルとして `name` が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="052e7-157">If set, this will replace the `name` as the title to pass to the shell on startup.</span></span> <span data-ttu-id="052e7-158">一部のシェル (`bash` など) では、この初期値を無視することができますが、他のシェル (`Command Prompt`、`PowerShell`) では、アプリケーションの有効期間中、この値を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="052e7-158">Some shells (like `bash`) may choose to ignore this initial value, while others (`Command Prompt`, `PowerShell`) may use this value over the lifetime of the application.</span></span> <span data-ttu-id="052e7-159">シェルでタイトルを設定する方法については、[タブ タイトルのチュートリアル](./../tutorials/tab-title.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="052e7-159">If you'd like to learn how to have the shell set your title, visit the [tab title tutorial](./../tutorials/tab-title.md).</span></span>

<span data-ttu-id="052e7-160">**プロパティ名:** `tabTitle`</span><span class="sxs-lookup"><span data-stu-id="052e7-160">**Property name:** `tabTitle`</span></span>

<span data-ttu-id="052e7-161">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-161">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-162">**受け入れ可能:** String</span><span class="sxs-lookup"><span data-stu-id="052e7-162">**Accepts:** String</span></span>

### <a name="suppress-title-changes-from-the-shell"></a><span data-ttu-id="052e7-163">シェルからのタイトルの変更を抑制する</span><span class="sxs-lookup"><span data-stu-id="052e7-163">Suppress title changes from the shell</span></span>

<span data-ttu-id="052e7-164">これが `true` に設定されている場合、`tabTitle` によってタブの既定のタイトルがオーバーライドされ、アプリケーションからのタイトルの変更メッセージはすべて抑制されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-164">When this is set to `true`, `tabTitle` overrides the default title of the tab and any title change messages from the application will be suppressed.</span></span> <span data-ttu-id="052e7-165">`tabTitle` が設定されていない場合は、代わりに `name` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-165">If `tabTitle` isn't set, `name` will be used instead.</span></span> <span data-ttu-id="052e7-166">これが `false` に設定されている場合、`tabTitle` は通常どおりに動作します。</span><span class="sxs-lookup"><span data-stu-id="052e7-166">When this is set to `false`, `tabTitle` behaves as normal.</span></span>

<span data-ttu-id="052e7-167">**プロパティ名:** `suppressApplicationTitle`</span><span class="sxs-lookup"><span data-stu-id="052e7-167">**Property name:** `suppressApplicationTitle`</span></span>

<span data-ttu-id="052e7-168">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-168">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-169">**受け入れ可能:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="052e7-169">**Accepts:** `true`, `false`</span></span>

<br />

___

## <a name="text-settings"></a><span data-ttu-id="052e7-170">テキストの設定</span><span class="sxs-lookup"><span data-stu-id="052e7-170">Text settings</span></span>

### <a name="font-face"></a><span data-ttu-id="052e7-171">フォント フェイス</span><span class="sxs-lookup"><span data-stu-id="052e7-171">Font face</span></span>

<span data-ttu-id="052e7-172">これは、プロファイルで使用されるフォント フェイスの名前です。</span><span class="sxs-lookup"><span data-stu-id="052e7-172">This is the name of the font face used in the profile.</span></span> <span data-ttu-id="052e7-173">これが見つからないか無効である場合は、ターミナルによって Consolas へのフォールバックが試行されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-173">The terminal will try to fallback to Consolas if this can't be found or is invalid.</span></span> <span data-ttu-id="052e7-174">既定のフォント Cascadia Mono のその他のバリアントについては、[Cascadia Code に関するページ](./../cascadia-code.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="052e7-174">To learn about the other variants of the default font, Cascadia Mono, visit the [Cascadia Code page](./../cascadia-code.md).</span></span>

<span data-ttu-id="052e7-175">**プロパティ名:** `fontFace`</span><span class="sxs-lookup"><span data-stu-id="052e7-175">**Property name:** `fontFace`</span></span>

<span data-ttu-id="052e7-176">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-176">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-177">**受け入れ可能:** フォント名を表す文字列</span><span class="sxs-lookup"><span data-stu-id="052e7-177">**Accepts:** Font name as a string</span></span>

<span data-ttu-id="052e7-178">**既定値:** `"Cascadia Mono"`</span><span class="sxs-lookup"><span data-stu-id="052e7-178">**Default value:** `"Cascadia Mono"`</span></span>

### <a name="font-size"></a><span data-ttu-id="052e7-179">フォント サイズ</span><span class="sxs-lookup"><span data-stu-id="052e7-179">Font size</span></span>

<span data-ttu-id="052e7-180">これにより、プロファイルのフォント サイズがポイント単位で設定されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-180">This sets the profile's font size in points.</span></span>

<span data-ttu-id="052e7-181">**プロパティ名:** `fontSize`</span><span class="sxs-lookup"><span data-stu-id="052e7-181">**Property name:** `fontSize`</span></span>

<span data-ttu-id="052e7-182">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-182">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-183">**値:** 整数</span><span class="sxs-lookup"><span data-stu-id="052e7-183">**Accepts:** Integer</span></span>

<span data-ttu-id="052e7-184">**既定値:** `12`</span><span class="sxs-lookup"><span data-stu-id="052e7-184">**Default value:** `12`</span></span>

### <a name="padding"></a><span data-ttu-id="052e7-185">余白</span><span class="sxs-lookup"><span data-stu-id="052e7-185">Padding</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="052e7-186">これにより、ウィンドウ内のテキストの周囲の余白が設定されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-186">This sets the padding around the text within the window.</span></span> <span data-ttu-id="052e7-187">これには、次の 3 つの異なる形式が使用できます。`"#"` は、すべての辺に同じ余白を設定し、`"#, #"` は左右と上下に同じ余白を設定し、`"#, #, #, #"` は左、上、右、下に個別に余白を設定します。</span><span class="sxs-lookup"><span data-stu-id="052e7-187">This will accept three different formats: `"#"` sets the same padding for all sides, `"#, #"` sets the same padding for left-right and top-bottom, and `"#, #, #, #"` sets the padding individually for left, top, right, and bottom.</span></span>

<span data-ttu-id="052e7-188">**プロパティ名:** `padding`</span><span class="sxs-lookup"><span data-stu-id="052e7-188">**Property name:** `padding`</span></span>

<span data-ttu-id="052e7-189">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-189">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-190">**受け入れ可能:** 次の形式の値を表す文字列: `"#"`、`"#, #"`、`"#, #, #, #"`</span><span class="sxs-lookup"><span data-stu-id="052e7-190">**Accepts:** Values as a string in the following formats: `"#"`, `"#, #"`, `"#, #, #, #"`</span></span>

<span data-ttu-id="052e7-191">**既定値:** `"8, 8, 8, 8"`</span><span class="sxs-lookup"><span data-stu-id="052e7-191">**Default value:** `"8, 8, 8, 8"`</span></span>

:::column-end:::
:::column span="":::
![Windows ターミナルの余白](./../images/padding.gif)

:::column-end:::
:::row-end:::

### <a name="antialiasing-text"></a><span data-ttu-id="052e7-193">アンチエイリアシング テキスト</span><span class="sxs-lookup"><span data-stu-id="052e7-193">Antialiasing text</span></span>

<span data-ttu-id="052e7-194">これは、レンダラーでテキストをアンチエイリアシングする方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="052e7-194">This controls how text is antialiased in the renderer.</span></span> <span data-ttu-id="052e7-195">この設定を変更すると、新しいターミナル インスタンスを開始する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="052e7-195">Note that changing this setting will require starting a new terminal instance.</span></span>

![Windows ターミナルのアンチエイリアシング テキスト](./../images/antialiasing-mode.gif)

<span data-ttu-id="052e7-197">**プロパティ名:** `antialiasingMode`</span><span class="sxs-lookup"><span data-stu-id="052e7-197">**Property name:** `antialiasingMode`</span></span>

<span data-ttu-id="052e7-198">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-198">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-199">**値:** `"grayscale"`、`"cleartype"`、`"aliased"`</span><span class="sxs-lookup"><span data-stu-id="052e7-199">**Accepts:** `"grayscale"`, `"cleartype"`, `"aliased"`</span></span>

<span data-ttu-id="052e7-200">**既定値:** `"grayscale"`</span><span class="sxs-lookup"><span data-stu-id="052e7-200">**Default value:** `"grayscale"`</span></span>

<br />

___

## <a name="cursor-settings"></a><span data-ttu-id="052e7-201">カーソルの設定</span><span class="sxs-lookup"><span data-stu-id="052e7-201">Cursor settings</span></span>

### <a name="cursor-shape"></a><span data-ttu-id="052e7-202">カーソルの形</span><span class="sxs-lookup"><span data-stu-id="052e7-202">Cursor shape</span></span>

<span data-ttu-id="052e7-203">これにより、プロファイルのカーソルの形が設定されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-203">This sets the cursor shape for the profile.</span></span> <span data-ttu-id="052e7-204">使用可能なカーソル: `"bar"` ( &#x2503; )、`"vintage"` ( &#x2583; )、`"underscore"` ( &#x2581; )、`"filledBox"` ( &#x2588; )、`"emptyBox"` ( &#x25AF; )</span><span class="sxs-lookup"><span data-stu-id="052e7-204">The possible cursors are as follows: `"bar"` ( &#x2503; ), `"vintage"` ( &#x2583; ), `"underscore"` ( &#x2581; ), `"filledBox"` ( &#x2588; ), `"emptyBox"` ( &#x25AF; )</span></span>

<span data-ttu-id="052e7-205">**プロパティ名:** `cursorShape`</span><span class="sxs-lookup"><span data-stu-id="052e7-205">**Property name:** `cursorShape`</span></span>

<span data-ttu-id="052e7-206">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-206">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-207">**受け入れ可能:** `"bar"`、`"vintage"`、`"underscore"`、`"filledBox"`、`"emptyBox"`</span><span class="sxs-lookup"><span data-stu-id="052e7-207">**Accepts:** `"bar"`, `"vintage"`, `"underscore"`, `"filledBox"`, `"emptyBox"`</span></span>

<span data-ttu-id="052e7-208">**既定値:** `"bar"`</span><span class="sxs-lookup"><span data-stu-id="052e7-208">**Default value:** `"bar"`</span></span>

### <a name="cursor-color"></a><span data-ttu-id="052e7-209">カーソルの色</span><span class="sxs-lookup"><span data-stu-id="052e7-209">Cursor color</span></span>

<span data-ttu-id="052e7-210">これにより、プロファイルのカーソルの色が設定されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-210">This sets the cursor color of the profile.</span></span> <span data-ttu-id="052e7-211">これにより、配色で設定された `cursorColor` がオーバーライドされます (`colorScheme` が設定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="052e7-211">This will override the `cursorColor` set in the color scheme if `colorScheme` is set.</span></span>

<span data-ttu-id="052e7-212">**プロパティ名:** `cursorColor`</span><span class="sxs-lookup"><span data-stu-id="052e7-212">**Property name:** `cursorColor`</span></span>

<span data-ttu-id="052e7-213">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-213">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-214">**受け入れ可能:** 色を表す 16 進形式の文字列: `"#rgb"` または `"#rrggbb"`</span><span class="sxs-lookup"><span data-stu-id="052e7-214">**Accepts:** Color as a string in hex format: `"#rgb"` or `"#rrggbb"`</span></span>

### <a name="cursor-height"></a><span data-ttu-id="052e7-215">カーソルの高さ</span><span class="sxs-lookup"><span data-stu-id="052e7-215">Cursor height</span></span>

<span data-ttu-id="052e7-216">これにより、下部からのカーソルの高さの割合が設定されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-216">This sets the percentage height of the cursor starting from the bottom.</span></span> <span data-ttu-id="052e7-217">これは `cursorShape` が `"vintage"` に設定されている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="052e7-217">This will only work when `cursorShape` is set to `"vintage"`.</span></span>

<span data-ttu-id="052e7-218">**プロパティ名:** `cursorHeight`</span><span class="sxs-lookup"><span data-stu-id="052e7-218">**Property name:** `cursorHeight`</span></span>

<span data-ttu-id="052e7-219">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-219">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-220">**受け入れ可能:** 25 から 100 までの整数</span><span class="sxs-lookup"><span data-stu-id="052e7-220">**Accepts:** Integer from 25-100</span></span>

<br />

___

## <a name="color-settings"></a><span data-ttu-id="052e7-221">色の設定</span><span class="sxs-lookup"><span data-stu-id="052e7-221">Color settings</span></span>

### <a name="color-scheme"></a><span data-ttu-id="052e7-222">配色</span><span class="sxs-lookup"><span data-stu-id="052e7-222">Color scheme</span></span>

<span data-ttu-id="052e7-223">これは、プロファイルで使用される配色の名前です。</span><span class="sxs-lookup"><span data-stu-id="052e7-223">This is the name of the color scheme used in the profile.</span></span> <span data-ttu-id="052e7-224">配色は `schemes` オブジェクトで定義されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-224">Color schemes are defined in the `schemes` object.</span></span> <span data-ttu-id="052e7-225">詳細については、[配色に関するページ](./color-schemes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="052e7-225">More detailed information can be found on the [Color schemes page](./color-schemes.md).</span></span>

<span data-ttu-id="052e7-226">**プロパティ名:** `colorScheme`</span><span class="sxs-lookup"><span data-stu-id="052e7-226">**Property name:** `colorScheme`</span></span>

<span data-ttu-id="052e7-227">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-227">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-228">**受け入れ可能:** 配色の名前を表す文字列</span><span class="sxs-lookup"><span data-stu-id="052e7-228">**Accepts:** Name of color scheme as a string</span></span>

<span data-ttu-id="052e7-229">**既定値:** `"Campbell"`</span><span class="sxs-lookup"><span data-stu-id="052e7-229">**Default value:** `"Campbell"`</span></span>

### <a name="foreground-color"></a><span data-ttu-id="052e7-230">前景色</span><span class="sxs-lookup"><span data-stu-id="052e7-230">Foreground color</span></span>

<span data-ttu-id="052e7-231">これにより、プロファイルの前景色が変更されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-231">This changes the foreground color of the profile.</span></span> <span data-ttu-id="052e7-232">これにより、配色で設定された `foreground` がオーバーライドされます (`colorScheme` が設定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="052e7-232">This overrides `foreground` set in the color scheme if `colorScheme` is set.</span></span>

<span data-ttu-id="052e7-233">**プロパティ名:** `foreground`</span><span class="sxs-lookup"><span data-stu-id="052e7-233">**Property name:** `foreground`</span></span>

<span data-ttu-id="052e7-234">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-234">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-235">**受け入れ可能:** 色を表す 16 進形式の文字列: `"#rgb"` または `"#rrggbb"`</span><span class="sxs-lookup"><span data-stu-id="052e7-235">**Accepts:** Color as a string in hex format: `"#rgb"` or `"#rrggbb"`</span></span>

### <a name="background-color"></a><span data-ttu-id="052e7-236">背景の色</span><span class="sxs-lookup"><span data-stu-id="052e7-236">Background color</span></span>

<span data-ttu-id="052e7-237">これにより、プロファイルの背景色がこの設定で変更されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-237">This changes the background color of the profile with this setting.</span></span> <span data-ttu-id="052e7-238">これにより、配色で設定された `background` がオーバーライドされます (`colorScheme` が設定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="052e7-238">This overrides `background` set in the color scheme if `colorScheme` is set.</span></span>

<span data-ttu-id="052e7-239">**プロパティ名:** `background`</span><span class="sxs-lookup"><span data-stu-id="052e7-239">**Property name:** `background`</span></span>

<span data-ttu-id="052e7-240">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-240">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-241">**受け入れ可能:** 色を表す 16 進形式の文字列: `"#rgb"` または `"#rrggbb"`</span><span class="sxs-lookup"><span data-stu-id="052e7-241">**Accepts:** Color as a string in hex format: `"#rgb"` or `"#rrggbb"`</span></span>

### <a name="selection-background-color"></a><span data-ttu-id="052e7-242">選択範囲の背景色</span><span class="sxs-lookup"><span data-stu-id="052e7-242">Selection background color</span></span>

<span data-ttu-id="052e7-243">これにより、プロファイル内の選択範囲の背景色が設定されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-243">This sets the background color of a selection within the profile.</span></span> <span data-ttu-id="052e7-244">これにより、配色で設定された `selectionBackground` がオーバーライドされます (`colorScheme` が設定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="052e7-244">This will override the `selectionBackground` set in the color scheme if `colorScheme` is set.</span></span>

<span data-ttu-id="052e7-245">**プロパティ名:** `selectionBackground`</span><span class="sxs-lookup"><span data-stu-id="052e7-245">**Property name:** `selectionBackground`</span></span>

<span data-ttu-id="052e7-246">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-246">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-247">**受け入れ可能:** 色を表す 16 進形式の文字列: `"#rgb"` または `"#rrggbb"`</span><span class="sxs-lookup"><span data-stu-id="052e7-247">**Accepts:** Color as a string in hex format: `"#rgb"` or `"#rrggbb"`</span></span>

<br />

___

## <a name="acrylic-settings"></a><span data-ttu-id="052e7-248">アクリルの設定</span><span class="sxs-lookup"><span data-stu-id="052e7-248">Acrylic settings</span></span>

### <a name="enable-acrylic"></a><span data-ttu-id="052e7-249">アクリルを有効にする</span><span class="sxs-lookup"><span data-stu-id="052e7-249">Enable acrylic</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="052e7-250">これを `true` に設定すると、ウィンドウにアクリルの背景が表示されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-250">When this is set to `true`, the window will have an acrylic background.</span></span> <span data-ttu-id="052e7-251">`false` に設定すると、ウィンドウは無地の平坦な背景になります。</span><span class="sxs-lookup"><span data-stu-id="052e7-251">When it's set to `false`, the window will have a plain, untextured background.</span></span> <span data-ttu-id="052e7-252">透過性は、OS の制限のため、フォーカスされているウィンドウにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-252">The transparency only applies to focused windows due to OS limitations.</span></span>

<span data-ttu-id="052e7-253">**プロパティ名:** `useAcrylic`</span><span class="sxs-lookup"><span data-stu-id="052e7-253">**Property name:** `useAcrylic`</span></span>

<span data-ttu-id="052e7-254">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-254">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-255">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="052e7-255">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="052e7-256">**既定値:** `false`</span><span class="sxs-lookup"><span data-stu-id="052e7-256">**Default value:** `false`</span></span>

:::column-end:::
:::column span="":::
![Windows ターミナルのアクリル](./../images/acrylic.gif)

:::column-end:::
:::row-end:::

### <a name="acrylic-opacity"></a><span data-ttu-id="052e7-258">アクリルの不透明度</span><span class="sxs-lookup"><span data-stu-id="052e7-258">Acrylic opacity</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="052e7-259">`useAcrylic` が `true` に設定されている場合、これによりプロファイルのウィンドウの透明度が設定されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-259">When `useAcrylic` is set to `true`, this sets the transparency of the window for the profile.</span></span> <span data-ttu-id="052e7-260">0 - 1 の浮動小数点値が受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="052e7-260">This accepts floating point values from 0-1.</span></span>

<span data-ttu-id="052e7-261">**プロパティ名:** `acrylicOpacity`</span><span class="sxs-lookup"><span data-stu-id="052e7-261">**Property name:** `acrylicOpacity`</span></span>

<span data-ttu-id="052e7-262">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-262">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-263">**受け入れ可能:** 0 - 1 の浮動小数点値の数値</span><span class="sxs-lookup"><span data-stu-id="052e7-263">**Accepts:** Number as a floating point value from 0-1</span></span>

<span data-ttu-id="052e7-264">**既定値:** `0.5`</span><span class="sxs-lookup"><span data-stu-id="052e7-264">**Default value:** `0.5`</span></span>

:::column-end:::
:::column span="":::
![Windows ターミナル アクリルの不透明度](./../images/acrylic-opacity.gif)

:::column-end:::
:::row-end:::

<br />

___

## <a name="background-image-settings"></a><span data-ttu-id="052e7-266">背景画像の設定</span><span class="sxs-lookup"><span data-stu-id="052e7-266">Background image settings</span></span>

### <a name="setting-the-background-image"></a><span data-ttu-id="052e7-267">背景画像を設定する</span><span class="sxs-lookup"><span data-stu-id="052e7-267">Setting the background image</span></span>

<span data-ttu-id="052e7-268">これにより、ウィンドウの背景に描画する画像のファイルの場所が設定されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-268">This sets the file location of the image to draw over the window background.</span></span> <span data-ttu-id="052e7-269">背景画像には、.jpg、.png、.gif のいずれかのファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="052e7-269">The background image can be a .jpg, .png, or .gif file.</span></span>

<span data-ttu-id="052e7-270">**プロパティ名:** `backgroundImage`</span><span class="sxs-lookup"><span data-stu-id="052e7-270">**Property name:** `backgroundImage`</span></span>

<span data-ttu-id="052e7-271">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-271">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-272">**受け入れ可能:** ファイルの場所を表す文字列</span><span class="sxs-lookup"><span data-stu-id="052e7-272">**Accepts:** File location as a string</span></span>

### <a name="background-image-stretch-mode"></a><span data-ttu-id="052e7-273">背景画像のストレッチ モード</span><span class="sxs-lookup"><span data-stu-id="052e7-273">Background image stretch mode</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="052e7-274">これにより、ウィンドウいっぱいに広がるように背景画像のサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-274">This sets how the background image is resized to fill the window.</span></span>

<span data-ttu-id="052e7-275">**プロパティ名:** `backgroundImageStretchMode`</span><span class="sxs-lookup"><span data-stu-id="052e7-275">**Property name:** `backgroundImageStretchMode`</span></span>

<span data-ttu-id="052e7-276">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-276">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-277">**受け入れ可能:** `"none"`、`"fill"`、`"uniform"`、`"uniformToFill"`</span><span class="sxs-lookup"><span data-stu-id="052e7-277">**Accepts:** `"none"`, `"fill"`, `"uniform"`, `"uniformToFill"`</span></span>

<span data-ttu-id="052e7-278">**既定値:** `"uniformToFill"`</span><span class="sxs-lookup"><span data-stu-id="052e7-278">**Default value:** `"uniformToFill"`</span></span>

:::column-end:::
:::column span="":::
<span data-ttu-id="052e7-279">![Windows ターミナルの背景画像のストレッチ モード](./../images/background-image-stretch-mode.gif)
 _[背景画像のソース](https://wallpaperhub.app/wallpapers/6287)_</span><span class="sxs-lookup"><span data-stu-id="052e7-279">![Windows Terminal background image stretch mode](./../images/background-image-stretch-mode.gif)
_[Background image source](https://wallpaperhub.app/wallpapers/6287)_</span></span>

:::column-end:::
:::row-end:::

### <a name="background-image-alignment"></a><span data-ttu-id="052e7-280">背景画像の配置</span><span class="sxs-lookup"><span data-stu-id="052e7-280">Background image alignment</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="052e7-281">これにより、ウィンドウの境界への背景画像の配置方法が設定されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-281">This sets how the background image aligns to the boundaries of the window.</span></span>

<span data-ttu-id="052e7-282">**プロパティ名:** `backgroundImageAlignment`</span><span class="sxs-lookup"><span data-stu-id="052e7-282">**Property name:** `backgroundImageAlignment`</span></span>

<span data-ttu-id="052e7-283">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-283">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-284">**受け入れ可能:** `"center"`、`"left"`、`"top"`、`"right"`、`"bottom"`、`"topLeft"`、`"topRight"`、`"bottomLeft"`、`"bottomRight"`</span><span class="sxs-lookup"><span data-stu-id="052e7-284">**Accepts:** `"center"`, `"left"`, `"top"`, `"right"`, `"bottom"`, `"topLeft"`, `"topRight"`, `"bottomLeft"`, `"bottomRight"`</span></span>

<span data-ttu-id="052e7-285">**既定値:** `"center"`</span><span class="sxs-lookup"><span data-stu-id="052e7-285">**Default value:** `"center"`</span></span>

:::column-end:::
:::column span="":::
<span data-ttu-id="052e7-286">![Windows ターミナルの背景画像の配置](./../images/background-image-alignment.gif)
 _[背景画像のソース](https://design.ubuntu.com/brand/ubuntu-logo/)_</span><span class="sxs-lookup"><span data-stu-id="052e7-286">![Windows Terminal background image alignment](./../images/background-image-alignment.gif)
_[Background image source](https://design.ubuntu.com/brand/ubuntu-logo/)_</span></span>

:::column-end:::
:::row-end:::

### <a name="background-image-opacity"></a><span data-ttu-id="052e7-287">背景画像の不透明度</span><span class="sxs-lookup"><span data-stu-id="052e7-287">Background image opacity</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="052e7-288">これにより、背景画像の透明度が設定されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-288">This sets the transparency of the background image.</span></span>

:::column-end:::
:::row-end:::

<span data-ttu-id="052e7-289">**プロパティ名:** `backgroundImageOpacity`</span><span class="sxs-lookup"><span data-stu-id="052e7-289">**Property name:** `backgroundImageOpacity`</span></span>

<span data-ttu-id="052e7-290">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-290">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-291">**受け入れ可能:** 0 - 1 の浮動小数点値の数値</span><span class="sxs-lookup"><span data-stu-id="052e7-291">**Accepts:** Number as a floating point value from 0-1</span></span>

<span data-ttu-id="052e7-292">**既定値:** `1.0`</span><span class="sxs-lookup"><span data-stu-id="052e7-292">**Default value:** `1.0`</span></span>

<br />

___

## <a name="scroll-settings"></a><span data-ttu-id="052e7-293">スクロールの設定</span><span class="sxs-lookup"><span data-stu-id="052e7-293">Scroll settings</span></span>

### <a name="scrollbar-visibility"></a><span data-ttu-id="052e7-294">スクロールバーの表示</span><span class="sxs-lookup"><span data-stu-id="052e7-294">Scrollbar visibility</span></span>

<span data-ttu-id="052e7-295">これにより、スクロールバーの表示が設定されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-295">This sets the visibility of the scrollbar.</span></span>

<span data-ttu-id="052e7-296">**プロパティ名:** `scrollbarState`</span><span class="sxs-lookup"><span data-stu-id="052e7-296">**Property name:** `scrollbarState`</span></span>

<span data-ttu-id="052e7-297">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-297">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-298">**受け入れ可能:** `"visible"`、`"hidden"`</span><span class="sxs-lookup"><span data-stu-id="052e7-298">**Accepts:** `"visible"`, `"hidden"`</span></span>

### <a name="scroll-to-input-line-when-typing"></a><span data-ttu-id="052e7-299">入力時に入力行までスクロール</span><span class="sxs-lookup"><span data-stu-id="052e7-299">Scroll to input line when typing</span></span>

<span data-ttu-id="052e7-300">これを `true` に設定すると、入力時にウィンドウがコマンド入力行までスクロールします。</span><span class="sxs-lookup"><span data-stu-id="052e7-300">When this is set to `true`, the window will scroll to the command input line when typing.</span></span> <span data-ttu-id="052e7-301">`false` に設定されている場合、入力を開始してもウィンドウはスクロールしません。</span><span class="sxs-lookup"><span data-stu-id="052e7-301">When it's set to `false`, the window will not scroll when you start typing.</span></span>

<span data-ttu-id="052e7-302">**プロパティ名:** `snapOnInput`</span><span class="sxs-lookup"><span data-stu-id="052e7-302">**Property name:** `snapOnInput`</span></span>

<span data-ttu-id="052e7-303">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-303">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-304">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="052e7-304">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="052e7-305">**既定値:** `true`</span><span class="sxs-lookup"><span data-stu-id="052e7-305">**Default value:** `true`</span></span>

### <a name="history-size"></a><span data-ttu-id="052e7-306">履歴のサイズ</span><span class="sxs-lookup"><span data-stu-id="052e7-306">History size</span></span>

<span data-ttu-id="052e7-307">これにより、ウィンドウに表示されているよりも上の行にスクロールして戻すことができる行の数が設定されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-307">This sets the number of lines above the ones displayed in the window you can scroll back to.</span></span>

<span data-ttu-id="052e7-308">**プロパティ名:** `historySize`</span><span class="sxs-lookup"><span data-stu-id="052e7-308">**Property name:** `historySize`</span></span>

<span data-ttu-id="052e7-309">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-309">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-310">**値:** 整数</span><span class="sxs-lookup"><span data-stu-id="052e7-310">**Accepts:** Integer</span></span>

<span data-ttu-id="052e7-311">**既定値:** `9001`</span><span class="sxs-lookup"><span data-stu-id="052e7-311">**Default value:** `9001`</span></span>

<br />

___

## <a name="how-the-profile-closes-when-exiting"></a><span data-ttu-id="052e7-312">終了時のプロファイルの閉じ方</span><span class="sxs-lookup"><span data-stu-id="052e7-312">How the profile closes when exiting</span></span>

<span data-ttu-id="052e7-313">これにより、プロファイルが終了または起動に失敗したときにどのように反応するかが設定されます。</span><span class="sxs-lookup"><span data-stu-id="052e7-313">This sets how the profile reacts to termination or failure to launch.</span></span> <span data-ttu-id="052e7-314">`"graceful"` は、`exit` が入力されたとき、またはプロセスが正常に終了したときに、プロファイルを閉じます。</span><span class="sxs-lookup"><span data-stu-id="052e7-314">`"graceful"` will close the profile when `exit` is typed or when the process exits normally.</span></span> <span data-ttu-id="052e7-315">`"always"` は常にプロファイルを閉じ、`"never"` はプロファイルを閉じません。</span><span class="sxs-lookup"><span data-stu-id="052e7-315">`"always"` will always close the profile and `"never"` will never close the profile.</span></span> <span data-ttu-id="052e7-316">`true` と `false` は、それぞれ `"graceful"` と `"never"` のシノニムとして受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="052e7-316">`true` and `false` are accepted as synonyms for `"graceful"` and `"never"`, respectively.</span></span>

<span data-ttu-id="052e7-317">**プロパティ名:** `closeOnExit`</span><span class="sxs-lookup"><span data-stu-id="052e7-317">**Property name:** `closeOnExit`</span></span>

<span data-ttu-id="052e7-318">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-318">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-319">**受け入れ可能:** `"graceful"`、`"always"`、`"never"`、`true`、`false`</span><span class="sxs-lookup"><span data-stu-id="052e7-319">**Accepts:** `"graceful"`, `"always"`, `"never"`, `true`, `false`</span></span>

<span data-ttu-id="052e7-320">**既定値:** `"graceful"`</span><span class="sxs-lookup"><span data-stu-id="052e7-320">**Default value:** `"graceful"`</span></span>

<br />

___

## <a name="retro-terminal-effects"></a><span data-ttu-id="052e7-321">レトロ ターミナル効果</span><span class="sxs-lookup"><span data-stu-id="052e7-321">Retro terminal effects</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="052e7-322">これを `true` に設定すると、走査線やぼやけたテキストの端がある古い CRT ディスプレイがターミナルでエミュレートされます。</span><span class="sxs-lookup"><span data-stu-id="052e7-322">When this is set to `true`, the terminal will emulate a classic CRT display with scan lines and blurry text edges.</span></span> <span data-ttu-id="052e7-323">これは試験的な機能であり、存続は保証されていません。</span><span class="sxs-lookup"><span data-stu-id="052e7-323">This is an experimental feature and its continued existence is not guaranteed.</span></span>

<span data-ttu-id="052e7-324">**プロパティ名:** `experimental.retroTerminalEffect`</span><span class="sxs-lookup"><span data-stu-id="052e7-324">**Property name:** `experimental.retroTerminalEffect`</span></span>

<span data-ttu-id="052e7-325">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="052e7-325">**Necessity:** Optional</span></span>

<span data-ttu-id="052e7-326">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="052e7-326">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="052e7-327">**既定値:** `false`</span><span class="sxs-lookup"><span data-stu-id="052e7-327">**Default value:** `false`</span></span>

:::column-end:::
:::column span="":::
<span data-ttu-id="052e7-328">![Windows ターミナルの実験的なレトロ ターミナル効果](./../images/experimental-retro-terminal-effect.gif)
_構成:[レトロ コマンド プロンプト](./../custom-terminal-gallery/retro-command-prompt.md)_</span><span class="sxs-lookup"><span data-stu-id="052e7-328">![Windows Terminal experimental retro terminal effect](./../images/experimental-retro-terminal-effect.gif)
_Configuration: [Retro Command Prompt](./../custom-terminal-gallery/retro-command-prompt.md)_</span></span>

:::column-end:::
:::row-end:::
