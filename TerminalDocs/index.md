---
title: Windows ターミナルの概要
description: Windows ターミナルの概要と、それによってコマンド ライン ワークフローを改善する方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: overview
ms.service: terminal
ms.localizationpriority: high
ms.openlocfilehash: abc0397c3f26da92980377aac2df466fe1bf190e
ms.sourcegitcommit: d8e23557224bc50a82a36dc80ac68b9d11dfdde9
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2020
ms.locfileid: "84720118"
---
# <a name="what-is-windows-terminal"></a>Windows ターミナルとは

Windows ターミナルは、コマンド プロンプト、PowerShell、Linux 用 Windows サブシステム (WSL) などのコマンドライン ツールとシェルのユーザー向けの最新のターミナル アプリケーションです。 主な機能には、複数のタブ、ペイン、Unicode および UTF-8 文字のサポート、GPU で高速化されたテキスト レンダリング エンジン、独自のテーマを作成したり、テキスト、色、背景、およびショートカット キーのバインドをカスタマイズしたりする機能があります。

![Windows ターミナルのスクリーンショット](./images/overview.png)

> [!NOTE]
> [コンソール、ターミナル、シェルの違いとは](https://www.hanselman.com/blog/WhatsTheDifferenceBetweenAConsoleATerminalAndAShell.aspx) Scott Hanselman の説明をお読みください。

## <a name="multiple-profiles-supporting-a-variety-of-command-line-applications"></a>さまざまなコマンドライン アプリケーションをサポートする複数のプロファイル

コマンドライン インターフェイスを持つ任意のアプリケーションを Windows ターミナル内で実行できます。 これには、PowerShell およびコマンド プロンプトから Azure Cloud Shell、Ubuntu や Oh-My-Zsh などの任意の WSL ディストリビューションまで、あらゆるものが含まれます。

## <a name="customized-schemes-and-configurations"></a>カスタマイズされたスキームと構成

Windows ターミナルにさまざまな配色や設定を構成できます。 独自の配色を作成する方法については、[配色に関するページ](./customize-settings/color-schemes.md)を参照してください。 [カスタム ターミナル ギャラリー](./custom-terminal-gallery/powerline-in-powershell.md)でカスタム ターミナル構成を見つけることもできます。

## <a name="custom-key-bindings"></a>カスタム キー バインド

Windows ターミナルでは、より自然に使用できるようにするためにさまざまなカスタム キーの組み合わせが用意されています。 特定のショートカット キーが気に入らない場合は、お好きなものに変更できます。

たとえば、コマンド ラインからテキストをコピーするための既定のショートカット キー バインドは、<kbd>ctrl+shift+c</kbd> です。 これを、<kbd>ctrl+1</kbd> やお好きなものに変更できます。 新しいタブを開くための既定のショートカットは <kbd>ctrl+shift+t</kbd> ですが、これを <kbd>ctrl+2</kbd> に変更することもできます。 開いているタブの間を切り替える既定のショートカットは <kbd>ctrl+tab</kbd> ですが、これを <kbd>ctrl+-</kbd> に変更し、代わりに新しいタブを作成するために使用できます。

キー バインドのカスタマイズについては、[キー バインドに関するページ](./customize-settings/key-bindings.md)を参照してください。

## <a name="unicode-and-utf-8-character-support"></a>Unicode および UTF-8 文字のサポート

Windows ターミナルでは、絵文字やさまざまな言語の文字などの Unicode および UTF-8 文字を表示できます。

## <a name="gpu-accelerated-text-rendering"></a>GPU で高速化されたテキスト レンダリング

Windows ターミナルではテキストのレンダリングに GPU を使用しているため、既定の Windows コマンドライン エクスペリエンスよりもパフォーマンスが向上します。

## <a name="background-image-support"></a>背景画像のサポート

Windows ターミナル ウィンドウ内に背景画像と gif を含めることができます。 プロファイルに背景画像を追加する方法については、[プロファイル設定に関するページ](./customize-settings/profile-settings.md#background-image-settings)を参照してください。

## <a name="command-line-arguments"></a>コマンド ライン引数

コマンドライン引数を使用して、特定の構成で起動するように Windows ターミナルを設定できます。 新しいタブで開くプロファイルや選択されるフォルダー ディレクトリを指定したり、分割したウィンドウ ペインでターミナルを開いたり、フォーカスするタブを選択したりすることができます。

たとえば、左側のペインでコマンド プロンプト プロファイルを実行し、右側のペインを PowerShell と WSL を実行する既定のプロファイルとの間で分割した、3 つのペインがある PowerShell から Windows ターミナルを開くには、次のように入力します。

```bash
wt -p "Command Prompt" `; split-pane -p "Windows PowerShell" `; split-pane -H wsl.exe
```

コマンド ライン引数を設定する方法については、[コマンド ライン引数に関するページ](./command-line-arguments.md)を参照してください。
