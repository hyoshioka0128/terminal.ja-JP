---
title: Windows ターミナルのグローバル設定
description: Windows ターミナル内でグローバル設定をカスタマイズする方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: how-to
ms.service: terminal
ms.localizationpriority: high
ms.openlocfilehash: 3cbe4b2b99f8115ff4eeaab5f525de393d7e5eb1
ms.sourcegitcommit: bb5b7fd7db4b81e0d44e060989dc16b6775c802a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83415957"
---
# <a name="global-settings-in-the-windows-terminal"></a>Windows ターミナルでのグローバル設定

以下に示すプロパティは、プロファイルの設定に関係なく、ターミナル ウィンドウ全体に影響します。 これらは、settings.json ファイルのルートに配置する必要があります。

## <a name="default-profile"></a>Default profile

<kbd>Ctrl + Shift + T</kbd> キーを押したとき、`newTab` に割り当てられているキー バインドを押したとき、プロファイルを指定せずに `wt new-tab` を実行したとき、または [+] アイコンをクリックしたときに開かれる、既定のプロファイルを設定します。

**プロパティ名:** `defaultProfile`

**必須かどうか:** 必須

**値:** 文字列としての GUID

**既定値:** PowerShell の GUID

<br />

___

## <a name="disable-dynamic-profiles"></a>動的プロファイルを無効にする

無効な動的プロファイル ジェネレーターを設定し、スタートアップ時にそれらのジェネレーターでプロファイルのリストにプロファイルが追加されないようにします。 動的プロファイルの詳細については、[動的プロファイルに関するページ](./../dynamic-profiles.md)を参照してください。

**プロパティ名:** `disabledProfileSources`

**必須かどうか:** オプション

**値:** `"Windows.Terminal.Wsl"`、`"Windows.Terminal.Azure"`、`"Windows.Terminal.PowershellCore"` (配列内)

**既定値:** `[]`

<br />

___

## <a name="darklight-theme"></a>ダーク/ライト テーマ

:::row:::
:::column span="":::
アプリケーションのテーマを設定します。 `"system"` では、Windows と同じテーマが使用されます。

**プロパティ名:** `theme`

**必須かどうか:** オプション

**値:** `"system"`、`"dark"`、`"light"`

**既定値:** `"system"`

:::column-end:::
:::column span="":::
![Windows ターミナルのダーク テーマ](./../images/requested-themes.gif)
_構成: [PowerShell での Powerline](./../custom-terminal-gallery/powerline-in-powershell.md)_

:::column-end:::
:::row-end:::

<br />

___

## <a name="tab-settings"></a>タブの設定

### <a name="always-show-tabs"></a>常にタブを表示する

:::row:::
:::column span="":::
これが `true` に設定されていると、常にタブが表示されます。 これが `false` に設定され、`showTabsInTitlebar` が `true` に設定されていると、タブは常にタイトル バーの下に表示されます。 これが `false` に設定され、`showTabsInTitlebar` が `false` に設定されていると、<kbd>Ctrl + Shift + T</kbd> キーを押すか、`newTab` に割り当てられているキー バインドを押すことによって、複数のタブが存在するようになった後でのみ、タブが表示されます。 この設定を変更すると、新しいターミナル インスタンスを開始する必要があることに注意してください。

**プロパティ名:** `alwaysShowTabs`

**必須かどうか:** オプション

**値:** `true`、`false`

**既定値:** `true`

:::column-end:::
:::column span="":::
![Windows ターミナルでは常にタブが表示されます](./../images/always-show-tabs.gif)

:::column-end:::
:::row-end:::

### <a name="tab-width-mode"></a>タブ幅モード

:::row:::
:::column span="":::
タブの幅を設定します。 `"equal"` を指定すると、各タブの幅が同じになります。 `"titleLength"` を指定すると、各タブのサイズはタイトルの長さになります。

**プロパティ名:** `tabWidthMode`

**必須かどうか:** オプション

**値:** `"equal"`、`"titleLength"`

**既定値:** `"equal"`

:::column-end:::
:::column span="":::
![Windows ターミナルのタブ幅モード](./../images/tab-width-mode.gif)

:::column-end:::
:::row-end:::

### <a name="hide-close-all-tabs-popup"></a>すべてのタブを閉じるポップアップを非表示にする

:::row:::
:::column span="":::
これが `true` に設定されていると、複数のタブが開かれているウィンドウを閉じるときに、確認が "_必要です_"。 これが `false` に設定されていると、複数のタブが開かれているウィンドウを閉じるときに、確認は "_必要ありません_"。

**プロパティ名:** `confirmCloseAllTabs`

**必須かどうか:** オプション

**値:** `true`、`false`

**既定値:** `true`

:::column-end:::
:::column span="":::
![Windows ターミナルのすべてのタブを閉じるの確認](./../images/confirm-close-all-tabs.png)

:::column-end:::
:::row-end:::

<br />

___

## <a name="launch-settings"></a>起動の設定

### <a name="launch-maximized"></a>起動時の最大化

起動時に、ターミナルを最大化して画面全体に表示するか、またはウィンドウ内に表示するかを定義します。

**プロパティ名:** `launchMode`

**必須かどうか:** オプション

**値:** `"default"`、`"maximized"`

**既定値:** `"default"`

### <a name="launch-position"></a>起動時の位置

