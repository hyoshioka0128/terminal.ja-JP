---
title: Windows ターミナルのコマンドライン引数
description: Windows ターミナルのコマンドライン引数を作成する方法について説明します。
author: cinnamon-msft
ms.author: cinnamon
ms.date: 06/18/2020
ms.topic: how-to
ms.service: terminal
ms.openlocfilehash: d40b0527bab94289457cf8c8a88931f4df943496
ms.sourcegitcommit: 91a802863cd0730d2e364377ffe44f819a66ff2a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84994384"
---
# <a name="using-command-line-arguments-for-windows-terminal"></a><span data-ttu-id="6d8a4-103">Windows ターミナルにコマンド ライン引数を使用する</span><span class="sxs-lookup"><span data-stu-id="6d8a4-103">Using command-line arguments for Windows Terminal</span></span>

<span data-ttu-id="6d8a4-104">`wt.exe` を使用すると、コマンド ラインから Windows ターミナルの新しいインスタンスを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-104">You can use `wt.exe` to open a new instance of Windows Terminal from the command line.</span></span> <span data-ttu-id="6d8a4-105">代わりに、実行エイリアス `wt` を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-105">You can also use the execution alias `wt` instead.</span></span>

> [!NOTE]
> <span data-ttu-id="6d8a4-106">[GitHub](https://github.com/microsoft/terminal) のソース コードから Windows ターミナルをビルドした場合、`wtd.exe` または `wtd` を使用してそのビルドを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-106">If you built Windows Terminal from the source code on [GitHub](https://github.com/microsoft/terminal), you can open that build using `wtd.exe` or `wtd`.</span></span>

![分割ペインの Windows ターミナル コマンドライン引数](./images/terminal-command-args.gif)

## <a name="command-line-syntax"></a><span data-ttu-id="6d8a4-108">コマンド ライン構文</span><span class="sxs-lookup"><span data-stu-id="6d8a4-108">Command line syntax</span></span>

<span data-ttu-id="6d8a4-109">`wt` コマンド ラインでは、**オプション** と **コマンド** の 2 種類の値が受け付けられます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-109">The `wt` command line accepts two types of values: **options** and **commands**.</span></span> <span data-ttu-id="6d8a4-110">**オプション** は、`wt` コマンド ライン全体の動作を制御できるフラグとその他のパラメーターのリストです。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-110">**Options** are a list of flags and other parameters that can control the behavior of the `wt` command line as a whole.</span></span> <span data-ttu-id="6d8a4-111">**コマンド** では、実装する必要がある 1 つのアクション、またはセミコロンで区切られたアクションのリストを提供します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-111">**Commands** provide the action, or list of actions separated by semicolons, that should be implemented.</span></span> <span data-ttu-id="6d8a4-112">コマンドを指定しないと、コマンドは既定で `new-tab` と見なされます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-112">If no command is specified, then the command is assumed to be `new-tab` by default.</span></span>

```bash
wt [options] [command ; ]
```

<span data-ttu-id="6d8a4-113">使用可能なコマンドライン引数を一覧表示するヘルプ メッセージを表示するには、`wt -h`、`wt --help`、`wt -?`、`wt /?` と入力します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-113">To display a help message listing the available command-line arguments, enter: `wt -h`, `wt --help`, `wt -?`, or `wt /?`.</span></span>

## <a name="options-and-commands"></a><span data-ttu-id="6d8a4-114">オプションとコマンド</span><span class="sxs-lookup"><span data-stu-id="6d8a4-114">Options and commands</span></span>

<span data-ttu-id="6d8a4-115">`wt` コマンド ラインでサポートされているコマンドとオプションの完全な一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-115">Below is the full list of supported commands and options for the `wt` command line.</span></span>

| <span data-ttu-id="6d8a4-116">オプション</span><span class="sxs-lookup"><span data-stu-id="6d8a4-116">Option</span></span> | <span data-ttu-id="6d8a4-117">説明</span><span class="sxs-lookup"><span data-stu-id="6d8a4-117">Description</span></span> |
| ------ | ----------- |
| <span data-ttu-id="6d8a4-118">`--help`、`-h`、`-?`、`/?`</span><span class="sxs-lookup"><span data-stu-id="6d8a4-118">`--help`, `-h`, `-?`, `/?`</span></span> | <span data-ttu-id="6d8a4-119">ヘルプ メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-119">Displays the help message.</span></span> |
| <span data-ttu-id="6d8a4-120">`--maximized`、`-M`</span><span class="sxs-lookup"><span data-stu-id="6d8a4-120">`--maximized`, `-M`</span></span> | <span data-ttu-id="6d8a4-121">ターミナルを最大化して起動します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-121">Launches the terminal maximized.</span></span> |
| <span data-ttu-id="6d8a4-122">`--fullscreen`、`-F`</span><span class="sxs-lookup"><span data-stu-id="6d8a4-122">`--fullscreen`, `-F`</span></span> | <span data-ttu-id="6d8a4-123">ターミナルを全画面で起動します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-123">Launches the terminal as full screen.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="6d8a4-124">`--maximized`、`-M` と `--fullscreen`、`-F` は、[Windows ターミナル プレビュー](https://aka.ms/terminal-preview/)でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-124">`--maximized`, `-M` and `--fullscreen`, `-F` are only available in [Windows Terminal Preview](https://aka.ms/terminal-preview/).</span></span>

| <span data-ttu-id="6d8a4-125">コマンド</span><span class="sxs-lookup"><span data-stu-id="6d8a4-125">Command</span></span> | <span data-ttu-id="6d8a4-126">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6d8a4-126">Parameters</span></span> | <span data-ttu-id="6d8a4-127">説明</span><span class="sxs-lookup"><span data-stu-id="6d8a4-127">Description</span></span> |
| ------- | ---------- | ----------- |
| `new-tab` | <span data-ttu-id="6d8a4-128">`--profile, -p profile-name`、`--startingDirectory, -d starting-directory`、`commandline`、`--title`</span><span class="sxs-lookup"><span data-stu-id="6d8a4-128">`--profile, -p profile-name`, `--startingDirectory, -d starting-directory`, `commandline`, `--title`</span></span> | <span data-ttu-id="6d8a4-129">新しいタブを作成します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-129">Creates a new tab.</span></span> |
| `split-pane` | <span data-ttu-id="6d8a4-130">`-H, --horizontal`、`-V, --vertical`、`--profile, -p profile-name`、`--startingDirectory, -d starting-directory`、`commandline`、`--title`</span><span class="sxs-lookup"><span data-stu-id="6d8a4-130">`-H, --horizontal`, `-V, --vertical`, `--profile, -p profile-name`, `--startingDirectory, -d starting-directory`, `commandline`, `--title`</span></span> | <span data-ttu-id="6d8a4-131">新しいペインを分割します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-131">Splits a new pane.</span></span> |
| `focus-tab` | `--target, -t tab-index` | <span data-ttu-id="6d8a4-132">特定のタブにフォーカスを設定します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-132">Focuses on a specific tab.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="6d8a4-133">`--title` は、[Windows ターミナル プレビュー](https://aka.ms/terminal-preview/)でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-133">`--title` is only available in [Windows Terminal Preview](https://aka.ms/terminal-preview/).</span></span>

## <a name="command-line-argument-examples"></a><span data-ttu-id="6d8a4-134">コマンド ライン引数の例</span><span class="sxs-lookup"><span data-stu-id="6d8a4-134">Command line argument examples</span></span>

<span data-ttu-id="6d8a4-135">コマンドは、使用しているコマンド ラインによって多少異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-135">Commands may vary slightly depending on which command line you're using.</span></span>

### <a name="open-a-new-profile-instance"></a><span data-ttu-id="6d8a4-136">新しいプロファイル インスタンスを開く</span><span class="sxs-lookup"><span data-stu-id="6d8a4-136">Open a new profile instance</span></span>

<span data-ttu-id="6d8a4-137">新しいターミナル インスタンスを開くには、次のように入力します。このコマンドでは、"Ubuntu-18.04" という名前のプロファイルが開かれます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-137">To open a new terminal instance, in this case the command will open the profile named "Ubuntu-18.04", enter:</span></span>

<!-- Start tab selectors. -->
#### <a name="command-prompt"></a>[<span data-ttu-id="6d8a4-138">コマンド プロンプト</span><span class="sxs-lookup"><span data-stu-id="6d8a4-138">Command Prompt</span></span>](#tab/windows)

```bash
wt -p "Ubuntu-18.04"
```

#### <a name="powershell"></a>[<span data-ttu-id="6d8a4-139">PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d8a4-139">PowerShell</span></span>](#tab/powershell)

```powershell
wt -p "Ubuntu-18.04"
```

#### <a name="linux"></a>[<span data-ttu-id="6d8a4-140">Linux</span><span class="sxs-lookup"><span data-stu-id="6d8a4-140">Linux</span></span>](#tab/linux)

```bash
cmd.exe /c "wt.exe" -p "Ubuntu-18.04"
```

<span data-ttu-id="6d8a4-141">実行エイリアスは、WSL ディストリビューションでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-141">Execution aliases do not work in WSL distributions.</span></span> <span data-ttu-id="6d8a4-142">WSL コマンド ラインから wt.exe を使用する場合は、`cmd.exe` を実行することにより、CMD から直接生成することができます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-142">If you want to use wt.exe from a WSL command line, you can spawn it from CMD directly by running `cmd.exe`.</span></span> <span data-ttu-id="6d8a4-143">`/c` オプションは、実行後に終了するよう CMD に指示します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-143">The `/c` option tells CMD to terminate after running.</span></span>

---
<!-- End tab selectors.  -->

 <span data-ttu-id="6d8a4-144">`-p` フラグを使用して、開く必要がある Windows ターミナル プロファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-144">The `-p` flag is used to specify the Windows Terminal profile that should be opened.</span></span> <span data-ttu-id="6d8a4-145">"Ubuntu-18.04" を、インストールされているターミナル プロファイルの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-145">Substitute "Ubuntu-18.04" with the name of any terminal profile that you have installed.</span></span> <span data-ttu-id="6d8a4-146">このようにすると、常に新しいウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-146">This will always open a new window.</span></span> <span data-ttu-id="6d8a4-147">Windows ターミナルでは、既存のインスタンスで新しいタブまたはペインを開くことはまだできません。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-147">Windows Terminal is not yet capable of opening new tabs or panes in an existing instance.</span></span>

### <a name="target-a-directory"></a><span data-ttu-id="6d8a4-148">ディレクトリをターゲットにする</span><span class="sxs-lookup"><span data-stu-id="6d8a4-148">Target a directory</span></span>

<span data-ttu-id="6d8a4-149">コンソールの開始ディレクトリとして使用するフォルダーを指定するには、次のように入力します。この場合は d:\ ディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-149">To specify the folder that should be used as the starting directory for the console, in this case the d:\ directory, enter:</span></span>

<!-- Start tab selectors. -->
#### <a name="command-prompt"></a>[<span data-ttu-id="6d8a4-150">コマンド プロンプト</span><span class="sxs-lookup"><span data-stu-id="6d8a4-150">Command Prompt</span></span>](#tab/windows)

```bash
wt -d d:\
```

#### <a name="powershell"></a>[<span data-ttu-id="6d8a4-151">PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d8a4-151">PowerShell</span></span>](#tab/powershell)

```powershell
wt -d d:\
```

#### <a name="linux"></a>[<span data-ttu-id="6d8a4-152">Linux</span><span class="sxs-lookup"><span data-stu-id="6d8a4-152">Linux</span></span>](#tab/linux)

```bash
cmd.exe /c "wt.exe" -d d:\
```

<span data-ttu-id="6d8a4-153">実行エイリアスは、WSL ディストリビューションでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-153">Execution aliases do not work in WSL distributions.</span></span> <span data-ttu-id="6d8a4-154">WSL コマンド ラインから wt.exe を使用する場合は、`cmd.exe` を実行することにより、CMD から直接生成することができます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-154">If you want to use wt.exe from a WSL command line, you can spawn it from CMD directly by running `cmd.exe`.</span></span> <span data-ttu-id="6d8a4-155">`/c` オプションは、実行後に終了するよう CMD に指示します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-155">The `/c` option tells CMD to terminate after running.</span></span>

---
<!-- End tab selectors.  -->

### <a name="multiple-tabs"></a><span data-ttu-id="6d8a4-156">複数のタブ</span><span class="sxs-lookup"><span data-stu-id="6d8a4-156">Multiple tabs</span></span>

<span data-ttu-id="6d8a4-157">複数のタブを持つ新しいターミナル インスタンスを開くには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-157">To open a new terminal instance with multiple tabs, enter:</span></span>

<!-- Start tab selectors. -->
#### <a name="command-prompt"></a>[<span data-ttu-id="6d8a4-158">コマンド プロンプト</span><span class="sxs-lookup"><span data-stu-id="6d8a4-158">Command Prompt</span></span>](#tab/windows)

```bash
wt ; ;
```

#### <a name="powershell"></a>[<span data-ttu-id="6d8a4-159">PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d8a4-159">PowerShell</span></span>](#tab/powershell)

```powershell
wt `; `;
```

<span data-ttu-id="6d8a4-160">PowerShell では、ステートメントを区切るためにセミコロン ; を使用します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-160">PowerShell uses a semicolon ; to delimit statements.</span></span> <span data-ttu-id="6d8a4-161">wt コマンドライン引数でセミコロン ; がコマンド区切り記号として解釈されるためには、バッククォートを使用してセミコロン文字をエスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-161">To interpret a semicolon ; as a command delimiter for wt command-line arguments, you need to escape semicolon characters using backticks.</span></span> <span data-ttu-id="6d8a4-162">また、PowerShell には、解析停止演算子 (--%) もあります。これにより、それより後のすべての解釈が停止され、逐語的にただ渡されます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-162">PowerShell also has the stop parsing operator (--%), which instructs it to stop interpreting anything after it and just pass it on verbatim.</span></span>

#### <a name="linux"></a>[<span data-ttu-id="6d8a4-163">Linux</span><span class="sxs-lookup"><span data-stu-id="6d8a4-163">Linux</span></span>](#tab/linux)

```bash
cmd.exe /c "wt.exe" \; \;
```

<span data-ttu-id="6d8a4-164">実行エイリアスは、WSL ディストリビューションでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-164">Execution aliases do not work in WSL distributions.</span></span> <span data-ttu-id="6d8a4-165">WSL コマンド ラインから wt.exe を使用する場合は、`cmd.exe` を実行することにより、CMD から直接生成することができます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-165">If you want to use wt.exe from a WSL command line, you can spawn it from CMD directly by running `cmd.exe`.</span></span> <span data-ttu-id="6d8a4-166">`/c` オプションは、実行後に終了するよう CMD に指示します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-166">The `/c` option tells CMD to terminate after running.</span></span>

---
<!-- End tab selectors.  -->

<span data-ttu-id="6d8a4-167">複数のタブを持つ新しいターミナル インスタンスを開くには、次のように入力します。この場合はコマンド プロンプト プロファイルと PowerShell プロファイルです。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-167">To open a new terminal instance with multiple tabs, in this case a Command Prompt profile and a PowerShell profile, enter:</span></span>

<!-- Start tab selectors. -->
#### <a name="command-prompt"></a>[<span data-ttu-id="6d8a4-168">コマンド プロンプト</span><span class="sxs-lookup"><span data-stu-id="6d8a4-168">Command Prompt</span></span>](#tab/windows)

```bash
wt -p "Command Prompt" ; new-tab -p "Windows PowerShell"
```

#### <a name="powershell"></a>[<span data-ttu-id="6d8a4-169">PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d8a4-169">PowerShell</span></span>](#tab/powershell)

```powershell
wt -p "Command Prompt" `; new-tab -p "Windows PowerShell"
```

<span data-ttu-id="6d8a4-170">PowerShell では、ステートメントを区切るためにセミコロン ; を使用します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-170">PowerShell uses a semicolon ; to delimit statements.</span></span> <span data-ttu-id="6d8a4-171">wt コマンドライン引数でセミコロン ; がコマンド区切り記号として解釈されるためには、バッククォートを使用してセミコロン文字をエスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-171">To interpret a semicolon ; as a command delimiter for wt command-line arguments, you need to escape semicolon characters using backticks.</span></span> <span data-ttu-id="6d8a4-172">また、PowerShell には、解析停止演算子 (--%) もあります。これにより、それより後のすべての解釈が停止され、逐語的にただ渡されます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-172">PowerShell also has the stop parsing operator (--%), which instructs it to stop interpreting anything after it and just pass it on verbatim.</span></span>

#### <a name="linux"></a>[<span data-ttu-id="6d8a4-173">Linux</span><span class="sxs-lookup"><span data-stu-id="6d8a4-173">Linux</span></span>](#tab/linux)

```bash
cmd.exe /c "wt.exe" -p "Command Prompt" \; new-tab -p "Windows Powershell"
```

<span data-ttu-id="6d8a4-174">実行エイリアスは、WSL ディストリビューションでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-174">Execution aliases do not work in WSL distributions.</span></span> <span data-ttu-id="6d8a4-175">WSL コマンド ラインから wt.exe を使用する場合は、`cmd.exe` を実行することにより、CMD から直接生成することができます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-175">If you want to use wt.exe from a WSL command line, you can spawn it from CMD directly by running `cmd.exe`.</span></span> <span data-ttu-id="6d8a4-176">`/c` オプションは実行後に終了するよう CMD に指示するものであり、`\;` (スラッシュ + セミコロン) はコマンド間の区切りです。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-176">The `/c` option tells CMD to terminate after running and the `\;` forward-slash + semicolon separates commands.</span></span>

---
<!-- End tab selectors.  -->

### <a name="multiple-panes"></a><span data-ttu-id="6d8a4-177">複数のペイン</span><span class="sxs-lookup"><span data-stu-id="6d8a4-177">Multiple panes</span></span>

<span data-ttu-id="6d8a4-178">コマンド プロンプト プロファイル、PowerShell プロファイル、および WSL コマンド ラインを実行する既定のプロファイルが実行されている 3 つのペインが含まれる 1 つのタブを持つ新しいターミナル インスタンスを開くには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-178">To open a new terminal instance with one tab containing three panes running a Command Prompt profile, a PowerShell profile, and your default profile running a WSL command line, enter:</span></span>

<!-- Start tab selectors. -->
#### <a name="command-prompt"></a>[<span data-ttu-id="6d8a4-179">コマンド プロンプト</span><span class="sxs-lookup"><span data-stu-id="6d8a4-179">Command Prompt</span></span>](#tab/windows)

```bash
wt -p "Command Prompt" ; split-pane -p "Windows PowerShell" ; split-pane -H wsl.exe
```

#### <a name="powershell"></a>[<span data-ttu-id="6d8a4-180">PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d8a4-180">PowerShell</span></span>](#tab/powershell)

```powershell
wt -p "Command Prompt" `; split-pane -p "Windows PowerShell" `; split-pane -H wsl.exe
```

<span data-ttu-id="6d8a4-181">PowerShell では、ステートメントを区切るためにセミコロン ; を使用します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-181">PowerShell uses a semicolon ; to delimit statements.</span></span> <span data-ttu-id="6d8a4-182">wt コマンドライン引数でセミコロン ; がコマンド区切り記号として解釈されるためには、バッククォートを使用してセミコロン文字をエスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-182">To interpret a semicolon ; as a command delimiter for wt command-line arguments, you need to escape semicolon characters using backticks.</span></span> <span data-ttu-id="6d8a4-183">また、PowerShell には、解析停止演算子 (--%) もあります。これにより、それより後のすべての解釈が停止され、逐語的にただ渡されます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-183">PowerShell also has the stop parsing operator (--%), which instructs it to stop interpreting anything after it and just pass it on verbatim.</span></span>

#### <a name="linux"></a>[<span data-ttu-id="6d8a4-184">Linux</span><span class="sxs-lookup"><span data-stu-id="6d8a4-184">Linux</span></span>](#tab/linux)

```bash
cmd.exe /c "wt.exe" -p "Command Prompt" \; split-pane -p "Windows PowerShell" \; split-pane -H wsl.exe
```

<span data-ttu-id="6d8a4-185">実行エイリアスは、WSL ディストリビューションでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-185">Execution aliases do not work in WSL distributions.</span></span> <span data-ttu-id="6d8a4-186">WSL コマンド ラインから wt.exe を使用する場合は、`cmd.exe` を実行することにより、CMD から直接生成することができます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-186">If you want to use wt.exe from a WSL command line, you can spawn it from CMD directly by running `cmd.exe`.</span></span> <span data-ttu-id="6d8a4-187">`/c` オプションは実行後に終了するよう CMD に指示するものであり、`\;` (スラッシュ + セミコロン) はコマンド間の区切りです。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-187">The `/c` option tells CMD to terminate after running and the `\;` forward-slash + semicolon separates commands.</span></span>

---
<!-- End tab selectors.  -->

<span data-ttu-id="6d8a4-188">`-H` フラグ (または `--horizontal`) は、ペインを水平方向に分割するように指定します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-188">The `-H` flag (or `--horizontal`) indicates that you would like the panes to be split horizontally.</span></span> <span data-ttu-id="6d8a4-189">`-V` フラグ (または `--vertical`) は、ペインを垂直方向に分割するように指定します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-189">The `-V` flag (or `--vertical`) indicates that you would like the panes split vertically.</span></span>

### <a name="tab-title-preview"></a><span data-ttu-id="6d8a4-190">タブ タイトル ([プレビュー](https://aka.ms/terminal-preview/))</span><span class="sxs-lookup"><span data-stu-id="6d8a4-190">Tab title ([Preview](https://aka.ms/terminal-preview/))</span></span>

<span data-ttu-id="6d8a4-191">カスタム タブ タイトルを使用して新しいターミナル インスタンスを開くには、`--title` 引数を使用します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-191">To open a new terminal instance with custom tab titles, use the `--title` argument.</span></span> <span data-ttu-id="6d8a4-192">2 つのタブを開くときに各タブのタイトルを設定するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-192">To set the title of each tab when opening two tabs, enter:</span></span>

<!-- Start tab selectors. -->
#### <a name="command-prompt"></a>[<span data-ttu-id="6d8a4-193">コマンド プロンプト</span><span class="sxs-lookup"><span data-stu-id="6d8a4-193">Command Prompt</span></span>](#tab/windows)

```bash
wt --title tabname1 ; new-tab -p "Ubuntu-18.04" --title tabname2
```

#### <a name="powershell"></a>[<span data-ttu-id="6d8a4-194">PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d8a4-194">PowerShell</span></span>](#tab/powershell)

```powershell
wt --title tabname1 `; new-tab -p "Ubuntu-18.04" --title tabname2
```

#### <a name="linux"></a>[<span data-ttu-id="6d8a4-195">Linux</span><span class="sxs-lookup"><span data-stu-id="6d8a4-195">Linux</span></span>](#tab/linux)

```bash
cmd.exe /c "wt.exe" --title tabname1 \; new-tab -p "Ubuntu-18.04" --title tabname2
```

<span data-ttu-id="6d8a4-196">実行エイリアスは、WSL ディストリビューションでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-196">Execution aliases do not work in WSL distributions.</span></span> <span data-ttu-id="6d8a4-197">WSL コマンド ラインから wt.exe を使用する場合は、`cmd.exe` を実行することにより、CMD から直接生成することができます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-197">If you want to use wt.exe from a WSL command line, you can spawn it from CMD directly by running `cmd.exe`.</span></span> <span data-ttu-id="6d8a4-198">`/c` オプションは実行後に終了するよう CMD に指示するものであり、`\;` (スラッシュ + セミコロン) はコマンド間の区切りです。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-198">The `/c` option tells CMD to terminate after running and the `\;` forward-slash + semicolon separates commands.</span></span>

---
<!-- End tab selectors.  -->

> [!IMPORTANT]
> <span data-ttu-id="6d8a4-199">この機能は、[Windows ターミナル プレビュー](https://aka.ms/terminal-preview/)でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-199">This feature is only available in [Windows Terminal Preview](https://aka.ms/terminal-preview/).</span></span>

### <a name="tab-focus"></a><span data-ttu-id="6d8a4-200">タブ フォーカス</span><span class="sxs-lookup"><span data-stu-id="6d8a4-200">Tab focus</span></span>

<span data-ttu-id="6d8a4-201">特定のタブにフォーカスを設定して新しいターミナル インスタンスを開くには、`-t` フラグ (または `--target`) とタブ インデックス番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-201">To open a new terminal instance with a specific tab in focus, use the `-t` flag (or `--target`), along with the tab-index number.</span></span> <span data-ttu-id="6d8a4-202">1 番目のタブで既定のプロファイルを開き、2 番目のタブ (`-t 1`) で "Ubuntu-18.04" プロファイルを開いてフォーカスを設定するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-202">To open your default profile in the first tab and the "Ubuntu-18.04" profile focused in the second tab (`-t 1`), enter:</span></span>

<!-- Start tab selectors. -->
#### <a name="command-prompt"></a>[<span data-ttu-id="6d8a4-203">コマンド プロンプト</span><span class="sxs-lookup"><span data-stu-id="6d8a4-203">Command Prompt</span></span>](#tab/windows)

```bash
wt ; new-tab -p "Ubuntu-18.04" ; focus-tab -t 1
```

#### <a name="powershell"></a>[<span data-ttu-id="6d8a4-204">PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d8a4-204">PowerShell</span></span>](#tab/powershell)

```powershell
wt `; new-tab -p "Ubuntu-18.04" `; focus-tab -t 1
```

#### <a name="linux"></a>[<span data-ttu-id="6d8a4-205">Linux</span><span class="sxs-lookup"><span data-stu-id="6d8a4-205">Linux</span></span>](#tab/linux)

```bash
cmd.exe /c "wt.exe" \; new-tab -p "Ubuntu-18.04" \; focus-tab -t 1
```

<span data-ttu-id="6d8a4-206">実行エイリアスは、WSL ディストリビューションでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-206">Execution aliases do not work in WSL distributions.</span></span> <span data-ttu-id="6d8a4-207">WSL コマンド ラインから wt.exe を使用する場合は、`cmd.exe` を実行することにより、CMD から直接生成することができます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-207">If you want to use wt.exe from a WSL command line, you can spawn it from CMD directly by running `cmd.exe`.</span></span> <span data-ttu-id="6d8a4-208">`/c` オプションは実行後に終了するよう CMD に指示するものであり、`\;` (スラッシュ + セミコロン) はコマンド間の区切りです。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-208">The `/c` option tells CMD to terminate after running and the `\;` forward-slash + semicolon separates commands.</span></span>

---
<!-- End tab selectors.  -->

## <a name="examples-of-multiple-commands-from-powershell"></a><span data-ttu-id="6d8a4-209">PowerShell からの複数のコマンドの例</span><span class="sxs-lookup"><span data-stu-id="6d8a4-209">Examples of multiple commands from PowerShell</span></span>

<span data-ttu-id="6d8a4-210">Windows ターミナルでは、`wt` コマンド ラインのコマンドを区切るための区切り記号として、セミコロン文字 `;` を使用します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-210">Windows Terminal uses the semicolon character `;` as a delimiter for separating commands in the `wt` command line.</span></span> <span data-ttu-id="6d8a4-211">残念ながら、PowerShell では、コマンドの区切り記号としても `;` を使用します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-211">Unfortunately, PowerShell also uses `;` as a command separator.</span></span> <span data-ttu-id="6d8a4-212">これを回避するには、次の方法を使用して、PowerShell から複数の `wt` コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-212">To work around this, you can use the following tricks to run multiple `wt` commands from PowerShell.</span></span> <span data-ttu-id="6d8a4-213">以下のすべての例では、3 つのペインから成る新しいターミナル ウィンドウが作成されます。コマンド プロンプトを実行するペイン、PowerShell のペイン、WSL を実行するペインです。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-213">In all the following examples, a new terminal window is created with three panes - one running Command Prompt, one with PowerShell, and the last one running WSL.</span></span>

<span data-ttu-id="6d8a4-214">次の例では、`Start-Process` コマンドを使用して `wt` を実行します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-214">The following examples use the `Start-Process` command to run `wt`.</span></span> <span data-ttu-id="6d8a4-215">ターミナルで `Start-Process` を使用する理由について詳しくは、後の「[start を使用する](#using-start)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-215">For more information on why the terminal uses `Start-Process`, see [Using start](#using-start) below.</span></span>

### <a name="single-quoted-parameters"></a><span data-ttu-id="6d8a4-216">単一引用符で囲まれたパラメーター</span><span class="sxs-lookup"><span data-stu-id="6d8a4-216">Single quoted parameters</span></span>

<span data-ttu-id="6d8a4-217">この例では、`wt` パラメーターは単一引用符 (`'`) でラップされています。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-217">In this example, the `wt` parameters are wrapped in single quotes (`'`).</span></span> <span data-ttu-id="6d8a4-218">この構文は、何も計算されていない場合に役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-218">This syntax is useful if nothing is being calculated.</span></span>

```powershell
start wt 'new-tab "cmd" ; split-pane -p "Windows PowerShell" ; split-pane -H wsl.exe'
```

### <a name="escaped-quotes"></a><span data-ttu-id="6d8a4-219">エスケープされた引用符</span><span class="sxs-lookup"><span data-stu-id="6d8a4-219">Escaped quotes</span></span>

<span data-ttu-id="6d8a4-220">変数に格納されている値を `wt` のコマンド ラインに渡す場合は、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-220">When passing a value contained in a variable to the `wt` command line, use the following syntax:</span></span>

```powershell
$ThirdPane = "wsl.exe"
start wt "new-tab cmd ; split-pane -p `"Windows PowerShell`" ; split-pane -H $ThirdPane"
```

<span data-ttu-id="6d8a4-221">`split-pane` パラメーターに対する `-p` パラメーターの "Windows PowerShell" を囲む二重引用符 (`"`) をエスケープするために、`` ` `` が使用されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-221">Note the usage of  `` ` `` to escape the double-quotes (`"`) around "Windows PowerShell" in the `-p` parameter to the `split-pane` parameter.</span></span>

### <a name="using-start"></a><span data-ttu-id="6d8a4-222">`start` を使用する</span><span class="sxs-lookup"><span data-stu-id="6d8a4-222">Using `start`</span></span>

<span data-ttu-id="6d8a4-223">上記の例ではすべて、ターミナルを起動するために `start` が明示的に使用されています。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-223">All the above examples explicitly used `start` to launch the terminal.</span></span>

<span data-ttu-id="6d8a4-224">次の例では、`start` を使用しないでコマンド ラインを実行しています。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-224">The following examples do not use `start` to run the command line.</span></span> <span data-ttu-id="6d8a4-225">代わりに、コマンド ラインをエスケープする方法が他に 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-225">Instead, there are two other methods of escaping the command line:</span></span>

* <span data-ttu-id="6d8a4-226">`PowerShell` によってセミコロンが無視され、`wt` にそのまま渡されるように、セミコロンだけをエスケープします。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-226">Only escaping the semicolons so that `PowerShell` will ignore them and pass them straight to `wt`.</span></span>
* <span data-ttu-id="6d8a4-227">コマンド ラインの残りの部分が PowerShell によってアプリケーションへの引数として扱われるように、`--%` を使用します。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-227">Using `--%`, so PowerShell will treat the rest of the command line as arguments to the application.</span></span>

```powershell
wt new-tab "cmd" `; split-pane -p "Windows PowerShell" `; split-pane -H wsl.exe
```

```powershell
wt --% new-tab cmd ; split-pane -p "Windows PowerShell" ; split-pane -H wsl.exe
```

<span data-ttu-id="6d8a4-228">どちらの例でも、新しく作成される Windows ターミナル ウィンドウでは、指定したすべてのコマンドライン引数が正しく解析されてウィンドウが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-228">In both of these examples, the newly created Windows Terminal window will create the window by correctly parsing all the provided command-line arguments.</span></span>

<span data-ttu-id="6d8a4-229">ただし、新しく作成されたターミナル ウィンドウが閉じられるまで待ってから、PowerShell に制御が返されるため、現在は、これらの方法は推奨 "_されません_"。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-229">However, these methods are _not_ recommended currently, as PowerShell will wait for the newly-created terminal window to be closed before returning control to PowerShell.</span></span> <span data-ttu-id="6d8a4-230">既定では、PowerShell は常に、Windows ストア アプリケーション (Windows ターミナルなど) が終了するまで待ってからプロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-230">By default, PowerShell will always wait for Windows Store applications (like Windows Terminal) to close before returning to the prompt.</span></span> <span data-ttu-id="6d8a4-231">これは、すぐにプロンプトに戻るコマンド プロンプトの動作とは異なることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6d8a4-231">Note that this is different than the behavior of Command Prompt, which will return to the prompt immediately.</span></span>
