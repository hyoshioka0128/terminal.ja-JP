---
title: Windows ターミナルのヒントとコツ
description: このページには、Windows ターミナル エクスペリエンスの改善に役立つヒントとコツが記載されています。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 06/18/2020
ms.topic: how-to
ms.service: terminal
ms.localizationpriority: high
ms.openlocfilehash: 414300450e4039a2d16c125fca7e692e1ebacbef
ms.sourcegitcommit: 91a802863cd0730d2e364377ffe44f819a66ff2a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "85060460"
---
# <a name="windows-terminal-tips-and-tricks"></a><span data-ttu-id="758e7-103">Windows ターミナルのヒントとコツ</span><span class="sxs-lookup"><span data-stu-id="758e7-103">Windows Terminal tips and tricks</span></span>

## <a name="rename-a-tab-preview"></a><span data-ttu-id="758e7-104">タブの名前変更 ([プレビュー](https://aka.ms/terminal-preview/))</span><span class="sxs-lookup"><span data-stu-id="758e7-104">Rename a tab ([Preview](https://aka.ms/terminal-preview/))</span></span>

<span data-ttu-id="758e7-105">タブを右クリックして [タブ名を変更] を選択すると、そのターミナル セッションのタブの名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="758e7-105">You can right click on a tab and select Rename Tab to rename a tab for that terminal session.</span></span> <span data-ttu-id="758e7-106">コンテキスト メニューでこのオプションをクリックすると、タブ タイトルがテキスト フィールドに変更され、タイトルを編集できるようになります。</span><span class="sxs-lookup"><span data-stu-id="758e7-106">Clicking this option in the context menu will change your tab title into a text field, where you can then edit the title.</span></span> <span data-ttu-id="758e7-107">各ターミナル インスタンスに対してそのプロファイルのタブ タイトルを設定する場合は、[タブ タイトルのチュートリアル](./tutorials/tab-title.md)で詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="758e7-107">If you'd like to set the tab title for that profile for every terminal instance, you can learn more in the [Tab title tutorial](./tutorials/tab-title.md).</span></span>

![Windows ターミナルのタブの名前変更](./images/tab-rename.gif)

> [!IMPORTANT]
> <span data-ttu-id="758e7-109">この機能は、[Windows ターミナル プレビュー](https://aka.ms/terminal-preview/)でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="758e7-109">This feature is only available in [Windows Terminal Preview](https://aka.ms/terminal-preview/).</span></span>

## <a name="color-a-tab-preview"></a><span data-ttu-id="758e7-110">タブの色付け ([プレビュー](https://aka.ms/terminal-preview/))</span><span class="sxs-lookup"><span data-stu-id="758e7-110">Color a tab ([Preview](https://aka.ms/terminal-preview/))</span></span>

<span data-ttu-id="758e7-111">タブを右クリックして [色...] を選択すると、そのターミナル セッションのタブに色を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="758e7-111">You can right click on a tab and select Color... to color the tab for that terminal session.</span></span> <span data-ttu-id="758e7-112">定義済みの色の一覧から選択するか、または [カスタム...] をクリックしてカラーピッカー、RGB/HSV、16 進数のフィールドを使用して任意の色を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="758e7-112">You can select from a predefined list of colors or you can click Custom... to pick any color using the color picker or the RGB/HSV or hex fields.</span></span>

![Windows ターミナルのタブの色](./images/tab-color.png)

> [!TIP]
> <span data-ttu-id="758e7-114">タブに背景と同じ色を設定してシームレスな外観を実現するには、16 進数フィールドを使用します。</span><span class="sxs-lookup"><span data-stu-id="758e7-114">Use the hex field to set your tab to the same color as your background color for a seamless look.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="758e7-115">この機能は、[Windows ターミナル プレビュー](https://aka.ms/terminal-preview/)でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="758e7-115">This feature is only available in [Windows Terminal Preview](https://aka.ms/terminal-preview/).</span></span>

## <a name="zoom-with-the-mouse"></a><span data-ttu-id="758e7-116">マウスを使用して拡大/縮小する</span><span class="sxs-lookup"><span data-stu-id="758e7-116">Zoom with the mouse</span></span>

<span data-ttu-id="758e7-117"><kbd>Ctrl</kbd> キーを押しながらスクロールすると、Windows ターミナルのテキスト ウィンドウを拡大/縮小できます。</span><span class="sxs-lookup"><span data-stu-id="758e7-117">You can zoom the text window of Windows Terminal by holding <kbd>ctrl</kbd> and scrolling.</span></span> <span data-ttu-id="758e7-118">そのターミナル セッションでは、拡大/縮小された状態が維持されます。</span><span class="sxs-lookup"><span data-stu-id="758e7-118">The zoom will persist for that terminal session.</span></span> <span data-ttu-id="758e7-119">フォント サイズを変更する場合は、[プロファイル設定に関するページ](./customize-settings/profile-settings#text-settings)でフォント サイズ機能の詳細をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="758e7-119">If you want to change your font size, you can learn more about the font size feature on the [Profile settings page](./customize-settings/profile-settings#text-settings).</span></span>

## <a name="adjust-background-opacity-with-the-mouse"></a><span data-ttu-id="758e7-120">マウスを使用して背景の不透明度を調整する</span><span class="sxs-lookup"><span data-stu-id="758e7-120">Adjust background opacity with the mouse</span></span>

<span data-ttu-id="758e7-121"><kbd>ctrl+shift</kbd> を押しながらスクロールすると、背景の不透明度を調整できます。</span><span class="sxs-lookup"><span data-stu-id="758e7-121">You can adjust the opacity of the background by holding <kbd>ctrl+shift</kbd> and scrolling.</span></span> <span data-ttu-id="758e7-122">そのターミナルセッションでは、不透明度が維持されます。</span><span class="sxs-lookup"><span data-stu-id="758e7-122">The opacity will persist for that terminal session.</span></span> <span data-ttu-id="758e7-123">プロファイルのアクリルの不透明度を変更する場合は、[プロファイル設定に関するページ](./customize-settings/profile-settings#acrylic-settings)でアクリルの背景効果の詳細をご確認ください</span><span class="sxs-lookup"><span data-stu-id="758e7-123">If you want to change your acrylic opacity for a profile, you can learn more about acrylic background effects on the [Profile settings page](./customize-settings/profile-settings#acrylic-settings)</span></span>
