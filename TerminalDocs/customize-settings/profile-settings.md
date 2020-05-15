---
title: Windows ターミナル プロファイルの設定
description: Windows ターミナル内の個々のプロファイルをカスタマイズする方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: how-to
ms.service: terminal
ms.localizationpriority: high
ms.openlocfilehash: 309fb40736718df7d1670a7376806b70ef0e35fe
ms.sourcegitcommit: bb5b7fd7db4b81e0d44e060989dc16b6775c802a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83416087"
---
# <a name="profile-settings-in-the-windows-terminal"></a>Windows ターミナルでのプロファイル設定

以下に示す設定は、それぞれ一意のプロファイルに固有のものです。 設定を自分のすべてのプロファイルに適用する場合は、ご自分の settings.json ファイル内のプロファイルの一覧の上にある `defaults` セクションに追加できます。

```json
"defaults":
{
    // SETTINGS TO APPLY TO ALL PROFILES
},
"list":
[
    // PROFILE OBJECTS
]
```

## <a name="unique-identifier"></a>一意識別子

プロファイルでは、GUID を一意の識別子として使用できます。 プロファイルを既定のプロファイルにするには、`defaultProfile` グローバル設定の GUID が必要です。

**プロパティ名:** `guid`

**必須かどうか:** 必須

**受け入れ可能:** レジストリ形式の GUID を表す文字列: `"{00000000-0000-0000-0000-000000000000}"`

<br />

___

## <a name="executable-settings"></a>実行可能ファイルの設定

### <a name="command-line"></a>コマンド ライン

これは、プロファイルで使用される実行可能ファイルです。

**プロパティ名:** `commandline`

**必須かどうか:** オプション

**受け入れ可能:** 実行可能ファイル名を表す文字列

**既定値:** `"cmd.exe"`

### <a name="source"></a>ソース

これには、プロファイルを生成したプロファイル ジェネレーターの名前が格納されます。 _このフィールドには検出可能な値がありません。_ 動的プロファイルの詳細については、[動的プロファイルに関するページ](./../dynamic-profiles.md)を参照してください。

**プロパティ名:** `source`

**必須かどうか:** オプション

**受け入れ可能:** String

### <a name="starting-directory"></a>開始ディレクトリ

これは、シェルが読み込まれるときに開始されるディレクトリです。

**プロパティ名:** `startingDirectory`

**必須かどうか:** オプション

**受け入れ可能:** フォルダーの場所を表す文字列

**既定値:** `"%USERPROFILE%"`

<br />

___

## <a name="dropdown-settings"></a>ドロップダウンの設定

![Windows ターミナルのドロップダウン](./../images/dropdown.png)
_構成:[Raspberry Ubuntu](./../custom-terminal-gallery/raspberry-ubuntu.md)_

### <a name="name"></a>名前

これは、ドロップダウン メニューに表示されるプロファイルの名前です。 この値は、起動時にシェルに渡す "タイトル" としても使用されます。 一部のシェル (`bash` など) では、この初期値を無視することができますが、他のシェル (`Command Prompt`、`PowerShell`) では、アプリケーションの有効期間中、この値を使用することができます。 この "タイトル" の動作は、`tabTitle` を使用してオーバーライドできます。

**プロパティ名:** `name`

**必須かどうか:** 必須

**受け入れ可能:** String

### <a name="icon"></a>［アイコン］

これにより、タブとドロップダウン メニュー内に表示されるアイコンが設定されます。

**プロパティ名:** `icon`

**必須かどうか:** オプション

**受け入れ可能:** ファイルの場所を表す文字列

### <a name="hide-a-profile-from-the-dropdown"></a>ドロップダウンからプロファイルを非表示にする

`hidden` が `true` に設定されている場合、そのプロファイルはプロファイルの一覧に表示されません。 これを使用すると、既定のプロファイルと動的に生成されたプロファイルを設定ファイルに残したまま、非表示にすることができます。 動的プロファイルの詳細については、[動的プロファイルに関するページ](./../dynamic-profiles.md)を参照してください。

**プロパティ名:** `hidden`

**必須かどうか:** オプション

**値:** `true`、`false`

**既定値:** `false`

<br />

___

