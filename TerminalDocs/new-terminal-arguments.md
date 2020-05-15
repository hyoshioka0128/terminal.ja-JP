---
title: Windows ターミナルの新しいターミナル引数
description: Windows ターミナルの新しいターミナル引数。
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
# <a name="new-terminal-arguments-in-the-windows-terminal"></a><span data-ttu-id="68869-103">Windows ターミナルの新しいターミナル引数</span><span class="sxs-lookup"><span data-stu-id="68869-103">New Terminal Arguments in the Windows Terminal</span></span>

<span data-ttu-id="68869-104">キー バインドを使用して新しいペインまたはタブを開くときに、プロファイルの名前、guid、またはインデックスを含めることによって、使用するプロファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="68869-104">When opening a new pane or tab with a key binding, you can specify which profile is used by including the profile's name, guid, or index.</span></span> <span data-ttu-id="68869-105">何も指定されていない場合は、既定のプロファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="68869-105">If none are specified, the default profile is used.</span></span> <span data-ttu-id="68869-106">これを行うには、`profile` または `index` を引数として `splitPane` または `newTab` キー バインドに追加します。</span><span class="sxs-lookup"><span data-stu-id="68869-106">This can be done by adding `profile` or `index` as an argument to a `splitPane` or `newTab` key binding.</span></span> <span data-ttu-id="68869-107">インデックスは 0 から開始されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="68869-107">Note that indexing starts at 0.</span></span>

```json
{ "command": { "action": "splitPane", "split": "vertical", "profile": "profile1" }, "keys": "ctrl+a" },
{ "command": { "action": "splitPane", "split": "vertical", "profile": "{00000000-0000-0000-0000-000000000000}" }, "keys": "ctrl+b" },
{ "command": { "action": "newTab", "index": 0 }, "keys": "ctrl+c" }
```

<span data-ttu-id="68869-108">また、プロファイルのコマンド ライン実行可能ファイル、開始ディレクトリ、タブ タイトルなど、プロファイルの特定の側面をオーバーライドすることもできます。</span><span class="sxs-lookup"><span data-stu-id="68869-108">Additionally, you can override certain aspects of the profile such as the profile's command line executable, starting directory, or tab title.</span></span> <span data-ttu-id="68869-109">これは、`commandline`、`startingDirectory`、`tabTitle` のいずれかまたは両方を `splitPane` または `newTab` キー バインドに追加することによって実現できます。</span><span class="sxs-lookup"><span data-stu-id="68869-109">This can be accomplished by adding `commandline`, `startingDirectory`, and/or `tabTitle` to a `splitPane` or `newTab` key binding.</span></span>

```json
{ "command": { "action": "splitPane", "split": "auto", "profile": "profile1", "commandline": "foo.exe" }, "keys": "ctrl+a" },
{ "command": { "action": "newTab", "profile": "{00000000-0000-0000-0000-000000000000}", "startingDirectory": "C:\\foo" }, "keys": "ctrl+b" },
{ "command": { "action": "newTab", "index": 0, "tabTitle": "bar", "startingDirectory": "C:\\foo", "commandline": "foo.exe" }, "keys": "ctrl+c" }
```
