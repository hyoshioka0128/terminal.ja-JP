---
title: Windows Terminal Raspberry Ubuntu の構成
description: これは、Raspberry Ubuntu のテーマです。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: sample
ms.service: terminal
ms.openlocfilehash: e3443256c196484028ce85bd4fa0d045a3a8973a
ms.sourcegitcommit: bb5b7fd7db4b81e0d44e060989dc16b6775c802a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83416497"
---
# <a name="raspberry-ubuntu-in-windows-terminal"></a>Windows Terminal での Raspberry Ubuntu

![Windows ターミナル Raspberry Ubuntu](./../images/raspberry-ubuntu.png)

```json
    {
        "theme": "dark",
        "profiles": [
            {
                "name" : "Ubuntu",
                "source" : "Windows.Terminal.Wsl",
                "colorScheme" : "Raspberry",
                "cursorColor" : "#FFFFFF",
                "fontFace" : "Cascadia Code",
                "padding" : "5, 5, 5, 5",
                "suppressApplicationTitle": true,
                "tabTitle": "Ubuntu"
            }
        ],
        "schemes": [
            {
                "name" : "Raspberry",
                "background" : "#3C0315",
                "black" : "#282A2E",
                "blue" : "#0170C5",
                "brightBlack" : "#676E7A",
                "brightBlue" : "#80c8ff",
                "brightCyan" : "#8ABEB7",
                "brightGreen" : "#B5D680",
                "brightPurple" : "#AC79BB",
                "brightRed" : "#BD6D85",
                "brightWhite" : "#FFFFFD",
                "brightYellow" : "#FFFD76",
                "cyan" : "#3F8D83",
                "foreground" : "#FFFFFD",
                "green" : "#76AB23",
                "purple" : "#7D498F",
                "red" : "#BD0940",
                "white" : "#FFFFFD",
                "yellow" : "#E0DE48"
            }
        ]
    }
```