## <a name="tab-title-settings"></a>タブ タイトルの設定

### <a name="custom-tab-title"></a>カスタム タブのタイトル

設定すると、起動時にシェルに渡すタイトルとして `name` が置き換えられます。 一部のシェル (`bash` など) では、この初期値を無視することができますが、他のシェル (`Command Prompt`、`PowerShell`) では、アプリケーションの有効期間中、この値を使用することができます。 シェルでタイトルを設定する方法については、[タブ タイトルのチュートリアル](./../tutorials/tab-title.md)を参照してください。

**プロパティ名:** `tabTitle`

**必須かどうか:** オプション

**受け入れ可能:** String

### <a name="suppress-title-changes-from-the-shell"></a>シェルからのタイトルの変更を抑制する

これが `true` に設定されている場合、`tabTitle` によってタブの既定のタイトルがオーバーライドされ、アプリケーションからのタイトルの変更メッセージはすべて抑制されます。 `tabTitle` が設定されていない場合は、代わりに `name` が使用されます。 これが `false` に設定されている場合、`tabTitle` は通常どおりに動作します。

**プロパティ名:** `suppressApplicationTitle`

**必須かどうか:** オプション

**受け入れ可能:** `true`、`false`

<br />

___

## <a name="text-settings"></a>テキストの設定

### <a name="font-face"></a>フォント フェイス

これは、プロファイルで使用されるフォント フェイスの名前です。 これが見つからないか無効である場合は、ターミナルによって Consolas へのフォールバックが試行されます。 既定のフォント Cascadia Mono のその他のバリアントについては、[Cascadia Code に関するページ](./../cascadia-code.md)を参照してください。

**プロパティ名:** `fontFace`

**必須かどうか:** オプション

**受け入れ可能:** フォント名を表す文字列

**既定値:** `"Cascadia Mono"`

### <a name="font-size"></a>フォント サイズ

これにより、プロファイルのフォント サイズがポイント単位で設定されます。

**プロパティ名:** `fontSize`

**必須かどうか:** オプション

**値:** 整数

**既定値:** `12`

### <a name="padding"></a>余白

:::row:::
:::column span="":::
これにより、ウィンドウ内のテキストの周囲の余白が設定されます。 これには、次の 3 つの異なる形式が使用できます。`"#"` は、すべての辺に同じ余白を設定し、`"#, #"` は左右と上下に同じ余白を設定し、`"#, #, #, #"` は左、上、右、下に個別に余白を設定します。

**プロパティ名:** `padding`

**必須かどうか:** オプション

**受け入れ可能:** 次の形式の値を表す文字列: `"#"`、`"#, #"`、`"#, #, #, #"`

**既定値:** `"8, 8, 8, 8"`

:::column-end:::
:::column span="":::
![Windows ターミナルの余白](./../images/padding.gif)

:::column-end:::
:::row-end:::

### <a name="antialiasing-text"></a>アンチエイリアシング テキスト

これは、レンダラーでテキストをアンチエイリアシングする方法を制御します。 この設定を変更すると、新しいターミナル インスタンスを開始する必要があることに注意してください。

![Windows ターミナルのアンチエイリアシング テキスト](./../images/antialiasing-mode.gif)

**プロパティ名:** `antialiasingMode`

**必須かどうか:** オプション

**値:** `"grayscale"`、`"cleartype"`、`"aliased"`

**既定値:** `"grayscale"`

<br />

___

## <a name="cursor-settings"></a>カーソルの設定

### <a name="cursor-shape"></a>カーソルの形

