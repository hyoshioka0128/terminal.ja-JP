---
title: Windows ターミナル プロファイルの設定
description: Windows ターミナル内の個々のプロファイルをカスタマイズする方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 06/18/2020
ms.topic: how-to
ms.service: terminal
ms.localizationpriority: high
ms.openlocfilehash: ad7121f9cd6583562c03bf0e35d2928f46fe5d91
ms.sourcegitcommit: 91a802863cd0730d2e364377ffe44f819a66ff2a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84994391"
---
# <a name="profile-settings-in-windows-terminal"></a><span data-ttu-id="dc159-103">Windows ターミナルでのプロファイル設定</span><span class="sxs-lookup"><span data-stu-id="dc159-103">Profile settings in Windows Terminal</span></span>

<span data-ttu-id="dc159-104">以下に示す設定は、それぞれ一意のプロファイルに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="dc159-104">The settings listed below are specific to each unique profile.</span></span> <span data-ttu-id="dc159-105">設定を自分のすべてのプロファイルに適用する場合は、ご自分の settings.json ファイル内のプロファイルの一覧の上にある `defaults` セクションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="dc159-105">If you'd like a setting to apply to all of your profiles, you can add it to the `defaults` section above the list of profiles in your settings.json file.</span></span>

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

## <a name="unique-identifier"></a><span data-ttu-id="dc159-106">一意識別子</span><span class="sxs-lookup"><span data-stu-id="dc159-106">Unique identifier</span></span>

<span data-ttu-id="dc159-107">プロファイルでは、GUID を一意の識別子として使用できます。</span><span class="sxs-lookup"><span data-stu-id="dc159-107">Profiles can use a GUID as a unique identifier.</span></span> <span data-ttu-id="dc159-108">プロファイルを既定のプロファイルにするには、`defaultProfile` グローバル設定の GUID が必要です。</span><span class="sxs-lookup"><span data-stu-id="dc159-108">To make a profile your default profile, it needs a GUID for the `defaultProfile` global setting.</span></span>

<span data-ttu-id="dc159-109">**プロパティ名:** `guid`</span><span class="sxs-lookup"><span data-stu-id="dc159-109">**Property name:** `guid`</span></span>

<span data-ttu-id="dc159-110">**必須かどうか:** 必須</span><span class="sxs-lookup"><span data-stu-id="dc159-110">**Necessity:** Required</span></span>

<span data-ttu-id="dc159-111">**受け入れ可能:** レジストリ形式の GUID を表す文字列: `"{00000000-0000-0000-0000-000000000000}"`</span><span class="sxs-lookup"><span data-stu-id="dc159-111">**Accepts:** GUID as a string in registry format: `"{00000000-0000-0000-0000-000000000000}"`</span></span>

<br />

___

## <a name="executable-settings"></a><span data-ttu-id="dc159-112">実行可能ファイルの設定</span><span class="sxs-lookup"><span data-stu-id="dc159-112">Executable settings</span></span>

### <a name="command-line"></a><span data-ttu-id="dc159-113">コマンド ライン</span><span class="sxs-lookup"><span data-stu-id="dc159-113">Command line</span></span>

<span data-ttu-id="dc159-114">これは、プロファイルで使用される実行可能ファイルです。</span><span class="sxs-lookup"><span data-stu-id="dc159-114">This is the executable used in the profile.</span></span>

<span data-ttu-id="dc159-115">**プロパティ名:** `commandline`</span><span class="sxs-lookup"><span data-stu-id="dc159-115">**Property name:** `commandline`</span></span>

<span data-ttu-id="dc159-116">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-116">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-117">**受け入れ可能:** 実行可能ファイル名を表す文字列</span><span class="sxs-lookup"><span data-stu-id="dc159-117">**Accepts:** Executable file name as a string</span></span>

<span data-ttu-id="dc159-118">**既定値:** `"cmd.exe"`</span><span class="sxs-lookup"><span data-stu-id="dc159-118">**Default value:** `"cmd.exe"`</span></span>

### <a name="source"></a><span data-ttu-id="dc159-119">ソース</span><span class="sxs-lookup"><span data-stu-id="dc159-119">Source</span></span>

<span data-ttu-id="dc159-120">これには、プロファイルを生成したプロファイル ジェネレーターの名前が格納されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-120">This stores the name of the profile generator that originated the profile.</span></span> <span data-ttu-id="dc159-121">_このフィールドには検出可能な値がありません。_</span><span class="sxs-lookup"><span data-stu-id="dc159-121">_There are no discoverable values for this field._</span></span> <span data-ttu-id="dc159-122">動的プロファイルの詳細については、[動的プロファイルに関するページ](./../dynamic-profiles.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc159-122">For additional information on dynamic profiles, visit the [Dynamic profiles page](./../dynamic-profiles.md).</span></span>

<span data-ttu-id="dc159-123">**プロパティ名:** `source`</span><span class="sxs-lookup"><span data-stu-id="dc159-123">**Property name:** `source`</span></span>

<span data-ttu-id="dc159-124">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-124">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-125">**受け入れ可能:** String</span><span class="sxs-lookup"><span data-stu-id="dc159-125">**Accepts:** String</span></span>

### <a name="starting-directory"></a><span data-ttu-id="dc159-126">開始ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="dc159-126">Starting directory</span></span>

<span data-ttu-id="dc159-127">これは、シェルが読み込まれるときに開始されるディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="dc159-127">This is the directory the shell starts in when it is loaded.</span></span>

<span data-ttu-id="dc159-128">**プロパティ名:** `startingDirectory`</span><span class="sxs-lookup"><span data-stu-id="dc159-128">**Property name:** `startingDirectory`</span></span>

<span data-ttu-id="dc159-129">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-129">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-130">**受け入れ可能:** フォルダーの場所を表す文字列</span><span class="sxs-lookup"><span data-stu-id="dc159-130">**Accepts:** Folder location as a string</span></span>

<span data-ttu-id="dc159-131">**既定値:** `"%USERPROFILE%"`</span><span class="sxs-lookup"><span data-stu-id="dc159-131">**Default value:** `"%USERPROFILE%"`</span></span>

