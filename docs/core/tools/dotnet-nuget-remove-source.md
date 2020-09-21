---
title: dotnet nuget remove source コマンド
description: dotnet nuget remove source コマンドを使うと、NuGet 構成ファイルから既存のソースを削除できます。
ms.date: 03/20/2020
ms.openlocfilehash: b5575c31c0008d6e3e5a2e52906a076614217dd0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537893"
---
# <a name="dotnet-nuget-remove-source"></a><span data-ttu-id="c94ab-103">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="c94ab-103">dotnet nuget remove source</span></span>

<span data-ttu-id="c94ab-104">**この記事の対象:** ✔️ .NET Core 3.1.200 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="c94ab-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c94ab-105">名前</span><span class="sxs-lookup"><span data-stu-id="c94ab-105">Name</span></span>

<span data-ttu-id="c94ab-106">`dotnet nuget remove source` - NuGet ソースを削除します。</span><span class="sxs-lookup"><span data-stu-id="c94ab-106">`dotnet nuget remove source` - Remove a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c94ab-107">構文</span><span class="sxs-lookup"><span data-stu-id="c94ab-107">Synopsis</span></span>

```dotnetcli
dotnet nuget remove source <NAME> [--configfile <FILE>]

dotnet nuget remove source -h|--help
```

## <a name="description"></a><span data-ttu-id="c94ab-108">説明</span><span class="sxs-lookup"><span data-stu-id="c94ab-108">Description</span></span>

<span data-ttu-id="c94ab-109">`dotnet nuget remove source` コマンドを使うと、NuGet 構成ファイルから既存のソースを削除できます。</span><span class="sxs-lookup"><span data-stu-id="c94ab-109">The `dotnet nuget remove source` command removes an existing source from your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="c94ab-110">引数</span><span class="sxs-lookup"><span data-stu-id="c94ab-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="c94ab-111">ソースの名前。</span><span class="sxs-lookup"><span data-stu-id="c94ab-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="c94ab-112">オプション</span><span class="sxs-lookup"><span data-stu-id="c94ab-112">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="c94ab-113">NuGet 構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="c94ab-113">The NuGet configuration file.</span></span> <span data-ttu-id="c94ab-114">指定した場合、このファイルの設定のみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c94ab-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="c94ab-115">指定しない場合、現在のディレクトリからの構成ファイルの階層が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c94ab-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="c94ab-116">詳細については、「[一般的な NuGet 構成](/nuget/consume-packages/configuring-nuget-behavior)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c94ab-116">For more information, see [Common NuGet Configurations](/nuget/consume-packages/configuring-nuget-behavior).</span></span>

## <a name="examples"></a><span data-ttu-id="c94ab-117">使用例</span><span class="sxs-lookup"><span data-stu-id="c94ab-117">Examples</span></span>

- <span data-ttu-id="c94ab-118">`mySource` という名前のソースを削除します。</span><span class="sxs-lookup"><span data-stu-id="c94ab-118">Remove a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget remove source mySource
  ```

## <a name="see-also"></a><span data-ttu-id="c94ab-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="c94ab-119">See also</span></span>

- [<span data-ttu-id="c94ab-120">NuGet.config ファイルのパッケージ ソース セクション</span><span class="sxs-lookup"><span data-stu-id="c94ab-120">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="c94ab-121">sources コマンド (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="c94ab-121">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
