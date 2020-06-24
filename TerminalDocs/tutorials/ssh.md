---
title: Windows ターミナル SSH
description: このチュートリアルでは、Windows ターミナルで SSH 接続を設定する方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: tutorial
ms.service: terminal
ms.openlocfilehash: 02f4704b81cd0d287c207f0138ef27c537929711
ms.sourcegitcommit: bae07a8dd2010a95de4d53b1465abe226e4ad18e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2020
ms.locfileid: "83856340"
---
# <a name="tutorial-ssh-in-windows-terminal"></a><span data-ttu-id="b253c-103">チュートリアル: Windows ターミナルでの SSH</span><span class="sxs-lookup"><span data-stu-id="b253c-103">Tutorial: SSH in Windows Terminal</span></span>

<span data-ttu-id="b253c-104">Windows 10 には、Windows ターミナルで使用できる組み込みの SSH クライアントが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b253c-104">Windows 10 has a built-in SSH client that you can use in Windows Terminal.</span></span>

<span data-ttu-id="b253c-105">このチュートリアルでは、SSH を使用する Windows ターミナルでプロファイルを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b253c-105">In this tutorial, you'll learn how to set up a profile in Windows Terminal that uses SSH.</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="b253c-106">プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="b253c-106">Create a profile</span></span>

<span data-ttu-id="b253c-107">`ssh user@machine` を実行すると、コマンド プロンプトで SSH セッションを開始できます。パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="b253c-107">You can start an SSH session in your command prompt by executing `ssh user@machine` and you will be prompted to enter your password.</span></span> <span data-ttu-id="b253c-108">この設定をスタートアップ時に実行する Windows ターミナルプロファイルを作成するには、`commandline` 設定を settings.json ファイルのプロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="b253c-108">You can create a Windows Terminal profile that does this on startup by adding the `commandline` setting to a profile in your settings.json file.</span></span>

```js
"commandline": "ssh cinnamon@roll"
```

## <a name="specify-starting-directory"></a><span data-ttu-id="b253c-109">開始ディレクトリを指定する</span><span class="sxs-lookup"><span data-stu-id="b253c-109">Specify starting directory</span></span>

<span data-ttu-id="b253c-110">Windows ターミナルによって起動される ssh セッションの開始ディレクトリを指定するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b253c-110">To specify the starting directory for a ssh session invoked by Windows Terminal, you can use this command:</span></span>

```bash
"commandline": "ssh -t bob@foo \"cd /data/bob && exec bash -l\""
```

<span data-ttu-id="b253c-111">`-t` フラグは、擬似端末を強制的に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b253c-111">The `-t` flag forces pseudo-terminal allocation.</span></span> <span data-ttu-id="b253c-112">これは、メニュー サービスを実装する場合など、リモート マシン上で任意の画面ベースのプログラムを実行するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="b253c-112">This can be used to execute arbitrary screen-based programs on a remote machine, e.g. when implementing menu services.</span></span> <span data-ttu-id="b253c-113">Bourne Shell の派生物では単一引用符で囲まれた文字列に対して追加の解析を行わないため、エスケープされた二重引用符を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b253c-113">You will need to use escaped double quotes as bourne shell derivatives don't do any additional parsing for a string in single quotes.</span></span>

<span data-ttu-id="b253c-114">詳細については、次のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b253c-114">For more information, see:</span></span>

* [<span data-ttu-id="b253c-115">GH の問題:ssh セッションの開始ディレクトリを指定するにはどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="b253c-115">GH Issue: How to specify the starting directory for a ssh session?</span></span>](https://github.com/MicrosoftDocs/terminal/issues/25)
* [<span data-ttu-id="b253c-116">StackOverflow:特定のディレクトリに直接 ssh 接続するにはどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="b253c-116">StackOverflow: How can I ssh directly to a particular directory?</span></span>](https://stackoverflow.com/questions/626533/how-can-i-ssh-directly-to-a-particular-directory)

## <a name="resources"></a><span data-ttu-id="b253c-117">参照情報</span><span class="sxs-lookup"><span data-stu-id="b253c-117">Resources</span></span>

* [<span data-ttu-id="b253c-118">Windows 10 の新しい組み込みの SSH コマンドを有効にして使用する方法</span><span class="sxs-lookup"><span data-stu-id="b253c-118">How to Enable and Use Windows 10’s New Built-in SSH Commands</span></span>](https://www.howtogeek.com/336775/how-to-enable-and-use-windows-10s-built-in-ssh-commands/)
