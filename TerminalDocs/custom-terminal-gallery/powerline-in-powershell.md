---
title: PowerShell 構成の Windows ターミナル Powerline
description: これは、PowerShell の Powerline の構成とテーマです。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: sample
ms.openlocfilehash: 0c754cac9e286e1a928c2ddf3e711c552cc67d3c
ms.sourcegitcommit: 8e0901b83a8cc437f090fe58688b86acb73f3cb3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90988683"
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
