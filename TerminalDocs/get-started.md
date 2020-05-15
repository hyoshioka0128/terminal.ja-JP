---
title: Windows ターミナルのインストール
description: このクイックスタートでは、Windows ターミナルをインストールして実行する方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: quickstart
ms.service: terminal
ms.localizationpriority: high
ms.openlocfilehash: 901e3a0f447cdfe19a69ee43c7f76ed529d87108
ms.sourcegitcommit: bb5b7fd7db4b81e0d44e060989dc16b6775c802a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83415847"
---
# <a name="install-and-set-up-windows-terminal"></a>Windows ターミナルをインストールしてセットアップする

## <a name="installation"></a>インストール

Windows ターミナルは、[Microsoft Store](https://aka.ms/terminal) からインストールできます。

Microsoft Store にアクセスできない場合は、[GitHub のリリース ページ](https://github.com/microsoft/terminal/releases)でビルドが公開されています。 GitHub からインストールしたターミナルの場合、新しいバージョンが公開されても自動的には更新されません。

## <a name="first-run"></a>最初の実行

インストール後にターミナルを開くと、開いているタブで PowerShell を既定のプロファイルとして開始されます。

![Windows ターミナルの初回実行](./images/first-run.png)

### <a name="dynamic-profiles"></a>動的プロファイル

WSL ディストリビューションまたは PowerShell の複数のバージョンがインストールされている場合、ターミナルによって自動的にプロファイルが作成されます。 動的プロファイルの詳細については、[動的プロファイルに関するページ](./dynamic-profiles.md)を参照してください。

## <a name="open-a-new-tab"></a>新しいタブを開く

<kbd>Ctrl + Shift + T</kbd> キーを押すか、[+] (プラス) ボタンを選択することで、既定のプロファイルの新しいタブを開くことができます。 別のプロファイルを開くには、[+] ボタンの横にある [˅] (矢印) を選択して、ドロップダウン メニューを開きます。 そこから、開くプロファイルを選択できます。

## <a name="open-a-new-pane"></a>新しいペインを開く

ペインを使用すると、複数のシェルを並行して実行できます。 ペインを開くには、<kbd>Alt + Shift + D</kbd> キーを押します。 このキー バインドを使用すると、フォーカスが設定されているプロファイルのペインが重複して開かれます。 ペインの詳細については、[ペインに関するページ](./panes.md)を参照してください。

## <a name="configuration"></a>構成

Windows ターミナルの設定をカスタマイズするには、ドロップダウン メニューの **[設定]** を選択します。 これにより、既定のテキスト エディターで `settings.json` ファイルが開きます。 (既定のテキスト エディターは、[Windows 設定](ms-settings:defaultapps)で定義されています)。

ターミナルでは、アプリケーション全体に影響を与える[グローバル プロパティ](./customize-settings/global-settings.md)、各プロファイルの設定に影響する[プロファイル プロパティ](./customize-settings/profile-settings.md)、キーボードを使用してターミナルと対話できるようにする[キー バインド](./customize-settings/key-bindings.md)のカスタマイズがサポートされています。

## <a name="command-line-arguments"></a>コマンド ライン引数

コマンド ライン引数を使用すると、特定の構成でターミナルを起動できます。 これらの引数を使用すると、カスタム プロファイル設定が適用された特定のタブとペインでターミナルを開くことができます。 コマンド ライン引数の詳細については、[コマンド ライン引数に関するページ](./command-line-arguments.md)を参照してください。

## <a name="troubleshooting"></a>トラブルシューティング

ターミナルの使用に関して問題が発生した場合は、[トラブルシューティングのページ](./troubleshooting.md)を参照してください。 バグが見つかった場合、または要求したい機能がある場合は、ターミナルの **[バージョン情報]** メニューでフィードバック リンクを選択して [GitHub のページ](https://github.com/microsoft/terminal)に移動し、そこで新しいイシューを報告することができます。
