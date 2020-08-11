---
title: Windows Terminal のタブのタイトルの設定
description: このチュートリアルでは、Windows Terminal でタブのタイトルを設定する方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: tutorial
ms.service: terminal
ms.openlocfilehash: 94c0d9afc8ccd3d95a3f52f5f9f6bdd0cb05bc12
ms.sourcegitcommit: bb5b7fd7db4b81e0d44e060989dc16b6775c802a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83416467"
---
# <a name="tutorial-configure-tab-titles-in-windows-terminal"></a>チュートリアル: Windows Terminal でタブのタイトルを構成する

既定では、タブのタイトルはシェルのタイトルに設定されます。 タブが複数のペインで構成されている場合、タブのタイトルは、現在フォーカスがあるペインのタイトルに設定されます。 タブのタイトルとして設定する内容をカスタマイズする場合は、このチュートリアルに従ってください。

このチュートリアルでは、次の方法について説明します。

> [!div class="checklist"]
> * `tabTitle` 設定を使用する
> * シェルのタイトルを設定する
> * `suppressApplicationTitle` 設定を使用する

## <a name="use-the-tabtitle-setting"></a>`tabTitle` 設定を使用する

`tabTitle` 設定では、シェルの新しいインスタンスの開始タイトルを定義できます。 設定されていない場合は、代わりにプロファイル `name` が使用されます。 この設定への応答はシェルごとに異なります。

| Shell | 動作 |
| ----- | -------- |
| PowerShell | タイトルが設定されます。 |
| Command Prompt | タイトルが設定されます。 コマンドが実行されている場合は、一時的にタイトルの末尾にそれが追加されます。 |
| Ubuntu | タイトルは無視され、代わりに `user@machine:path` に設定されます |
| Debian | タイトルが設定されます。 |

> [!NOTE]
> Ubuntu と Debian ではどちらも bash が実行されますが、動作は異なります。 これは、ディストリビューションによって動作が異なる場合があることを示しています。

## <a name="set-the-shells-title"></a>シェルのタイトルを設定する

シェルは、自身のタイトルを完全に制御できます。 ただし、各シェルのタイトルの設定方法は異なります。

| Shell | コマンド |
| ----- | ------- |
| PowerShell | `$Host.UI.RawUI.WindowTitle = "New Title"` |
| Command Prompt | `TITLE "New Title"` |
| bash* | `echo -ne "\033]0;New Title\a"` |

一部の Linux ディストリビューション (Ubuntu) では、シェルと対話するときにタイトルが自動的に設定されることに注意してください。 上記のコマンドが動作しない場合は、次のコマンドを実行します。

```bash
PS1=$
PROMPT_COMMAND=
echo -ne "\033]0;New Title\a"
```

これにより、タイトルが "New Title" に変更され、プロンプトが "$" に設定されます。

## <a name="use-the-suppressapplicationtitle-setting"></a>`suppressApplicationTitle` 設定を使用する

シェルは自身のタイトルを制御しているため、いつでもタブタイトルを上書きすることができます。 たとえば、PowerShell の `posh-git` モジュールでは、Git リポジトリに関する情報がタイトルに追加されます。

Windows Terminal では、プロファイルの `suppressApplicationTitle` を `true` に設定することによって、タイトルの変更を抑制できます。 これにより、プロファイルの新しいインスタンスによって、表示されるタイトルが `tabTitle` に設定されます。 `tabTitle` が設定されていない場合、表示されるタイトルはプロファイルの `name` に設定されます。

これにより、タブに表示されている表示タイトルからシェルのタイトルが分離されることに注意してください。タイトルが設定されているシェルの変数を読み取ると、タブのタイトルと異なる場合があります。

## <a name="resources"></a>参照情報

* [コンソールのタイトルが現在の作業ディレクトリになるように設定する](https://devblogs.microsoft.com/powershell/setting-the-console-title-to-be-your-current-working-directory/)
* [Ubuntu 16.04 でターミナルのタイトルを変更する](https://www.zachpfeffer.com/single-post/Change-the-title-of-a-terminal-on-Ubuntu-1604)