<br />

> [!NOTE]
> <span data-ttu-id="dc159-132">インストールされている WSL ディストリビューションを開く開始ディレクトリを設定する際に、"startingDirectory": "//wsl$/<distro name>" の形式を使用し、お使いのディストリビューションの名前に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc159-132">When setting the starting directory that your installed WSL distributions open to, you should use this format: "startingDirectory": "//wsl$/<distro name>", replacing with the name of your distribution.</span></span> <span data-ttu-id="dc159-133">たとえば、"startingDirectory": "//wsl$/Ubuntu-20.04" のようになります。</span><span class="sxs-lookup"><span data-stu-id="dc159-133">For example, "startingDirectory": "//wsl$/Ubuntu-20.04".</span></span>

___

## <a name="dropdown-settings"></a><span data-ttu-id="dc159-134">ドロップダウンの設定</span><span class="sxs-lookup"><span data-stu-id="dc159-134">Dropdown settings</span></span>

<span data-ttu-id="dc159-135">![Windows ターミナルのドロップダウン](./../images/dropdown.png)
_構成:[Raspberry Ubuntu](./../custom-terminal-gallery/raspberry-ubuntu.md)_</span><span class="sxs-lookup"><span data-stu-id="dc159-135">![Windows Terminal dropdown](./../images/dropdown.png)
_Configuration: [Raspberry Ubuntu](./../custom-terminal-gallery/raspberry-ubuntu.md)_</span></span>

### <a name="name"></a><span data-ttu-id="dc159-136">名前</span><span class="sxs-lookup"><span data-stu-id="dc159-136">Name</span></span>

<span data-ttu-id="dc159-137">これは、ドロップダウン メニューに表示されるプロファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="dc159-137">This is the name of the profile that will be displayed in the dropdown menu.</span></span> <span data-ttu-id="dc159-138">この値は、起動時にシェルに渡す "タイトル" としても使用されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-138">This value is also used as the "title" to pass to the shell on startup.</span></span> <span data-ttu-id="dc159-139">一部のシェル (`bash` など) では、この初期値を無視することができますが、他のシェル (`Command Prompt`、`PowerShell`) では、アプリケーションの有効期間中、この値を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="dc159-139">Some shells (like `bash`) may choose to ignore this initial value, while others (`Command Prompt`, `PowerShell`) may use this value over the lifetime of the application.</span></span> <span data-ttu-id="dc159-140">この "タイトル" の動作は、`tabTitle` を使用してオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="dc159-140">This "title" behavior can be overridden by using `tabTitle`.</span></span>

<span data-ttu-id="dc159-141">**プロパティ名:** `name`</span><span class="sxs-lookup"><span data-stu-id="dc159-141">**Property name:** `name`</span></span>

<span data-ttu-id="dc159-142">**必須かどうか:** 必須</span><span class="sxs-lookup"><span data-stu-id="dc159-142">**Necessity:** Required</span></span>

<span data-ttu-id="dc159-143">**受け入れ可能:** String</span><span class="sxs-lookup"><span data-stu-id="dc159-143">**Accepts:** String</span></span>

### <a name="icon"></a><span data-ttu-id="dc159-144">［アイコン］</span><span class="sxs-lookup"><span data-stu-id="dc159-144">Icon</span></span>

<span data-ttu-id="dc159-145">これにより、タブとドロップダウン メニュー内に表示されるアイコンが設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-145">This sets the icon that displays within the tab and the dropdown menu.</span></span>

<span data-ttu-id="dc159-146">**プロパティ名:** `icon`</span><span class="sxs-lookup"><span data-stu-id="dc159-146">**Property name:** `icon`</span></span>

<span data-ttu-id="dc159-147">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-147">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-148">**受け入れ可能:** ファイルの場所を表す文字列</span><span class="sxs-lookup"><span data-stu-id="dc159-148">**Accepts:** File location as a string</span></span>

### <a name="hide-a-profile-from-the-dropdown"></a><span data-ttu-id="dc159-149">ドロップダウンからプロファイルを非表示にする</span><span class="sxs-lookup"><span data-stu-id="dc159-149">Hide a profile from the dropdown</span></span>

