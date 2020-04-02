---
title: dotnet nuget list source コマンド
description: dotnet nuget list source コマンドを使うと、NuGet 構成ファイルの既存のソースをすべて一覧表示できます。
ms.date: 03/20/2020
ms.openlocfilehash: 4d7bc3dbd3ab5eb14c1ebf592044b685d28355cd
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148496"
---
# <a name="dotnet-nuget-list-source"></a><span data-ttu-id="9f286-103">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="9f286-103">dotnet nuget list source</span></span>

<span data-ttu-id="9f286-104">**この記事の対象:** ✔️ .NET Core 3.1.200 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="9f286-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="9f286-105">名前</span><span class="sxs-lookup"><span data-stu-id="9f286-105">Name</span></span>

<span data-ttu-id="9f286-106">`dotnet nuget list source` - 構成されている NuGet ソースをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="9f286-106">`dotnet nuget list source` - Lists all configured NuGet sources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9f286-107">構文</span><span class="sxs-lookup"><span data-stu-id="9f286-107">Synopsis</span></span>

```dotnetcli
dotnet nuget list source [--format] [--configfile]
dotnet nuget list source [-h|--help]
```

## <a name="description"></a><span data-ttu-id="9f286-108">説明</span><span class="sxs-lookup"><span data-stu-id="9f286-108">Description</span></span>

<span data-ttu-id="9f286-109">`dotnet nuget list source` コマンドを使うと、NuGet 構成ファイルの既存のソースをすべて一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="9f286-109">The `dotnet nuget list source` command lists all existing sources from your NuGet configuration files.</span></span>

## <a name="options"></a><span data-ttu-id="9f286-110">オプション</span><span class="sxs-lookup"><span data-stu-id="9f286-110">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="9f286-111">NuGet 構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="9f286-111">The NuGet configuration file.</span></span> <span data-ttu-id="9f286-112">指定した場合、このファイルの設定のみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="9f286-112">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="9f286-113">指定しない場合、現在のディレクトリからの構成ファイルの階層が使用されます。</span><span class="sxs-lookup"><span data-stu-id="9f286-113">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="9f286-114">詳細については、「[一般的な NuGet 構成](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9f286-114">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`--format`**

  <span data-ttu-id="9f286-115">list コマンドの出力の形式: `Detailed` (既定) と `Short`。</span><span class="sxs-lookup"><span data-stu-id="9f286-115">The format of the list command output: `Detailed` (the default) and `Short`.</span></span>

## <a name="examples"></a><span data-ttu-id="9f286-116">使用例</span><span class="sxs-lookup"><span data-stu-id="9f286-116">Examples</span></span>

- <span data-ttu-id="9f286-117">現在のディレクトリから構成されているソースを一覧表示します:</span><span class="sxs-lookup"><span data-stu-id="9f286-117">List configured sources from the current directory:</span></span>

  ```dotnetcli
  dotnet nuget list source
  ```

## <a name="see-also"></a><span data-ttu-id="9f286-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f286-118">See also</span></span>

- [<span data-ttu-id="9f286-119">NuGet.config ファイルのパッケージ ソース セクション</span><span class="sxs-lookup"><span data-stu-id="9f286-119">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="9f286-120">sources コマンド (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="9f286-120">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
