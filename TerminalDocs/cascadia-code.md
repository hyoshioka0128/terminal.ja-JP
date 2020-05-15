---
title: Windows ターミナル Cascadia Code
description: さまざまな Cascadia Code フォントと、それらが Windows ターミナルでどのように機能するかについて説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: overview
ms.service: terminal
ms.openlocfilehash: e9af1ea8445514534c64410fe494d35186d028b5
ms.sourcegitcommit: bb5b7fd7db4b81e0d44e060989dc16b6775c802a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83415857"
---
# <a name="cascadia-code"></a><span data-ttu-id="63335-103">Cascadia Code</span><span class="sxs-lookup"><span data-stu-id="63335-103">Cascadia Code</span></span>

<span data-ttu-id="63335-104">Cascadia Code は、コマンド ライン アプリケーションやテキスト エディターに新鮮なエクスペリエンスを提供する、Microsoft が提供する新しい等幅フォントです。</span><span class="sxs-lookup"><span data-stu-id="63335-104">Cascadia Code is a new monospaced font from Microsoft that provides a fresh experience for command line applications and text editors.</span></span> <span data-ttu-id="63335-105">Cascadia Code は、Windows ターミナルと共に開発されました。</span><span class="sxs-lookup"><span data-stu-id="63335-105">Cascadia Code was developed alongside Windows Terminal.</span></span> <span data-ttu-id="63335-106">このフォントは、ターミナル アプリケーションや、Visual Studio や Visual Studio Code などのテキスト エディターで使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="63335-106">This font is most recommended to be used with terminal applications and text editors such as Visual Studio and Visual Studio Code.</span></span>

## <a name="cascadia-code-versions"></a><span data-ttu-id="63335-107">Cascadia Code のバージョン</span><span class="sxs-lookup"><span data-stu-id="63335-107">Cascadia Code versions</span></span>

<span data-ttu-id="63335-108">Cascadia Code には、合字とグリフを含む使用可能な複数のバージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="63335-108">There are multiple versions of Cascadia Code available that include ligatures and glyphs.</span></span> <span data-ttu-id="63335-109">Cascadia Code のすべてのバージョンが、[Cascadia Code GitHub リリース ページ](https://github.com/microsoft/cascadia-code/releases)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="63335-109">All versions of Cascadia Code can be downloaded from the [Cascadia Code GitHub releases page](https://github.com/microsoft/cascadia-code/releases).</span></span> <span data-ttu-id="63335-110">Windows ターミナルでは、Cascadia Code と Cascadia Mono がパッケージに付属しており、既定で Cascadia Mono が使用されています。</span><span class="sxs-lookup"><span data-stu-id="63335-110">Windows Terminal ships Cascadia Code and Cascadia Mono in its package and uses Cascadia Mono by default.</span></span>

| <span data-ttu-id="63335-111">フォント名</span><span class="sxs-lookup"><span data-stu-id="63335-111">Font Name</span></span> | <span data-ttu-id="63335-112">合字を含む</span><span class="sxs-lookup"><span data-stu-id="63335-112">Includes Ligatures</span></span> | <span data-ttu-id="63335-113">Powerline Glyph を含む</span><span class="sxs-lookup"><span data-stu-id="63335-113">Includes Powerline Glyphs</span></span> |
| --------- | ------------------ | ------------------------- |
| <span data-ttu-id="63335-114">Cascadia Code</span><span class="sxs-lookup"><span data-stu-id="63335-114">Cascadia Code</span></span> | <span data-ttu-id="63335-115">はい</span><span class="sxs-lookup"><span data-stu-id="63335-115">Yes</span></span> | <span data-ttu-id="63335-116">いいえ</span><span class="sxs-lookup"><span data-stu-id="63335-116">No</span></span> |
| <span data-ttu-id="63335-117">Cascadia Mono</span><span class="sxs-lookup"><span data-stu-id="63335-117">Cascadia Mono</span></span> | <span data-ttu-id="63335-118">いいえ</span><span class="sxs-lookup"><span data-stu-id="63335-118">No</span></span>  | <span data-ttu-id="63335-119">いいえ</span><span class="sxs-lookup"><span data-stu-id="63335-119">No</span></span> |
| <span data-ttu-id="63335-120">Cascadia Code PL</span><span class="sxs-lookup"><span data-stu-id="63335-120">Cascadia Code PL</span></span> | <span data-ttu-id="63335-121">はい</span><span class="sxs-lookup"><span data-stu-id="63335-121">Yes</span></span> | <span data-ttu-id="63335-122">はい</span><span class="sxs-lookup"><span data-stu-id="63335-122">Yes</span></span> |
| <span data-ttu-id="63335-123">Cascadia Mono PL</span><span class="sxs-lookup"><span data-stu-id="63335-123">Cascadia Mono PL</span></span> | <span data-ttu-id="63335-124">いいえ</span><span class="sxs-lookup"><span data-stu-id="63335-124">No</span></span> | <span data-ttu-id="63335-125">はい</span><span class="sxs-lookup"><span data-stu-id="63335-125">Yes</span></span> |

## <a name="powerline-and-programming-ligatures"></a><span data-ttu-id="63335-126">Powerline とプログラミングの合字</span><span class="sxs-lookup"><span data-stu-id="63335-126">Powerline and programming ligatures</span></span>

<span data-ttu-id="63335-127">Powerline は、一般的なコマンド ライン プラグインで、プロンプトに追加情報を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="63335-127">Powerline is a common command line plugin that allows you to display additional information in your prompt.</span></span> <span data-ttu-id="63335-128">この情報を適切に表示するために、いくつかの追加のグリフが使用されています。</span><span class="sxs-lookup"><span data-stu-id="63335-128">It uses a few additional glyphs to display this information properly.</span></span> <span data-ttu-id="63335-129">コマンド プロンプトでの Powerline の設定の詳細については、[Windows ターミナルの Powerline に関するページ](./tutorials/powerline-setup.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63335-129">To learn more about setting up Powerline in your command prompt, visit the [Powerline in Windows Terminal](./tutorials/powerline-setup.md) page.</span></span>

<span data-ttu-id="63335-130">プログラミング合字は、文字を組み合わせることによって作成されるグリフです。</span><span class="sxs-lookup"><span data-stu-id="63335-130">Programming ligatures are glyphs that are created by combining characters.</span></span> <span data-ttu-id="63335-131">これらは、コードを記述するときに役立つものである必要があります。</span><span class="sxs-lookup"><span data-stu-id="63335-131">They are must useful when writing code.</span></span> <span data-ttu-id="63335-132">合字は、"Code" のバリアントには含まれていますが、"Mono" のバリアントでは除外されています。</span><span class="sxs-lookup"><span data-stu-id="63335-132">The "Code" variants include ligatures, whereas the "Mono" variants exclude them.</span></span>

![Cascadia Code のプログラミング合字](./images/programming-ligatures.gif)

## <a name="contributing-to-cascadia-code"></a><span data-ttu-id="63335-134">Cascadia Code への貢献</span><span class="sxs-lookup"><span data-stu-id="63335-134">Contributing to Cascadia Code</span></span>

<span data-ttu-id="63335-135">Cascadia Code は、[GitHub](https://github.com/microsoft/cascadia-code) の [SIL Open Font License](https://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&id=OFL) でライセンス供与されています。</span><span class="sxs-lookup"><span data-stu-id="63335-135">Cascadia Code is licensed under the [SIL Open Font license](https://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&id=OFL) on [GitHub](https://github.com/microsoft/cascadia-code).</span></span>
