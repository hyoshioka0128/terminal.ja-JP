---
title: Windows Terminal の配色
description: Windows Terminal 用の配色を作成する方法について説明します。
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
# <a name="color-schemes-in-windows-terminal"></a>Windows Terminal での配色

## <a name="creating-your-own-color-scheme"></a>独自の配色を作成する

配色は、settings.json ファイルの `schemes` 配列で定義できます。 記述形式は次のとおりです。

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

`name` 以外のすべての設定では、`"#rgb"` または `"#rrggbb"` の 16 進形式の文字列として色を指定できます。 `cursorColor` と `selectionBackground` の設定は省略可能です。

<br />

___

## <a name="included-color-schemes"></a>含まれる配色

Windows Terminal の defaults.json ファイルには、以下の配色が含まれています。このファイルには、<kbd>Alt</kbd> キーを押しながら設定ボタンを選択することでアクセスできます。 いずれかのコマンドライン プロファイルで配色を設定する場合は、配色の `name` を値として `colorScheme` プロパティを追加します。

```json
"colorScheme": "COLOR SCHEME NAME"
```

### <a name="campbell"></a>Campbell

![Windows ターミナルの Campbell 配色](./../images/campbell-color-scheme.png)

### <a name="campbell-powershell"></a>Campbell Powershell

![Windows ターミナルの Campbell Powershell 配色](./../images/campbell-powershell-color-scheme.png)

### <a name="vintage"></a>Vintage

![Windows ターミナルの Vintage 配色](./../images/vintage-color-scheme.png)

### <a name="one-half-dark"></a>One Half Dark

![Windows ターミナルの One Half Dark 配色](./../images/one-half-dark-color-scheme.png)

### <a name="one-half-light"></a>One Half Light

![Windows ターミナルの One Half Light 配色](./../images/one-half-light-color-scheme.png)

### <a name="solarized-dark"></a>Solarized Dark

![Windows ターミナルの Solarized Dark 配色](./../images/solarized-dark-color-scheme.png)

### <a name="solarized-light"></a>Solarized Light

![Windows ターミナルの Solarized Light 配色](./../images/solarized-light-color-scheme.png)

### <a name="tango-dark"></a>Tango Dark

![Windows ターミナルの Tango Dark 配色](./../images/tango-dark-color-scheme.png)

### <a name="tango-light"></a>Tango Light

![Windows ターミナルの Tango Light 配色](./../images/tango-light-color-scheme.png)
