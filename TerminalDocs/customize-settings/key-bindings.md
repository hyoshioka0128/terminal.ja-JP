---
title: Windows ターミナルのキー バインド
description: Windows ターミナルのカスタム キー バインドを作成する方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 05/19/2020
ms.topic: how-to
ms.service: terminal
ms.localizationpriority: high
ms.openlocfilehash: 76bf91f8d7c2b49c2dc6bcf0c83640b57b2acd01
ms.sourcegitcommit: bb5b7fd7db4b81e0d44e060989dc16b6775c802a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83415967"
---
# <a name="custom-key-bindings-in-windows-terminal"></a>Windows ターミナルのカスタム キー バインド

Windows ターミナル内にカスタム キー バインド (キーボード ショートカット) を作成して、キーボードを使用してターミナルとの対話方法を制御することができます。

## <a name="key-binding-formats"></a>キー バインドの形式

キー バインドは、次の形式で構成できます。

### <a name="commands-without-arguments"></a>引数なしのコマンド

```json
{ "command": "commandName", "keys": "modifiers+key" }
```

たとえば、この既定の設定では、ショートカット キー <kbd>alt+f4</kbd> を使用してターミナル ウィンドウを閉じます。

```json
{ "command": "closeWindow", "keys": "alt+f4" }
```

### <a name="commands-with-arguments"></a>引数を指定したコマンド

```json
{ "command": { "action": "commandName", "argument": "value" }, "keys": "modifiers+key" }
```

たとえば、この既定の設定では、ショートカット キー <kbd>Ctrl + Shift + 1</kbd> を使用すると、ドロップダウン メニューにどのプロファイルが最初に表示されるかに基づいて、ターミナルで新しいタブが開きます (通常は PowerShell プロファイルを開きます)。

```json
{ "command": { "action": "newTab", "index": 0 }, "keys": "ctrl+shift+1" }
```

<br />

___

## <a name="key-binding-properties"></a>キー バインドのプロパティ

キー バインドは、次のプロパティを使用して作成できます。

### <a name="command"></a>コマンド

これは、関連付けられたキーが押されたときに実行されるコマンドです。

**プロパティ名:** `command`

**必須かどうか:** 必須

**受け入れ可能:** String

### <a name="keys"></a>キー

