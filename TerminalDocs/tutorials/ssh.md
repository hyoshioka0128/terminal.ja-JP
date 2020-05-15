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
# <a name="tutorial-ssh-in-windows-terminal"></a><span data-ttu-id="2bc53-103">チュートリアル: Windows ターミナルでの SSH</span><span class="sxs-lookup"><span data-stu-id="2bc53-103">Tutorial: SSH in Windows Terminal</span></span>

<span data-ttu-id="2bc53-104">Windows 10 には、Windows ターミナルで使用できる組み込みの SSH クライアントが用意されています。</span><span class="sxs-lookup"><span data-stu-id="2bc53-104">Windows 10 has a build-in SSH client that you can use in the Windows Terminal.</span></span>

<span data-ttu-id="2bc53-105">このチュートリアルでは、SSH を使用する Windows ターミナルでプロファイルを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2bc53-105">In this tutorial, you'll learn how to set up a profile in Windows Terminal that uses SSH.</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="2bc53-106">プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="2bc53-106">Create a profile</span></span>

<span data-ttu-id="2bc53-107">`ssh user@machine` を実行すると、コマンド プロンプトで SSH セッションを開始できます。パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="2bc53-107">You can start an SSH session in your command prompt by executing `ssh user@machine` and you will be prompted to enter your password.</span></span> <span data-ttu-id="2bc53-108">この設定をスタートアップ時に実行する Windows ターミナルプロファイルを作成するには、`commandline` 設定を settings.json ファイルのプロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="2bc53-108">You can create a Windows Terminal profile that does this on startup by adding the `commandline` setting to a profile in your settings.json file.</span></span>

```js
"commandline": "ssh cinnamon@roll"
```

## <a name="resources"></a><span data-ttu-id="2bc53-109">参照情報</span><span class="sxs-lookup"><span data-stu-id="2bc53-109">Resources</span></span>

* [<span data-ttu-id="2bc53-110">Windows 10 の新しい組み込みの SSH コマンドを有効にして使用する方法</span><span class="sxs-lookup"><span data-stu-id="2bc53-110">How to Enable and Use Windows 10’s New Built-in SSH Commands</span></span>](https://www.howtogeek.com/336775/how-to-enable-and-use-windows-10s-built-in-ssh-commands/)
