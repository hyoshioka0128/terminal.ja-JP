---
title: Windows ターミナルの検索
description: Windows ターミナルでの検索方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: how-to
ms.service: terminal
ms.openlocfilehash: 94932d71e6543a83650e2e2a5febcb0206e22548
ms.sourcegitcommit: bb5b7fd7db4b81e0d44e060989dc16b6775c802a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83416337"
---
# <a name="how-to-search-in-windows-terminal"></a>Windows ターミナルでの検索方法

Windows ターミナルには、特定のキーワードのテキスト バッファーを調べることができる検索機能が付属しています。 これは、以前に実行したコマンドを検索したり、特定のファイル名を検索したりする場合に便利です。

## <a name="using-search"></a>検索を使用する

既定では、<kbd>ctrl+shift+f</kbd> を入力して、検索ダイアログを開くことができます。 開いたら、テキスト ボックスに検索するキーワードを入力し、<kbd>Enter</kbd> キーを押して検索します。

![Windows ターミナル検索のスクリーンショット](./images/search.png)
_構成:[PowerShell での Powerline](./custom-terminal-gallery/powerline-in-powershell.md)_

## <a name="directional-search"></a>方向検索

ターミナルでは、既定でテキスト バッファーの一番下から一番上に向かって検索されます。 検索の方向を変更するには、検索ダイアログでいずれかの矢印を選択します。

![Windows ターミナルの方向検索のスクリーンショット](./images/search-direction.gif)

## <a name="case-match-search"></a>大文字と小文字を区別する検索

検索結果を絞り込むには、検索のオプションとして大文字と小文字の区別を追加します。 大文字と小文字の区別を切り替えるには、大文字と小文字を区別するボタンを選択します。結果には、特定の文字の大文字と小文字を区別して入力されたキーワードと一致するものだけが表示されます。

![Windows ターミナルの大文字と小文字を区別する検索のスクリーンショット](./images/search-case-match.gif)

## <a name="searching-within-panes"></a>ペイン内の検索

検索ダイアログは、[ペイン](./panes.md)でも機能します。 ペインにフォーカスを置くと、検索ダイアログが開き、そのペインの右上に表示されます。 入力したキーワードは、そのペイン内に見つかった結果にのみ表示されます。

![Windows ターミナル ペイン検索のスクリーンショット](./images/search-panes.gif)

## <a name="customize-the-search-key-binding"></a>検索キー バインドのカスタマイズ

お好みの任意のキー バインド (ショートカット キーの組み合わせ) を使用して検索ダイアログを開くことができます。 検索キー バインドを変更するには、settings.json ファイルを開き、`find` コマンドを検索します。 既定では、このコマンドは `ctrl+shift+f` に設定されています。

```json
// Press ctrl+shift+f to open the search box
        { "command": "find", "keys": "ctrl+shift+f" },
```

たとえば、`ctrl+f` を入力したときに検索ダイアログが開くように、"ctrl+shift+f" から "ctrl+f" に変更することができます。

キー バインドの詳細については、[キー バインドに関するページ](./customize-settings/key-bindings.md)を参照してください。
