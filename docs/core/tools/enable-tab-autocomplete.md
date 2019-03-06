---
title: タブ補完を有効にする
description: この記事では、PowerShell、Bash、および zsh 向けの .NET Core CLI のタブ補完を有効にする方法を説明します。
author: thraka
ms.author: adegeo
ms.date: 12/17/2018
ms.openlocfilehash: 16574e02aa9f9167602401eef2ad7a73e07ad107
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "57203338"
---
# <a name="how-to-enable-tab-completion-for-net-core-cli"></a><span data-ttu-id="e64e8-103">.NET Core CLI のタブ補完を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="e64e8-103">How to enable TAB completion for .NET Core CLI</span></span>

<span data-ttu-id="e64e8-104">.NET Core 2.0 SDK 以降では、.NET Core CLI はタブ補完をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e64e8-104">Starting with .NET Core 2.0 SDK, the .NET Core CLI supports tab completion.</span></span> <span data-ttu-id="e64e8-105">この記事では、3 つのシェル、PowerShell、Bash、および zsh のタブ補完を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e64e8-105">This article describes how to configure tab completion for three shells, PowerShell, Bash, and zsh.</span></span> <span data-ttu-id="e64e8-106">その他のシェルでは、オート コンプリートのサポートがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e64e8-106">Other shells may have support for auto completion.</span></span> <span data-ttu-id="e64e8-107">オート コンプリートの構成方法については、それぞれのドキュメントを参照してください。手順は、この記事で説明されている手順と同様です。</span><span class="sxs-lookup"><span data-stu-id="e64e8-107">Refer to their documentation on how to configure auto completion, the steps should be similar to the steps described in this article.</span></span>

[!INCLUDE [topic-appliesto-net-core-2plus](~/includes/topic-appliesto-net-core-2plus.md)]

<span data-ttu-id="e64e8-108">セットアップが完了したら、シェルに `dotnet` コマンドを入力した後、TAB キーを押すと、.NET Core CLI のタブ補完がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="e64e8-108">Once setup, tab completion for the .NET Core CLI is triggered by typing a `dotnet` command in the shell, and then pressing the TAB key.</span></span> <span data-ttu-id="e64e8-109">現在のコマンド ラインが `dotnet complete` コマンドに送信され、結果がシェルによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="e64e8-109">The current command line is sent to the `dotnet complete` command, and the results are processed by your shell.</span></span> <span data-ttu-id="e64e8-110">何かを `dotnet complete` コマンドに直接送信することで、タブ補完を有効にせずに結果をテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="e64e8-110">You can test the results without enabling tab completion by sending something directly to the `dotnet complete` command.</span></span> <span data-ttu-id="e64e8-111">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e64e8-111">For example:</span></span>

```
> dotnet complete "dotnet a"
add
clean
--diagnostics
migrate
pack
```