最初に読み込まれたときの、ウィンドウの左上隅のピクセル位置を設定します。 複数のディスプレイがあるシステムでは、これらの座標はプライマリ ディスプレイの左上が基準になります。 X 座標または Y 座標が指定されていない場合は、その値に対するシステムの既定値が使用されます。 `launchMode` が `"maximized"` に設定されている場合、ウィンドウはそれらの座標によって指定されているモニターで最大化されます。

**プロパティ名:** `initialPosition`

**必須かどうか:** オプション

**値:** 次の形式の文字列として表された座標: `","`、`"#,#"`、`"#,"`、`",#"`

**既定値:** `","`

### <a name="columns-on-first-launch"></a>最初の起動時の列数

これは、最初の読み込み時にウィンドウに表示される文字の列の数です。 `launchMode` が `"maximized"` に設定されていると、このプロパティは無視されます。

**プロパティ名:** `initialCols`

**必須かどうか:** オプション

**値:** 整数

**既定値:** `120`

### <a name="rows-on-first-launch"></a>最初の起動時の行数

これは、最初の読み込み時にウィンドウに表示される行の数です。 `launchMode` が `"maximized"` に設定されていると、このプロパティは無視されます。

**プロパティ名:** `initialRows`

**必須かどうか:** オプション

**値:** 整数

**既定値:** `30`

<br />

___

## <a name="title-bar-settings"></a>タイトル バーの設定

### <a name="showhide-the-title-bar"></a>タイトル バーの表示/非表示

:::row:::
:::column span="":::
これを `true` に設定すると、タブはタイトル バー内に移動され、タイトル バーは表示されなくなります。 `false` に設定すると、タイトル バーはタブの上に表示されます。 この設定を変更すると、新しいターミナル インスタンスを開始する必要があることに注意してください。

**プロパティ名:** `showTabsInTitlebar`

**必須かどうか:** オプション

**値:** `true`、`false`

**既定値:** `true`

:::column-end:::
:::column span="":::
![Windows ターミナルのタブをタイトル バーに表示する](./../images/show-tabs-in-title-bar.gif)

:::column-end:::
:::row-end:::

### <a name="set-the-text-in-the-title-bar"></a>タイトル バーのテキストを設定する

これが `true` に設定されていると、選択されているタブのタイトルがタイトル バーに表示されます。`false` に設定すると、タイトル バーには "Windows ターミナル" と表示されます。 この設定を変更すると、新しいターミナル インスタンスを開始する必要があることに注意してください。

**プロパティ名:** `showTerminalTitleInTitlebar`

**必須かどうか:** オプション

**値:** `true`、`false`

**既定値:** `true`

<br />

___

## <a name="selection-settings"></a>選択の設定

### <a name="copy-after-selection-is-made"></a>選択後にコピーする

これを `true` に設定すると、作成時に選択内容がすぐにクリップボードにコピーされます。 この場合、マウスを右クリックすると常に貼り付けられます。 `false` に設定すると、選択内容が保持され、追加の操作が待機されます。 マウスを右クリックすると、選択内容がコピーされます。

**プロパティ名:** `copyOnSelect`

**必須かどうか:** オプション

**値:** `true`、`false`

**既定値:** `false`

### <a name="copy-formatting"></a>書式指定をコピーする

これを `true` に設定すると、選択したテキストの色とフォントの書式もクリップボードにコピーされます。 `false` に設定すると、プレーンテキストのみがクリップボードにコピーされます。

**プロパティ名:** `copyFormatting`

**必須かどうか:** オプション

**値:** `true`、`false`

**既定値:** `false`

### <a name="word-delimiters"></a>単語の区切り記号

ダブルクリックの選択で使用される単語の区切り記号を決定します。 単語の区切り記号は、2 つの単語の間の境界がどこにあるかを指定する文字です。 最も一般的な例は、スペース、セミコロン、コンマ、ピリオドなどです。

**プロパティ名:** `wordDelimiters`

**必須かどうか:** オプション

**値:** 文字列としての文字

**既定値:** <code>&nbsp;&#x2f;&#x5c;&#x28;&#x29;&#x22;&#x27;&#x2d;&#x3a;&#x2c;&#x2e;&#x3b;&#x3c;&#x3e;&#x7e;&#x21;&#x40;&#x23;&#x24;&#x25;&#x5e;&#x26;&#x2a;&#x7c;&#x2b;&#x3d;&#x5b;&#x5d;&#x7b;&#x7d;&#x7e;&#x3f;│</code><br>_(`│` は `U+2502 BOX DRAWINGS LIGHT VERTICAL` です)_

<br />

___

## <a name="scroll-speed"></a>スクロール速度

これは、マウス ホイールで一度にスクロールする行の数です。 値がゼロまたは `"system"` でない場合は、システム設定がオーバーライドされます。

**プロパティ名:** `rowsToScroll`

**必須かどうか:** オプション

**値:** 整数

**既定値:** `"system"`

<br />

___

## <a name="window-resize-behavior"></a>ウィンドウ サイズ変更の動作

:::row:::
:::column span="":::
これを `true` に設定すると、サイズ変更時にウィンドウは最も近い文字境界にスナップされます。 `false` に設定すると、ウィンドウのサイズは "スムーズ" に変更されます。

**プロパティ名:** `snapToGridOnResize`

**必須かどうか:** オプション

**値:** `true`、`false`

**既定値:** `true`

:::column-end:::
:::column span="":::
![サイズ変更時に Windows ターミナルはグリッドにスナップする](./../images/snap-to-grid-on-resize.gif)

:::column-end:::
:::row-end:::
