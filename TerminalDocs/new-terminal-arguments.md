---
title: Windows Terminal の新しいターミナル引数
description: Windows Terminal の新しいターミナル引数。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: include
ms.service: terminal
ms.openlocfilehash: 4430124e3f9319e79cbf7b097d8743543c1d52a6
ms.sourcegitcommit: bb5b7fd7db4b81e0d44e060989dc16b6775c802a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83416317"
---
# <a name="new-terminal-arguments-in-the-windows-terminal"></a>Windows Terminal の新しいターミナル引数

キー バインドを使用して新しいペインまたはタブを開くときに、プロファイルの名前、guid、またはインデックスを含めることによって、使用するプロファイルを指定できます。 何も指定されていない場合は、既定のプロファイルが使用されます。 これを行うには、`profile` または `index` を引数として `splitPane` または `newTab` キー バインドに追加します。 インデックスは 0 から開始されることに注意してください。

```json
{ "command": { "action": "splitPane", "split": "vertical", "profile": "profile1" }, "keys": "ctrl+a" },
{ "command": { "action": "splitPane", "split": "vertical", "profile": "{00000000-0000-0000-0000-000000000000}" }, "keys": "ctrl+b" },
{ "command": { "action": "newTab", "index": 0 }, "keys": "ctrl+c" }
```

また、プロファイルのコマンド ライン実行可能ファイル、開始ディレクトリ、タブ タイトルなど、プロファイルの特定の側面をオーバーライドすることもできます。 これは、`commandline`、`startingDirectory`、`tabTitle` のいずれかまたは両方を `splitPane` または `newTab` キー バインドに追加することによって実現できます。

```json
{ "command": { "action": "splitPane", "split": "auto", "profile": "profile1", "commandline": "foo.exe" }, "keys": "ctrl+a" },
{ "command": { "action": "newTab", "profile": "{00000000-0000-0000-0000-000000000000}", "startingDirectory": "C:\\foo" }, "keys": "ctrl+b" },
{ "command": { "action": "newTab", "index": 0, "tabTitle": "bar", "startingDirectory": "C:\\foo", "commandline": "foo.exe" }, "keys": "ctrl+c" }
```