コマンドを呼び出すために使用するキーの組み合わせを定義します。 1 つのキーで任意の数の修飾子を持つことができます。 受け入れられる修飾子とキーを[以下](#accepted-modifiers-and-keys)に一覧表示します。

**プロパティ名:** `keys`

**必須かどうか:** 必須

**受け入れ可能:** String または array[string]

### <a name="action"></a>操作

これにより、特定のコマンドに機能が追加されます。

**プロパティ名:** `action`

**必須かどうか:** オプション

**受け入れ可能:** String

<br />

___

## <a name="accepted-modifiers-and-keys"></a>受け入れられる修飾子とキー

### <a name="modifiers"></a>修飾子

`ctrl+`、`shift+`、`alt+`

### <a name="modifier-keys"></a>修飾キー

| 種類 | キー |
| ---- | ---- |
| 関数と英数字キー | `f1-f24`、`a-z`、`0-9` |
| 記号 | ``` ` ```、`-`、`=`、`[`、`]`、`\`、`;`、`'`、`,`、`.`、`/` |
| 方向キー | `down`、`left`、`right`、`up`、`pagedown`、`pageup`、`pgdn`、`pgup`、`end`、`home`、`plus` |
| アクション キー | `tab`、`enter`、`esc`、`escape`、`space`、`backspace`、`delete`、`insert` |
| テンキーのキー | `numpad_0-numpad_9`、`numpad0-numpad9`、`numpad_add`、`numpad_plus`、`numpad_decimal`、`numpad_period`、`numpad_divide`、`numpad_minus`、`numpad_subtract`、`numpad_multiply` |

<br />

___

## <a name="application-level-commands"></a>アプリケーションレベルのコマンド

### <a name="close-window"></a>ウィンドウを閉じる

:::row:::
:::column span="":::
現在のウィンドウとその中のすべてのタブが閉じられます。 `confirmCloseAllTabs` が `true` に設定されている場合は、すべてのタブを閉じることを確認する確認ダイアログが表示されます。 この設定の詳細については、[グローバル設定に関するページ](./global-settings.md#hide-close-all-tabs-popup)を参照してください。

**コマンド名:** `closeWindow`

**既定のバインド:**

```json
{ "command": "closeWindow", "keys": "alt+f4" }
```

:::column-end:::
:::column span="":::
![Windows ターミナルのすべてのタブを閉じるの確認](./../images/confirm-close-all-tabs.png)

:::column-end:::
:::row-end:::

### <a name="find"></a>［検索］

[検索] ダイアログ ボックスが開きます。 検索の詳細については、[検索に関するページ](./../search.md)を参照してください。

**コマンド名:** `find`

**既定のバインド:**

```json
{ "command": "find", "keys": "ctrl+shift+f" }
```

### <a name="open-the-dropdown"></a>ドロップダウンを開く

ドロップダウン メニューが開きます。

**コマンド名:** `openNewTabDropdown`

**既定のバインド:**

```json
{ "command": "openNewTabDropdown", "keys": "ctrl+shift+space" }
```

### <a name="open-settings-file"></a>設定ファイルを開く

設定ファイルが開きます。

**コマンド名:** `openSettings`

**既定のバインド:**

```json
{ "command": "openSettings", "keys": "ctrl+," }
```

### <a name="toggle-full-screen"></a>全画面表示の切り替え

全画面表示と既定のウィンドウ サイズを切り替えることができます。

**コマンド名:** `toggleFullscreen`

**既定のバインド:**

```json
{ "command": "toggleFullscreen", "keys": "alt+enter" },
{ "command": "toggleFullscreen", "keys": "f11" }
```

<br />

___

## <a name="tab-management-commands"></a>タブ管理コマンド

### <a name="close-tab"></a>タブを閉じる

現在のタブが閉じます。

**コマンド名:** `closeTab`

### <a name="duplicate-tab"></a>タブを複製

現在のタブのコピーが作成されて開きます。

**コマンド名:** `duplicateTab`

**既定のバインド:**

```json
{ "command": "duplicateTab", "keys": "ctrl+shift+d" }
```

### <a name="new-tab"></a>新しいタブ

新しいタブが作成されます。引数を指定しないと、既定のプロファイルが新しいタブで開きます。アクションが指定されていない場合は、既定のプロファイルの同等の設定が使用されます。

**コマンド名:** `newTab`

**既定のバインド:**

```json
{ "command": "newTab", "keys": "ctrl+shift+t" },
{ "command": { "action": "newTab", "index": 0 }, "keys": "ctrl+shift+1" },
{ "command": { "action": "newTab", "index": 1 }, "keys": "ctrl+shift+2" },
{ "command": { "action": "newTab", "index": 2 }, "keys": "ctrl+shift+3" },
{ "command": { "action": "newTab", "index": 3 }, "keys": "ctrl+shift+4" },
{ "command": { "action": "newTab", "index": 4 }, "keys": "ctrl+shift+5" },
{ "command": { "action": "newTab", "index": 5 }, "keys": "ctrl+shift+6" },
{ "command": { "action": "newTab", "index": 6 }, "keys": "ctrl+shift+7" },
{ "command": { "action": "newTab", "index": 7 }, "keys": "ctrl+shift+8" },
{ "command": { "action": "newTab", "index": 8 }, "keys": "ctrl+shift+9" }
```

#### <a name="actions"></a>操作

| 名前 | 必要 | 受け入れられる型 | 説明 |
| ---- | --------- | ------- | ----------- |
| `commandLine` | オプション | 実行可能ファイル名を表す文字列 | 実行可能ファイルがタブ内で実行されます。 |
| `startingDirectory` | オプション | フォルダーの場所を表す文字列 | タブが開かれるディレクトリ。 |
| `tabTitle` | オプション | String | 新しいタブのタイトル。 |
| `index` | オプション | 整数 | ドロップダウンでの位置 (0 から開始) に基づいて開かれるプロファイル。 |
| `profile` | オプション | プロファイルの名前または GUID を表す文字列 | GUID または名前に基づいて開かれるプロファイル。 |

### <a name="open-next-tab"></a>次のタブを開く

現在のタブの右側にタブが開きます。

**コマンド名:** `nextTab`

**既定のバインド:**

```json
{ "command": "nextTab", "keys": "ctrl+tab" }
```

### <a name="open-previous-tab"></a>前のタブを開く

現在のタブの左側にタブが開きます。

**コマンド名:** `prevTab`

**既定のバインド:**

```json
{ "command": "prevTab", "keys": "ctrl+shift+tab" }
```

### <a name="open-a-specific-tab"></a>特定のタブを開く

インデックスに応じて特定のタブが開きます。

**コマンド名:** `switchToTab`

**既定のバインド:**

```json
{ "command": { "action": "switchToTab", "index": 0 }, "keys": "ctrl+alt+1" },
{ "command": { "action": "switchToTab", "index": 1 }, "keys": "ctrl+alt+2" },
{ "command": { "action": "switchToTab", "index": 2 }, "keys": "ctrl+alt+3" },
{ "command": { "action": "switchToTab", "index": 3 }, "keys": "ctrl+alt+4" },
{ "command": { "action": "switchToTab", "index": 4 }, "keys": "ctrl+alt+5" },
{ "command": { "action": "switchToTab", "index": 5 }, "keys": "ctrl+alt+6" },
{ "command": { "action": "switchToTab", "index": 6 }, "keys": "ctrl+alt+7" },
{ "command": { "action": "switchToTab", "index": 7 }, "keys": "ctrl+alt+8" },
{ "command": { "action": "switchToTab", "index": 8 }, "keys": "ctrl+alt+9" }
```

#### <a name="actions"></a>操作

| 名前 | 必要 | 受け入れられる型 | 説明 |
| ---- | --------- | ------- | ----------- |
| `index` | 必須 | 整数 | タブ バー内の位置 (0 から開始) に基づいて開かれるタブ。 |

<br />

___

## <a name="pane-management-commands"></a>ペイン管理コマンド

### <a name="close-pane"></a>ペインを閉じる

アクティブなペインを閉じます。 分割ペインがない場合は、現在のタブが閉じられます。開いているタブが 1 つだけの場合は、ウィンドウが閉じられます。

**コマンド名:** `closePane`

**既定のバインド:**

```json
{ "command": "closePane", "keys": "ctrl+shift+w" }
```

### <a name="move-pane-focus"></a>ペイン フォーカスの移動

方向に応じて、別のペインにフォーカスが移動します。

**コマンド名:** `moveFocus`

**既定のバインド:**

```json
{ "command": { "action": "moveFocus", "direction": "down" }, "keys": "alt+down" },
{ "command": { "action": "moveFocus", "direction": "left" }, "keys": "alt+left" },
{ "command": { "action": "moveFocus", "direction": "right" }, "keys": "alt+right" },
{ "command": { "action": "moveFocus", "direction": "up" }, "keys": "alt+up" }
```

#### <a name="actions"></a>操作

| 名前 | 必要 | 受け入れられる型 | 説明 |
| ---- | --------- | ------- | ----------- |
| `direction` | 必須 | `"left"`、`"right"`、`"up"`、`"down"` | フォーカスを移動する方向。 |

### <a name="resize-a-pane"></a>ペインのサイズを変更する

アクティブなペインのサイズが変更されます。

**コマンド名:** `resizePane`

**既定のバインド:**

```json
{ "command": { "action": "resizePane", "direction": "down" }, "keys": "alt+shift+down" },
{ "command": { "action": "resizePane", "direction": "left" }, "keys": "alt+shift+left" },
{ "command": { "action": "resizePane", "direction": "right" }, "keys": "alt+shift+right" },
{ "command": { "action": "resizePane", "direction": "up" }, "keys": "alt+shift+up" }
```

#### <a name="actions"></a>操作

| 名前 | 必要 | 受け入れられる型 | 説明 |
| ---- | --------- | ------- | ----------- |
| `direction` | 必須 | `"left"`、`"right"`、`"up"`、`"down"` | ペインのサイズを変更する方向。 |

### <a name="split-a-pane"></a>ペインの分割

アクティブなペインのサイズが半分になり、別のペインが開きます。 引数を指定しないと、既定のプロファイルが新しいペインで開かれます。 アクションが指定されていない場合は、既定のプロファイルの同等の設定が使用されます。

**コマンド名:** `splitPane`

**既定のバインド:**

```json
// In settings.json
{ "command": { "action": "splitPane", "split": "auto", "splitMode": "duplicate" }, "keys": "alt+shift+d" },

// In defaults.json
{ "command": { "action": "splitPane", "split": "horizontal"}, "keys": "alt+shift+-" },
{ "command": { "action": "splitPane", "split": "vertical"}, "keys": "alt+shift+plus" }
```

#### <a name="actions"></a>操作

| 名前 | 必要 | 受け入れられる型 | 説明 |
| ---- | --------- | ------- | ----------- |
| `split` | 必須 | `"vertical"`、`"horizontal"`、`"auto"` | ペインの分割方法。 `"auto"` は、最も多くの領域を提供する方向に分割します。 |
| `commandLine` | オプション | 実行可能ファイル名を表す文字列 | 実行可能ファイルがペイン内で実行されます。 |
| `startingDirectory` | オプション | フォルダーの場所を表す文字列 | ペインが開かれるディレクトリ。 |
| `tabTitle` | オプション | String | 新しいペインにフォーカスがあるときのタブのタイトル。 |
| `index` | オプション | 整数 | ドロップダウンでの位置 (0 から開始) に基づいて開かれるプロファイル。 |
| `profile` | オプション | プロファイルの名前または GUID を表す文字列 | GUID または名前に基づいて開かれるプロファイル。 |
| `splitMode` | オプション | `"duplicate"` | ペインの分割方法を制御します。 フォーカスがあるペインのプロファイルを新しいペインに複製する、`"duplicate"` のみを受け入れます。 |

<br />

___

## <a name="clipboard-integration-commands"></a>クリップボードの統合コマンド

### <a name="copy"></a>コピー

選択したターミナル コンテンツがクリップボードにコピーされます。

**コマンド名:** `copy`

**既定のバインド:**

```json
// In settings.json
{ "command": { "action": "copy", "singleLine": false }, "keys": "ctrl+c" },

// In defaults.json
{ "command": { "action": "copy", "singleLine": false }, "keys": "ctrl+shift+c" },
{ "command": { "action": "copy", "singleLine": false }, "keys": "ctrl+insert" }
```

#### <a name="clipboard-actions"></a>クリップボードのアクセス

| 名前 | 必要 | 受け入れられる型 | 説明 |
| ---- | --------- | ------- | ----------- |
| `singleLine` | オプション | `true`、`false` | `true` の場合、コピーされたコンテンツは単一行としてコピーされます。 `false` の場合、選択したテキストから改行が保持されます。 |

### <a name="paste"></a>貼り付け

クリップボードにコピーされたコンテンツが挿入されます。

**コマンド名:** `paste`

**既定のバインド:**

```json
// In settings.json
{ "command": "paste", "keys": "ctrl+v" },

// In defaults.json
{ "command": "paste", "keys": "ctrl+shift+v" },
{ "command": "paste", "keys": "shift+insert" }
```

<br />

___

## <a name="scrollback-commands"></a>Scrollback コマンド

### <a name="scroll-up"></a>上にスクロール

画面を上にスクロールします。

**コマンド名:** `scrollUp`

**既定のバインド:**

```json
{ "command": "scrollUp", "keys": "ctrl+shift+up" }
```

### <a name="scroll-down"></a>下にスクロール

画面を下にスクロールします。

**コマンド名:** `scrollDown`

**既定のバインド:**

```json
{ "command": "scrollDown", "keys": "ctrl+shift+down" }
```

### <a name="scroll-up-a-whole-page"></a>ページ全体を上にスクロール

ページ全体 (ウィンドウの高さ) で画面を上にスクロールします。

**コマンド名:** `scrollUpPage`

**既定のバインド:**

```json
{ "command": "scrollUpPage", "keys": "ctrl+shift+pgup" }
```

### <a name="scroll-down-a-whole-page"></a>ページ全体を下にスクロール

ページ全体 (ウィンドウの高さ) で画面を下にスクロールします。

**コマンド名:** `scrollDownPage`

**既定のバインド:**

```json
{ "command": "scrollDownPage", "keys": "ctrl+shift+pgdn" }
```

<br />

___

## <a name="visual-adjustment-commands"></a>ビジュアル調整コマンド

### <a name="adjust-font-size"></a>フォント サイズの調整

指定したポイントの大きさによってテキストのサイズが変更されます。

**コマンド名:** `adjustFontSize`

**既定のバインド:**

```json
{ "command": { "action": "adjustFontSize", "delta": 1 }, "keys": "ctrl+=" },
{ "command": { "action": "adjustFontSize", "delta": -1 }, "keys": "ctrl+-" }
```

#### <a name="actions"></a>操作

| 名前 | 必要 | 受け入れられる型 | 説明 |
| ---- | --------- | ------- | ----------- |
| `delta` | 必須 | 整数 | コマンド呼び出しごとのサイズ変更の量。 |

### <a name="reset-font-size"></a>フォント サイズのリセット

テキスト サイズが既定値にリセットされます。

**コマンド名:** `resetFontSize`

**既定のバインド:**

```json
{ "command": "resetFontSize", "keys": "ctrl+0" }
```

<br />

___

## <a name="unbind-keys"></a>キーのバインド解除

関連付けられたキーが任意のコマンドからバインド解除されます。

**コマンド名:** `unbound`
