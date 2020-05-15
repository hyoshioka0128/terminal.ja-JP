---
title: Windows ターミナルのトラブルシューティング
description: Windows ターミナルでの一般的な障害の修正について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: overview
ms.service: terminal
ms.localizationpriority: high
ms.openlocfilehash: 29d3ce72210c30fcbf38393d733c6157670465bb
ms.sourcegitcommit: bb5b7fd7db4b81e0d44e060989dc16b6775c802a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83415877"
---
# <a name="troubleshooting-in-windows-terminal"></a>Windows ターミナルでのトラブルシューティング

このガイドでは、Windows ターミナルを使用するときに発生する可能性のある一般的なエラーと障害について説明します。

## <a name="set-your-wsl-distribution-to-start-in-the-home--directory-when-launched"></a>起動時にホーム `~` ディレクトリで開始するように WSL ディストリビューションを設定します

既定では、プロファイルの `startingDirectory` は `%USERPROFILE%` (`C:\Users\<YourUsername>`) です。 これは Windows パスです。 ただし、WSL の場合は、代わりに WSL ホーム パスを使用することもできます。 `startingDirectory` は Windows スタイルのパスのみを受け入れます。そのため、WSL ディストリビューション内で開始するように設定するには、プレフィックスが必要です。

Windows 10 バージョン 1903 以降では、`\\wsl$\` プレフィックスを使用して、WSL ディストリビューションのファイルシステムに対処できます。 `DistroName` という名前の WSL ディストリビューションの場合は、そのディストリビューションのファイル システムのルートを指す Windows パスとして `\\wsl$\DistroName` を使用します。

たとえば、次の設定では、"Ubuntu-18.04" のディストリビューションがそのホーム ファイル パスで開始されます。

```json
{
    "name": "Ubuntu-18.04",
    "commandline" : "wsl -d Ubuntu-18.04",
    "startingDirectory" : "//wsl$/Ubuntu-18.04/home/<Your Ubuntu Username>",
}
```

## <a name="setting-the-tab-title"></a>タブ タイトルを設定する

シェルでタブ タイトルを自動的に設定するには、[タブ タイトルの設定のチュートリアル](./tutorials/tab-title.md)を参照してください。 独自のタブ タイトルを設定する場合は、次の手順に従って、settings.json ファイルを開きます。

1. 任意のコマンド ラインのプロファイルで、`"suppressApplicationTitle": true` を追加して、シェルから送信されるタイトル変更イベントを抑制します。 この設定 "*のみ*" をプロファイルに追加すると、タブ タイトルがプロファイルの名前に設定されます。

2. プロファイルの名前ではないカスタム タブ タイトルが必要な場合は、`"tabTitle": "TITLE"` を追加します。 "TITLE" を任意のタブ タイトルに置き換えます。

## <a name="command-line-arguments-in-powershell"></a>PowerShell のコマンド ライン引数

PowerShell でコマンド ライン引数を操作する方法については、[コマンド ライン引数に関するページ](./command-line-arguments.md)を参照してください。

## <a name="command-line-arguments-in-wsl"></a>WSL のコマンド ライン引数

WSL でコマンド ライン引数を操作する方法については、[コマンド ライン引数に関するページ](./command-line-arguments.md)を参照してください。

## <a name="problem-setting-startingdirectory"></a>問題の設定 `startingDirectory`

プロファイルで `startingDirectory` が無視されている場合は、まず、settings.json の構文が正しいことを確認してください。 この構文を確認するために、`"$schema": "https://aka.ms/terminal-profiles-schema"` が自動的に挿入されます。 [Visual Studio Code](https://code.visualstudio.com/download) などの一部のアプリケーションでは、挿入されたスキーマを使用して、編集を行うときに json ファイルを検証できます。

設定が正しい場合は、ターミナルの開始ディレクトリを個別に設定するスタートアップ スクリプトを実行している可能性があります。 たとえば、PowerShell には独自のプロファイルの概念があります。 開始ディレクトリを変更すると、Windows ターミナルで定義されている設定よりも優先されます。

または、`commandline` プロファイル設定を使用してスクリプトを実行している場合は、そこに場所を設定している可能性があります。 PowerShell プロファイルと同様に、そこのコマンドが `startingDirectory` プロファイル設定よりも優先されます。

`startingDirectory` の目的は、指定されたディレクトリで新しい Windows ターミナル インスタンスを起動することです。 ターミナルで、そのディレクトリを変更するコードが実行されている場合は、調べてみることをお勧めします。

## <a name="ctrl-does-not-increase-the-font-size"></a>Ctrl+= でフォント サイズが大きくならない

ドイツ語のキーボード レイアウトを使用している場合は、この問題が発生する可能性があります。 メインのキーボード レイアウトがドイツ語に設定されている場合、<kbd>ctrl+=</kbd> は <kbd>ctrl+shift+0</kbd> として逆シリアル化されます。 これは、ドイツ語のキーボードの正しいマッピングです。

さらに重要なことに、アプリが <kbd>ctrl+shift+0</kbd> キーストロークを受け取ることはありません。 これは、複数のキーボード レイアウトをアクティブにしている場合、<kbd>ctrl+shift+0</kbd> は Windows によって予約されるためです。

`Ctrl+=` を正常に機能させるためにこの機能を無効にする場合は、この[ブログ記事](https://winaero.com/blog/change-hotkeys-switch-keyboard-layout-windows-10/)の「Change Hotkeys to Switch Keyboard Layout in Windows 10」 (Windows 10 でホットキーを変更してキーボード レイアウトを切り替える) の手順に従ってください。

[キーボード レイアウトの切り替え] オプションを [割り当てられていません] (または <kbd>ctrl+shift</kbd>) に変更し、 **[OK]** 、 **[適用]** の順に選択します。 <kbd>ctrl+shift+0</kbd> はキー バインドとして機能するようになり、ターミナルに渡されます。

一方、複数の入力言語に対してこのホットキー機能を使用する場合は、settings.json ファイルで[独自のカスタム キー バインドを構成](./customize-settings/key-bindings.md)できます。
