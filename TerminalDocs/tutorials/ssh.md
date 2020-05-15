---
title: Windows ターミナル SSH
description: このチュートリアルでは、Windows ターミナルで SSH 接続を設定する方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: tutorial
ms.service: terminal
ms.openlocfilehash: c418460cd47935ed8b8eb57ebdb89322d543a20e
ms.sourcegitcommit: bb5b7fd7db4b81e0d44e060989dc16b6775c802a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83415867"
---
# <a name="tutorial-ssh-in-windows-terminal"></a>チュートリアル: Windows ターミナルでの SSH

Windows 10 には、Windows ターミナルで使用できる組み込みの SSH クライアントが用意されています。

このチュートリアルでは、SSH を使用する Windows ターミナルでプロファイルを設定する方法について説明します。

## <a name="create-a-profile"></a>プロファイルを作成する

`ssh user@machine` を実行すると、コマンド プロンプトで SSH セッションを開始できます。パスワードを入力するように求められます。 この設定をスタートアップ時に実行する Windows ターミナルプロファイルを作成するには、`commandline` 設定を settings.json ファイルのプロファイルに追加します。

```js
"commandline": "ssh cinnamon@roll"
```

## <a name="resources"></a>参照情報

* [Windows 10 の新しい組み込みの SSH コマンドを有効にして使用する方法](https://www.howtogeek.com/336775/how-to-enable-and-use-windows-10s-built-in-ssh-commands/)
