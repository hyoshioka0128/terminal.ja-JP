---
title: Windows Terminal での SSH
description: このチュートリアルでは、Windows Terminal での SSH 接続を設定する方法について説明します。
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
# <a name="tutorial-ssh-in-windows-terminal"></a>チュートリアル: Windows Terminal での SSH

Windows 10 には、Windows Terminal で使用できる組み込みの SSH クライアントが用意されています。

このチュートリアルでは、SSH を使用する Windows Terminal でプロファイルを設定する方法について説明します。

## <a name="create-a-profile"></a>プロファイルを作成する

`ssh user@machine` を実行すると、コマンド プロンプトで SSH セッションを開始できます。パスワードを入力するように求められます。 この設定をスタートアップ時に実行する Windows Terminal プロファイルを作成するには、`commandline` 設定を settings.json ファイルのプロファイルに追加します。

```js
"commandline": "ssh cinnamon@roll"
```

## <a name="specify-starting-directory"></a>開始ディレクトリを指定する

Windows Terminal によって起動される ssh セッションの開始ディレクトリを指定するには、次のコマンドを使用します。

```bash
"commandline": "ssh -t bob@foo \"cd /data/bob && exec bash -l\""
```

`-t` フラグは、擬似端末を強制的に割り当てます。 これは、メニュー サービスを実装する場合など、リモート マシン上で任意の画面ベースのプログラムを実行するために使用できます。 Bourne Shell の派生物では単一引用符で囲まれた文字列に対して追加の解析を行わないため、エスケープされた二重引用符を使用する必要があります。

詳細については、次のドキュメントを参照してください。

* [GH の問題:ssh セッションの開始ディレクトリを指定するにはどうすればよいですか。](https://github.com/MicrosoftDocs/terminal/issues/25)
* [StackOverflow:特定のディレクトリに直接 ssh 接続するにはどうすればよいですか。](https://stackoverflow.com/questions/626533/how-can-i-ssh-directly-to-a-particular-directory)

## <a name="resources"></a>参照情報

* [Windows 10 の新しい組み込みの SSH コマンドを有効にして使用する方法](https://www.howtogeek.com/336775/how-to-enable-and-use-windows-10s-built-in-ssh-commands/)