これにより、プロファイルのカーソルの形が設定されます。 使用可能なカーソル: `"bar"` ( &#x2503; )、`"vintage"` ( &#x2583; )、`"underscore"` ( &#x2581; )、`"filledBox"` ( &#x2588; )、`"emptyBox"` ( &#x25AF; )

**プロパティ名:** `cursorShape`

**必須かどうか:** オプション

**受け入れ可能:** `"bar"`、`"vintage"`、`"underscore"`、`"filledBox"`、`"emptyBox"`

**既定値:** `"bar"`

### <a name="cursor-color"></a>カーソルの色

これにより、プロファイルのカーソルの色が設定されます。 これにより、配色で設定された `cursorColor` がオーバーライドされます (`colorScheme` が設定されている場合)。

**プロパティ名:** `cursorColor`

**必須かどうか:** オプション

**受け入れ可能:** 色を表す 16 進形式の文字列: `"#rgb"` または `"#rrggbb"`

### <a name="cursor-height"></a>カーソルの高さ

これにより、下部からのカーソルの高さの割合が設定されます。 これは `cursorShape` が `"vintage"` に設定されている場合にのみ機能します。

**プロパティ名:** `cursorHeight`

**必須かどうか:** オプション

**受け入れ可能:** 25 から 100 までの整数

<br />

___

## <a name="color-settings"></a>色の設定

### <a name="color-scheme"></a>配色

これは、プロファイルで使用される配色の名前です。 配色は `schemes` オブジェクトで定義されます。 詳細については、[配色に関するページ](./color-schemes.md)を参照してください。

**プロパティ名:** `colorScheme`

**必須かどうか:** オプション

**受け入れ可能:** 配色の名前を表す文字列

**既定値:** `"Campbell"`

### <a name="foreground-color"></a>前景色

これにより、プロファイルの前景色が変更されます。 これにより、配色で設定された `foreground` がオーバーライドされます (`colorScheme` が設定されている場合)。

**プロパティ名:** `foreground`

**必須かどうか:** オプション

**受け入れ可能:** 色を表す 16 進形式の文字列: `"#rgb"` または `"#rrggbb"`

### <a name="background-color"></a>背景の色

これにより、プロファイルの背景色がこの設定で変更されます。 これにより、配色で設定された `background` がオーバーライドされます (`colorScheme` が設定されている場合)。

**プロパティ名:** `background`

**必須かどうか:** オプション

**受け入れ可能:** 色を表す 16 進形式の文字列: `"#rgb"` または `"#rrggbb"`

### <a name="selection-background-color"></a>選択範囲の背景色

これにより、プロファイル内の選択範囲の背景色が設定されます。 これにより、配色で設定された `selectionBackground` がオーバーライドされます (`colorScheme` が設定されている場合)。

**プロパティ名:** `selectionBackground`

**必須かどうか:** オプション

**受け入れ可能:** 色を表す 16 進形式の文字列: `"#rgb"` または `"#rrggbb"`

<br />

___

## <a name="acrylic-settings"></a>アクリルの設定

### <a name="enable-acrylic"></a>アクリルを有効にする

:::row:::
:::column span="":::
これを `true` に設定すると、ウィンドウにアクリルの背景が表示されます。 `false` に設定すると、ウィンドウは無地の平坦な背景になります。 透過性は、OS の制限のため、フォーカスされているウィンドウにのみ適用されます。

**プロパティ名:** `useAcrylic`

**必須かどうか:** オプション

**値:** `true`、`false`

**既定値:** `false`

:::column-end:::
:::column span="":::
![Windows ターミナルのアクリル](./../images/acrylic.gif)

:::column-end:::
:::row-end:::

### <a name="acrylic-opacity"></a>アクリルの不透明度

:::row:::
:::column span="":::
`useAcrylic` が `true` に設定されている場合、これによりプロファイルのウィンドウの透明度が設定されます。 0 - 1 の浮動小数点値が受け入れられます。

**プロパティ名:** `acrylicOpacity`

**必須かどうか:** オプション

**受け入れ可能:** 0 - 1 の浮動小数点値の数値

**既定値:** `0.5`

:::column-end:::
:::column span="":::
![Windows ターミナル アクリルの不透明度](./../images/acrylic-opacity.gif)

:::column-end:::
:::row-end:::

<br />

___

## <a name="background-image-settings"></a>背景画像の設定

### <a name="setting-the-background-image"></a>背景画像を設定する

これにより、ウィンドウの背景に描画する画像のファイルの場所が設定されます。 背景画像には、.jpg、.png、.gif のいずれかのファイルを指定できます。

**プロパティ名:** `backgroundImage`

**必須かどうか:** オプション

**受け入れ可能:** ファイルの場所を表す文字列

### <a name="background-image-stretch-mode"></a>背景画像のストレッチ モード

:::row:::
:::column span="":::
これにより、ウィンドウいっぱいに広がるように背景画像のサイズが変更されます。

**プロパティ名:** `backgroundImageStretchMode`

**必須かどうか:** オプション

**受け入れ可能:** `"none"`、`"fill"`、`"uniform"`、`"uniformToFill"`

**既定値:** `"uniformToFill"`

:::column-end:::
:::column span="":::
![Windows ターミナルの背景画像のストレッチ モード](./../images/background-image-stretch-mode.gif)
 _[背景画像のソース](https://wallpaperhub.app/wallpapers/6287)_

:::column-end:::
:::row-end:::

### <a name="background-image-alignment"></a>背景画像の配置

:::row:::
:::column span="":::
これにより、ウィンドウの境界への背景画像の配置方法が設定されます。

**プロパティ名:** `backgroundImageAlignment`

**必須かどうか:** オプション

**受け入れ可能:** `"center"`、`"left"`、`"top"`、`"right"`、`"bottom"`、`"topLeft"`、`"topRight"`、`"bottomLeft"`、`"bottomRight"`

**既定値:** `"center"`

:::column-end:::
:::column span="":::
![Windows ターミナルの背景画像の配置](./../images/background-image-alignment.gif)
 _[背景画像のソース](https://design.ubuntu.com/brand/ubuntu-logo/)_

:::column-end:::
:::row-end:::

### <a name="background-image-opacity"></a>背景画像の不透明度

:::row:::
:::column span="":::
これにより、背景画像の透明度が設定されます。

:::column-end:::
:::row-end:::

**プロパティ名:** `backgroundImageOpacity`

**必須かどうか:** オプション

**受け入れ可能:** 0 - 1 の浮動小数点値の数値

**既定値:** `1.0`

<br />

___

## <a name="scroll-settings"></a>スクロールの設定

### <a name="scrollbar-visibility"></a>スクロールバーの表示

これにより、スクロールバーの表示が設定されます。

**プロパティ名:** `scrollbarState`

**必須かどうか:** オプション

**受け入れ可能:** `"visible"`、`"hidden"`

### <a name="scroll-to-input-line-when-typing"></a>入力時に入力行までスクロール

これを `true` に設定すると、入力時にウィンドウがコマンド入力行までスクロールします。 `false` に設定されている場合、入力を開始してもウィンドウはスクロールしません。

**プロパティ名:** `snapOnInput`

**必須かどうか:** オプション

**値:** `true`、`false`

**既定値:** `true`

### <a name="history-size"></a>履歴のサイズ

これにより、ウィンドウに表示されているよりも上の行にスクロールして戻すことができる行の数が設定されます。

**プロパティ名:** `historySize`

**必須かどうか:** オプション

**値:** 整数

**既定値:** `9001`

<br />

___

## <a name="how-the-profile-closes-when-exiting"></a>終了時のプロファイルの閉じ方

これにより、プロファイルが終了または起動に失敗したときにどのように反応するかが設定されます。 `"graceful"` は、`exit` が入力されたとき、またはプロセスが正常に終了したときに、プロファイルを閉じます。 `"always"` は常にプロファイルを閉じ、`"never"` はプロファイルを閉じません。 `true` と `false` は、それぞれ `"graceful"` と `"never"` のシノニムとして受け入れられます。

**プロパティ名:** `closeOnExit`

**必須かどうか:** オプション

**受け入れ可能:** `"graceful"`、`"always"`、`"never"`、`true`、`false`

**既定値:** `"graceful"`

<br />

___

## <a name="retro-terminal-effects"></a>レトロ ターミナル効果

:::row:::
:::column span="":::
これを `true` に設定すると、走査線やぼやけたテキストの端がある古い CRT ディスプレイがターミナルでエミュレートされます。 これは試験的な機能であり、存続は保証されていません。

**プロパティ名:** `experimental.retroTerminalEffect`

**必須かどうか:** オプション

**値:** `true`、`false`

**既定値:** `false`

:::column-end:::
:::column span="":::
![Windows ターミナルの実験的なレトロ ターミナル効果](./../images/experimental-retro-terminal-effect.gif)
_構成:[レトロ コマンド プロンプト](./../custom-terminal-gallery/retro-command-prompt.md)_

:::column-end:::
:::row-end:::
