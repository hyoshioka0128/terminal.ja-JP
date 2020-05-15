---
title: Windows ターミナルすりグラステーマの構成
description: これは、すりグラステーマのサンプル構成です。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: sample
ms.service: terminal
ms.openlocfilehash: c6fa0ef042e48a151f0a29b557997f2bbed90495
ms.sourcegitcommit: bb5b7fd7db4b81e0d44e060989dc16b6775c802a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83416537"
---
# <a name="frosted-glass-theme-in-windows-terminal"></a><span data-ttu-id="d591f-103">Windows ターミナルのすりグラステーマ</span><span class="sxs-lookup"><span data-stu-id="d591f-103">Frosted Glass Theme in Windows Terminal</span></span>

<span data-ttu-id="d591f-104">プロンプトのスタイルは Powerline で、 `Cascadia Code PL` [Cascadia Code GitHub リリースページ](https://github.com/microsoft/cascadia-code/releases)からダウンロードできるフォントを使用しています。</span><span class="sxs-lookup"><span data-stu-id="d591f-104">The prompt is styled using Powerline and is using the `Cascadia Code PL` font, which can be downloaded from the [Cascadia Code GitHub releases page](https://github.com/microsoft/cascadia-code/releases).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d591f-105">Powerline を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d591f-105">Learn how to set up Powerline</span></span>](./../tutorials/powerline-setup.md)

![Windows ターミナルすりグラステーマ](./../images/frosted-glass-theme.png)

```json
    {
        "theme": "light",
        "profiles": [
            {
                "name" : "PowerShell",
                "source" : "Windows.Terminal.PowershellCore",
                "acrylicOpacity": 0.7,
                "colorScheme" : "Frost",
                "cursorColor" : "#000000",
                "fontFace" : "Cascadia Code PL",
                "useAcrylic": true
            }
        ],
        "schemes": [
            {
                "name" : "Frost",
                "background" : "#FFFFFF",
                "black" : "#3C5712",
                "blue" : "#17b2ff",
                "brightBlack" : "#749B36",
                "brightBlue" : "#27B2F6",
                "brightCyan" : "#13A8C0",
                "brightGreen" : "#89AF50",
                "brightPurple" : "#F2A20A",
                "brightRed" : "#F49B36",
                "brightWhite" : "#741274",
                "brightYellow" : "#991070",
                "cyan" : "#3C96A6",
                "foreground" : "#000000",
                "green" : "#6AAE08",
                "purple" : "#991070",
                "red" : "#8D0C0C",
                "white" : "#6E386E",
                "yellow" : "#991070"
            }
        ]
    }
```
