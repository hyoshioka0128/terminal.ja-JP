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
# <a name="cascadia-code"></a>Cascadia Code

Cascadia Code は、コマンドライン アプリケーションやテキスト エディターに新鮮なエクスペリエンスを提供する、Microsoft が提供する新しい等幅フォントです。 Cascadia Code は、Windows ターミナルと共に開発されました。 このフォントは、ターミナル アプリケーションや、Visual Studio や Visual Studio Code などのテキスト エディターで使用することをお勧めします。

## <a name="cascadia-code-versions"></a>Cascadia Code のバージョン

Cascadia Code には、合字とグリフを含む使用可能な複数のバージョンがあります。 Cascadia Code のすべてのバージョンが、[Cascadia Code GitHub リリース ページ](https://github.com/microsoft/cascadia-code/releases)からダウンロードできます。 Windows ターミナルでは、Cascadia Code と Cascadia Mono がパッケージに付属しており、既定で Cascadia Mono が使用されています。

| フォント名 | 合字を含む | Powerline Glyph を含む |
| --------- | ------------------ | ------------------------- |
| Cascadia Code | はい | いいえ |
| Cascadia Mono | いいえ  | いいえ |
| Cascadia Code PL | はい | はい |
| Cascadia Mono PL | いいえ | はい |

## <a name="powerline-and-programming-ligatures"></a>Powerline とプログラミングの合字

Powerline は、一般的なコマンドライン プラグインで、プロンプトに追加情報を表示することができます。 この情報を適切に表示するために、いくつかの追加のグリフが使用されています。 コマンド プロンプトでの Powerline の設定の詳細については、[Windows ターミナルの Powerline に関するページ](./tutorials/powerline-setup.md)を参照してください。

プログラミング合字は、文字を組み合わせることによって作成されるグリフです。 これらは、コードを記述するときに最適です。 合字は、"Code" のバリアントには含まれていますが、"Mono" のバリアントでは除外されています。

![Cascadia Code のプログラミング合字](./images/programming-ligatures.gif)

## <a name="contributing-to-cascadia-code"></a>Cascadia Code への貢献

Cascadia Code は、[GitHub](https://github.com/microsoft/cascadia-code) の [SIL Open Font License](https://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&id=OFL) でライセンス供与されています。
