---
title: Windows Terminal ペイン
description: Windows Terminal でペインを分割する方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 06/18/2020
ms.topic: how-to
ms.service: terminal
ms.openlocfilehash: 0e2d7a50e1a3c933f7ab2d98bda5be6b8ee44e7e
ms.sourcegitcommit: 91a802863cd0730d2e364377ffe44f819a66ff2a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84994322"
---
# <a name="panes-in-windows-terminal"></a>Windows Terminal のペイン

ペインでは、同じタブ内で複数のコマンドライン アプリケーションを並べて同時に実行することができます。これにより、タブを切り替える必要が最小限に抑えられ、一度に複数のプロンプトを表示することができます。

## <a name="creating-a-new-pane"></a>新しいペインを作成する

### <a name="using-the-keyboard"></a>キーボードを使用する

Windows Terminal で、垂直方向または水平方向の新しいペインを作成できます。 垂直方向に分割すると、フォーカスがあるペインの右側に新しいペインが開かれ、水平方向に分割すると、フォーカスがあるペインの下に新しいペインが開かれます。 既定のプロファイルの新しい垂直ペインを作成するには、<kbd>alt+shift+plus</kbd> を入力します。 既定のプロファイルの水平ペインの場合は、<kbd>alt+shift+-</kbd> と入力します。

![Windows ターミナルのペインの作成](./images/open-panes.gif)
_構成:[Raspberry Ubuntu](./custom-terminal-gallery/raspberry-ubuntu.md)_

これらのキー バインドを変更する場合は、`splitPane` アクションと、profiles.json ファイルで `split` プロパティの値に `vertical` または `horizontal` を使用することで、新しいキー バインドを作成できます。 最大値の領域を持つペインが必要な場合は、`split` を `auto` に設定できます。 キー バインドの詳細については、[キー バインドに関するページ](./customize-settings/key-bindings.md)を参照してください。

```json
{ "command": { "action": "splitPane", "split": "vertical" }, "keys": "alt+shift+plus" },
{ "command": { "action": "splitPane", "split": "horizontal" }, "keys": "alt+shift+-" },
{ "command": { "action": "splitPane", "split": "auto" }, "keys": "alt+shift+|" }
```

### <a name="using-the-dropdown-menu-preview"></a>ドロップダウン メニューを使用する ([プレビュー](https://aka.ms/terminal-preview/))

ドロップダウン メニューから新しいペインを開く場合、<kbd>Alt</kbd> キーを押しながら、目的のプロファイルをクリックします。 これにより、アクティブなウィンドウまたはペインが、選択したプロファイルの新しいペインに `auto` 分割されます。 `auto` 分割モードは、ペインを作成するために長辺の方向に分割されます。

![Windows ターミナルのドロップダウン ペイン](./images/alt-click-pane.gif)

> [!IMPORTANT]
> この機能は、[Windows Terminal プレビュー](https://aka.ms/terminal-preview/)でのみ使用できます。

## <a name="switching-between-panes"></a>ペインを切り替える

ターミナルでは、キーボードを使用してペイン間を移動できます。 <kbd>alt</kbd> キーを押したままにすると、方向キーを使用してペイン間でフォーカスを移動できます。 フォーカスがあるペインは、それを囲むアクセント カラーの境界線で特定できます。 このアクセント カラーは、Windows の色の設定で設定されています。

![Windows ターミナルのペインの切り替え](./images/navigate-panes.gif)

これをカスタマイズするには、`moveFocus` コマンドのキー バインドを追加し、`direction` を `down`、`left`、`right`、`up` のいずれかに設定します。

```json
{ "command": { "action": "moveFocus", "direction": "down" }, "keys": "alt+down" },
{ "command": { "action": "moveFocus", "direction": "left" }, "keys": "alt+left" },
{ "command": { "action": "moveFocus", "direction": "right" }, "keys": "alt+right" },
{ "command": { "action": "moveFocus", "direction": "up" }, "keys": "alt+up" }
```

## <a name="resizing-a-pane"></a>ペインのサイズを変更する

ペインのサイズを調整するには、<kbd>alt+shift</kbd> キーを押したまま、方向キーを使用してフォーカスがあるペインのサイズを変更します。

![Windows ターミナルのペインの作成](./images/resize-panes.gif)

このキー バインドをカスタマイズするには、`resizePane` アクションを使用して新しいキー バインドを追加し、`direction` を `down`、`left`、`right`、`up` のいずれかに設定します。

```json
{ "command": { "action": "resizePane", "direction": "down" }, "keys": "alt+shift+down" },
{ "command": { "action": "resizePane", "direction": "left" }, "keys": "alt+shift+left" },
{ "command": { "action": "resizePane", "direction": "right" }, "keys": "alt+shift+right" },
{ "command": { "action": "resizePane", "direction": "up" }, "keys": "alt+shift+up" }
```

## <a name="closing-a-pane"></a>ペインを閉じる

<kbd>ctrl+shift+w</kbd> を入力すると、フォーカスされているペインを閉じることができます。 ペインが 1 つしかない場合は、<kbd>ctrl+shift+w</kbd> でタブが閉じます。いつものとおり、最後のタブを閉じると、ウィンドウが閉じます。

![Windows ターミナルのペインを閉じる](./images/close-panes.gif)

ペインを閉じるキーを変更するには、`closePane` コマンドを使用するキー バインドを追加します。

```json
{ "command": "closePane", "keys": "ctrl+shift+w" }
```

## <a name="customizing-panes-using-key-bindings"></a>キー バインドを使用してペインをカスタマイズする

カスタム キー バインドに応じて、新しいペイン内に開くものをカスタマイズできます。

### <a name="duplicating-a-pane"></a>ペインを複製する

ターミナルでは、フォーカスがあるペインのプロファイルを別のペインに複製できます。

![Windows ターミナルのペインの複製](./images/duplicate-panes.gif)

これを行うには、`splitMode` プロパティと値として `duplicate` を `splitPane` キー バインドに追加します。

```json
{ "command": { "action": "splitPane", "split": "auto", "splitMode": "duplicate" }, "keys": "alt+shift+d" }
```

### <a name="new-terminal-arguments"></a>新しいターミナル引数

[!INCLUDE [new-terminal-arguments](./new-terminal-arguments.md)]
