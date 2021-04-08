---
title: カスタム配色ガイド
description: Windows ターミナルのいくつかのサンプル構成。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 07/27/2020
ms.topic: sample
ms.openlocfilehash: b505abf18f1dcf5bf211193dd9918d7131d2ed06
ms.sourcegitcommit: 8e0901b83a8cc437f090fe58688b86acb73f3cb3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "91003645"
---
# <a name="custom-terminal-guide"></a>カスタムターミナルガイド

ここでは、独自のデザインの基礎として使用したり、使用したりするための配色をいくつか示します。

## <a name="installing-schemes"></a>スキーマのインストール

次の例のように、 **"スキーム"** セクションから settings.jsの正しいセクションに JSON をコピーします。

次の処理の前

```json
"schemes:" [],
```

次の処理の後

```json
 "schemes": [
            {
                "name": "Retro",
                "background": "#000000",
                "black": "#00ff00",
                "blue": "#00ff00",
                "brightBlack": "#00ff00",
                "brightBlue": "#00ff00",
                "brightCyan": "#00ff00",
                "brightGreen": "#00ff00",
                "brightPurple": "#00ff00",
                "brightRed": "#00ff00",
                "brightWhite": "#00ff00",
                "brightYellow": "#00ff00",
                "cyan": "#00ff00",
                "foreground": "#00ff00",
                "green": "#00ff00",
                "purple": "#00ff00",
                "red": "#00ff00",
                "white": "#00ff00",
                "yellow": "#00ff00"
            }
        ]
```

次に、プロファイル固有のセクションを追加します。次に例を示します。

次の処理の前

```json
{
    "guid": "{234ab24f-34dd-ff3-ade434aad345}",
    "name": "Command Prompt",
    "commandline": "cmd.exe",
    "hidden": false
}
```

次の処理の後

```json
{
    "guid": "{234ab24f-34dd-ff3-ade434aad345}",
    "name": "Command Prompt",
    "commandline": "cmd.exe",
    "hidden": false,
    "colorScheme" : "Retro",
    "cursorColor" : "#FFFFFF",
    "cursorShape": "filledBox",
    "fontSize" : 16,
    "padding" : "5, 5, 5, 5",
    "tabTitle" : "Command Prompt",
    "fontFace": "PxPlus IBM VGA8",
    "experimental.retroTerminalEffect": true
}
```

## <a name="frosted-glass"></a>すりグラス

![Windows ターミナルすりグラステーマ](./../images/frosted-glass-theme.png)

[詳細](frosted-glass-theme.md)

## <a name="powerline"></a>Powerline

![Windows ターミナル Powerline PowerShell](./../images/powerline-powershell.png)

[詳細](powerline-in-powershell.md)

## <a name="raspberry-ubuntu"></a>Raspberry Ubuntu

![Windows ターミナル Raspberry Ubuntu](./../images/raspberry-ubuntu.png)

[詳細](raspberry-ubuntu.md)

## <a name="retro-command"></a>レトロコマンド

![Windows ターミナルレトロコマンドプロンプト](./../images/retro-command-prompt.png)

[詳細](retro-command-prompt.md)

## <a name="share"></a>共有！

Windows ターミナルスキームを共有しますか? [Twitter](https://twitter.com/WindowsDocs)にご連絡ください。