<span data-ttu-id="dc159-150">`hidden` が `true` に設定されている場合、そのプロファイルはプロファイルの一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="dc159-150">If `hidden` is set to `true`, the profile will not appear in the list of profiles.</span></span> <span data-ttu-id="dc159-151">これを使用すると、既定のプロファイルと動的に生成されたプロファイルを設定ファイルに残したまま、非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="dc159-151">This can be used to hide default profiles and dynamically generated profiles, while leaving them in your settings file.</span></span> <span data-ttu-id="dc159-152">動的プロファイルの詳細については、[動的プロファイルに関するページ](./../dynamic-profiles.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc159-152">To learn more about dynamic profiles, visit the [Dynamic profiles page](./../dynamic-profiles.md).</span></span>

<span data-ttu-id="dc159-153">**プロパティ名:** `hidden`</span><span class="sxs-lookup"><span data-stu-id="dc159-153">**Property name:** `hidden`</span></span>

<span data-ttu-id="dc159-154">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-154">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-155">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="dc159-155">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="dc159-156">**既定値:** `false`</span><span class="sxs-lookup"><span data-stu-id="dc159-156">**Default value:** `false`</span></span>

<br />

___

## <a name="tab-title-settings"></a><span data-ttu-id="dc159-157">タブ タイトルの設定</span><span class="sxs-lookup"><span data-stu-id="dc159-157">Tab title settings</span></span>

### <a name="custom-tab-title"></a><span data-ttu-id="dc159-158">カスタム タブのタイトル</span><span class="sxs-lookup"><span data-stu-id="dc159-158">Custom tab title</span></span>

<span data-ttu-id="dc159-159">設定すると、起動時にシェルに渡すタイトルとして `name` が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="dc159-159">If set, this will replace the `name` as the title to pass to the shell on startup.</span></span> <span data-ttu-id="dc159-160">一部のシェル (`bash` など) では、この初期値を無視することができますが、他のシェル (`Command Prompt`、`PowerShell`) では、アプリケーションの有効期間中、この値を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="dc159-160">Some shells (like `bash`) may choose to ignore this initial value, while others (`Command Prompt`, `PowerShell`) may use this value over the lifetime of the application.</span></span> <span data-ttu-id="dc159-161">シェルでタイトルを設定する方法については、[タブ タイトルのチュートリアル](./../tutorials/tab-title.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc159-161">If you'd like to learn how to have the shell set your title, visit the [tab title tutorial](./../tutorials/tab-title.md).</span></span>

<span data-ttu-id="dc159-162">**プロパティ名:** `tabTitle`</span><span class="sxs-lookup"><span data-stu-id="dc159-162">**Property name:** `tabTitle`</span></span>

<span data-ttu-id="dc159-163">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-163">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-164">**受け入れ可能:** String</span><span class="sxs-lookup"><span data-stu-id="dc159-164">**Accepts:** String</span></span>

### <a name="suppress-title-changes-from-the-shell"></a><span data-ttu-id="dc159-165">シェルからのタイトルの変更を抑制する</span><span class="sxs-lookup"><span data-stu-id="dc159-165">Suppress title changes from the shell</span></span>

<span data-ttu-id="dc159-166">これが `true` に設定されている場合、`tabTitle` によってタブの既定のタイトルがオーバーライドされ、アプリケーションからのタイトルの変更メッセージはすべて抑制されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-166">When this is set to `true`, `tabTitle` overrides the default title of the tab and any title change messages from the application will be suppressed.</span></span> <span data-ttu-id="dc159-167">`tabTitle` が設定されていない場合は、代わりに `name` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-167">If `tabTitle` isn't set, `name` will be used instead.</span></span> <span data-ttu-id="dc159-168">これが `false` に設定されている場合、`tabTitle` は通常どおりに動作します。</span><span class="sxs-lookup"><span data-stu-id="dc159-168">When this is set to `false`, `tabTitle` behaves as normal.</span></span>

<span data-ttu-id="dc159-169">**プロパティ名:** `suppressApplicationTitle`</span><span class="sxs-lookup"><span data-stu-id="dc159-169">**Property name:** `suppressApplicationTitle`</span></span>

<span data-ttu-id="dc159-170">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-170">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-171">**受け入れ可能:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="dc159-171">**Accepts:** `true`, `false`</span></span>

<br />

___

## <a name="text-settings"></a><span data-ttu-id="dc159-172">テキストの設定</span><span class="sxs-lookup"><span data-stu-id="dc159-172">Text settings</span></span>

### <a name="font-face"></a><span data-ttu-id="dc159-173">フォント フェイス</span><span class="sxs-lookup"><span data-stu-id="dc159-173">Font face</span></span>

<span data-ttu-id="dc159-174">これは、プロファイルで使用されるフォント フェイスの名前です。</span><span class="sxs-lookup"><span data-stu-id="dc159-174">This is the name of the font face used in the profile.</span></span> <span data-ttu-id="dc159-175">これが見つからないか無効である場合は、ターミナルによって Consolas へのフォールバックが試行されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-175">The terminal will try to fallback to Consolas if this can't be found or is invalid.</span></span> <span data-ttu-id="dc159-176">既定のフォント Cascadia Mono のその他のバリアントについては、[Cascadia Code に関するページ](./../cascadia-code.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc159-176">To learn about the other variants of the default font, Cascadia Mono, visit the [Cascadia Code page](./../cascadia-code.md).</span></span>

<span data-ttu-id="dc159-177">**プロパティ名:** `fontFace`</span><span class="sxs-lookup"><span data-stu-id="dc159-177">**Property name:** `fontFace`</span></span>

<span data-ttu-id="dc159-178">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-178">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-179">**受け入れ可能:** フォント名を表す文字列</span><span class="sxs-lookup"><span data-stu-id="dc159-179">**Accepts:** Font name as a string</span></span>

<span data-ttu-id="dc159-180">**既定値:** `"Cascadia Mono"`</span><span class="sxs-lookup"><span data-stu-id="dc159-180">**Default value:** `"Cascadia Mono"`</span></span>

### <a name="font-size"></a><span data-ttu-id="dc159-181">フォント サイズ</span><span class="sxs-lookup"><span data-stu-id="dc159-181">Font size</span></span>

<span data-ttu-id="dc159-182">これにより、プロファイルのフォント サイズがポイント単位で設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-182">This sets the profile's font size in points.</span></span>

<span data-ttu-id="dc159-183">**プロパティ名:** `fontSize`</span><span class="sxs-lookup"><span data-stu-id="dc159-183">**Property name:** `fontSize`</span></span>

<span data-ttu-id="dc159-184">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-184">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-185">**値:** 整数</span><span class="sxs-lookup"><span data-stu-id="dc159-185">**Accepts:** Integer</span></span>

<span data-ttu-id="dc159-186">**既定値:** `12`</span><span class="sxs-lookup"><span data-stu-id="dc159-186">**Default value:** `12`</span></span>

### <a name="font-weight-preview"></a><span data-ttu-id="dc159-187">フォントの太さ ([プレビュー](https://aka.ms/terminal-preview/))</span><span class="sxs-lookup"><span data-stu-id="dc159-187">Font weight ([Preview](https://aka.ms/terminal-preview/))</span></span>

<span data-ttu-id="dc159-188">これにより、プロファイルのフォントの太さ (ストロークの明るさまたは太さ) が設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-188">This sets the weight (lightness or heaviness of the strokes) for the profile's font.</span></span>

<span data-ttu-id="dc159-189">**プロパティ名:** `fontWeight`</span><span class="sxs-lookup"><span data-stu-id="dc159-189">**Property name:** `fontWeight`</span></span>

<span data-ttu-id="dc159-190">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-190">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-191">**受け入れ可能:** `"normal"`、`"thin"`、`"extra-light"`、`"light"`、`"semi-light"`、`"medium"`、`"semi-bold"`、`"bold"`、`"extra-bold"`、`"black"`、`"extra-black"`、OpenType フォントの太さの数値表記に対応する整数</span><span class="sxs-lookup"><span data-stu-id="dc159-191">**Accepts:** `"normal"`, `"thin"`, `"extra-light"`, `"light"`, `"semi-light"`, `"medium"`, `"semi-bold"`, `"bold"`, `"extra-bold"`, `"black"`, `"extra-black"`, or an integer corresponding to the numeric representation of the OpenType font weight</span></span>

<span data-ttu-id="dc159-192">**既定値:** `"normal"`</span><span class="sxs-lookup"><span data-stu-id="dc159-192">**Default value:** `"normal"`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc159-193">この機能は、[Windows ターミナル プレビュー](https://aka.ms/terminal-preview/)でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="dc159-193">This feature is only available in [Windows Terminal Preview](https://aka.ms/terminal-preview/).</span></span>

### <a name="padding"></a><span data-ttu-id="dc159-194">余白</span><span class="sxs-lookup"><span data-stu-id="dc159-194">Padding</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="dc159-195">これにより、ウィンドウ内のテキストの周囲の余白が設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-195">This sets the padding around the text within the window.</span></span> <span data-ttu-id="dc159-196">これには、次の 3 つの異なる形式が使用できます。`"#"` は、すべての辺に同じ余白を設定し、`"#, #"` は左右と上下に同じ余白を設定し、`"#, #, #, #"` は左、上、右、下に個別に余白を設定します。</span><span class="sxs-lookup"><span data-stu-id="dc159-196">This will accept three different formats: `"#"` sets the same padding for all sides, `"#, #"` sets the same padding for left-right and top-bottom, and `"#, #, #, #"` sets the padding individually for left, top, right, and bottom.</span></span>

<span data-ttu-id="dc159-197">**プロパティ名:** `padding`</span><span class="sxs-lookup"><span data-stu-id="dc159-197">**Property name:** `padding`</span></span>

<span data-ttu-id="dc159-198">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-198">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-199">**受け入れ可能:** 次の形式の値を表す文字列: `"#"`、`"#, #"`、`"#, #, #, #"`</span><span class="sxs-lookup"><span data-stu-id="dc159-199">**Accepts:** Values as a string in the following formats: `"#"`, `"#, #"`, `"#, #, #, #"`</span></span>

<span data-ttu-id="dc159-200">**既定値:** `"8, 8, 8, 8"`</span><span class="sxs-lookup"><span data-stu-id="dc159-200">**Default value:** `"8, 8, 8, 8"`</span></span>

:::column-end:::
:::column span="":::
![Windows ターミナルの余白](./../images/padding.gif)

:::column-end:::
:::row-end:::

### <a name="antialiasing-text"></a><span data-ttu-id="dc159-202">アンチエイリアシング テキスト</span><span class="sxs-lookup"><span data-stu-id="dc159-202">Antialiasing text</span></span>

<span data-ttu-id="dc159-203">これは、レンダラーでテキストをアンチエイリアシングする方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="dc159-203">This controls how text is antialiased in the renderer.</span></span> <span data-ttu-id="dc159-204">この設定を変更すると、新しいターミナル インスタンスを開始する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dc159-204">Note that changing this setting will require starting a new terminal instance.</span></span>

![Windows ターミナルのアンチエイリアシング テキスト](./../images/antialiasing-mode.gif)

<span data-ttu-id="dc159-206">**プロパティ名:** `antialiasingMode`</span><span class="sxs-lookup"><span data-stu-id="dc159-206">**Property name:** `antialiasingMode`</span></span>

<span data-ttu-id="dc159-207">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-207">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-208">**値:** `"grayscale"`、`"cleartype"`、`"aliased"`</span><span class="sxs-lookup"><span data-stu-id="dc159-208">**Accepts:** `"grayscale"`, `"cleartype"`, `"aliased"`</span></span>

<span data-ttu-id="dc159-209">**既定値:** `"grayscale"`</span><span class="sxs-lookup"><span data-stu-id="dc159-209">**Default value:** `"grayscale"`</span></span>

<br />

___

## <a name="cursor-settings"></a><span data-ttu-id="dc159-210">カーソルの設定</span><span class="sxs-lookup"><span data-stu-id="dc159-210">Cursor settings</span></span>

### <a name="cursor-shape"></a><span data-ttu-id="dc159-211">カーソルの形</span><span class="sxs-lookup"><span data-stu-id="dc159-211">Cursor shape</span></span>

<span data-ttu-id="dc159-212">これにより、プロファイルのカーソルの形が設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-212">This sets the cursor shape for the profile.</span></span> <span data-ttu-id="dc159-213">使用可能なカーソル: `"bar"` ( &#x2503; )、`"vintage"` ( &#x2583; )、`"underscore"` ( &#x2581; )、`"filledBox"` ( &#x2588; )、`"emptyBox"` ( &#x25AF; )</span><span class="sxs-lookup"><span data-stu-id="dc159-213">The possible cursors are as follows: `"bar"` ( &#x2503; ), `"vintage"` ( &#x2583; ), `"underscore"` ( &#x2581; ), `"filledBox"` ( &#x2588; ), `"emptyBox"` ( &#x25AF; )</span></span>

<span data-ttu-id="dc159-214">**プロパティ名:** `cursorShape`</span><span class="sxs-lookup"><span data-stu-id="dc159-214">**Property name:** `cursorShape`</span></span>

<span data-ttu-id="dc159-215">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-215">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-216">**受け入れ可能:** `"bar"`、`"vintage"`、`"underscore"`、`"filledBox"`、`"emptyBox"`</span><span class="sxs-lookup"><span data-stu-id="dc159-216">**Accepts:** `"bar"`, `"vintage"`, `"underscore"`, `"filledBox"`, `"emptyBox"`</span></span>

<span data-ttu-id="dc159-217">**既定値:** `"bar"`</span><span class="sxs-lookup"><span data-stu-id="dc159-217">**Default value:** `"bar"`</span></span>

### <a name="cursor-color"></a><span data-ttu-id="dc159-218">カーソルの色</span><span class="sxs-lookup"><span data-stu-id="dc159-218">Cursor color</span></span>

<span data-ttu-id="dc159-219">これにより、プロファイルのカーソルの色が設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-219">This sets the cursor color of the profile.</span></span> <span data-ttu-id="dc159-220">これにより、配色で設定された `cursorColor` がオーバーライドされます (`colorScheme` が設定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="dc159-220">This will override the `cursorColor` set in the color scheme if `colorScheme` is set.</span></span>

<span data-ttu-id="dc159-221">**プロパティ名:** `cursorColor`</span><span class="sxs-lookup"><span data-stu-id="dc159-221">**Property name:** `cursorColor`</span></span>

<span data-ttu-id="dc159-222">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-222">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-223">**受け入れ可能:** 色を表す 16 進形式の文字列: `"#rgb"` または `"#rrggbb"`</span><span class="sxs-lookup"><span data-stu-id="dc159-223">**Accepts:** Color as a string in hex format: `"#rgb"` or `"#rrggbb"`</span></span>

### <a name="cursor-height"></a><span data-ttu-id="dc159-224">カーソルの高さ</span><span class="sxs-lookup"><span data-stu-id="dc159-224">Cursor height</span></span>

<span data-ttu-id="dc159-225">これにより、下部からのカーソルの高さの割合が設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-225">This sets the percentage height of the cursor starting from the bottom.</span></span> <span data-ttu-id="dc159-226">これは `cursorShape` が `"vintage"` に設定されている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="dc159-226">This will only work when `cursorShape` is set to `"vintage"`.</span></span>

<span data-ttu-id="dc159-227">**プロパティ名:** `cursorHeight`</span><span class="sxs-lookup"><span data-stu-id="dc159-227">**Property name:** `cursorHeight`</span></span>

<span data-ttu-id="dc159-228">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-228">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-229">**受け入れ可能:** 25 から 100 までの整数</span><span class="sxs-lookup"><span data-stu-id="dc159-229">**Accepts:** Integer from 25-100</span></span>

<br />

___

## <a name="keyboard-settings"></a><span data-ttu-id="dc159-230">キーボード設定</span><span class="sxs-lookup"><span data-stu-id="dc159-230">Keyboard settings</span></span>

### <a name="altgr-aliasing-preview"></a><span data-ttu-id="dc159-231">AltGr エイリアシング ([プレビュー](https://aka.ms/terminal-preview/))</span><span class="sxs-lookup"><span data-stu-id="dc159-231">AltGr aliasing ([Preview](https://aka.ms/terminal-preview/))</span></span>

<span data-ttu-id="dc159-232">これにより、Windows ターミナルで <kbd>ctrl+alt</kbd> を <kbd>AltGr</kbd> のエイリアスとして扱うかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="dc159-232">This allows you to control if Windows Terminal will treat <kbd>ctrl+alt</kbd> as an alias for <kbd>AltGr</kbd>.</span></span>

<span data-ttu-id="dc159-233">**プロパティ名:** `altGrAliasing`</span><span class="sxs-lookup"><span data-stu-id="dc159-233">**Property name:** `altGrAliasing`</span></span>

<span data-ttu-id="dc159-234">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-234">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-235">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="dc159-235">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="dc159-236">**既定値:** `true`</span><span class="sxs-lookup"><span data-stu-id="dc159-236">**Default value:** `true`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc159-237">この機能は、[Windows ターミナル プレビュー](https://aka.ms/terminal-preview/)でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="dc159-237">This feature is only available in [Windows Terminal Preview](https://aka.ms/terminal-preview/).</span></span>

<br />

___

## <a name="color-settings"></a><span data-ttu-id="dc159-238">色の設定</span><span class="sxs-lookup"><span data-stu-id="dc159-238">Color settings</span></span>

### <a name="color-scheme"></a><span data-ttu-id="dc159-239">配色</span><span class="sxs-lookup"><span data-stu-id="dc159-239">Color scheme</span></span>

<span data-ttu-id="dc159-240">これは、プロファイルで使用される配色の名前です。</span><span class="sxs-lookup"><span data-stu-id="dc159-240">This is the name of the color scheme used in the profile.</span></span> <span data-ttu-id="dc159-241">配色は `schemes` オブジェクトで定義されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-241">Color schemes are defined in the `schemes` object.</span></span> <span data-ttu-id="dc159-242">詳細については、[配色に関するページ](./color-schemes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc159-242">More detailed information can be found on the [Color schemes page](./color-schemes.md).</span></span>

<span data-ttu-id="dc159-243">**プロパティ名:** `colorScheme`</span><span class="sxs-lookup"><span data-stu-id="dc159-243">**Property name:** `colorScheme`</span></span>

<span data-ttu-id="dc159-244">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-244">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-245">**受け入れ可能:** 配色の名前を表す文字列</span><span class="sxs-lookup"><span data-stu-id="dc159-245">**Accepts:** Name of color scheme as a string</span></span>

<span data-ttu-id="dc159-246">**既定値:** `"Campbell"`</span><span class="sxs-lookup"><span data-stu-id="dc159-246">**Default value:** `"Campbell"`</span></span>

### <a name="foreground-color"></a><span data-ttu-id="dc159-247">前景色</span><span class="sxs-lookup"><span data-stu-id="dc159-247">Foreground color</span></span>

<span data-ttu-id="dc159-248">これにより、プロファイルの前景色が変更されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-248">This changes the foreground color of the profile.</span></span> <span data-ttu-id="dc159-249">これにより、配色で設定された `foreground` がオーバーライドされます (`colorScheme` が設定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="dc159-249">This overrides `foreground` set in the color scheme if `colorScheme` is set.</span></span>

<span data-ttu-id="dc159-250">**プロパティ名:** `foreground`</span><span class="sxs-lookup"><span data-stu-id="dc159-250">**Property name:** `foreground`</span></span>

<span data-ttu-id="dc159-251">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-251">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-252">**受け入れ可能:** 色を表す 16 進形式の文字列: `"#rgb"` または `"#rrggbb"`</span><span class="sxs-lookup"><span data-stu-id="dc159-252">**Accepts:** Color as a string in hex format: `"#rgb"` or `"#rrggbb"`</span></span>

### <a name="background-color"></a><span data-ttu-id="dc159-253">背景の色</span><span class="sxs-lookup"><span data-stu-id="dc159-253">Background color</span></span>

<span data-ttu-id="dc159-254">これにより、プロファイルの背景色がこの設定で変更されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-254">This changes the background color of the profile with this setting.</span></span> <span data-ttu-id="dc159-255">これにより、配色で設定された `background` がオーバーライドされます (`colorScheme` が設定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="dc159-255">This overrides `background` set in the color scheme if `colorScheme` is set.</span></span>

<span data-ttu-id="dc159-256">**プロパティ名:** `background`</span><span class="sxs-lookup"><span data-stu-id="dc159-256">**Property name:** `background`</span></span>

<span data-ttu-id="dc159-257">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-257">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-258">**受け入れ可能:** 色を表す 16 進形式の文字列: `"#rgb"` または `"#rrggbb"`</span><span class="sxs-lookup"><span data-stu-id="dc159-258">**Accepts:** Color as a string in hex format: `"#rgb"` or `"#rrggbb"`</span></span>

### <a name="selection-background-color"></a><span data-ttu-id="dc159-259">選択範囲の背景色</span><span class="sxs-lookup"><span data-stu-id="dc159-259">Selection background color</span></span>

<span data-ttu-id="dc159-260">これにより、プロファイル内の選択範囲の背景色が設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-260">This sets the background color of a selection within the profile.</span></span> <span data-ttu-id="dc159-261">これにより、配色で設定された `selectionBackground` がオーバーライドされます (`colorScheme` が設定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="dc159-261">This will override the `selectionBackground` set in the color scheme if `colorScheme` is set.</span></span>

<span data-ttu-id="dc159-262">**プロパティ名:** `selectionBackground`</span><span class="sxs-lookup"><span data-stu-id="dc159-262">**Property name:** `selectionBackground`</span></span>

<span data-ttu-id="dc159-263">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-263">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-264">**受け入れ可能:** 色を表す 16 進形式の文字列: `"#rgb"` または `"#rrggbb"`</span><span class="sxs-lookup"><span data-stu-id="dc159-264">**Accepts:** Color as a string in hex format: `"#rgb"` or `"#rrggbb"`</span></span>

<br />

___

## <a name="acrylic-settings"></a><span data-ttu-id="dc159-265">アクリルの設定</span><span class="sxs-lookup"><span data-stu-id="dc159-265">Acrylic settings</span></span>

### <a name="enable-acrylic"></a><span data-ttu-id="dc159-266">アクリルを有効にする</span><span class="sxs-lookup"><span data-stu-id="dc159-266">Enable acrylic</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="dc159-267">これを `true` に設定すると、ウィンドウにアクリルの背景が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-267">When this is set to `true`, the window will have an acrylic background.</span></span> <span data-ttu-id="dc159-268">`false` に設定すると、ウィンドウは無地の平坦な背景になります。</span><span class="sxs-lookup"><span data-stu-id="dc159-268">When it's set to `false`, the window will have a plain, untextured background.</span></span> <span data-ttu-id="dc159-269">透過性は、OS の制限のため、フォーカスされているウィンドウにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-269">The transparency only applies to focused windows due to OS limitations.</span></span>

<span data-ttu-id="dc159-270">**プロパティ名:** `useAcrylic`</span><span class="sxs-lookup"><span data-stu-id="dc159-270">**Property name:** `useAcrylic`</span></span>

<span data-ttu-id="dc159-271">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-271">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-272">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="dc159-272">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="dc159-273">**既定値:** `false`</span><span class="sxs-lookup"><span data-stu-id="dc159-273">**Default value:** `false`</span></span>

:::column-end:::
:::column span="":::
![Windows ターミナルのアクリル](./../images/acrylic.gif)

:::column-end:::
:::row-end:::

### <a name="acrylic-opacity"></a><span data-ttu-id="dc159-275">アクリルの不透明度</span><span class="sxs-lookup"><span data-stu-id="dc159-275">Acrylic opacity</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="dc159-276">`useAcrylic` が `true` に設定されている場合、これによりプロファイルのウィンドウの透明度が設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-276">When `useAcrylic` is set to `true`, this sets the transparency of the window for the profile.</span></span> <span data-ttu-id="dc159-277">0 - 1 の浮動小数点値が受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="dc159-277">This accepts floating point values from 0-1.</span></span>

<span data-ttu-id="dc159-278">**プロパティ名:** `acrylicOpacity`</span><span class="sxs-lookup"><span data-stu-id="dc159-278">**Property name:** `acrylicOpacity`</span></span>

<span data-ttu-id="dc159-279">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-279">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-280">**受け入れ可能:** 0 - 1 の浮動小数点値の数値</span><span class="sxs-lookup"><span data-stu-id="dc159-280">**Accepts:** Number as a floating point value from 0-1</span></span>

<span data-ttu-id="dc159-281">**既定値:** `0.5`</span><span class="sxs-lookup"><span data-stu-id="dc159-281">**Default value:** `0.5`</span></span>

:::column-end:::
:::column span="":::
![Windows ターミナル アクリルの不透明度](./../images/acrylic-opacity.gif)

:::column-end:::
:::row-end:::

<br />

___

## <a name="background-image-settings"></a><span data-ttu-id="dc159-283">背景画像の設定</span><span class="sxs-lookup"><span data-stu-id="dc159-283">Background image settings</span></span>

### <a name="setting-the-background-image"></a><span data-ttu-id="dc159-284">背景画像を設定する</span><span class="sxs-lookup"><span data-stu-id="dc159-284">Setting the background image</span></span>

<span data-ttu-id="dc159-285">これにより、ウィンドウの背景に描画する画像のファイルの場所が設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-285">This sets the file location of the image to draw over the window background.</span></span> <span data-ttu-id="dc159-286">背景画像には、.jpg、.png、.gif のいずれかのファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="dc159-286">The background image can be a .jpg, .png, or .gif file.</span></span>

<span data-ttu-id="dc159-287">**プロパティ名:** `backgroundImage`</span><span class="sxs-lookup"><span data-stu-id="dc159-287">**Property name:** `backgroundImage`</span></span>

<span data-ttu-id="dc159-288">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-288">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-289">**受け入れ可能:** ファイルの場所を表す文字列</span><span class="sxs-lookup"><span data-stu-id="dc159-289">**Accepts:** File location as a string</span></span>

### <a name="background-image-stretch-mode"></a><span data-ttu-id="dc159-290">背景画像のストレッチ モード</span><span class="sxs-lookup"><span data-stu-id="dc159-290">Background image stretch mode</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="dc159-291">これにより、ウィンドウいっぱいに広がるように背景画像のサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-291">This sets how the background image is resized to fill the window.</span></span>

<span data-ttu-id="dc159-292">**プロパティ名:** `backgroundImageStretchMode`</span><span class="sxs-lookup"><span data-stu-id="dc159-292">**Property name:** `backgroundImageStretchMode`</span></span>

<span data-ttu-id="dc159-293">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-293">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-294">**受け入れ可能:** `"none"`、`"fill"`、`"uniform"`、`"uniformToFill"`</span><span class="sxs-lookup"><span data-stu-id="dc159-294">**Accepts:** `"none"`, `"fill"`, `"uniform"`, `"uniformToFill"`</span></span>

<span data-ttu-id="dc159-295">**既定値:** `"uniformToFill"`</span><span class="sxs-lookup"><span data-stu-id="dc159-295">**Default value:** `"uniformToFill"`</span></span>

:::column-end:::
:::column span="":::
<span data-ttu-id="dc159-296">![Windows ターミナルの背景画像のストレッチ モード](./../images/background-image-stretch-mode.gif)
 _[背景画像のソース](https://wallpaperhub.app/wallpapers/6287)_</span><span class="sxs-lookup"><span data-stu-id="dc159-296">![Windows Terminal background image stretch mode](./../images/background-image-stretch-mode.gif)
_[Background image source](https://wallpaperhub.app/wallpapers/6287)_</span></span>

:::column-end:::
:::row-end:::

### <a name="background-image-alignment"></a><span data-ttu-id="dc159-297">背景画像の配置</span><span class="sxs-lookup"><span data-stu-id="dc159-297">Background image alignment</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="dc159-298">これにより、ウィンドウの境界への背景画像の配置方法が設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-298">This sets how the background image aligns to the boundaries of the window.</span></span>

<span data-ttu-id="dc159-299">**プロパティ名:** `backgroundImageAlignment`</span><span class="sxs-lookup"><span data-stu-id="dc159-299">**Property name:** `backgroundImageAlignment`</span></span>

<span data-ttu-id="dc159-300">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-300">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-301">**受け入れ可能:** `"center"`、`"left"`、`"top"`、`"right"`、`"bottom"`、`"topLeft"`、`"topRight"`、`"bottomLeft"`、`"bottomRight"`</span><span class="sxs-lookup"><span data-stu-id="dc159-301">**Accepts:** `"center"`, `"left"`, `"top"`, `"right"`, `"bottom"`, `"topLeft"`, `"topRight"`, `"bottomLeft"`, `"bottomRight"`</span></span>

<span data-ttu-id="dc159-302">**既定値:** `"center"`</span><span class="sxs-lookup"><span data-stu-id="dc159-302">**Default value:** `"center"`</span></span>

:::column-end:::
:::column span="":::
<span data-ttu-id="dc159-303">![Windows ターミナルの背景画像の配置](./../images/background-image-alignment.gif)
 _[背景画像のソース](https://design.ubuntu.com/brand/ubuntu-logo/)_</span><span class="sxs-lookup"><span data-stu-id="dc159-303">![Windows Terminal background image alignment](./../images/background-image-alignment.gif)
_[Background image source](https://design.ubuntu.com/brand/ubuntu-logo/)_</span></span>

:::column-end:::
:::row-end:::

### <a name="background-image-opacity"></a><span data-ttu-id="dc159-304">背景画像の不透明度</span><span class="sxs-lookup"><span data-stu-id="dc159-304">Background image opacity</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="dc159-305">これにより、背景画像の透明度が設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-305">This sets the transparency of the background image.</span></span>

:::column-end:::
:::row-end:::

<span data-ttu-id="dc159-306">**プロパティ名:** `backgroundImageOpacity`</span><span class="sxs-lookup"><span data-stu-id="dc159-306">**Property name:** `backgroundImageOpacity`</span></span>

<span data-ttu-id="dc159-307">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-307">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-308">**受け入れ可能:** 0 - 1 の浮動小数点値の数値</span><span class="sxs-lookup"><span data-stu-id="dc159-308">**Accepts:** Number as a floating point value from 0-1</span></span>

<span data-ttu-id="dc159-309">**既定値:** `1.0`</span><span class="sxs-lookup"><span data-stu-id="dc159-309">**Default value:** `1.0`</span></span>

<br />

___

## <a name="scroll-settings"></a><span data-ttu-id="dc159-310">スクロールの設定</span><span class="sxs-lookup"><span data-stu-id="dc159-310">Scroll settings</span></span>

### <a name="scrollbar-visibility"></a><span data-ttu-id="dc159-311">スクロールバーの表示</span><span class="sxs-lookup"><span data-stu-id="dc159-311">Scrollbar visibility</span></span>

<span data-ttu-id="dc159-312">これにより、スクロールバーの表示が設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-312">This sets the visibility of the scrollbar.</span></span>

<span data-ttu-id="dc159-313">**プロパティ名:** `scrollbarState`</span><span class="sxs-lookup"><span data-stu-id="dc159-313">**Property name:** `scrollbarState`</span></span>

<span data-ttu-id="dc159-314">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-314">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-315">**受け入れ可能:** `"visible"`、`"hidden"`</span><span class="sxs-lookup"><span data-stu-id="dc159-315">**Accepts:** `"visible"`, `"hidden"`</span></span>

### <a name="scroll-to-input-line-when-typing"></a><span data-ttu-id="dc159-316">入力時に入力行までスクロール</span><span class="sxs-lookup"><span data-stu-id="dc159-316">Scroll to input line when typing</span></span>

<span data-ttu-id="dc159-317">これを `true` に設定すると、入力時にウィンドウがコマンド入力行までスクロールします。</span><span class="sxs-lookup"><span data-stu-id="dc159-317">When this is set to `true`, the window will scroll to the command input line when typing.</span></span> <span data-ttu-id="dc159-318">`false` に設定されている場合、入力を開始してもウィンドウはスクロールしません。</span><span class="sxs-lookup"><span data-stu-id="dc159-318">When it's set to `false`, the window will not scroll when you start typing.</span></span>

<span data-ttu-id="dc159-319">**プロパティ名:** `snapOnInput`</span><span class="sxs-lookup"><span data-stu-id="dc159-319">**Property name:** `snapOnInput`</span></span>

<span data-ttu-id="dc159-320">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-320">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-321">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="dc159-321">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="dc159-322">**既定値:** `true`</span><span class="sxs-lookup"><span data-stu-id="dc159-322">**Default value:** `true`</span></span>

### <a name="history-size"></a><span data-ttu-id="dc159-323">履歴のサイズ</span><span class="sxs-lookup"><span data-stu-id="dc159-323">History size</span></span>

<span data-ttu-id="dc159-324">これにより、ウィンドウに表示されているよりも上の行にスクロールして戻すことができる行の数が設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-324">This sets the number of lines above the ones displayed in the window you can scroll back to.</span></span>

<span data-ttu-id="dc159-325">**プロパティ名:** `historySize`</span><span class="sxs-lookup"><span data-stu-id="dc159-325">**Property name:** `historySize`</span></span>

<span data-ttu-id="dc159-326">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-326">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-327">**値:** 整数</span><span class="sxs-lookup"><span data-stu-id="dc159-327">**Accepts:** Integer</span></span>

<span data-ttu-id="dc159-328">**既定値:** `9001`</span><span class="sxs-lookup"><span data-stu-id="dc159-328">**Default value:** `9001`</span></span>

<br />

___

## <a name="how-the-profile-closes-when-exiting"></a><span data-ttu-id="dc159-329">終了時のプロファイルの閉じ方</span><span class="sxs-lookup"><span data-stu-id="dc159-329">How the profile closes when exiting</span></span>

<span data-ttu-id="dc159-330">これにより、プロファイルが終了または起動に失敗したときにどのように反応するかが設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc159-330">This sets how the profile reacts to termination or failure to launch.</span></span> <span data-ttu-id="dc159-331">`"graceful"` は、`exit` が入力されたとき、またはプロセスが正常に終了したときに、プロファイルを閉じます。</span><span class="sxs-lookup"><span data-stu-id="dc159-331">`"graceful"` will close the profile when `exit` is typed or when the process exits normally.</span></span> <span data-ttu-id="dc159-332">`"always"` は常にプロファイルを閉じ、`"never"` はプロファイルを閉じません。</span><span class="sxs-lookup"><span data-stu-id="dc159-332">`"always"` will always close the profile and `"never"` will never close the profile.</span></span> <span data-ttu-id="dc159-333">`true` と `false` は、それぞれ `"graceful"` と `"never"` のシノニムとして受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="dc159-333">`true` and `false` are accepted as synonyms for `"graceful"` and `"never"`, respectively.</span></span>

<span data-ttu-id="dc159-334">**プロパティ名:** `closeOnExit`</span><span class="sxs-lookup"><span data-stu-id="dc159-334">**Property name:** `closeOnExit`</span></span>

<span data-ttu-id="dc159-335">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-335">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-336">**受け入れ可能:** `"graceful"`、`"always"`、`"never"`、`true`、`false`</span><span class="sxs-lookup"><span data-stu-id="dc159-336">**Accepts:** `"graceful"`, `"always"`, `"never"`, `true`, `false`</span></span>

<span data-ttu-id="dc159-337">**既定値:** `"graceful"`</span><span class="sxs-lookup"><span data-stu-id="dc159-337">**Default value:** `"graceful"`</span></span>

<br />

___

## <a name="retro-terminal-effects"></a><span data-ttu-id="dc159-338">レトロ ターミナル効果</span><span class="sxs-lookup"><span data-stu-id="dc159-338">Retro terminal effects</span></span>

:::row:::
:::column span="":::
<span data-ttu-id="dc159-339">これを `true` に設定すると、走査線やぼやけたテキストの端がある古い CRT ディスプレイがターミナルでエミュレートされます。</span><span class="sxs-lookup"><span data-stu-id="dc159-339">When this is set to `true`, the terminal will emulate a classic CRT display with scan lines and blurry text edges.</span></span> <span data-ttu-id="dc159-340">これは試験的な機能であり、存続は保証されていません。</span><span class="sxs-lookup"><span data-stu-id="dc159-340">This is an experimental feature and its continued existence is not guaranteed.</span></span>

<span data-ttu-id="dc159-341">**プロパティ名:** `experimental.retroTerminalEffect`</span><span class="sxs-lookup"><span data-stu-id="dc159-341">**Property name:** `experimental.retroTerminalEffect`</span></span>

<span data-ttu-id="dc159-342">**必須かどうか:** オプション</span><span class="sxs-lookup"><span data-stu-id="dc159-342">**Necessity:** Optional</span></span>

<span data-ttu-id="dc159-343">**値:** `true`、`false`</span><span class="sxs-lookup"><span data-stu-id="dc159-343">**Accepts:** `true`, `false`</span></span>

<span data-ttu-id="dc159-344">**既定値:** `false`</span><span class="sxs-lookup"><span data-stu-id="dc159-344">**Default value:** `false`</span></span>

:::column-end:::
:::column span="":::
<span data-ttu-id="dc159-345">![Windows ターミナルの実験的なレトロ ターミナル効果](./../images/experimental-retro-terminal-effect.gif)
_構成:[レトロ コマンド プロンプト](./../custom-terminal-gallery/retro-command-prompt.md)_</span><span class="sxs-lookup"><span data-stu-id="dc159-345">![Windows Terminal experimental retro terminal effect](./../images/experimental-retro-terminal-effect.gif)
_Configuration: [Retro Command Prompt](./../custom-terminal-gallery/retro-command-prompt.md)_</span></span>

:::column-end:::
:::row-end:::
