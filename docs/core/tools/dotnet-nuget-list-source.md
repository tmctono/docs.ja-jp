---
title: dotnet nuget list source コマンド
description: dotnet nuget list source コマンドを使うと、NuGet 構成ファイルの既存のソースをすべて一覧表示できます。
ms.date: 03/20/2020
ms.openlocfilehash: 071061e32aa1bf888e197ec6bf97f4e4f6859f0b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537897"
---
# <a name="dotnet-nuget-list-source"></a><span data-ttu-id="3f9d6-103">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="3f9d6-103">dotnet nuget list source</span></span>

<span data-ttu-id="3f9d6-104">**この記事の対象:** ✔️ .NET Core 3.1.200 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="3f9d6-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="3f9d6-105">名前</span><span class="sxs-lookup"><span data-stu-id="3f9d6-105">Name</span></span>

<span data-ttu-id="3f9d6-106">`dotnet nuget list source` - 構成されている NuGet ソースをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="3f9d6-106">`dotnet nuget list source` - Lists all configured NuGet sources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3f9d6-107">構文</span><span class="sxs-lookup"><span data-stu-id="3f9d6-107">Synopsis</span></span>

```dotnetcli
dotnet nuget list source [--format [Detailed|Short]] [--configfile <FILE>]

dotnet nuget list source -h|--help
```

## <a name="description"></a><span data-ttu-id="3f9d6-108">説明</span><span class="sxs-lookup"><span data-stu-id="3f9d6-108">Description</span></span>

<span data-ttu-id="3f9d6-109">`dotnet nuget list source` コマンドを使うと、NuGet 構成ファイルの既存のソースをすべて一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="3f9d6-109">The `dotnet nuget list source` command lists all existing sources from your NuGet configuration files.</span></span>

## <a name="options"></a><span data-ttu-id="3f9d6-110">オプション</span><span class="sxs-lookup"><span data-stu-id="3f9d6-110">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="3f9d6-111">NuGet 構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="3f9d6-111">The NuGet configuration file.</span></span> <span data-ttu-id="3f9d6-112">指定した場合、このファイルの設定のみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3f9d6-112">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="3f9d6-113">指定しない場合、現在のディレクトリからの構成ファイルの階層が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3f9d6-113">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="3f9d6-114">詳細については、「[一般的な NuGet 構成](/nuget/consume-packages/configuring-nuget-behavior)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3f9d6-114">For more information, see [Common NuGet Configurations](/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`--format [Detailed|Short]`**

  <span data-ttu-id="3f9d6-115">list コマンドの出力の形式: `Detailed` (既定) と `Short`。</span><span class="sxs-lookup"><span data-stu-id="3f9d6-115">The format of the list command output: `Detailed` (the default) and `Short`.</span></span>

## <a name="examples"></a><span data-ttu-id="3f9d6-116">使用例</span><span class="sxs-lookup"><span data-stu-id="3f9d6-116">Examples</span></span>

- <span data-ttu-id="3f9d6-117">現在のディレクトリから構成されているソースを一覧表示します:</span><span class="sxs-lookup"><span data-stu-id="3f9d6-117">List configured sources from the current directory:</span></span>

  ```dotnetcli
  dotnet nuget list source
  ```

## <a name="see-also"></a><span data-ttu-id="3f9d6-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f9d6-118">See also</span></span>

- [<span data-ttu-id="3f9d6-119">NuGet.config ファイルのパッケージ ソース セクション</span><span class="sxs-lookup"><span data-stu-id="3f9d6-119">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="3f9d6-120">sources コマンド (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="3f9d6-120">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
