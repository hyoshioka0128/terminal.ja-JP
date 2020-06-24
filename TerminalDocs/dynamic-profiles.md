---
title: Windows ターミナル動的プロファイル
description: Windows ターミナルの動的プロファイルについて説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: concept
ms.service: terminal
ms.openlocfilehash: 7ab394cea84eaab08b14edf859ef0cd9390d7267
ms.sourcegitcommit: a489b75e14e2c123bf6b4ac2a15ff85b515564be
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2020
ms.locfileid: "83553194"
---
# <a name="dynamic-profiles-in-windows-terminal"></a>Windows ターミナルでの動的プロファイル

Windows ターミナルでは、Linux 用 Windows サブシステム (WSL) と PowerShell のシェルがマシンにインストールされている場合、これらに対するプロファイルが自動的に作成されます。 これにより、実行可能ファイルを探す必要なしに、すべてのシェルをターミナルに簡単に含めることができるようになります。 これらのプロファイルは、`source` プロパティを使用して生成されます。このプロパティでは、適切な実行可能ファイルを見つける場所がターミナルに通知されます。

ターミナルをインストールすると、PowerShell が既定のプロファイルとして設定されます。 既定のプロファイルを変更する方法については、[グローバル設定に関するページ](./customize-settings/global-settings.md)を参照してください。

![Windows ターミナル動的プロファイル](./images/dynamic-profiles.png)
_構成: [ライト テーマ](./custom-terminal-gallery/frosted-glass-theme.md)_

## <a name="installing-a-new-shell-after-installing-windows-terminal"></a>Windows ターミナルをインストールした後で新しいシェルをインストールする

新しいシェルがインストールされるのがターミナルのインストールの前か後かに関係なく、ターミナルでは新しくインストールされたシェルに対する新しいプロファイルが作成されます。

## <a name="hide-a-profile"></a>プロファイルを非表示にする

ターミナルのドロップダウン メニューにプロファイルが表示されないようにするには、settings.json ファイルのプロファイル オブジェクトに `hidden` プロパティを追加して、`true` に設定します。

```json
"hidden": true
```

動的に作成されたプロファイルを削除すると、ターミナルによって自動的にプロファイルが再生成され、settings.json ファイルで置き換えられます。

## <a name="prevent-a-profile-from-being-generated"></a>プロファイルが生成されないようにする

動的プロファイルが生成されないようにするには、プロファイル ジェネレーターをグローバル設定の `disabledProfileSources` 配列に追加します。 この設定の詳細については、[グローバル設定に関するページ](./customize-settings/global-settings.md#disable-dynamic-profiles)を参照してください。

```json
"disabledProfileSources": ["Windows.Terminal.Wsl", "Windows.Terminal.Azure", "Windows.Terminal.PowershellCore"]
```
