---
title: Windows ターミナルの配色
description: Windows ターミナル用の配色を作成する方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: how-to
ms.service: terminal
ms.localizationpriority: high
ms.openlocfilehash: 9f7e6133a08a21c3b77689cd8dce32dacbf80351
ms.sourcegitcommit: d8e23557224bc50a82a36dc80ac68b9d11dfdde9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2020
ms.locfileid: "84720138"
---
# <a name="color-schemes-in-windows-terminal"></a><span data-ttu-id="4eeef-103">Windows ターミナルでの配色</span><span class="sxs-lookup"><span data-stu-id="4eeef-103">Color schemes in Windows Terminal</span></span>

## <a name="creating-your-own-color-scheme"></a><span data-ttu-id="4eeef-104">独自の配色を作成する</span><span class="sxs-lookup"><span data-stu-id="4eeef-104">Creating your own color scheme</span></span>

<span data-ttu-id="4eeef-105">配色は、settings.json ファイルの `schemes` 配列で定義できます。</span><span class="sxs-lookup"><span data-stu-id="4eeef-105">Color schemes can be defined in the `schemes` array of your settings.json file.</span></span> <span data-ttu-id="4eeef-106">記述形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4eeef-106">They are written in the following format:</span></span>

```json
{
    "name" : "Campbell",

    "cursorColor": "#FFFFFF",
    "selectionBackground": "#FFFFFF",

    "background" : "#0C0C0C",
    "foreground" : "#CCCCCC",

    "black" : "#0C0C0C",
    "blue" : "#0037DA",
    "cyan" : "#3A96DD",
    "green" : "#13A10E",
    "purple" : "#881798",
    "red" : "#C50F1F",
    "white" : "#CCCCCC",
    "yellow" : "#C19C00",
    "brightBlack" : "#767676",
    "brightBlue" : "#3B78FF",
    "brightCyan" : "#61D6D6",
    "brightGreen" : "#16C60C",
    "brightPurple" : "#B4009E",
    "brightRed" : "#E74856",
    "brightWhite" : "#F2F2F2",
    "brightYellow" : "#F9F1A5"
},
```

<span data-ttu-id="4eeef-107">`name` 以外のすべての設定では、`"#rgb"` または `"#rrggbb"` の 16 進形式の文字列として色を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4eeef-107">Every setting, aside from `name`, accepts a color as a string in hex format: `"#rgb"` or `"#rrggbb"`.</span></span> <span data-ttu-id="4eeef-108">`cursorColor` と `selectionBackground` の設定は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="4eeef-108">The `cursorColor` and `selectionBackground` settings are optional.</span></span>

<br />

___

## <a name="included-color-schemes"></a><span data-ttu-id="4eeef-109">含まれる配色</span><span class="sxs-lookup"><span data-stu-id="4eeef-109">Included color schemes</span></span>

<span data-ttu-id="4eeef-110">Windows ターミナルの defaults.json ファイルには、以下の配色が含まれています。このファイルには、<kbd>Alt</kbd> キーを押しながら設定ボタンを選択することでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4eeef-110">Windows Terminal includes these color schemes inside the defaults.json file, which can be accessed by holding <kbd>alt</kbd> and selecting the settings button.</span></span> <span data-ttu-id="4eeef-111">いずれかのコマンドライン プロファイルで配色を設定する場合は、配色の `name` を値として `colorScheme` プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="4eeef-111">If you would like to set up a color scheme inside one of your command-line profiles, add the `colorScheme` property with the color scheme's `name` as the value.</span></span>

```json
"colorScheme": "COLOR SCHEME NAME"
```

### <a name="campbell"></a><span data-ttu-id="4eeef-112">Campbell</span><span class="sxs-lookup"><span data-stu-id="4eeef-112">Campbell</span></span>

![Windows ターミナルの Campbell 配色](./../images/campbell-color-scheme.png)

### <a name="campbell-powershell"></a><span data-ttu-id="4eeef-114">Campbell Powershell</span><span class="sxs-lookup"><span data-stu-id="4eeef-114">Campbell Powershell</span></span>

![Windows ターミナルの Campbell Powershell 配色](./../images/campbell-powershell-color-scheme.png)

### <a name="vintage"></a><span data-ttu-id="4eeef-116">Vintage</span><span class="sxs-lookup"><span data-stu-id="4eeef-116">Vintage</span></span>

![Windows ターミナルの Vintage 配色](./../images/vintage-color-scheme.png)

### <a name="one-half-dark"></a><span data-ttu-id="4eeef-118">One Half Dark</span><span class="sxs-lookup"><span data-stu-id="4eeef-118">One Half Dark</span></span>

![Windows ターミナルの One Half Dark 配色](./../images/one-half-dark-color-scheme.png)

### <a name="one-half-light"></a><span data-ttu-id="4eeef-120">One Half Light</span><span class="sxs-lookup"><span data-stu-id="4eeef-120">One Half Light</span></span>

![Windows ターミナルの One Half Light 配色](./../images/one-half-light-color-scheme.png)

### <a name="solarized-dark"></a><span data-ttu-id="4eeef-122">Solarized Dark</span><span class="sxs-lookup"><span data-stu-id="4eeef-122">Solarized Dark</span></span>

![Windows ターミナルの Solarized Dark 配色](./../images/solarized-dark-color-scheme.png)

### <a name="solarized-light"></a><span data-ttu-id="4eeef-124">Solarized Light</span><span class="sxs-lookup"><span data-stu-id="4eeef-124">Solarized Light</span></span>

![Windows ターミナルの Solarized Light 配色](./../images/solarized-light-color-scheme.png)

### <a name="tango-dark"></a><span data-ttu-id="4eeef-126">Tango Dark</span><span class="sxs-lookup"><span data-stu-id="4eeef-126">Tango Dark</span></span>

![Windows ターミナルの Tango Dark 配色](./../images/tango-dark-color-scheme.png)

### <a name="tango-light"></a><span data-ttu-id="4eeef-128">Tango Light</span><span class="sxs-lookup"><span data-stu-id="4eeef-128">Tango Light</span></span>

![Windows ターミナルの Tango Light 配色](./../images/tango-light-color-scheme.png)
