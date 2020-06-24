---
title: Windows ターミナルの検索
description: Windows ターミナルでの検索方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: how-to
ms.service: terminal
ms.openlocfilehash: a0bc6ecfb337ab11414210fd4d3fe6cd565ad5bf
ms.sourcegitcommit: a489b75e14e2c123bf6b4ac2a15ff85b515564be
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2020
ms.locfileid: "83553254"
---
# <a name="how-to-search-in-windows-terminal"></a><span data-ttu-id="bbc57-103">Windows ターミナルでの検索方法</span><span class="sxs-lookup"><span data-stu-id="bbc57-103">How to search in Windows Terminal</span></span>

<span data-ttu-id="bbc57-104">Windows ターミナルには、特定のキーワードのテキスト バッファーを調べることができる検索機能が付属しています。</span><span class="sxs-lookup"><span data-stu-id="bbc57-104">Windows Terminal comes with a search feature that allows you to look through the text buffer for a specific keyword.</span></span> <span data-ttu-id="bbc57-105">これは、以前に実行したコマンドを検索したり、特定のファイル名を検索したりする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="bbc57-105">This is useful when trying to find a command you had run before or for a specific file name.</span></span>

## <a name="using-search"></a><span data-ttu-id="bbc57-106">検索を使用する</span><span class="sxs-lookup"><span data-stu-id="bbc57-106">Using search</span></span>

<span data-ttu-id="bbc57-107">既定では、<kbd>ctrl+shift+f</kbd> を入力して、検索ダイアログを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="bbc57-107">By default, you can open the search dialog by typing <kbd>ctrl+shift+f</kbd>.</span></span> <span data-ttu-id="bbc57-108">開いたら、テキスト ボックスに検索するキーワードを入力し、<kbd>Enter</kbd> キーを押して検索します。</span><span class="sxs-lookup"><span data-stu-id="bbc57-108">Once opened, you can type the keyword you're looking for into the text box and hit <kbd>enter</kbd> to search.</span></span>

<span data-ttu-id="bbc57-109">![Windows ターミナル検索のスクリーンショット](./images/search.png)
_構成:[PowerShell での Powerline](./custom-terminal-gallery/powerline-in-powershell.md)_</span><span class="sxs-lookup"><span data-stu-id="bbc57-109">![Windows Terminal search screenshot](./images/search.png)
_Configuration: [Powerline in PowerShell](./custom-terminal-gallery/powerline-in-powershell.md)_</span></span>

## <a name="directional-search"></a><span data-ttu-id="bbc57-110">方向検索</span><span class="sxs-lookup"><span data-stu-id="bbc57-110">Directional search</span></span>

<span data-ttu-id="bbc57-111">ターミナルでは、既定でテキスト バッファーの一番下から一番上に向かって検索されます。</span><span class="sxs-lookup"><span data-stu-id="bbc57-111">The terminal will default to searching from the bottom to the top of the text buffer.</span></span> <span data-ttu-id="bbc57-112">検索の方向を変更するには、検索ダイアログでいずれかの矢印を選択します。</span><span class="sxs-lookup"><span data-stu-id="bbc57-112">You can change the search direction by selecting one of the arrows in the search dialog.</span></span>

![Windows ターミナルの方向検索のスクリーンショット](./images/search-direction.gif)

## <a name="case-match-search"></a><span data-ttu-id="bbc57-114">大文字と小文字を区別する検索</span><span class="sxs-lookup"><span data-stu-id="bbc57-114">Case match search</span></span>

<span data-ttu-id="bbc57-115">検索結果を絞り込むには、検索のオプションとして大文字と小文字の区別を追加します。</span><span class="sxs-lookup"><span data-stu-id="bbc57-115">If you'd like to narrow down your search results, you can add case matching as an option in your search.</span></span> <span data-ttu-id="bbc57-116">大文字と小文字の区別を切り替えるには、大文字と小文字を区別するボタンを選択します。結果には、特定の文字の大文字と小文字を区別して入力されたキーワードと一致するものだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bbc57-116">You can toggle case matching by selecting the case match button, and the results that appear will only match the keyword entered with its specific letter casing.</span></span>

![Windows ターミナルの大文字と小文字を区別する検索のスクリーンショット](./images/search-case-match.gif)

## <a name="searching-within-panes"></a><span data-ttu-id="bbc57-118">ペイン内の検索</span><span class="sxs-lookup"><span data-stu-id="bbc57-118">Searching within panes</span></span>

<span data-ttu-id="bbc57-119">検索ダイアログは、[ペイン](./panes.md)でも機能します。</span><span class="sxs-lookup"><span data-stu-id="bbc57-119">The search dialog works with [panes](./panes.md) as well.</span></span> <span data-ttu-id="bbc57-120">ペインにフォーカスを置くと、検索ダイアログが開き、そのペインの右上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bbc57-120">When focused on a pane, you can open the search dialog and it will appear on the upper-right of that pane.</span></span> <span data-ttu-id="bbc57-121">入力したキーワードは、そのペイン内に見つかった結果にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="bbc57-121">Then any keyword you enter will only show results found within that pane.</span></span>

![Windows ターミナル ペイン検索のスクリーンショット](./images/search-panes.gif)

## <a name="customize-the-search-key-binding"></a><span data-ttu-id="bbc57-123">検索キー バインドのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="bbc57-123">Customize the search key binding</span></span>

<span data-ttu-id="bbc57-124">お好みの任意のキー バインド (ショートカット キーの組み合わせ) を使用して検索ダイアログを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="bbc57-124">You can open the search dialog with any key binding (shortcut key combination) that you prefer.</span></span> <span data-ttu-id="bbc57-125">検索キー バインドを変更するには、settings.json ファイルを開き、`find` コマンドを検索します。</span><span class="sxs-lookup"><span data-stu-id="bbc57-125">To change the search key binding, open your settings.json file and search for the `find` command.</span></span> <span data-ttu-id="bbc57-126">既定では、このコマンドは `ctrl+shift+f` に設定されています。</span><span class="sxs-lookup"><span data-stu-id="bbc57-126">By default, this command is set to `ctrl+shift+f`.</span></span>

```json
// Press ctrl+shift+f to open the search box
        { "command": "find", "keys": "ctrl+shift+f" },
```

<span data-ttu-id="bbc57-127">たとえば、`ctrl+f` を入力したときに検索ダイアログが開くように、"ctrl+shift+f" から "ctrl+f" に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="bbc57-127">For example, you can change "ctrl+shift+f" to "ctrl+f", so when typing `ctrl+f`, the search dialog will open.</span></span>

<span data-ttu-id="bbc57-128">キー バインドの詳細については、[キー バインドに関するページ](./customize-settings/key-bindings.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbc57-128">To learn more about key bindings, visit the [key bindings page](./customize-settings/key-bindings.md).</span></span>