<span data-ttu-id="e64e8-112">そのコマンドが機能しない場合は、.NET Core 2.0 SDK 以降がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e64e8-112">If that command doesn't work, make sure that .NET Core 2.0 SDK or above is installed.</span></span> <span data-ttu-id="e64e8-113">インストールされているにもかかわらず、そのコマンドが機能しない場合は、`dotnet` コマンドが .NET Core 2.0 SDK 以降のバージョンに解決されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e64e8-113">If it's installed, but that command still doesn't work, make sure that the `dotnet` command resolves to a version of .NET Core 2.0 SDK and above.</span></span> <span data-ttu-id="e64e8-114">`dotnet --version` コマンドを使用して、現在のパスの解決先となっている `dotnet` のバージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="e64e8-114">Use the `dotnet --version` command to see what version of `dotnet` your current path is resolving to.</span></span> <span data-ttu-id="e64e8-115">詳細については、「[使用する .NET Core のバージョンを選択する](../versions/selection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e64e8-115">For more information, see [Select the .NET Core version to use](../versions/selection.md).</span></span>

### <a name="examples"></a><span data-ttu-id="e64e8-116">使用例</span><span class="sxs-lookup"><span data-stu-id="e64e8-116">Examples</span></span>

<span data-ttu-id="e64e8-117">タブ補完で提供されることの例をいくつか次に示します。</span><span class="sxs-lookup"><span data-stu-id="e64e8-117">Here are some examples of what tab completion provides:</span></span>

<span data-ttu-id="e64e8-118">入力</span><span class="sxs-lookup"><span data-stu-id="e64e8-118">Input</span></span>                                | <span data-ttu-id="e64e8-119">結果</span><span class="sxs-lookup"><span data-stu-id="e64e8-119">becomes</span></span>                                                                     | <span data-ttu-id="e64e8-120">理由</span><span class="sxs-lookup"><span data-stu-id="e64e8-120">because</span></span>
:------------------------------------|:----------------------------------------------------------------------------|:--------------------------------
`dotnet a⇥`                          | `dotnet add`                                                                 | <span data-ttu-id="e64e8-121">アルファベット順では、`add` が最初のサブコマンドのため。</span><span class="sxs-lookup"><span data-stu-id="e64e8-121">`add` is the first subcommand, alphabetically.</span></span>
`dotnet add p⇥`                      | `dotnet add --help`                                                          | <span data-ttu-id="e64e8-122">タブ補完が部分文字列と一致しており、アルファベット順では `--help` が先になるため。</span><span class="sxs-lookup"><span data-stu-id="e64e8-122">Tab completion matches substrings and `--help` comes first alphabetically.</span></span>
`dotnet add p⇥⇥`                    | `dotnet add package`                                                          | <span data-ttu-id="e64e8-123">Tab キーを 2 回押すと、次の修正候補が表示されるため。</span><span class="sxs-lookup"><span data-stu-id="e64e8-123">Pressing tab a second time brings up the next suggestion.</span></span>      
`dotnet add package Microsoft⇥`      | `dotnet add package Microsoft.ApplicationInsights.Web`                      | <span data-ttu-id="e64e8-124">結果はアルファベット順に返されるため。</span><span class="sxs-lookup"><span data-stu-id="e64e8-124">Results are returned alphabetically.</span></span>
`dotnet remove reference ⇥`          | `dotnet remove reference ..\..\src\OmniSharp.DotNet\OmniSharp.DotNet.csproj` | <span data-ttu-id="e64e8-125">タブ補完がプロジェクト ファイルに対応しているため。</span><span class="sxs-lookup"><span data-stu-id="e64e8-125">Tab completion is project file aware.</span></span>

## <a name="powershell"></a><span data-ttu-id="e64e8-126">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e64e8-126">PowerShell</span></span>

<span data-ttu-id="e64e8-127">.NET Core CLI の **PowerShell** にタブ補完を追加するには、変数 `$PROFILE` に格納されているプロファイルを作成または編集します。</span><span class="sxs-lookup"><span data-stu-id="e64e8-127">To add tab completion to **PowerShell** for the .NET Core CLI, create or edit the profile stored in the variable `$PROFILE`.</span></span> <span data-ttu-id="e64e8-128">詳細については、[プロファイルの作成方法](/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6#how-to-create-a-profile)と[プロファイルと実行ポリシー](/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6#profiles-and-execution-policy)のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e64e8-128">For more information, see [How to create your profile](/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6#how-to-create-a-profile) and [Profiles and execution policy](/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6#profiles-and-execution-policy).</span></span> 

<span data-ttu-id="e64e8-129">自分のプロファイルに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e64e8-129">Add the following code to your profile:</span></span>

```powershell
# PowerShell parameter completion shim for the dotnet CLI 
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock {
     param($commandName, $wordToComplete, $cursorPosition)
         dotnet complete --position $cursorPosition "$wordToComplete" | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
         }
 }
```

## <a name="bash"></a><span data-ttu-id="e64e8-130">Bash</span><span class="sxs-lookup"><span data-stu-id="e64e8-130">Bash</span></span>

<span data-ttu-id="e64e8-131">.NET Core CLI の **bash** シェルにタブ補完を追加するには、次のコードを `.bashrc` ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="e64e8-131">To add tab completion to your **bash** shell for the .NET Core CLI, add the following code to your `.bashrc` file:</span></span>

```bash
# bash parameter completion for the dotnet CLI

_dotnet_bash_complete()
{
  local word=${COMP_WORDS[COMP_CWORD]}

  local completions
  completions="$(dotnet complete --position "${COMP_POINT}" "${COMP_LINE}")"

  COMPREPLY=( $(compgen -W "$completions" -- "$word") )
}

complete -f -F _dotnet_bash_complete dotnet
```

## <a name="zsh"></a><span data-ttu-id="e64e8-132">Zsh</span><span class="sxs-lookup"><span data-stu-id="e64e8-132">Zsh</span></span>

<span data-ttu-id="e64e8-133">.NET Core CLI の **zsh** シェルにタブ補完を追加するには、次のコードを `.zshrc` ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="e64e8-133">To add tab completion to your **zsh** shell for the .NET Core CLI, add the following code to your `.zshrc` file:</span></span>

```zsh
# zsh parameter completion for the dotnet CLI

_dotnet_zsh_complete() 
{
  local completions=("$(dotnet complete "$words")")

  reply=( "${(ps:\n:)completions}" )
}

compctl -K _dotnet_zsh_complete dotnet
```
