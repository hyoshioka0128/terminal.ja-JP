---
title: Windows ターミナル Cascadia Code
description: さまざまな Cascadia Code フォントと、それらが Windows ターミナルでどのように機能するかについて説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: overview
ms.service: terminal
ms.openlocfilehash: c2d9b8461c168639f1453050e18f0650afb738fb
ms.sourcegitcommit: d8e23557224bc50a82a36dc80ac68b9d11dfdde9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2020
ms.locfileid: "84720098"
---
# <a name="cascadia-code"></a><span data-ttu-id="6c62f-103">Cascadia Code</span><span class="sxs-lookup"><span data-stu-id="6c62f-103">Cascadia Code</span></span>

<span data-ttu-id="6c62f-104">Cascadia Code は、コマンドライン アプリケーションやテキスト エディターに新鮮なエクスペリエンスを提供する、Microsoft が提供する新しい等幅フォントです。</span><span class="sxs-lookup"><span data-stu-id="6c62f-104">Cascadia Code is a new monospaced font from Microsoft that provides a fresh experience for command-line applications and text editors.</span></span> <span data-ttu-id="6c62f-105">Cascadia Code は、Windows ターミナルと共に開発されました。</span><span class="sxs-lookup"><span data-stu-id="6c62f-105">Cascadia Code was developed alongside Windows Terminal.</span></span> <span data-ttu-id="6c62f-106">このフォントは、ターミナル アプリケーションや、Visual Studio や Visual Studio Code などのテキスト エディターで使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6c62f-106">This font is most recommended to be used with terminal applications and text editors such as Visual Studio and Visual Studio Code.</span></span>

## <a name="cascadia-code-versions"></a><span data-ttu-id="6c62f-107">Cascadia Code のバージョン</span><span class="sxs-lookup"><span data-stu-id="6c62f-107">Cascadia Code versions</span></span>

<span data-ttu-id="6c62f-108">Cascadia Code には、合字とグリフを含む使用可能な複数のバージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="6c62f-108">There are multiple versions of Cascadia Code available that include ligatures and glyphs.</span></span> <span data-ttu-id="6c62f-109">Cascadia Code のすべてのバージョンが、[Cascadia Code GitHub リリース ページ](https://github.com/microsoft/cascadia-code/releases)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="6c62f-109">All versions of Cascadia Code can be downloaded from the [Cascadia Code GitHub releases page](https://github.com/microsoft/cascadia-code/releases).</span></span> <span data-ttu-id="6c62f-110">Windows ターミナルでは、Cascadia Code と Cascadia Mono がパッケージに付属しており、既定で Cascadia Mono が使用されています。</span><span class="sxs-lookup"><span data-stu-id="6c62f-110">Windows Terminal ships Cascadia Code and Cascadia Mono in its package and uses Cascadia Mono by default.</span></span>

| <span data-ttu-id="6c62f-111">フォント名</span><span class="sxs-lookup"><span data-stu-id="6c62f-111">Font Name</span></span> | <span data-ttu-id="6c62f-112">合字を含む</span><span class="sxs-lookup"><span data-stu-id="6c62f-112">Includes Ligatures</span></span> | <span data-ttu-id="6c62f-113">Powerline Glyph を含む</span><span class="sxs-lookup"><span data-stu-id="6c62f-113">Includes Powerline Glyphs</span></span> |
| --------- | ------------------ | ------------------------- |
| <span data-ttu-id="6c62f-114">Cascadia Code</span><span class="sxs-lookup"><span data-stu-id="6c62f-114">Cascadia Code</span></span> | <span data-ttu-id="6c62f-115">はい</span><span class="sxs-lookup"><span data-stu-id="6c62f-115">Yes</span></span> | <span data-ttu-id="6c62f-116">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c62f-116">No</span></span> |
| <span data-ttu-id="6c62f-117">Cascadia Mono</span><span class="sxs-lookup"><span data-stu-id="6c62f-117">Cascadia Mono</span></span> | <span data-ttu-id="6c62f-118">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c62f-118">No</span></span>  | <span data-ttu-id="6c62f-119">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c62f-119">No</span></span> |
| <span data-ttu-id="6c62f-120">Cascadia Code PL</span><span class="sxs-lookup"><span data-stu-id="6c62f-120">Cascadia Code PL</span></span> | <span data-ttu-id="6c62f-121">はい</span><span class="sxs-lookup"><span data-stu-id="6c62f-121">Yes</span></span> | <span data-ttu-id="6c62f-122">はい</span><span class="sxs-lookup"><span data-stu-id="6c62f-122">Yes</span></span> |
| <span data-ttu-id="6c62f-123">Cascadia Mono PL</span><span class="sxs-lookup"><span data-stu-id="6c62f-123">Cascadia Mono PL</span></span> | <span data-ttu-id="6c62f-124">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c62f-124">No</span></span> | <span data-ttu-id="6c62f-125">はい</span><span class="sxs-lookup"><span data-stu-id="6c62f-125">Yes</span></span> |

## <a name="powerline-and-programming-ligatures"></a><span data-ttu-id="6c62f-126">Powerline とプログラミングの合字</span><span class="sxs-lookup"><span data-stu-id="6c62f-126">Powerline and programming ligatures</span></span>

<span data-ttu-id="6c62f-127">Powerline は、一般的なコマンドライン プラグインで、プロンプトに追加情報を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="6c62f-127">Powerline is a common command-line plugin that allows you to display additional information in your prompt.</span></span> <span data-ttu-id="6c62f-128">この情報を適切に表示するために、いくつかの追加のグリフが使用されています。</span><span class="sxs-lookup"><span data-stu-id="6c62f-128">It uses a few additional glyphs to display this information properly.</span></span> <span data-ttu-id="6c62f-129">コマンド プロンプトでの Powerline の設定の詳細については、[Windows ターミナルの Powerline に関するページ](./tutorials/powerline-setup.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c62f-129">To learn more about setting up Powerline in your command prompt, visit the [Powerline in Windows Terminal](./tutorials/powerline-setup.md) page.</span></span>

<span data-ttu-id="6c62f-130">プログラミング合字は、文字を組み合わせることによって作成されるグリフです。</span><span class="sxs-lookup"><span data-stu-id="6c62f-130">Programming ligatures are glyphs that are created by combining characters.</span></span> <span data-ttu-id="6c62f-131">これらは、コードを記述するときに最適です。</span><span class="sxs-lookup"><span data-stu-id="6c62f-131">They are most useful when writing code.</span></span> <span data-ttu-id="6c62f-132">合字は、"Code" のバリアントには含まれていますが、"Mono" のバリアントでは除外されています。</span><span class="sxs-lookup"><span data-stu-id="6c62f-132">The "Code" variants include ligatures, whereas the "Mono" variants exclude them.</span></span>

![Cascadia Code のプログラミング合字](./images/programming-ligatures.gif)

## <a name="contributing-to-cascadia-code"></a><span data-ttu-id="6c62f-134">Cascadia Code への貢献</span><span class="sxs-lookup"><span data-stu-id="6c62f-134">Contributing to Cascadia Code</span></span>

<span data-ttu-id="6c62f-135">Cascadia Code は、[GitHub](https://github.com/microsoft/cascadia-code) の [SIL Open Font License](https://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&id=OFL) でライセンス供与されています。</span><span class="sxs-lookup"><span data-stu-id="6c62f-135">Cascadia Code is licensed under the [SIL Open Font license](https://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&id=OFL) on [GitHub](https://github.com/microsoft/cascadia-code).</span></span>
