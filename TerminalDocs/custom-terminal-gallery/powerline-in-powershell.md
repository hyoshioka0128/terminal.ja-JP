---
title: PowerShell 構成の Windows ターミナル Powerline
description: これは、PowerShell の Powerline の構成とテーマです。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: sample
ms.service: terminal
ms.openlocfilehash: 2e8e19647df456ab69347f923e75601ddfcc2e2f
ms.sourcegitcommit: bb5b7fd7db4b81e0d44e060989dc16b6775c802a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83416547"
---
# <a name="powerline-in-powershell-theme-for-windows-terminal"></a>Windows ターミナルの PowerShell テーマの powerline

プロンプトのスタイルは Powerline で、 `Cascadia Code PL` [Cascadia Code GitHub リリースページ](https://github.com/microsoft/cascadia-code/releases)からダウンロードできるフォントを使用しています。

> [!div class="nextstepaction"]
> [Powerline を設定する方法について説明します。](./../tutorials/powerline-setup.md)

![Windows ターミナル Powerline PowerShell](./../images/powerline-powershell.png)

```json
    {
        "theme": "dark",
        "profiles": [
            {
                "name" : "Powershell",
                "source" : "Windows.Terminal.PowershellCore",
                "acrylicOpacity" : 0.7,
                "colorScheme" : "Campbell",
                "cursorColor" : "#FFFFFD",
                "fontFace" : "Cascadia Code PL",
                "useAcrylic" : true
            }
        ]
    }
```
